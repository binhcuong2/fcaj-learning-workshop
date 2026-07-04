---
title : "Cơ sở dữ liệu & Lưu trữ (DynamoDB & S3)"
date: 2026-07-03
weight : 3
chapter : false
pre : " <b> 5.4.3. </b> "
---

Thực hiện lưu trữ thông tin có cấu trúc của các tin tuyển dụng yêu thích (wishlist) trên DynamoDB và lưu trữ file CV định dạng PDF của người dùng trên Amazon S3 Bucket với các cơ chế kiểm tra bảo mật nghiêm ngặt.

---

## 1. Cấu hình AWS SAM Template (`template.yaml`)

```yaml
  SavedJobsTable:
    Type: AWS::DynamoDB::Table
    Properties:
      TableName: jobs-matching-saved-jobs-dev
      BillingMode: PAY_PER_REQUEST
      AttributeDefinitions:
        - AttributeName: userId
          AttributeType: S
        - AttributeName: jobId
          AttributeType: S
      KeySchema:
        - AttributeName: userId
          KeyType: HASH
        - AttributeName: jobId
          KeyType: RANGE

  CvBucket:
    Type: AWS::S3::Bucket
    Properties:
      BucketName: !Sub "jobs-matching-cvs-dev-${AWS::AccountId}"
      PublicAccessBlockConfiguration:
        BlockPublicAcls: false
        BlockPublicPolicy: false
        IgnorePublicAcls: false
        RestrictPublicBuckets: false
      CorsConfiguration:
        CorsRules:
          - AllowedHeaders:
              - "*"
            AllowedMethods:
              - GET
            AllowedOrigins:
              - "*"
            MaxAge: 3000

  CvBucketPolicy:
    Type: AWS::S3::BucketPolicy
    Properties:
      Bucket: !Ref CvBucket
      PolicyDocument:
        Version: "2012-10-17"
        Statement:
          - Effect: Allow
            Principal: "*"
            Action: "s3:GetObject"
            Resource: !Sub "arn:aws:s3:::${CvBucket}/*"
```

* **DynamoDB Billing Mode:** Sử dụng chế độ thanh toán theo nhu cầu (`PAY_PER_REQUEST`) để tối ưu hóa chi phí.
* **S3 CORS:**
  * Cho phép nguồn gốc (`AllowedOrigins`): Bất kỳ nguồn nào (`*`) hoặc cụ thể domain frontend.
  * Cho phép phương thức (`AllowedMethods`): `GET` (để hiển thị trực tiếp PDF trên trình duyệt thông qua Signed URL hoặc Public Read URL).

![Cấu hình S3 CORS cho CV Bucket](/images/5-Workshop/5.4-User-Interaction/dynamodb-saved-jobs_cors.png)
* **S3 Bucket Policy:** Chỉ cho phép đọc public đối với tài nguyên hoặc truy xuất bảo mật qua API Gateway.

---

## 2. Triển khai (Deployment)
Các thành phần Table và Bucket được tự động tạo và cập nhật chính xác khi chạy deployment stack SAM:
```bash
sam build
sam deploy
```

Sau khi triển khai thành công, bạn có thể kiểm tra cấu hình DynamoDB và S3 trên AWS Console.

---

## 3. Cơ sở dữ liệu (DynamoDB)

### A. Cấu trúc bảng: `SavedJobsTable` (Favorite Jobs)
* **Partition Key (PK):** `userId` (Kiểu String `S`, trích xuất từ Cognito Claim `sub`).
* **Sort Key (SK):** `jobId` (Kiểu String `S`, ID của tin tuyển dụng).

![Bảng DynamoDB Saved Jobs](/images/5-Workshop/5.4-User-Interaction/dynamodb-saved-jobs.png)

### B. Khái quát các API Endpoint
* **Thêm Yêu thích (`POST /saved-jobs/{jobId}`):**
  Endpoint này yêu cầu Header `Authorization: Bearer <Token>` và tham số đường dẫn `jobId`. Hệ thống sẽ trích xuất `userId` từ mã token và thực hiện thao tác `PutItem` trong DynamoDB để lưu trữ bản ghi có chứa thông tin `userId`, `jobId`, và mốc thời gian lưu `savedAt`. Khi thành công sẽ trả về HTTP 201 Created.
  
* **Xóa Yêu thích (`DELETE /saved-jobs/{jobId}`):**
  Yêu cầu quyền xác thực và tham số `jobId` trên path. Sử dụng các khóa `userId` và `jobId`, backend sẽ thực hiện thao tác xóa dữ liệu `DeleteItem` tương ứng trong bảng. Trả về HTTP 200 OK.
  
* **Lấy Danh sách Yêu thích (`GET /saved-jobs`):**
  Lấy toàn bộ tin tuyển dụng đã lưu của người dùng hiện tại. Backend lấy `userId` từ token và chạy lệnh truy vấn `Query` với khóa phân vùng PK = `userId`. Trả về HTTP 200 OK cùng danh sách các phần tử.

Bạn có thể kiểm tra danh sách bản ghi lưu tin tuyển dụng của người dùng trong tab Items trên DynamoDB Console:
![Danh sách bản ghi Saved Jobs](/images/5-Workshop/5.4-User-Interaction/dynamodb-saved-jobs_2.png)

---

## 4. Lưu trữ (S3)

### A. Cấu trúc lưu trữ: `CvBucket` (Lưu trữ CV PDF)
* **Quy chuẩn lưu trữ:** Tên tệp lưu dưới dạng khóa: `${userId}/cv_${timestamp}.pdf`.

### B. Quy trình kiểm tra nghiệp vụ và bảo mật tải lên
Hệ thống thực hiện kiểm tra an toàn tệp tải lên theo các bước tuần tự như sau trước khi tải lên Amazon S3:

1. **Kiểm tra Magic Bytes:** Đọc một vài byte đầu tiên của tệp để kiểm tra xem có khớp với signature `%PDF` (`25 50 44 46` dạng hex) hay không. Nếu không trùng khớp, hệ thống sẽ trả về lỗi HTTP 400 Bad Request để ngăn các tệp độc hại ngụy trang.
2. **Kiểm tra kích thước tệp:** Xác thực dung lượng tệp tải lên để đảm bảo nhỏ hơn hoặc bằng 5MB. Nếu dung lượng lớn hơn 5MB, hệ thống sẽ chặn và trả về lỗi 400 Bad Request.
3. **Giới hạn số lượng tệp:** Thực hiện quét số lượng tệp đang tồn tại của người dùng dưới tiền tố `userId/`. Nếu người dùng đã lưu từ 3 CV trở lên, yêu cầu tải lên tiếp theo sẽ bị từ chối với lỗi 400 Bad Request.
4. **Kiểm tra trùng lặp (SHA-256 Hash):** Tính toán mã băm SHA-256 của file tải lên và đối chiếu với giá trị metadata `x-amz-meta-content-hash` của các tệp cũ đã có. Nếu phát hiện tệp trùng lặp mã băm, yêu cầu tải lên sẽ bị chặn với lỗi 400 Bad Request.
5. **Đưa lên S3:** Nếu toàn bộ các kiểm tra trên đều hợp lệ, tệp sẽ được tải lên S3 kèm theo các thông tin metadata gốc (tên file gốc và mã hash nội dung).

### C. Ví dụ luồng dữ liệu Upload
* **Input (Client gửi lên):**
  * Header `Authorization`: `Bearer <JWT_ID_TOKEN>`
  * Header `Content-Type`: `application/pdf`
  * Header `x-original-filename`: `NguyenVanA_Resume.pdf` (được encode URL)
  * Request Body: Định dạng binary buffer của tệp PDF.
  * **Output (S3 Upload Lambda trả về):**
    ```json
    {
      "message": "CV uploaded successfully",
      "data": {
        "key": "d74b8c9d-d81a-4b92-91ef-f6d3a82741d4/cv_1782873600000.pdf",
        "url": "https://jobs-matching-cvs-dev-123456789012.s3.ap-southeast-1.amazonaws.com/d74b8c9d-d81a-4b92-91ef-f6d3a82741d4/cv_1782873600000.pdf",
        "originalFilename": "NguyenVanA_Resume.pdf",
        "sizeBytes": 1048576,
        "uploadedAt": "2026-07-01T15:52:00.000Z"
      }
    }
    ```
