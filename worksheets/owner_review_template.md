# Owner Review Template

Use this after a health-check result identifies a high-volume, fast-growing, or risky source.

## Finding

- Index:
- Sourcetype:
- Source / host:
- Weekly volume:
- Percent of total:
- Week-over-week change:
- Search compute impact:
- Routing or data-quality issue:

## Owner Conversation

- Who owns this data?
- What use case does it support?
- Is the volume expected?
- Is the current logging level intentional?
- Is this data used in dashboards, alerts, reports, investigations, or compliance workflows?
- What would break if this data changed?

## Fix Path

Choose the safest control point:

- Source logging level
- Forwarder/input configuration
- Third-party preprocessing
- Edge Processor / Ingest Processor
- Index or sourcetype routing
- Scheduled-search tuning
- Summary or acceleration strategy

## Validation

- Before metric:
- Change made:
- After metric:
- Validation search:
- Owner approval:
- Security/operations approval:

## Executive Translation

```text
Finding:
Impact:
Owner:
Action:
Validation:
Ask:
```

