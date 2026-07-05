---
title: "Week 8 Worklog"
date: 2026-07-03
weight: 8
chapter: false
pre: " <b> 1.8. </b> "
---

### Week 8 Objectives:

* Understand the job ingestion flow in the AI Job Matching Platform.
* Learn how Lambda fetches job data from SerpApi Google Jobs API.
* Understand the role of Amazon SQS in separating job fetching and job processing.
* Study the pipeline: Fetch Jobs Lambda -> Raw Jobs Queue -> Process Jobs Lambda -> Normalize/Deduplicate Lambda -> DynamoDB Jobs Table.
* Learn job data normalization for title, company name, location, posted date, and hash.
* Learn deduplication using hash and fuzzy matching.
* Recognize that external API data may be inconsistent, incomplete, duplicated, and must not expose hard-coded API keys.

### Tasks to be carried out this week:

| Day | Task | Start Date | Completion Date | Reference Material |
| --- | --- | --- | --- | --- |
| 1 | **SerpApi Google Jobs API and raw job data** <br>- Studied external job API response <br>- Reviewed raw job fields <br>- Identified inconsistent data issues | 08/06/2026 | 08/06/2026 | SerpApi Documentation |
| 2 | **Fetch Jobs Lambda and Raw Jobs Queue** <br>- Studied fetch Lambda responsibility <br>- Learned why raw jobs are sent to SQS <br>- Reviewed queue-based decoupling | 09/06/2026 | 09/06/2026 | Amazon SQS Documentation |
| 3 | **Process Jobs and Normalize/Deduplicate Lambda** <br>- Studied processing pipeline <br>- Reviewed normalization flow <br>- Learned deduplication purpose | 10/06/2026 | 10/06/2026 | AWS Lambda and SQS Guide |
| 4 | **Normalize title, company, location, and posted date** <br>- Studied common job fields <br>- Learned data cleanup purpose <br>- Prepared consistent job records | 11/06/2026 | 11/06/2026 | Data normalization notes |
| 5 | **Store processed jobs in DynamoDB Jobs Table** <br>- Reviewed DynamoDB item structure <br>- Studied hash/fuzzy matching output <br>- Connected processed data to search and matching features | 12/06/2026 | 12/06/2026 | DynamoDB Documentation |

### Week 8 Achievements:

* **Understood the reason for a multi-step ingestion flow:** Learned why fetching, processing, normalization, and storage should be separated.
* **Understood SQS decoupling:** Learned how SQS reduces coupling between fetch and process steps.
* **Understood normalization needs:** Learned why job data should be cleaned before being stored in DynamoDB.
* **Understood deduplication:** Learned how hash and fuzzy matching help detect duplicate jobs.
* **Prepared for job search and matching:** Built the foundation for search jobs and CV matching with job descriptions.
