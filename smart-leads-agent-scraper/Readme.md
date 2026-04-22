# Smart Leads Agent Scraper (n8n)

## Goal
Automate lead generation from a client intake form by using AI to build scraping configs, running dual-source scraping, validating leads, and exporting qualified contacts.

## Included workflow

1. **Smart Leads Agent Scraper Pipeline**
   - Source: `smart-leads-agent-scraper.json`
   - Starts from a form submission and logs campaign intake data.
   - Uses AI agents to generate/sanitize dynamic scraper configurations.
   - Runs Apify Google Maps and Leads Finder actors in parallel with run-status polling.
   - Splits email/no-email leads, merges valid streams, verifies emails, updates tables, and appends qualified leads to Google Sheets.

## Demonstrated skills
- Form-triggered lead-gen automation in n8n
- AI-configured scraping strategy per campaign/ICP
- Parallel actor orchestration with wait/poll retry flow
- Lead normalization, quality filtering, and verification gating
- Operational sync using Data Tables and Google Sheets
