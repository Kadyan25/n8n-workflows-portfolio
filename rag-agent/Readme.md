# RAG Agent (n8n)

## Goal
Build a retrieval-augmented generation (RAG) pipeline that ingests documents, stores vector embeddings, and answers user questions using grounded context.

## Included workflows

1. **Categorization Flow**
   - Source: `categorization flow.json`
   - Scans Google Drive folders and prepares brand/scope metadata.
   - Upserts brand-level records into MySQL for downstream linking.

2. **Ingestion Flow**
   - Source: `ingestion flow.json`
   - Finds and downloads a PDF from Google Drive.
   - Extracts text, chunks content, generates embeddings with Gemini, and stores vectors in Qdrant.
   - Writes chunk metadata to MySQL for traceability.

3. **Query Flow**
   - Source: `query flow.json`
   - Embeds the user question.
   - Retrieves relevant chunks from Qdrant with metadata filters.
   - Builds context and sends it to an AI agent for a grounded final answer.

## Demonstrated skills
- End-to-end RAG architecture in n8n
- Google Drive file retrieval and PDF text extraction
- Embedding generation with Gemini APIs
- Vector search with Qdrant
- Hybrid storage pattern (Qdrant + MySQL metadata)
- Context-grounded answer generation with an AI agent
