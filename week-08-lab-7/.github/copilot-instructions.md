# Capstone Project Context

## Project

- **Name:** AI-Powered Phishing Detection System
- **Team:** 
  - Rajwant Kaur – Data Ingestion Component
  - Deyon – AI Phishing Analysis Component
  - Amy – Security Dashboard Component

- **What it does:** 
This system analyzes suspicious emails using AI-powered phishing detection workflows. Users submit suspicious emails, which are processed through n8n ingestion workflows and stored in Airtable. AI analysis using Flowise and Groq API classifies emails as phishing or safe, generates confidence scores, and provides actionable threat analysis for monitoring through a security dashboard.

- **Project type:** Cybersecurity / Phishing Detection and Threat Analysis System

---

## Architecture

- **Ingestion:** 
n8n workflows receive suspicious email submissions, parse sender, subject, and email body fields, then store structured JSON records in Airtable.

- **AI Core:** 
Flowise LLM chains and Groq API process email text for phishing classification, confidence scoring, and threat analysis.

- **Specialist:** 
The dashboard component visualizes analyzed alerts, phishing classifications, and risk scores for monitoring and incident response.

- **Integration:** 
Airtable acts as the shared database connecting ingestion workflows, AI analysis components, and dashboard monitoring systems. n8n automates data movement between all services.

---

## Tech Stack

- n8n Cloud (workflow automation)
- Flowise Cloud (LLM chains and analysis workflows)
- Groq API (LLM inference and phishing classification)
- Hugging Face Inference API (text classification and NLP analysis)
- Airtable (shared database and monitoring records)
- GitHub (repository, documentation, and collaboration)
- VS Code (development environment)
- GitHub Copilot (AI-assisted development)

---

## Airtable Schema

### Emails Table

| Field | Type | Written By | Status Values |
|---|---|---|---|
| email_id | Number | n8n Ingestion | N/A |
| sender | Text | Ingestion Component | N/A |
| subject | Text | Ingestion Component | N/A |
| body | Long Text | Ingestion Component | N/A |
| risk_score | Number | AI Analysis Component | low, medium, high |
| classification | Single Select | AI Analysis Component | phishing, safe |
| confidence_score | Number | AI Analysis Component | N/A |
| analysis_notes | Long Text | AI Analysis Component | N/A |

### Alerts Table

| Field | Type | Written By | Status Values |
|---|---|---|---|
| alert_id | Number | n8n Workflow | N/A |
| email_id | Linked Record | n8n Workflow | N/A |
| alert_status | Single Select | Dashboard Component | triaged, investigating, resolved |
| assigned_to | Text | Dashboard Component | N/A |
| created_at | Date | n8n Workflow | N/A |

---

## Conventions

- Field names use snake_case
- Status values use lowercase
- Date fields end in _at
- Boolean fields use is_prefix
- Airtable records are linked using IDs
- AI outputs should remain structured and concise
- All workflow documentation should use markdown formatting

---

## Current State

- **What's working:** 
Email ingestion workflow, Flowise phishing analysis chains, Groq API integration, Airtable database structure, and GitHub repository organization.

- **What's in progress:** 
Dashboard integration, automated alert monitoring, and improved AI classification accuracy.

- **Known issues:** 
Final dashboard testing, workflow optimization, and Airtable automation refinement are still in progress.

- **Next milestone:** 
Checkpoint 2 (Week 9) – One suspicious email successfully processed end-to-end through ingestion, AI analysis, Airtable storage, and dashboard visualization.

---

# Repository Structure

- /component-1-data-ingestion
- /component-2-ai-analysis
- /component-3-dashboard
- /data
- /docs
- /week-04-model-comparison
- /week-05-automl-training
- /week-07
- /.github


# Current State Update - Checkpoint 2

## Current Workflow Status
The phishing detection workflow is partially integrated across ingestion, AI analysis, specialist processing, and dashboard components.

## What's Working
- Ingestion accepts phishing test records successfully
- AI analysis generates phishing classification output
- Dashboard structure exists for displaying processed records
- GitHub documentation and workflow structure are organized

## Current Issues
- Workflow routing still requires additional testing
- Dashboard formatting and visualization need refinement
- AI confidence scoring needs improvement
- End-to-end workflow validation is still in progress

## Current Development Focus
- Improve workflow reliability
- Reduce integration errors
- Validate routing between all workflow stages
- Finalize dashboard presentation and testing
