---
description: Run a comprehensive product health diagnosis — chains growth accounting, cohort analysis, funnel analysis, and feature adoption into a single weekly health brief. The GM's Monday morning read.
---

# Diagnose Product Health

You are running a 4-lens product health diagnostic. Each lens adds a layer to a growing **Health Brief** — growth trend first, then retention depth, then funnel state, then feature usage. The output is a single health report a PM can present to leadership.

Apply this workflow to: **$ARGUMENTS**

---

## Context intake

Ask before loading any skill:
1. What product or product area are we diagnosing?
2. What time period? (last 30 days / last quarter / specific dates)
3. What is the primary concern? (growth slowing / retention drop / funnel gap / feature adoption / all of the above)
4. What data is available? (MAU/DAU, cohort data, funnel events, feature usage — share what you have)

---

## Lens 1: Growth accounting — are we growing the right way?

Read and apply: `pm-data-analytics/skills/growth-accounting/SKILL.md`

Decompose MAU (or MRR) into: New + Retained + Resurrected − Churned
Compute quick ratio. Diagnose growth scenario.
Add to Health Brief: growth_table, quick_ratio, growth_scenario, primary_lever

---

## Lens 2: Retention — are users sticking?

Read and apply: `pm-data-analytics/skills/cohort-analysis/SKILL.md`

Use the product type and time period from Context intake.
Plot D30/D90/D180 retention curves. Compare to benchmarks (B2C top quartile: D30 60%, D90 35%).
Identify curve shape (healthy vs. smile vs. sloped vs. cliff). Segment by top attribute.
Add to Health Brief: d30_rate, d90_rate, curve_shape, benchmark_gap, top_segment_finding

---

## Lens 3: Funnel — where is the biggest drop-off?

Read and apply: `pm-data-analytics/skills/funnel-analysis/SKILL.md`

Ask: "What is the primary conversion funnel? (onboarding / activation / upgrade / checkout)" — use the most relevant funnel for this product.
Identify the single highest-leverage drop-off step. Segment to find which user attribute creates the biggest gap.
Add to Health Brief: funnel_type, biggest_dropoff_step, dropoff_rate, top_segment_gap, fix_recommendation

---

## Lens 4: Feature adoption — what are users actually using?

Read and apply: `pm-data-analytics/skills/feature-adoption-analysis/SKILL.md`

Ask: "What are the 2-3 core features of this product?" Focus analysis on those.
Measure breadth (% ever used) and depth (frequency among users who used it).
Identify if any feature is showing retirement signals.
Add to Health Brief: breadth_per_feature, depth_per_feature, aha_moment_hypothesis, retirement_risk

---

## Health brief output

Produce a **Product Health Report**:

```
PRODUCT HEALTH: [Product] | Period: [dates]
─────────────────────────────────────────
GROWTH
  Quick ratio: [N] (benchmark: top quartile B2C 3-5)
  Growth scenario: [Acquisition-led / Retention-led / Churning / Stagnant]
  Primary lever to pull: [lever]

RETENTION
  D30: [%] vs benchmark [%]   D90: [%] vs benchmark [%]
  Curve shape: [Healthy / Smile / Sloped / Cliff]
  Best segment: [segment] at [%]  |  Worst: [segment] at [%]

FUNNEL
  Biggest drop-off: [step] — [N]% relative drop
  Top segment gap: [segment] vs baseline [+/-pp]
  Top fix: [recommendation]

FEATURE ADOPTION
  Most adopted: [feature] — [breadth%] users, [depth] sessions/week
  At-risk feature: [feature] — [signal]
  Aha moment hypothesis: [action] within [timeframe]

PRIORITY ACTIONS
  1. [highest leverage — owner — timeline]
  2. [second]
  3. [third]
```
