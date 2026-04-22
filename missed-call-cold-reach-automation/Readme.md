# Missed Call Cold Reach Automation (n8n)

## Goal
Automatically convert missed calls into a structured callback/outreach process, then keep lead status in sync across calling and CRM workflows.

## Included workflows (full system)

1. **Dialora to GHL Missed Call Intake**
   - Source: `dialora to ghl missed call.json`
   - Receives webhook events from calling flow.
   - Builds contact payloads and pushes missed-call data into CRM-side processing.

2. **Missed Call Outreach Runner**
   - Source: `Missed Call.json`
   - Pulls pending leads, loops one-by-one, triggers outbound call attempts, and branches on success/failure.
   - Marks lead status and retries with wait/merge logic.

3. **GHL Status Sync to Sheet**
   - Source: `GHL Status Updates → Sheet.json`
   - Receives status webhooks from CRM sequence updates.
   - Updates tracking sheet statuses (including no-interaction outcomes).

## Demonstrated skills
- Event-driven missed-call recovery automation
- Webhook integration between dialer and CRM workflows
- Lead queue processing with loop, wait, and retry handling
- Google Sheets based operational tracking and status sync
- Reliable status propagation across multiple systems
