# CRM Automation Workflows (GoHighLevel) – n8n

## Goal
Automate lead capture, pipeline management, calling outcomes, and social posting for a CRM (e.g., GoHighLevel) using n8n.

## Included workflows (selected examples)

1. **Lead → Contact & Opportunity Creation**
   - Source: `Digital-Coaching-Mohit.json`
   - Takes new leads from a Google Sheet or webhook.
   - Upserts contacts in the CRM and creates opportunities in the correct pipeline and status.

2. **B2C Calling Status Automation**
   - Source: `b2c.json`
   - Listens to call/call-log webhooks with fields like `Calling_status`.
   - Uses conditional logic (If/Rules nodes) to branch on statuses such as "Meeting schedule", "Reschedule", "Done", "Switched off", etc.
   - Updates CRM records, tasks, or follow-up actions accordingly.

3. **Social Media Posting via CRM**
   - Source: `social-mk.json`
   - Receives content + media URL via webhook.
   - Uploads media, then posts to multiple social accounts through the CRM's social posting API.

## Demonstrated skills
- Deep REST API integrations with a CRM (GoHighLevel/LeadConnector)
- Webhook-driven workflows for leads, calls, and social events
- Complex conditional logic and branching on field values
- Mapping data across tools (Sheets → CRM → social posting)
- Handling auth headers, file uploads, and JSON bodies for third-party APIs
