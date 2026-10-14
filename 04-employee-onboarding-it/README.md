# AI Employee Onboarding & IT Provisioning

End-to-end onboarding: intake, validation, plan, provisioning tasks, welcome, follow-ups and a daily dashboard.

## How it works
Header-authenticated intake webhook → verify & normalise → check existing employees → validate → build onboarding plan → create HR folder, document checklist, IT provisioning tasks, training assignments → notify HR, IT and manager → welcome email, Slack message, first-day calendar event → audit log. Separate authenticated status-update webhook, daily follow-up dispatcher and executive dashboard.

## Reliability
AI failures go to a **dead-letter log** and alert IT; validation failures notify HR and are logged.

## Stack
n8n, Gemini, Google Sheets/Drive/Calendar, Slack, Gmail

## Hardening
Follow-up due dates and report dates are timezone-safe (Luxon) and follow the workflow or instance timezone.

## Import
Import `workflow.json` in n8n, then replace every `YOUR_*` placeholder and re-attach your own credentials. See [SETUP.md](../SETUP.md).

## Hire me
Need something like this? Free 15-minute workflow teardown: https://go.anchornovahq.com
