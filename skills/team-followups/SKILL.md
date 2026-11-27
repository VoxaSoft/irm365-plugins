---
name: team-followups
description: Check a team's follow-up discipline in IRM365. Use when a manager asks about their team's overdue follow-ups, what needs chasing, or for a team activity summary.
---

# Team follow-ups

## Decide the period first

Use the period the user named. Otherwise use the **last 7 days**, ending now, in the user's timezone (from `get_workspace_context`). State the period in the answer.

## Fetch

1. Call `list_my_team`. If it returns an error because the person has no employee record, or the team is only themselves, explain that a team view needs a reporting line in IRM365, and offer their own follow-ups instead.
2. Call `list_followups` with `window: "overdue"` and page through every result.
3. Call `list_activities` with `status: "completed"`. Results come newest first. Keep paging while `has_more` is true **and** the last row's `completed_at` is still inside the period, up to 400 rows. Count only rows whose `completed_at` falls inside the period.

## Report

Report the **team as a whole**. Never score, rate or rank people, never compare one person with another, and never single out who is ahead or behind.

- **Team totals:** overdue follow-ups, the oldest overdue date, and activities completed in the period, for the team together.
- **Oldest overdue items:** up to ten overdue follow-ups, oldest first, each by lead reference with what is due and since when. Each item may carry its owner, so it can be handed on, but don't add up items per person.
- **Next steps:** for an item, one concrete step on that piece of work, such as calling back or rescheduling the viewing.

If the manager asks about one named person, answer about that person's own items in the same factual way, without comparing them with anyone else.

**Evidence rule:** say the team completed nothing in the period only if you read every completed activity back to the start of the period. If you stopped at the row limit first, say the counts are incomplete and how far back they reach.

Keep it factual and neutral: describe the work, not the people. If activity notes aren't shared, judge by counts and outcomes only, and don't claim what was said on a call.
