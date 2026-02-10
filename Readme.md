# n8n Workflows Portfolio

This repository showcases real n8n workflows Iâ€™ve built for AI, automation, and CRM use cases. Each folder contains a `workflow.json` export plus a README explaining the goal, steps, and what the workflow demonstrates.

## Workflows

1. **AI Java Tips â†’ X (Twitter) Auto-Posting**  
   - Folder: `social-media-java-tips-x/`  
   - Automates a daily schedule â†’ AI-generated Java tip â†’ auto-post to X (Twitter) via the Twitter node.

2. **News â†’ AI Pain-Point Research**  
   - Folder: `news-pain-point-research/`  
   - Takes a topic from a form, reads Google News RSS, and uses an AI agent to extract client pain points and marketing insights.

3. **Coaching Chatbot with Memory**  
   - Folder: `coaching-chatbot-whatsapp-style/`  
   - Webhook-based chatbot that uses an AI model + conversation memory per user, then forwards replies to an external system (e.g., WhatsApp/CRM).

4. **Voice Instructions â†’ Structured Task Automation**  
   - Folder: `ai-audio-to-task-sheet/`  
   - Converts audio instructions to text, uses an AI agent to build a structured task JSON, and prepares it for storage in tools like Google Sheets or CRMs.

5. **AI Task Chat Webhook (optional/private)**  
   - Folder: `ai-task-chat-webhook/`  
   - Connects a custom backend AI chat endpoint with external webhooks for task-related conversations (kept generic / partially private if needed).

6. **CRM Automation Workflows (GoHighLevel)**  
   - Folder: `crm-automation-gohighlevel/`  
   - Multiple workflows for:
     - Lead â†’ contact + opportunity creation
     - Updating opportunities based on call/call-log statuses
     - Posting content and media to social accounts via the CRM API.

7. **Sheets & Internal Tools (Support / Tasks)**  
   - Folder: `sheets-task-management/`  
   - Workflows around Google Sheets triggers, Supabase/custom APIs, and internal dashboards for tickets and tasks.

8. **RAG Agent**  
   - Folder: `rag-agent/`  
   - Three connected flows for categorization, ingestion, and retrieval-grounded question answering.

## Tech & Tools Used

- **Automation:** n8n (webhooks, schedule triggers, forms, filters, IF/Rules, Code nodes)  
- **AI:** Google Gemini (LangChain nodes), OpenAI (chat + audio), AI agents, structured output parsing  
- **Data & Storage:** Google Sheets, custom APIs, serverless functions  
- **CRMs & Platforms:** GoHighLevel/LeadConnector, social posting APIs, webhooks  
- **Patterns:** Event-driven flows, API orchestration, error-safe designs, and reusable templates.



