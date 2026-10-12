---
name: team-followups
description: Check a team's follow-up discipline in IRM365. Use when a manager asks who in their team is behind, who has overdue follow-ups, how their agents are doing, or for a team activity summary.
---

# Team follow-ups

1. Call `list_my_team`. If it returns an error because the person has no employee record, or only themselves, explain that a team view needs a reporting line in IRM365, and offer their own follow-ups instead.
2. Call `list_followups` with `window: "overdue"` and page through every result.
3. Call `list_activities` with `status: "completed"` for the recent work, up to 100 rows.

Group by team member, using `performed_by` and the lead owner:

| Team member | Overdue follow-ups | Oldest overdue | Completed recently |
|---|---|---|---|

Under the table:

- name the two or three people with the most overdue work, and their oldest items by lead reference;
- point out anyone with no completed activity in the period.

Keep it factual and neutral. This is for coaching, so describe the numbers and don't judge the person. If activity notes aren't shared, judge by counts and outcomes only, and don't claim what was said on a call.
