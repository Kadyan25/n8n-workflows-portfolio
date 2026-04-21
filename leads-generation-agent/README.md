# Leads Generation Agent

An end-to-end AI-powered B2B lead generation pipeline built in n8n. A client fills out an intake form, an AI agent interprets their ICP (Ideal Customer Profile), and the system automatically scrapes, enriches, verifies, and stores qualified leads — all without manual intervention.

---

## What It Does

1. **Intake Form** — Client submits a detailed lead generation brief (target industry, roles, regions, volume, exclusions)
2. **AI Agent (GPT-4.1)** — Interprets the brief and generates optimised config objects for two Apify scrapers
3. **Data Cleaning (Code Node)** — Sanitizes and validates AI output (seniority levels, industry labels, size buckets, locations)
4. **Dual Scraping (parallel)**
   - **Google Maps Email Extractor** — Targets local/map-style businesses via niche + location search strings
   - **B2B Leads Finder** — Targets online-first and hybrid businesses by job title, seniority, industry, and company size
5. **Wait + Poll** — Waits 3 minutes then polls Apify for completed run results
6. **Split by Email** — Leads with emails go to Merge → DB; leads without emails go to a separate no-email table
7. **Merge** — Combines leads from both scrapers into a single stream
8. **Email Verification (AnyMailFinder)** — Verifies each email address
9. **Update + Export** — Updates the leads table with verification status and appends valid leads to Google Sheets

---

## Workflow Architecture

```
Intake Form
    │
    ├── Insert row (DB log)
    │
    └── Append to Sheet → AI Agent (GPT-4.1)
                              │
                         Data Cleaning
                         /           \
              GMaps Scraper      Leads Finder Scraper
              Wait 3min           Wait 3min
              Poll Run            Poll Run
              Fetch Results       Fetch Results
              /        \           /        \
        Has Email   No Email   Has Email   No Email
            │           │          │           │
         Merge        DB log     Merge       DB log
            │
       Insert to DB
            │
     Email Verification
            │
       Update DB row
            │
       If Valid Email
            │
    Append to Google Sheet
```

---

## Nodes Used

| Node | Purpose |
|---|---|
| Form Trigger | Collects client intake form |
| Google Sheets | Logs submissions + exports verified leads |
| AI Agent (LangChain) | Generates scraper configs from brief |
| OpenAI Chat Model (GPT-4.1) | Powers the AI agent |
| Code Node | Sanitizes and validates AI output |
| HTTP Request (x6) | Apify scraper runs + result fetching |
| Wait (x2) | Pause 3 min for Apify runs to complete |
| Filter (x4) | Splits leads by email presence |
| Merge | Combines GMaps + Leads Finder results |
| DataTable (x4) | Inserts/updates leads in n8n data tables |
| HTTP Request | AnyMailFinder email verification |
| IF | Routes only verified leads to Sheets |

---

## External Services

- **Apify** — `lukaskrivka/google-maps-with-contact-details` and `code_crafter/leads-finder`
- **AnyMailFinder** — Email verification API
- **OpenAI** — GPT-4.1 for ICP interpretation and config generation
- **Google Sheets** — Final export of verified leads

---

## Key Design Patterns

- **Dynamic scraper config** — AI generates fresh configs per client, not hardcoded templates
- **Dual-source lead generation** — GMaps for local businesses, Leads Finder for online-first B2B
- **Smart source split** — AI calculates weight between GMaps vs Leads Finder based on ICP type
- **Email-gated routing** — Only leads with emails proceed to verification; others stored separately
- **Over-generation buffer** — Scrapes ~1.3x the requested volume to account for email bounce rates
