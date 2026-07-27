# Weekly Monday Health Check Searches

Use these searches in order. They are designed as a portable starting point for Splunk Cloud and Splunk Enterprise health-check conversations.

## 1. Weekly Index Concentration

File: `spl/01_weekly_index_concentration.spl`

Use when you need to identify the indexes driving the largest share of weekly ingest. Treat the output as an owner-conversation list, not a delete list.

Public screenshot version: `spl/01_weekly_index_concentration_sanitized_for_screenshots.spl`

## 2. Weekly Sourcetype Concentration

File: `spl/02_weekly_sourcetype_concentration.spl`

Use when you need to find noisy source classes that may be spread across teams or indexes. Validate whether the top sourcetypes have owners, active use cases, and appropriate logging levels.

## 3. Daily Ingest Trend And Spikes

File: `spl/03_daily_ingest_trend_spikes_14d.spl`

Use when you need to see day-over-day ingest movement across the last 14 days. Look for step changes, backfills, debug logging, onboarding changes, or routing shifts.

Optional license-usage comparison: `extras/license_usage_daily_ingest_trend_if_available.spl`

## 4. Scheduled-Search Compute Burn

File: `spl/04_scheduled_search_compute_burn.spl`

Use when you need to find recurring scheduled searches consuming platform runtime. Look for high total hours, broad time windows, inefficient SPL, or orphaned owners.

## 5. Ad-Hoc Search Compute Burn

File: `spl/05_ad_hoc_search_compute_burn.spl`

Use when you need to find users driving interactive search runtime. `_audit` availability can vary by role and environment; if no data appears, record that as an access/data-availability finding.

Approximation if `_audit` is unavailable: `extras/ad_hoc_compute_fallback_internal_search_activity.spl`

## 6. Pipeline Pressure And Queue Backlog

File: `spl/06_pipeline_pressure_queue_backlog.spl`

Use when you need to identify queue pressure that may indicate pipeline bottlenecks. Look for sustained high fullness, large peak sizes, or queues that repeatedly approach capacity.

## 7. LastChanceIndex Misroute Triage

File: `spl/07_lastchanceindex_misroute_triage.spl`

Use when you need to detect data redirected because target indexes are unconfigured, disabled, or deleted. Treat every result as data-quality risk, even when volume is small.

## Bonus: Week-Over-Week Index Delta

File: `extras/bonus_week_over_week_index_delta.spl`

Use this when a customer wants a “what changed recently by index?” view. It is helpful for storytelling, but the seven primary searches above are the main QR handout sequence.

## Public-Slide Hygiene

For .conf or other public slides, hide or sanitize:

- index names
- sourcetype names if they reveal tooling or architecture
- host and source names
- saved-search names
- user names
- raw GB/day numbers unless approved

Keep percentages, rankings, and the decision logic. The goal is to show the health-check method without exposing customer internals.
