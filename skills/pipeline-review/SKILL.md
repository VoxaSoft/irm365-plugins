---
name: pipeline-review
description: Review the IRM365 sales pipeline. Use when the user asks about their pipeline, forecast, deals or opportunities closing soon, stalled deals, or expected revenue.
---

# Pipeline review

1. Call `search_opportunities` without filters and page through all open results (up to 200). If the user named a period, also pass `closing_before`.
2. For any opportunity that looks stalled, call `get_opportunity` for its detail. Stalled means the close date has passed, or there's no next follow-up.

Report:

- **Totals by stage**: count and expected value in AED per stage, and a probability-weighted total (expected value × win probability).
- **Closing soon**: opportunities due in the next 30 days, soonest first, with owner and probability.
- **At risk**: overdue close dates and opportunities without a next follow-up, each with one suggested next step.

Show amounts as AED with thousands separators. Say that the figures cover only the opportunities this person can see in IRM365, not necessarily the whole company. Don't round probabilities into certainty, and don't forecast beyond what the data shows.
