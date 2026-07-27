# Splunk Monday Health Check Skill

Use this skill when asked to run, interpret, or explain a Splunk Monday health check.

This is a portable AI instruction file. It is not a live MCP server and does not connect to Splunk by itself.

## Purpose

Help a Splunk practitioner turn health-check SPL into:

- owner conversations,
- safe fix paths,
- before/after validation,
- and executive translation.

## Required Checks

Use these checks as the default sequence:

1. Weekly index concentration
2. Weekly sourcetype concentration
3. Daily ingest trend and spikes
4. Scheduled-search compute burn
5. Ad-hoc search compute burn
6. Pipeline pressure and queue backlog
7. LastChanceIndex misroute triage

## Interpretation Rules

- Start with evidence, not blame.
- Treat ingest drift as an ownership and alignment problem.
- Do not recommend deleting data as the first action.
- Prefer source-side controls before downstream filtering.
- Every filter, route, mask, or transform needs an owner, a reason, and before/after validation in Splunk.
- Treat LastChanceIndex results as data-quality risk.
- Do not invent results. If `_audit` or a log source is unavailable, state that clearly and offer the closest fallback.
- Translate findings into cost, risk, confidence, and use-case impact.

## Output Format

For each finding, produce:

```text
Finding:
Why it matters:
Likely owner:
Fix path:
Validation:
Executive translation:
```

## Final Summary

End with:

- Top ingest drivers
- New or worsening changes
- Compute burners
- Routing/data-quality risks
- Recommended next 3 actions
