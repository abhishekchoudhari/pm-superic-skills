---
description: Decompose MAU or MRR into new, retained, resurrected, and churned buckets — compute quick ratio and NRR, identify which growth lever to prioritize
---

# Analyze Growth Accounting

You are invoking the **growth-accounting** skill from pm-data-analytics.

## Step 1: Load the growth accounting framework
Read and apply: `pm-data-analytics/skills/growth-accounting/SKILL.md`

## Step 2: Gather context
Ask the user:
- Are we analyzing MAU growth or MRR/revenue growth? (or both)
- What time period? (monthly, weekly — last 3 months, 6 months, or 12 months)
- Do you have data by bucket (new/retained/resurrected/churned) or raw user/revenue data?
- What's the current quick ratio or growth rate, if known?

## Step 3: Run the analysis
Following the growth-accounting skill:
1. Build the growth accounting table: New + Retained + Resurrected − Churned = Net change
2. Compute quick ratio: (New + Resurrected + Expansion) / (Churned + Contraction)
3. For revenue: compute NRR = (Starting MRR + Expansion − Contraction − Churn) / Starting MRR
4. Diagnose the scenario: identify which bucket is the primary drag or driver
5. Map to the correct intervention: acquisition, activation, retention, resurrection, or monetization

## Step 4: Deliver the output
Produce a **Growth Accounting Report** containing:
- Growth accounting table with all 4 buckets and net change
- Quick ratio with benchmark comparison (B2C top quartile: 3-5, mature: 1.5-2.5)
- Revenue version with NRR if applicable
- Scenario diagnosis: which bucket is driving / dragging growth
- Single highest-leverage lever recommendation with expected impact
- 10-minute leadership summary template (4 bullet points: state, trend, root cause, action)
