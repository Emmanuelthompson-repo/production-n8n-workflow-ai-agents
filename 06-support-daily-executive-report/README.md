# AI Support: Daily Executive Report

Every morning, summarises the previous day's support conversations for management.

## How it works
07:00 schedule → query yesterday's conversations → compute analytics in code (resolution rate, escalation rate, response time, sentiment, channels, top topics) → AI writes the executive narrative against a **strict output schema** → email report.

## Reliability
Database query retries 3x and still outputs on quiet days; AI and email steps retry.

## Stack
n8n, PostgreSQL, Gemini, Gmail

## Hardening
"Yesterday" is computed in the workflow timezone (no hardcoded zone); quiet days skip the AI step and send a plain notice.

## Import
Import `workflow.json` in n8n, then replace every `YOUR_*` placeholder and re-attach your own credentials. See [SETUP.md](../SETUP.md).

## Hire me
Need something like this? Free 15-minute workflow teardown: https://go.anchornovahq.com
