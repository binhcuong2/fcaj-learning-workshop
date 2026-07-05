---
title: "Week 11 Worklog"
date: 2026-07-03
weight: 11
chapter: false
pre: " <b> 1.11. </b> "
---

### Week 11 Objectives:

* Analyze the CV Matching Flow in the AI Job Matching Platform.
* Identify the main steps: Matching Trigger, Text Extraction, AI Evaluation, and Result Storage.
* Understand the required input: userId, cvKey, and jobId.
* Test Lambda using a simulated API Gateway event in the Lambda Console.
* Analyze how Lambda retrieves CV files from S3 through cvKey.
* Understand text extraction from PDF files to prepare data for the AI model.
* Analyze how job descriptions are loaded from the DynamoDB Jobs Table.
* Understand AI evaluation between CV text and job description.
* Design a JSON output containing overallScore, skillsScore, experienceScore, educationScore, summary, matchedSkills, missingSkills, and suggestions.
* Record Bedrock quota/throttling HTTP 429 and test Gemini API locally as a PoC fallback using `models/gemini-3.1-flash-lite`.
* Clearly distinguish the target production architecture with Amazon Bedrock from Gemini as a local PoC/testing fallback.

### Tasks to be carried out this week:

| Day | Task | Start Date | Completion Date | Reference Material |
| --- | --- | --- | --- | --- |
| 1 | **Matching Trigger and input analysis** <br>- Analyzed userId, cvKey, and jobId <br>- Reviewed API Gateway event shape <br>- Prepared Lambda Console test event | 29/06/2026 | 29/06/2026 | Project CV Matching notes |
| 2 | **Text Extraction from CV PDF in S3** <br>- Studied how cvKey points to S3 object <br>- Reviewed PDF text extraction requirement <br>- Prepared CV text for AI input | 30/06/2026 | 30/06/2026 | Amazon S3 and Textract notes |
| 3 | **Load Job Description from DynamoDB** <br>- Reviewed Jobs Table lookup by jobId <br>- Identified job description fields <br>- Connected job data to evaluation prompt | 01/07/2026 | 01/07/2026 | DynamoDB Jobs Table notes |
| 4 | **AI Evaluation output schema design** <br>- Designed JSON score schema <br>- Included scores, summary, matched skills, missing skills, and suggestions <br>- Prepared frontend-friendly output | 02/07/2026 | 02/07/2026 | AI evaluation schema notes |
| 5 | **Bedrock throttling and Gemini PoC fallback** <br>- Recorded Bedrock HTTP 429 issue <br>- Tested Gemini local PoC fallback <br>- Confirmed repeated request success and schema-shaped JSON output | 03/07/2026 | 03/07/2026 | Bedrock/Gemini testing notes |

### Week 11 Achievements:

* **Understood CV Matching Flow:** Learned that the flow includes multiple steps, not only an AI call.
* **Identified minimum input:** Understood that userId, cvKey, and jobId are required for evaluating a CV against a job.
* **Learned Lambda Console testing:** Used simulated API Gateway events to test the flow.
* **Understood cvKey usage:** Learned how cvKey is used to retrieve CV files from S3.
* **Standardized JSON output:** Designed an output structure that the frontend can render consistently.
* **Recognized managed AI service quota risks:** Recorded quota/throttling risk when using managed AI services.
* **Prepared workshop content:** Collected enough material for the `5-CV-Matching-Flow` workshop section.
