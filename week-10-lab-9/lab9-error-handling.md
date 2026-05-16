# Lab 9 – Error Handling

## Error Scenario Tested
The ingestion workflow was tested using an empty phishing alert input to simulate missing required data.

## What Happened
The workflow executed successfully even though the alert_text field was empty. This revealed that input validation and error handling for missing required fields have not yet been implemented in the ingestion workflow.

## Issue Found
The system currently allows empty records to move through the workflow instead of stopping the process or assigning an error status.

## Planned Fix
An IF validation branch will be added to the n8n ingestion workflow. If alert_text is empty:
- status will be set to "error"
- error_reason will explain the issue
- invalid records will be prevented from continuing through the AI pipeline

## Screenshot
- error-empty-input.png 
