---
title: "Workshop"
date: 2026-07-03
weight: 5
chapter: false
pre: " <b> 5. </b> "
---


# Serverless Jobs Matching Platform

#### Tổng quan

Trong workshop này, bạn sẽ xây dựng **Jobs Matching Platform** - một hệ thống tự động tổng hợp việc làm và phân tích hồ sơ ứng viên (CV) bằng cách sử dụng hoàn toàn các dịch vụ AWS Serverless (AWS Lambda, DynamoDB, SQS, S3, API Gateway, Cognito, EventBridge, WAF, và Amplify).

Bạn sẽ cấu hình và xây dựng các thành phần:
+ **Jobs Ingestion Pipeline** - Tự động thu thập dữ liệu việc làm bằng EventBridge, Lambda, SQS, và lưu trữ trong DynamoDB.
+ **Tương tác người dùng** - Bảo mật API Gateway, Cognito User Pool để xác thực, DynamoDB cho cơ sở dữ liệu, các Lambda API nghiệp vụ chính và triển khai Frontend trên AWS Amplify.
+ **Luồng đánh giá CV** - Xử lý CV được tải lên S3, trích xuất nội dung bằng Lambda, gọi API Gemini để phân tích mức độ phù hợp và lưu kết quả.
+ **Vận hành & Bảo mật** - Cấu hình IAM policies, quản lý API key, giám sát & cảnh báo với CloudWatch và quản lý chi phí qua AWS Budgets.

#### Nội dung

1. [Giới thiệu](5.1-Workshop-overview/)
2. [Các bước chuẩn bị](5.2-Prerequiste/)
3. [Jobs Ingestion Pipeline](5.3-Job-Ingestion/)
4. [Tương tác người dùng](5.4-User-Interaction/)
5. [Luồng đánh giá CV](5.5-CV-Matching-Flow/)
6. [Vận hành & Bảo mật](5.6-Operations-Security/)
7. [Dọn dẹp tài nguyên](5.7-Cleanup/)