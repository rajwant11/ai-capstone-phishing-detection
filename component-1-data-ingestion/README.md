# Data Ingestion Component – AI-Powered Phishing Detection System

## Overview

The Data Ingestion component automates the collection and structuring of suspicious email reports for the AI-Powered Phishing Detection System. Using n8n workflows, it parses incoming email submissions, extracts key fields such as sender, subject, and body, and stores them as structured records in Airtable. This allows downstream AI analysis and dashboard monitoring without manual data entry.

## Integration with Other Components

- **Input:** Receives suspicious email submissions through webhook forms or API requests.
- **Output:** Writes structured email records to the Airtable Emails table.
- **Downstream:** Triggers the AI Core component for phishing classification and threat analysis.

## Setup Instructions

### Required Accounts
- n8n Cloud account
- Airtable account
- GitHub repository access

### Required Tools
- n8n workflow automation
- Airtable database
- Groq API integration
- Flowise LLM chains

### Configuration
1. Configure Airtable credentials inside n8n.
2. Connect the workflow to the correct Airtable base and Emails table.
3. Verify webhook endpoints are active.
4. Confirm field names match the Airtable schema.

## Testing the Component

1. Submit a suspicious email sample through the webhook.
2. Verify that a new Airtable record is created.
3. Confirm sender, subject, and body fields are populated correctly.
4. Check that downstream AI processing is triggered successfully.

## Airtable Schema

| Field | Type |
|---|---|
| sender | Text |
| subject | Text |
| body | Long Text |
| severity | Single Select |
| analysis | Long Text |
| recommendations | Long Text |
| status | Single Select |

## Known Limitations

- Some malformed emails may require manual cleanup.
- Automated AI triggering is still being finalized.
- Field mismatches between components may interrupt automation if not standardized.

## Current Status

- [x] Design complete
- [x] Sample data prepared
- [x] Initial implementation
- [x] Testing
- [ ] Integration with other components
- [x] Documentation complete
