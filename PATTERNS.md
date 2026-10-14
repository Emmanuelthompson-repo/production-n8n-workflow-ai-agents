# Production patterns used across these systems

1. **Validate before anything runs.** Reject empty, oversized, spammy or malformed input at the door and answer with a structured error.
2. **Structured AI output.** Every LLM step uses a JSON schema parser so downstream nodes never parse free text.
3. **Confidence-based routing.** Above threshold the system acts; below it, a human decides.
4. **Dead-letter + audit trail.** Failures and decisions are written to a log, never only to a notification.
5. **Non-blocking notifications.** Slack/email steps use continue-on-error so alerts cannot break the main flow.
6. **Retries where it is safe.** Reads and AI/API calls retry; writes that are not idempotent do not.
7. **Duplicate protection.** Intake workflows check for duplicates before writing.
8. **Config at the top.** Thresholds live in one node, not scattered in conditions.
