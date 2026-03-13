# AI Capstone – Phishing Detection System

## Problem Statement
Phishing emails are one of the most common cybersecurity threats today. Many users struggle to determine whether an email is legitimate or a phishing attempt. This can lead to stolen credentials, financial loss, or malware infections.

This project builds an AI-powered phishing detection system that analyzes suspicious emails and classifies them as phishing or safe. The goal is to help users quickly identify potential threats and reduce the risk of cyber attacks.

---

## Architecture

System architecture diagram:

![Architecture Diagram](docs/architecture.png)

---

## Components

- **Data Ingestion**  
  Collect suspicious emails reported by users and convert the email content into structured data for analysis.  
  Tools: n8n, Airtable.

- **AI Processing**  
  Analyze email content using a Large Language Model through the Groq API to determine whether the message is phishing or legitimate.

- **Output / Dashboard**  
  Display analyzed phishing alerts and classification results through a dashboard interface using Airtable.

---

## How to Run

1. Install required tools and dependencies.
2. Configure the data pipeline for collecting suspicious emails.
3. Run the AI analysis module using the Groq API.
4. View results through the security dashboard.

---

## Team Members

| Name | Role | GitHub |
|-----|------|------|
| Rajwant Kaur | Data Ingestion | @rajwant11 |
| Deyon | AI Phishing Analysis | @Randinu-W |
| Amy | Security Dashboard / Integration | @amyag0730 |
