# Splunk Monday Health Check Pack

Community/session asset for the "Ingest Smarter, Prove More" talk.

This pack gives attendees a practical Monday health-check workflow:

- 5 core SPL searches from the session
- Optional advanced checks
- Splunk AI Assistant prompts
- A lightweight AI instruction file
- 90-day sprint worksheets
- Executive translation prompts

## What This Is

This is a field-ready starter kit for reviewing Splunk ingest, search compute, routing risk, and use-case alignment.

It is designed for Splunk practitioners who want to answer:

- What data is driving ingest?
- What changed recently?
- Which scheduled searches are burning compute?
- Is data being misrouted?
- How do I turn findings into owner actions and executive language?

## What This Is Not

This is not an official Splunk product, supported Splunk app, MCP server, certification, or professional services deliverable.

Validate every search in your own Splunk Cloud or Splunk Enterprise environment before using the output for operational, financial, security, or executive decisions.

## Quick Start

Start here:

- `START_HERE.md`

Run these five core searches in order:

1. `spl/01_weekly_index_concentration.spl`
2. `spl/02_week_over_week_index_change.spl`
3. `spl/03_weekly_sourcetype_concentration.spl`
4. `spl/04_scheduled_search_compute_burn.spl`
5. `spl/05_lastchanceindex_misroute_triage.spl`

Then use:

- `SEARCHES.md`
- `prompts/splunk_ai_assistant_monday_health_check.md`
- `worksheets/90_day_sprint_worksheet.md`
- `worksheets/owner_review_template.md`

Optional checks live in `optional/`. Use them only when your environment exposes the needed `_internal` or `_audit` data and the core checks point you toward deeper validation.

The SPL files return operational field values from the environment where they run. For conference slides or public screenshots, remove sensitive labels during slide preparation rather than changing the shared searches.

## Suggested Session Promise

"Scan the QR code and leave with a reusable Splunk health-check kit: core SPL searches, AI Assistant prompts, and a 90-day worksheet you can use Monday morning."

## QR Destination

Use one of these URLs for the session QR code:

- GitHub repository: `https://github.com/nsai003/splunk-health-check`
- GitHub Pages landing page, if enabled: `https://nsai003.github.io/splunk-health-check/`

For the slide, point the QR to the GitHub Pages URL if Pages is enabled. Otherwise, point it to the GitHub repository URL.

## Search Notes

- The core searches use `_internal` because it is the most portable starting point for this health-check workflow.
- `_audit` visibility can vary by role and environment. Treat optional `_audit` searches as deeper validation, not the required path.
- For ad-hoc search activity, use the optional `_audit` search when your role can access it. Search job log files are not consistently exposed in Splunk Cloud.
- `metrics.log` throughput is directional and operationally useful. If your environment exposes `license_usage.log`, compare against `optional/license_usage_daily_ingest_trend_if_available.spl` before using numbers in budget conversations.
- The searches are intended to prioritize owner conversations. They are not delete lists.

## Optional Use Case Discovery Step

After the health check identifies trusted sourcetypes and priority data owners, use Splunk Value Insights / Use Case Discovery, where available, to map data to Splunk Lantern capabilities and candidate use cases.

Reference: https://help.splunk.com/en/splunk-cloud-platform/administer/admin-manual/10.4.2604/monitor-your-splunk-cloud-platform-deployment/use-the-value-insights-dashboard/discover-new-use-cases-and-capabilities
