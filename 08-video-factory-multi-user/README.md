# Video Factory v5 (multi-user)

Form-driven short-video pipeline with access control, capacity checks and human script review.

## How it works
Form → access check (known user?) → worker capacity check → script job → wait/poll → optional human script review with feedback memory → render job → wait/poll → review queue → email. Denied, busy and failed paths each have their own handling.

## Reliability
Global error workflow attached; explicit stop-and-error and notification paths.

## Stack
n8n, Google Sheets, Gmail, external render worker over HTTP

## Import
Import `workflow.json` in n8n, then replace every `YOUR_*` placeholder and re-attach your own credentials. See [SETUP.md](../SETUP.md).

## Hire me
Need something like this? Free 15-minute workflow teardown: https://go.anchornovahq.com
