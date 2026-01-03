# Voice Instructions → Structured Task Automation (n8n)

## Goal
Convert spoken task instructions (Hindi, English, or Hinglish) into clean, structured tasks that can be stored or processed automatically.

## What this workflow does
- Receives an audio URL from a webhook or external system.
- Downloads the audio file and sends it to an OpenAI transcription endpoint to get the text.
- Uses an AI Agent with a detailed system prompt to interpret the transcript and build a structured JSON task object (assignee, phone, task name, details, due date, due time).
- Parses the AI output into valid JSON using a Code node so it can be sent to other tools (Google Sheets, CRMs, task managers, etc.).

## Demonstrated skills
- Audio processing and transcription with OpenAI
- Advanced prompt engineering for task extraction
- JSON parsing and validation via Code nodes
- Building voice-driven task automation suitable for operations or sales teams
- End-to-end pipeline from webhook → AI → structured data → external system
