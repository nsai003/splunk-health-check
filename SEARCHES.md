# Monday Health Check Searches

Use these five core searches in order. They match the health-check result slides from the session and are designed as a portable starting point for Splunk Cloud and Splunk Enterprise conversations.

## 1. Weekly Index Concentration

File: `spl/01_weekly_index_concentration.spl`

Use when you need to identify the indexes driving the largest share of weekly ingest. Treat the output as an owner-conversation list, not a delete list.

## 2. Week-over-Week Index Change

File: `spl/02_week_over_week_index_change.spl`

Use when you need to see what changed recently by index. It compares the last seven days with the previous seven days and helps move the conversation from "ingest is growing" to "this specific data stream changed."

## 3. Weekly Sourcetype Concentration

File: `spl/03_weekly_sourcetype_concentration.spl`

Use when you need to find noisy source classes that may be spread across teams or indexes. Validate whether the top sourcetypes have owners, active use cases, and appropriate logging levels.

## 4. Scheduled-Search Compute Burn

File: `spl/04_scheduled_search_compute_burn.spl`

Use when you need to find recurring scheduled searches consuming platform runtime. Look for high total hours, broad time windows, inefficient SPL, or orphaned owners.

## 5. LastChanceIndex Misroute Triage

File: `spl/05_lastchanceindex_misroute_triage.spl`

Use when you need to detect data redirected because target indexes are unconfigured, disabled, or deleted. Treat every result as data-quality risk, even when volume is small.

This search intentionally requires the actual `Received event for unconfigured/disabled/deleted index` or `Redirected event for unconfigured/disabled/deleted index` message from `splunkd.log`. It does not search for `LastChanceIndex` by itself because that can match normal search activity logs, such as `remote_searches.log`, that merely mention the term.

If the target index appears as `unspecified`, Splunk logged the destination index as empty or null. Use the source host, original source, and sourcetype columns to trace the input, HEC token, forwarder, or index-time routing rule that needs correction.

## Optional Checks

Optional checks:

- `optional/daily_ingest_trend_spikes_14d.spl`
- `optional/ad_hoc_search_compute_burn.spl`
- `optional/pipeline_pressure_queue_backlog.spl`
- `optional/license_usage_daily_ingest_trend_if_available.spl`

Use optional checks only when the core checks point you toward deeper validation and the environment exposes the required data. For example, `_audit` visibility varies by role and environment, so treat ad-hoc search runtime as optional validation rather than part of the required flow.

For ad-hoc search activity, use `optional/ad_hoc_search_compute_burn.spl` when `_audit` is available. Search job logs such as `dispatch/*/search.log` are not consistently exposed in Splunk Cloud, so they are not included in the public optional set.

## Public-Slide Hygiene

The repository searches intentionally return real operational field values from the environment where they run. For .conf or other public slides, remove or obscure sensitive labels during slide preparation:

- index names
- sourcetype names if they reveal tooling or architecture
- host and source names
- saved-search names
- user names
- raw GB/day numbers unless approved

Keep percentages, rankings, and the decision logic. The goal is to show the health-check method without exposing customer internals.
