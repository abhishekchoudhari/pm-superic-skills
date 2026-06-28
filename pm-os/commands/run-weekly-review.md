---
description: Run the Monday weekly review ritual — surfaces what moved, what didn't, and what to focus on this week. Takes last week's metrics, shipped items, and decisions and produces a structured weekly brief with clear focus areas.
---

# Run Weekly Review

You are running the PM's weekly review ritual. Input is whatever the PM has from last week — metrics, shipped items, decisions made, blockers hit. Output is a structured weekly brief that tells the PM exactly where to put their energy this week.

Apply this to: **$ARGUMENTS**

---

## Context intake

Ask before any analysis:
1. What product or product area is this for?
2. What are this week's dates? (Mon DD MMM to Fri DD MMM)
3. What shipped last week? (features, fixes, experiments — even partial)
4. What are the key metrics from last week? (share whatever you have: MAU, DAU, conversion, revenue, NPS, retention)
5. What decisions were made last week?
6. What was blocked or slipped?
7. What are your top committed OKRs this quarter? (paste or summarize)

---

## Analysis

### Section 1: What moved?

For each metric provided:
- Direction: up / down / flat vs prior week
- Size of movement: absolute and % change
- Signal vs noise check: is this within normal weekly variance or a real signal?
- Flag any metric that moved more than 10% — warrants investigation

### Section 2: What shipped and what did we learn?

For each shipped item:
- Is there an early signal? (any usage data, error rates, support tickets)
- What assumption was this validating?
- What should we watch in the next 7 days?

For each slipped item:
- Root cause: scope / dependency / resource / discovery?
- Action needed or accept the slip?

### Section 3: OKR pulse

For each OKR provided, rate the week:
- On track / at risk / off track
- If at risk or off track: what is the specific action needed this week to recover?

### Section 4: This week's focus

Based on the analysis above, produce:

**Top 3 focus areas for this week** — each with:
- The specific action (not a theme, an action)
- Why it is the top priority (metric signal, OKR risk, or opportunity)
- Owner and expected output by Friday

**One metric to watch** — the single leading indicator most likely to move this week based on what shipped

**One risk to monitor** — the thing most likely to become a fire if not watched

---

## Weekly brief output

```
WEEKLY REVIEW: [Product] | Week of [dates]
──────────────────────────────────────────
WHAT MOVED
  [Metric]: [value] [+/-N% WoW] — [signal / noise call]
  [Metric]: [value] [+/-N% WoW] — [signal / noise call]
  ⚠ Flag: [any >10% movement and why]

SHIPPED
  [Item]: [early signal or "too early to read"] — watch: [specific thing]
  [Item]: [early signal] — watch: [specific thing]

SLIPPED
  [Item]: root cause: [type] — action: [accept / unblock by doing X]

OKR PULSE
  [KR 1]: [on track / at risk] — [one-line status]
  [KR 2]: [on track / at risk] — [one-line status]

THIS WEEK
  1. [Action] — why: [reason] — owner: [person] — output: [deliverable by Fri]
  2. [Action] — why: [reason] — owner: [person] — output: [deliverable by Fri]
  3. [Action] — why: [reason] — owner: [person] — output: [deliverable by Fri]

  Watch: [one metric]
  Risk: [one risk]
```

---

## Notes

- If metrics are not shared, skip Section 1 and note: "No metrics provided — share last week's numbers to get a full review."
- If OKRs are not shared, skip the OKR pulse and offer: "Share your Q OKRs and I'll track them every week."
- This command is designed to run weekly. Run `/pm-os:run-weekly-review` every Monday with the prior week's data. Over time it will surface trends that individual weekly reviews miss.
