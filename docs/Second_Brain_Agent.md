# Second Brain Agent

## Overview
- Acts as a personal knowledge base using Supabase for vector storage.
- The `Vector Store Agent` powered by OpenAI GPT-4o-mini handles add/search operations.
- Conversation context is saved in Postgres via `Postgres Chat Memory`.
- Integrations include Telegram and YouTube transcription to ingest content.

## Flow
1. Incoming data is embedded and stored in Supabase.
2. User queries trigger retrieval from the vector store.
3. The agent composes responses using retrieved context and returns them to the user.

## Switching to Local Models
1. Replace GPT-4o-mini with a local LLM (e.g. `llama3-8b`), updating the node's model and `baseUrl`.
2. Swap OpenAI embeddings with a local embedding model such as `text-embedding-nomic`.
3. Update credentials to remove remote API keys and reference the local endpoints.
