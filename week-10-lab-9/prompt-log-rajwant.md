# Prompt Log – Rajwant Kaur
Project: AI-Powered Phishing Detection System  
Team: Rajwant Kaur, Deyon, Amy  
My Component: Ingestion  
AI Tools Used: GitHub Copilot, ChatGPT

---

## 2026-05-15 – Testing Error Handling With Empty Workflow Input

Context:
I was testing the ingestion workflow error handling for the AI-Powered Phishing Detection System. The goal was to determine how the workflow behaves when required phishing alert input data is missing.

Prompt:
> Help me test an error handling scenario for an n8n phishing detection workflow using empty alert input data.

Result:
The workflow executed even though the alert_text field was empty. This revealed that the ingestion workflow currently does not validate missing required input fields before processing.

Evaluation:
The test successfully exposed a workflow reliability gap. The workflow should prevent empty records from continuing through downstream AI analysis stages.

What I changed:
I documented the missing validation issue and planned an IF validation branch to assign status = "error" and populate an error_reason field for invalid records.

What I learned:
Testing bad input scenarios is important because workflows may appear functional during normal testing while still failing to properly handle invalid or incomplete data.

---

## 2026-05-15 – Implementing Confidence-Based Routing Logic

Context:
I was working on AI workflow routing logic for the phishing detection system. The objective was to create confidence-based workflow decisions using the Alert Classifier output.

Prompt:
> Help me create confidence-based routing logic in n8n using an IF node after AI classification output.

Result:
An IF node was added between the Alert Classifier and Threat Analyzer workflow stages. The routing logic checked whether the classifier response contained a high confidence value.

Evaluation:
The confidence routing logic successfully demonstrated how records can follow different workflow paths based on AI analysis confidence levels.

What I changed:
I configured an IF node to evaluate classifier confidence output and route high-confidence phishing records through the automated analysis pipeline.

What I learned:
Confidence-based routing improves workflow reliability by allowing uncertain or low-confidence records to be reviewed separately instead of automatically processed.
