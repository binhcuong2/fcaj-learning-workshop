---
title: "Week 10 Worklog"
date: 2026-07-03
weight: 10
chapter: false
pre: " <b> 1.10. </b> "
---

### Week 10 Objectives:

* Understand the CV upload flow in the AI Job Matching Platform.
* Learn the role of Amazon S3 in storing CV files.
* Analyze the flow: Frontend -> API Gateway -> Lambda Upload CV -> Amazon S3.
* Understand how the backend receives upload requests from the frontend.
* Learn CV file metadata such as userId, file name, file type, S3 object key, and upload time.
* Design S3 object keys so CV files can be retrieved by user.
* Understand secure upload practices such as keeping the bucket private, avoiding hard-coded bucket names, avoiding sensitive CV logs, and allowing users to access only their own files.
* Understand that `cvKey` becomes an input for the CV Matching Flow.

### Tasks to be carried out this week:

| Day | Task | Start Date | Completion Date | Reference Material |
| --- | --- | --- | --- | --- |
| 1 | **CV upload flow from frontend to backend** <br>- Studied upload request flow <br>- Reviewed frontend-to-API integration <br>- Identified backend upload responsibility | 22/06/2026 | 22/06/2026 | API integration notes |
| 2 | **S3 bucket and object key for CV files** <br>- Studied S3 object storage <br>- Reviewed key naming strategy <br>- Connected user identity with file path | 23/06/2026 | 23/06/2026 | Amazon S3 Documentation |
| 3 | **Lambda metadata processing** <br>- Reviewed file metadata fields <br>- Studied upload time and file type handling <br>- Prepared metadata for later retrieval | 24/06/2026 | 24/06/2026 | Lambda and S3 Notes |
| 4 | **Secure CV storage on S3** <br>- Reviewed private bucket usage <br>- Avoided logging sensitive CV content <br>- Checked ownership-based access concept | 25/06/2026 | 25/06/2026 | S3 Security Best Practices |
| 5 | **cvKey connection to CV Matching Flow** <br>- Studied how `cvKey` identifies the uploaded CV <br>- Connected upload output with matching input <br>- Prepared for AI evaluation flow | 26/06/2026 | 26/06/2026 | Project architecture notes |

### Week 10 Achievements:

* **Understood why S3 stores PDF files:** Learned that S3 is more suitable for file storage than DynamoDB.
* **Distinguished file and metadata storage:** Understood that PDF files are stored in S3 while metadata and results can be stored in DynamoDB.
* **Understood the role of cvKey:** Learned that `cvKey` links uploaded CV files to later processing steps.
* **Connected upload with AI evaluation:** Prepared the foundation for CV Matching Flow.
* **Recognized security and cost risks:** Learned that user files require controlled access and cost awareness.
