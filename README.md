# n8n Telegram AI Appointment Agent

This repository contains a self-hosted n8n workflow that implements an AI-powered Telegram assistant for managing calendar appointments via natural language (text and voice).

The workflow is designed with a strong focus on security, controlled execution, and real-world automation logic.

---

## Workflow Overview

![Workflow Overview](screenshots/workflow-overview.png)

---

## What this workflow does

- Receives incoming Telegram messages via webhook
- Validates incoming requests using a user ID check
- Handles both text messages and voice messages
- Automatically transcribes voice messages to text
- Uses an AI agent to interpret user intent
- Safely creates, updates, or deletes Google Calendar events
- Sends structured feedback back to the user via Telegram

---

## Core Logic & Flow

1. **Telegram Trigger**  
   Entry point for all incoming messages.

2. **Security Layer – User Validation**  
   A strict ID check ensures that only authorized users can interact with the system.

3. **Message Type Detection**  
   The workflow differentiates between:
   - text messages
   - voice messages (voicemails)

4. **Voice Processing (if applicable)**  
   - Downloads the audio file from Telegram
   - Transcribes the recording using an AI transcription model

5. **AI Agent Decision Layer**  
   A central AI Agent:
   - Interprets user intent
   - Decides which calendar action is required
   - Uses structured tool access instead of free-form execution

6. **Controlled Calendar Operations**  
   The agent can:
   - search for events
   - create new events
   - update existing events
   - delete events  

   Destructive actions are intentionally gated and require a safe execution path.

7. **Response Delivery**  
   The final response is sent back to the user via Telegram.

---

## Tech Stack

- n8n (self-hosted)
- Telegram Bot API
- OpenAI (Chat + Transcription)
- Google Calendar API
- Simple Memory for conversational context

---

## Key Concepts Demonstrated

- Event-driven automation
- AI agent orchestration
- Dual input handling (text & voice)
- API-based calendar management
- Safety-first execution design
- Prompt-controlled tool usage
- Modular workflow design in n8n

---

## How to use this workflow

1. Import `workflow.json` into n8n
2. Configure required credentials:
   - Telegram Bot
   - OpenAI
   - Google Calendar
3. Adjust user IDs and environment-specific values
4. Activate the workflow

---

## Notes

- Credentials, tokens, and IDs are not included
- This workflow is shared for portfolio and educational purposes
- The structure reflects a real-world automation setup, not a demo workflow

