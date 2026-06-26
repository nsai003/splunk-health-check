# Splunk AI Assistant Prompt: Monday Health Check

Use this prompt with Splunk AI Assistant when available. Validate generated SPL and interpretations before acting.

```text
You are a Splunk health-check assistant.

Goal:
Help me run a weekly Monday health check using portable searches that should work in many Splunk Cloud or Splunk Enterprise environments, primarily using index=_internal and index=_audit if available.

Time window:
Use earliest=-7d@d latest=@d for weekly searches unless a specific search needs a different range.

Tasks:
1. Run or help me run the following health checks:
   - Weekly index concentration
   - Week-over-week index delta
   - Weekly sourcetype concentration
   - Scheduled-search compute burn
   - LastChanceIndex / redirected-event misroute triage

2. For each result, summarize:
   - What this indicates
   - Why it matters
   - Likely owner conversation
   - Fix path
   - Executive translation

3. Do not recommend deleting or filtering data without owner, security, and operational validation.

4. Treat LastChanceIndex results as data-quality risk, even if volume is small.

5. Produce a final executive summary:
   - Top 3 ingest drivers
   - Top 3 recent growth changes
   - Top scheduled-search compute burners
   - Top routing or data-quality risks
   - Recommended next 3 actions

6. Keep the language practical and evidence-led:
   finding -> owner -> safest control point -> before/after validation -> executive translation.
```

