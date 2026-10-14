# AI Customer Support & Knowledge Assistant

Website chat assistant that answers from a vector knowledge base and escalates when it is not sure.

## How it works
Chat trigger → normalise → validate & sanitise (empty, oversize, spam links, repeated chars, attachment types) → identify or create customer → AI intent analysis (structured output) → pgvector knowledge search → AI response (structured output with confidence) → **confidence ≥ 90: auto-resolve**, otherwise **escalate** (ticket + Slack + email) → update CRM → store conversation.

## Reliability
Invalid input path logs an event and sends a validation message; email/Slack notifications are non-blocking.

## Stack
Gemini chat + embeddings, PostgreSQL + PGVector, Slack, Gmail, window-buffer memory

## Hardening
Failures route to the global error handler.

## Import
Import `workflow.json` in n8n, then replace every `YOUR_*` placeholder and re-attach your own credentials. See [SETUP.md](../SETUP.md).

## Hire me
Need something like this? Free 15-minute workflow teardown: https://go.anchornovahq.com
