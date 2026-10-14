# Intelligent Invoice Processing (Accounts Payable)

Invoices arrive by webhook, Gmail inbox or Drive folder; they are OCR'd, extracted, de-duplicated, approved and archived.

## How it works
Three intake paths → file validation → Google Vision OCR → AI field extraction (structured, with confidence score) → normalisation → **required-fields check** → **duplicate check (invoice number + vendor)** → save → AI summary → Slack approval request → approve / reject / human-review branches → notify submitter → archive original.

## Reliability
Duplicates, validation errors and human-review cases each write their own log row; execution success is logged for audit.

## Stack
n8n, Google Vision OCR, Gemini, PostgreSQL, Slack, Gmail, Google Drive

## Hardening
Intake webhook requires header authentication; failures route to the global error handler.

## Import
Import `workflow.json` in n8n, then replace every `YOUR_*` placeholder and re-attach your own credentials. See [SETUP.md](../SETUP.md).

## Hire me
Need something like this? Free 15-minute workflow teardown: https://go.anchornovahq.com
