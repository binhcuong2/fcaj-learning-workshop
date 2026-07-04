---
title : "Databases & Storage (DynamoDB & S3)"
date: 2026-07-03
weight : 3
chapter : false
pre : " <b> 5.4.3. </b> "
---

Store structured information for favorited jobs (wishlist) in DynamoDB and store users' PDF resumes in an Amazon S3 Bucket with strict security validation mechanisms.

---

## 1. AWS SAM Template Config (`template.yaml`)

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

* **DynamoDB Billing Mode:** Use On-Demand billing (`PAY_PER_REQUEST`) to optimize cost.
* **S3 CORS:**
  * `AllowedOrigins`: Allow any origin (`*`) or specific frontend domains.
  * `AllowedMethods`: Allow `GET` (for displaying PDF directly on the browser via Signed URL or Public Read URL).

![S3 CV Bucket CORS Configuration](/images/5-Workshop/5.4-User-Interaction/dynamodb-saved-jobs_cors.png)
* **S3 Bucket Policy:** Allow public read access to resources or restricted access via API Gateway.

---

## 2. Deployment
Table and Bucket resources are automatically created and updated when deploying the SAM stack:
```bash
sam build
sam deploy
```

Once deployed successfully, you can verify the DynamoDB table and S3 bucket configuration in the AWS Console.

---

## 3. Database (DynamoDB)

### A. Table Structure: `SavedJobsTable` (Favorite Jobs)
* **Partition Key (PK):** `userId` (String `S`, extracted from Cognito Claim `sub`).
* **Sort Key (SK):** `jobId` (String `S`, ID of the job post).

![DynamoDB Saved Jobs Table](/images/5-Workshop/5.4-User-Interaction/dynamodb-saved-jobs.png)

### B. API Endpoints Overview
* **Add Favorite (`POST /saved-jobs/{jobId}`):**
  This endpoint expects the `Authorization: Bearer <Token>` header and the `jobId` parameter in the request path. The backend extracts the unique `userId` from the JWT token and performs a `PutItem` operation to save the job record with the keys `userId` and `jobId`, alongside the current timestamp `savedAt`. It returns an HTTP 201 Created status upon success.
  
* **Remove Favorite (`DELETE /saved-jobs/{jobId}`):**
  This endpoint handles unsaving a job. It requires the authentication token and the specific `jobId` in the path. Using the extracted `userId` and `jobId`, the backend runs a `DeleteItem` command to remove the record. It returns an HTTP 200 OK status.
  
* **Get Favorites List (`GET /saved-jobs`):**
  This endpoint retrieves the complete list of favorited jobs for the current authenticated user. The backend extracts the `userId` and runs a `Query` command matching the partition key `userId`. It returns an HTTP 200 OK status containing the items list.

You can check the saved job records directly in the DynamoDB Console Items tab:
![DynamoDB Saved Jobs Items](/images/5-Workshop/5.4-User-Interaction/dynamodb-saved-jobs_2.png)

---

## 4. Storage (S3)

### A. Storage Structure: `CvBucket` (CV PDF Storage)
* **Storage Naming Convention:** Objects are saved under the key: `${userId}/cv_${timestamp}.pdf`.

### B. Validation & Security Flow for Uploads
The PDF upload pipeline enforces several strict security and validation steps sequentially before committing the file to Amazon S3:

1. **Magic Bytes Verification:** The backend extracts the initial few bytes of the file stream to verify it matches the `%PDF` signature (`25 50 44 46` in hex). If the signature is incorrect, the request is rejected with a 400 Bad Request error to block potentially malicious files.
2. **File Size Check:** The file size is validated to ensure it does not exceed 5MB. If the file is larger than 5MB, a 400 Bad Request error is returned.
3. **Existing CV Limits:** The system lists existing objects in the bucket under the user's prefix (`${userId}/`). If the user already has 3 or more CVs stored, the upload request is rejected with a 400 Bad Request error.
4. **SHA-256 Hash Deduplication:** The backend computes the SHA-256 hash of the uploaded PDF. It compares this hash with the `x-amz-meta-content-hash` metadata property of the user's existing S3 objects. If a duplicate hash is detected, it blocks the upload with a 400 Bad Request error.
5. **S3 PutObject:** If all validation checks pass, the PDF is uploaded to the S3 bucket with custom metadata tags (including original filename and hash).

### C. Upload Data Flow Example
* **Input (Sent by Client):**
  * `Authorization` Header: `Bearer <JWT_ID_TOKEN>`
  * `Content-Type` Header: `application/pdf`
  * `x-original-filename` Header: `NguyenVanA_Resume.pdf` (URL-encoded)
  * Request Body: Binary buffer of the PDF file.
  * **Output (Returned by S3 Upload Lambda):**
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
