# Capstone Project Context

## Project

- **Name:** AI-Powered Phishing Detection System
- **Team:** Rajwant Kaur (Data Ingestion), Deyon (AI Analysis), Amy (Security Dashboard)
- **What it does:** This system automatically analyzes suspicious emails using AI-powered workflows. Emails are collected through n8n, processed through Flowise and Groq AI models, classified as phishing or safe, and then displayed in a dashboard for security monitoring. The system helps security analysts quickly identify dangerous emails and automate threat analysis.

- **Project type:** Phishing Detection System

## Architecture

- **Ingestion:** n8n workflow receives suspicious email data, parses sender, subject, and body fields, then stores structured JSON records in Airtable.
- **AI Core:** Flowise chains and Groq API process the email text for phishing classification, confidence scoring, and threat analysis.
- **Specialist:** Dashboard component displays analyzed alerts, risk scores, and recommendations for security analysts.
- **Integration:** Airtable acts as the shared database between all components. Status fields and workflow triggers control handoffs between ingestion, AI analysis, and dashboard monitoring.

## Tech Stack

- n8n Cloud (workflow automation)
- Flowise Cloud (LLM chains)
- Groq API (llama-3.3-70b-versatile)
- Hugging Face Inference API (classification and analysis)
- Airtable (shared database)
- GitHub (documentation and repository)
- VS Code + GitHub Copilot

## Airtable Schema

### Emails Table

| Field | Type | Written By | Status Values |
|---|---|---|---|
| sender | Single line text | Ingestion | N/A |
| subject | Single line text | Ingestion | N/A |
| body | Long text | Ingestion | N/A |
| risk_score | Number | AI Core | low, medium, high |
| classification | Single select | AI Core | phishing, safe |
| analysis | Long text | AI Core | N/A |
| recommendations | Long text | Specialist | N/A |
| status | Single select | Integration | new, processing, analyzed, resolved |

## Conventions

- Field names use snake_case
- Status values use lowercase
- Date fields end with _at
- Boolean fields use is_prefix
- Shared Airtable schema must remain consistent across all components

## Current State

- **What's working:** n8n ingestion workflow, Flowise phishing classification chain, Airtable database integration, Groq API connection.
- **What's in progress:** Dashboard integration and automated status updates between components.
- **Known issues:** Some field name mismatches between components and incomplete automation triggers.
- **Next milestone:** Checkpoint 2 (Week 9) – one complete email record flows automatically through all components without manual intervention.

# Repository Structure

- component-1-data-ingestion/
- component-2-ai-analysis/
- component-3-dashboard/
- docs/
- data/
- week-08-lab-7/
- screenshots/
