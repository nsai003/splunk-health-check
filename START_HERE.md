# Start Here

Use this repo as the take-home kit for the "Ingest Smarter, Prove More" session.

## The Monday Motion

Run five core checks, then pick one owner conversation.

| Step | Search | What it tells you |
| --- | --- | --- |
| 1 | `spl/01_weekly_index_concentration.spl` | Which indexes drive the most weekly ingest |
| 2 | `spl/02_week_over_week_index_change.spl` | Which indexes changed most compared with the previous week |
| 3 | `spl/03_weekly_sourcetype_concentration.spl` | What kind of data is creating the volume |
| 4 | `spl/04_scheduled_search_compute_burn.spl` | Which recurring searches consume the most runtime |
| 5 | `spl/05_lastchanceindex_misroute_triage.spl` | Whether data is missing its intended destination |

## How To Use The Results

Do not treat the output as a delete list. Treat it as an owner conversation.

Ask:

- Is this expected?
- Who owns it?
- Does it support an active use case?
- What is the safest change?
- How will we measure before and after?

## What To Do By Friday

Pick one finding. Confirm the owner. Decide the action. Define the before-and-after measurement.

The action might be a logging-level change, routing fix, retention decision, or ownership cleanup.

## AI Prompt

Use `prompts/splunk_ai_assistant_monday_health_check.md` after you run the searches. Paste the results into Splunk AI Assistant, ChatGPT, or Claude and ask for a summary of findings, likely owners, safe fix paths, and executive translation.

## Optional Checks

Use the files in `optional/` only when you need deeper validation. They are not required for the main session workflow.
