# AI Lead Qualification & Sales Automation

Lead intake webhook that validates, de-duplicates, scores, routes and follows up.

## How it works
Webhook → normalise & validate (required fields, email and phone checks, spam score) → duplicate lookup → AI qualification (structured) → HubSpot upsert → **rules-based routing** (industry team; Senior Consultant for high budget or hot leads) → notify via Slack, email and Teams → customer confirmation (+ WhatsApp when a phone number exists) → log for reporting. Scheduled flows: daily follow-ups and a daily dashboard snapshot.

## Reliability
Validation failures return a structured error response; duplicates are logged and alerted instead of re-processed.

## Stack
n8n, Gemini, HubSpot, Google Sheets, Slack, Teams, WhatsApp, Gmail

## Hardening
Failures route to the global error handler.

## Import
Import `workflow.json` in n8n, then replace every `YOUR_*` placeholder and re-attach your own credentials. See [SETUP.md](../SETUP.md).

## Hire me
Need something like this? Free 15-minute workflow teardown: https://go.anchornovahq.com
