# Global Error & Dead-Letter Handler (v2)

One error workflow for every other workflow.

## How it works
Error trigger → **normalise & classify** (handles execution errors and trigger failures; error class: auth / transient / data / unknown; severity: critical / high / medium) → **always write a dead-letter row** → **throttle** (identical errors alert once per 15 minutes, audit rows are never dropped) → **AI triage** (likely cause, first fix, retry-safe flag, business impact, confidence; optional and non-blocking) → Slack for every alert, email for critical and high.

## Reliability
- The audit row is written before anything else; if that write fails the alert says so.
- Notifications and AI triage use continue-on-error, so a failing alert channel never hides the original failure.
- Alert de-duplication prevents an error storm from flooding Slack or email.

## Stack
n8n Error Trigger, n8n Data Table, Gemini (structured output), Slack, Gmail

## Import
See [SETUP.md](../SETUP.md).

## Hire me
Free 15-minute workflow teardown: https://go.anchornovahq.com
