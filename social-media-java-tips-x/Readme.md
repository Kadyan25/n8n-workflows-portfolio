# AI Java Tips → X (Twitter) Auto-Posting (n8n)

## Goal
Automatically post a short, useful Java programming tip to X (Twitter) every day without manual work.

## What this workflow does
- Triggers once per day using a Schedule Trigger.
- Uses an AI chat model (Google Gemini) to generate a concise Java tip under 280 characters, ready for posting.
- Optionally parses the AI output into a structured format.
- Sends the final text directly to X (Twitter) using the Twitter node with an OAuth2-connected account.

## Demonstrated skills
- n8n scheduling and cron configuration
- AI integration via LangChain nodes (Google Gemini)
- Prompt design for social-friendly, character-limited content
- Using the Twitter/X node for authenticated posting
- Clean node structure and reusable automation template
