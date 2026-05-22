# LinkedIn DMs Campaign System (n8n)

## Goal
Automate LinkedIn outreach end-to-end by launching connection invites, running scheduled follow-up DMs, tracking replies, and enforcing account-level daily limits.

## Included workflows (full system)

1. **Start Campaign**
   - Source: `LinkedIn DMs - 1. Start Campaign.json`
   - Reads database, campaign, and account sheets.
   - Filters only eligible prospects based on campaign/account status and daily connection limits.
   - Sends connection invites via Unipile and updates delivery status + counters.

2. **Campaign Tick**
   - Source: `LinkedIn DMs - 2. Campaign Tick.json`
   - Runs every 30 minutes to process ongoing outreach actions.
   - Checks pending invite acceptance, sends sequenced DM follow-ups, and records DM outcomes.
   - Detects replies and handles expired pending invites with withdrawal + status updates.

3. **Daily Counter Reset**
   - Source: `LinkedIn DMs - 3. Daily Counter Reset.json`
   - Runs daily at 00:00 IST.
   - Resets `connections_sent_today` and `dms_sent_today` in the accounts sheet.
   - Writes reset timestamps for operational tracking.

## Demonstrated skills
- Multi-workflow LinkedIn campaign orchestration
- Google Sheets-driven campaign state and account governance
- Per-account throttling and pacing controls for safer outreach
- Sequenced DM automation with reply/acceptance tracking
- Daily operations reset workflow for reusable campaign cycles
