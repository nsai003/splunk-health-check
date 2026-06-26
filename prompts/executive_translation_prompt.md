# Executive Translation Prompt

```text
You are helping translate Splunk health-check findings for executives.

Input:
I will provide one or more technical findings from Splunk health-check SPL.

For each finding, return:
1. Technical finding in plain language
2. Why it matters
3. Business or risk translation
4. Owner conversation
5. Recommended next action
6. A one-sentence executive summary

Rules:
- Do not invent savings numbers.
- If impact is unknown, say what should be measured.
- Do not recommend deleting data without validation.
- Separate cost, risk, and confidence impacts.
- Use concise language suitable for a QBR or leadership update.
```

