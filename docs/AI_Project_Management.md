# AI Project Management Agent

## Overview
- Built with n8n and LangChain to manage Asana projects.
- Uses an Anthropic Claude model as the main LLM.
- Maintains conversation context via **Simple Memory** and leverages a **Think** tool for reasoning.
- Includes dedicated Asana nodes for creating projects, tasks, subtasks and for user lookup.

## Flow
1. Chat trigger sends user input to the **Project Manager** agent.
2. The agent decides which Asana tool to use: create project, task, subtask or find user.
3. Conversation history is stored in **Simple Memory** to give the agent context.

## Switching to Local Models
1. Run a local LLM server (e.g. LocalAI, Ollama) exposing an OpenAI-compatible `/v1` endpoint.
2. Replace the Anthropic Claude node with an OpenAI-compatible chat node pointing at your local server.
3. Update the node's `model` value to your chosen local model (e.g. `llama3-8b-instruct`) and set the `baseUrl` option to the local endpoint.
4. Update credentials in n8n to remove remote API keys and reference the local server instead.
