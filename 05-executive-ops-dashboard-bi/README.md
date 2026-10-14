# Executive Operations Dashboard & BI

Pulls revenue, pipeline, support and traffic data into one KPI report with threshold alerts.

## How it works
Hourly/weekly schedule, webhook or manual trigger → load config & thresholds → fetch Stripe, HubSpot, Jira and Google Analytics in parallel → merge & normalise (multi-currency) → calculate KPIs → alert engine (support backlog, pipeline vs target, cash flow, escalation rate) → AI commentary → store report history and audit log in Postgres → email summary / weekly HTML report → high-priority alerts to Slack and owners.

## Reliability
Thresholds are configurable per run; every run is written to report history and the audit log.

## Stack
n8n, Stripe, HubSpot, Jira, Google Analytics, PostgreSQL, Gemini, Slack, Gmail

## Hardening
Webhook requires header authentication; weekly report runs once (Monday 07:00 local) or on demand with `{"weekly": true}`.

## Import
Import `workflow.json` in n8n, then replace every `YOUR_*` placeholder and re-attach your own credentials. See [SETUP.md](../SETUP.md).

## Hire me
Need something like this? Free 15-minute workflow teardown: https://go.anchornovahq.com
