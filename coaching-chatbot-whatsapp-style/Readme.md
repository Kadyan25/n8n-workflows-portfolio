# Coaching Chatbot with Memory (n8n)

## Goal
Provide a conversational coaching assistant that remembers previous messages per user and can integrate with WhatsApp or any chat front-end.

## What this workflow does
- Receives incoming chat messages via a webhook (e.g., from WhatsApp, a website form, or a custom chat UI).
- Uses an AI agent with an OpenAI chat model to generate helpful, context-aware replies.
- Stores short-term conversation history per user using a memory node keyed by the user's mobile number.
- Sends the AI response and chat data to an external webhook endpoint to deliver the reply back to the user or log the conversation.

## Demonstrated skills
- Webhook-based chat integration
- AI agent + OpenAI chat model orchestration
- Session-based conversation memory in n8n
- Forwarding structured chat data to external systems via HTTP
- Designing a reusable chatbot template for coaching or support use cases
