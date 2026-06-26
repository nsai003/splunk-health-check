# Splunk Monday Health Check Pack

Community/session asset for the "Ingest Smarter, Prove More" talk.

This pack gives attendees a practical Monday health-check workflow:

- 5 portable SPL searches
- Splunk AI Assistant prompts
- A lightweight AI skill file
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

Run these five searches first:

1. `spl/01_weekly_index_concentration.spl`
2. `spl/02_week_over_week_index_delta.spl`
3. `spl/03_weekly_sourcetype_concentration.spl`
4. `spl/04_scheduled_search_compute_burn.spl`
5. `spl/05_lastchanceindex_misroute_triage.spl`

Then use:

- `prompts/splunk_ai_assistant_monday_health_check.md`
- `worksheets/90_day_sprint_worksheet.md`
- `worksheets/owner_review_template.md`

## Suggested Session Promise

"Scan the QR code and leave with a reusable Splunk health-check skill: five SPL searches, AI Assistant prompts, and a 90-day worksheet you can use Monday morning."

## Optional Use Case Discovery Step

After the health check identifies trusted sourcetypes and priority data owners, use Splunk Value Insights / Use Case Discovery, where available, to map data to Splunk Lantern capabilities and candidate use cases.

Reference: https://help.splunk.com/en/splunk-cloud-platform/administer/admin-manual/10.4.2604/monitor-your-splunk-cloud-platform-deployment/use-the-value-insights-dashboard/discover-new-use-cases-and-capabilities

