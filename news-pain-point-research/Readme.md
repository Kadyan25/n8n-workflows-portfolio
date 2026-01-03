# News → AI Pain-Point Research (n8n)

## Goal
Turn recent news articles into structured client pain-point insights that can be used for LinkedIn posts, marketing content, or research.

## What this workflow does
- Starts from a form submission that collects:
  - Subject for research
  - Lookback period (number of articles/days)
  - Base message for LinkedIn
- Reads recent news from a Google News RSS feed for the given subject.
- Uses JavaScript Code nodes to:
  - Merge form data and RSS results
  - Extract and limit article links based on the lookback input
- Sends the combined data to an AI agent powered by a Gemini chat model to:
  - Extract key client problems and pain points
  - Summarize findings in a structured, marketing-ready format.

## Demonstrated skills
- n8n form triggers and user input handling
- Working with RSS feeds and external data sources
- JavaScript Code nodes for data transformation and slicing
- AI agent orchestration with Google Gemini
- Building research workflows useful for content and marketing teams
