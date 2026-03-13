# AI Capstone – Phishing Detection System

![Architecture Diagram](docs/architecture.png)

---

## Problem Statement

Phishing emails are one of the most common cybersecurity threats today. Many users struggle to determine whether an email is legitimate or a phishing attempt. This can lead to stolen credentials, financial loss, or malware infections.

This project develops an AI-powered phishing detection system that analyzes suspicious emails and classifies them as phishing or safe. The system automates email collection, uses an AI model to analyze the content, and displays the results in a dashboard so users can quickly identify potential threats.

---

## Architecture

The system is composed of three main components connected through an automated data pipeline:

1. Data ingestion collects suspicious emails submitted by users.
2. AI processing analyzes the email text using a large language model.
3. The dashboard displays classification results and phishing alerts.

The architecture diagram above shows how these components interact.

---

## Components

### Data Ingestion
Collect suspicious emails reported by users and convert the email content into structured data for analysis.

Tools:
- n8n
- Airtable

Input:
- Suspicious email (sender, subject, body)

Output:
- Structured email data stored in Airtable.

---

### AI Processing
Analyze the email content using an AI model to determine whether the message is phishing or legitimate.

Tools:
- Groq API
- Large Language Model (LLM)

Output:
- Email classification (phishing or safe)
- Confidence score.

---

### Output / Security Dashboard
Display analyzed phishing alerts and allow users to review classification results through a simple dashboard.

Tools:
- Airtable dashboard
- n8n integration

Features:
- View analyzed emails
- Filter phishing alerts
- Display risk scores.

---

## How to Run

1. Install required tools and dependencies.
2. Configure the email ingestion workflow using n8n.
3. Connect Airtable to store structured email data.
4. Run the AI analysis module using the Groq API.
5. View classification results through the dashboard.

---

## Repository Structure

```
ai-capstone-phishing-detection
│
├── docs
│   ├── proposal.md
│   └── architecture.png
│
├── README.md
└── .gitignore
```

---

## Team Members

| Name | Role | GitHub |
|-----|------|------|
| Rajwant Kaur | Data Ingestion | @rajwant11 |
| Deyon | AI Phishing Analysis | @Randinu-W |
| Amy | Security Dashboard / Integration | @amyag0730 |

---

## Project Goal

The goal of this system is to build an AI-powered cybersecurity tool that helps users quickly analyze suspicious emails and identify phishing attempts. The system integrates automated data pipelines, AI-based classification, and a visual dashboard to provide a simple and effective phishing detection workflow.
