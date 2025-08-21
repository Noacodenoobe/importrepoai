# Deep Research Agent

## Overview
- Specialised in deep research using Perplexity's Sonar and Sonar Pro models.
- Central `AI Agent` (OpenAI GPT-4o-mini) decides when to call each Perplexity tool.
- Includes a `Window Buffer Memory` node to retain recent dialogue.
- Designed for Telegram integration with an access filter.

## Flow
1. User message arrives via Telegram and passes through an access `Filter`.
2. The `AI Agent` analyses the query and chooses between Sonar and Sonar Pro tools.
3. The chosen tool returns data which the agent summarises for the user.

## Switching to Local Models
1. Replace the main OpenAI model with a local LLM via an OpenAI-compatible chat node.
2. If Perplexity access is not desired, substitute the Sonar tools with local web-search or RAG tools.
3. Update credentials to reference the local endpoint and remove API keys.
