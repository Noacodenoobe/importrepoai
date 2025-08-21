# Personal Assistant

## Overview
- Telegram-based assistant orchestrating multiple specialised agents.
- Handles text and voice input, research, finance tracking, email management, weather/news and content writing.
- Maintains long-term context using Postgres-backed chat memory.

## Flow
1. **Telegram Trigger** receives user messages or audio.
2. Audio is transcribed and merged with text in `Combine fields`.
3. The **Orchestrator Agent** selects sub-agents such as Research, Finance Tracker, Email Manager or Write Section Tool.
4. Responses are sent back through Telegram.

## Local Model Integration
- Replaced remote models with locally hosted equivalents:
  - **GPT-4.1** → `mixtral-8x7b` at `http://localhost:8080/v1`.
  - **Anthropic Chat Model** → `qwen2-7b-instruct` via the same local endpoint.
  - **GPT-5-Nano** → `phi-3-mini` for lightweight tasks.
  - **OpenAI** transcription → `faster-whisper` running locally.
- All LLM nodes now reference credentials named **Local OpenAI** pointing to the local server.
- These changes allow the entire assistant workflow to operate without external API calls.

## Further Enhancements
- Insert a translation layer using a Polish model such as **Bielik 11B** to ensure natural language output.
- Swap remaining OpenAI tool nodes for self-hosted alternatives as needed.
