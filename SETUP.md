# Setup

These exports are sanitised and inactive. Before activating:

1. Replace every `YOUR_*` placeholder (sheet, folder, table and calendar IDs) and re-attach your own credentials.
2. Replace `you@example.com` with real recipients (the alert email is set at the top of the error handler's `Normalize & Classify` node).
3. Import `07-global-error-handler` first, then set it as the **Error Workflow** of every other workflow (Settings > Error Workflow).
4. Create one **Header Auth** credential for webhook intake (header `X-Webhook-Token`) and select it on the invoice and dashboard webhooks. Callers must send the header.
5. Timezone: set `GENERIC_TIMEZONE` on your n8n instance, or override per workflow in Settings. Nothing is hardcoded.
6. Create the audit Data Table with columns: event_type, source_workflow, conversation_id, channel, severity, message, payload_json.
7. Test the handler with a throwaway workflow containing a Code node that throws.
