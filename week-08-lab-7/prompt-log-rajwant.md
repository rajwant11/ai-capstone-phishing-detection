# Prompt Log – Rajwant Kaur

Project: AI-Powered Phishing Detection System
Team: Rajwant Kaur, Deyon, Amy
My Component: Ingestion
AI Tools Used: GitHub Copilot, ChatGPT

---

## How to Use This Log

This log tracks significant AI-assisted development interactions during the capstone project. It records prompts, AI outputs, evaluations, corrections, and lessons learned while using GitHub Copilot and other AI tools.

---

## 2026-05-14 – Capstone Project Audit Using GitHub Copilot

Context:
I was working inside the capstone project repository in VS Code and using GitHub Copilot Chat to evaluate our project readiness for Checkpoint 2. The project uses n8n, Flowise, Airtable, Groq API, and GitHub integration.

Prompt:
> I need you to act as a capstone project advisor for a university AI integration course. I'm going to describe my group project, and I need you to interview me about its current state, then produce a structured gap analysis.

Result:
Copilot generated a full "Checkpoint 2 Readiness Assessment" report identifying:
- working components
- missing integrations
- schema issues
- test data gaps
- recommended fixes

Evaluation:
The audit was useful and helped identify important workflow gaps that still need testing. Some field mismatch suggestions were partially incorrect because the AI guessed a few schema details that were not fully finalized.

What I changed:
I manually reviewed the suggested schema mismatches and verified which field names were actually being used in Airtable and n8n workflows.

What I learned:
Providing detailed project context through the copilot-instructions.md file greatly improved the quality of Copilot responses. AI-generated audits are most useful when the project context is specific and accurate.


## 2026-05-14 – Debugging Workflow Field Name Mismatch

Context:
I was reviewing the phishing detection workflow and checking how records moved between Airtable, n8n, and the AI analysis pipeline. During testing, I noticed that some fields were not appearing correctly in downstream workflow stages.

Prompt:
> Help me identify possible field name mismatches between Airtable schema fields and n8n workflow variables for my phishing detection pipeline.

Result:
The AI suggested reviewing naming consistency between Airtable fields, workflow variables, and AI output mappings. It recommended using lowercase snake_case naming conventions across all workflow stages.

Evaluation:
The suggestions helped identify areas where inconsistent naming could create routing or parsing issues. The AI guidance was useful for improving workflow consistency.

What I changed:
I reviewed field naming conventions and verified that workflow field names matched the Airtable schema structure.

What I learned:
Consistent field naming conventions are important for preventing workflow routing and parsing problems in AI-integrated systems.


## 2026-05-14 – Generating Test Data for End-to-End Workflow Testing

Context:
I was preparing a realistic phishing email example to test the complete workflow integration between ingestion, AI analysis, specialist processing, and dashboard visualization components.

Prompt:
> Generate a realistic phishing email example that can be used for end-to-end workflow testing in an AI-powered phishing detection system.

Result:
The AI generated several phishing email examples containing urgent account warnings, suspicious links, and credential verification requests suitable for workflow testing.

Evaluation:
The generated examples were realistic and useful for testing phishing classification behavior and workflow routing.

What I changed:
I selected one phishing example and adjusted the wording slightly to better match the expected phishing detection scenarios used in our project.

What I learned:
AI-generated test data can significantly speed up workflow validation and system testing during development.


## 2026-05-14 – Reviewing Workflow Routing and Integration Flow

Context:
I was validating how records moved across the ingestion workflow, AI analysis pipeline, and dashboard integration during Checkpoint 2 testing.

Prompt:
> Review my phishing detection workflow design and explain possible routing or integration problems that could happen between ingestion, AI analysis, and dashboard stages.

Result:
The AI explained common integration issues such as workflow trigger failures, incorrect status values, missing fields, and routing mismatches between workflow stages.

Evaluation:
The guidance helped me better understand where workflow failures might occur during end-to-end testing and how to isolate integration issues more effectively.

What I changed:
I reviewed workflow routing logic and checked whether records were moving correctly between Airtable, AI analysis, and dashboard stages.

What I learned:
End-to-end workflow validation is important because even small routing or status mismatches can stop the full pipeline from functioning correctly.

## 2026-05-14 – Updating Copilot Instructions for Checkpoint 2

Context:
I updated the copilot-instructions.md file to reflect the current project state after completing Checkpoint 2 workflow testing and integration review.

Prompt:
> Help me update my copilot-instructions.md file to reflect the current workflow status, known issues, integration progress, and current development priorities for Checkpoint 2.

Result:
The AI generated a structured project status update including workflow progress, working components, integration gaps, and development priorities.

Evaluation:
The generated update improved the project context available to GitHub Copilot and made the repository documentation more organized and accurate.

What I changed:
I added a new "Current State Update - Checkpoint 2" section to the copilot-instructions.md file and updated workflow status information.

What I learned:
Providing updated project context helps AI development tools generate more accurate workflow suggestions, debugging assistance, and project analysis.
