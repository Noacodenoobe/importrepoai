# Deep Research V2 + RAG

## Overview
- Advanced research agent combining web search with Retrieval-Augmented Generation.
- Utilises Supabase as a vector store for document retrieval.
- Includes PDF ingestion and text splitting nodes to populate the knowledge base.
- Employs DeepSeek chat models for reasoning.

## Flow
1. A Telegram trigger forwards user messages to a `Switch` that selects the desired agent mode.
2. Documents can be uploaded, split and embedded into Supabase for later retrieval.
3. The `AI Agent` queries the vector store and external tools to craft a comprehensive answer.

## Switching to Local Models
1. Swap the DeepSeek chat nodes with local models hosted on an OpenAI-style endpoint.
2. For embeddings, use a local embedding model or an offline service compatible with Supabase.
3. Ensure all credential nodes point to the local services and remove remote keys.
