# AI Sub Agent Demo

## Overview
- Demonstrates a hierarchy of sub-agents used to compose blog posts.
- The main **Blog Writer Agent** orchestrates research, outline generation, writing and image creation.
- Tools include Perplexity search, title/structure generation, section writing and image generation.
- Relies on several OpenAI chat model nodes.

## Flow
1. **Research Agent** gathers information using Perplexity and other search tools.
2. **Titles and Structure Tool** proposes titles and an outline.
3. **Write Section Tool** drafts each section of the post.
4. **Generate Image Tool** creates a matching graphic.
5. Results are merged and returned by the **Blog Writer Agent**.

## Switching to Local Models
1. Spin up a local LLM endpoint compatible with the OpenAI API.
2. Replace each OpenAI chat node with a local model (e.g. `llama3-8b` or `mixtral-8x7b`).
3. Point the `baseUrl` option of the node to the local server and remove API keys.
4. For image generation, use a local diffusion model or leave the API-based node as-is.
