---
description: Measure feature adoption across breadth, depth, and frequency — map the 4-stage adoption funnel, identify the Aha moment, diagnose the bottleneck stage, and produce an improvement roadmap
---

# Analyze Feature Adoption

You are invoking the **feature-adoption-analysis** skill from pm-data-analytics.

## Step 1: Load the feature adoption framework
Read and apply: `pm-data-analytics/skills/feature-adoption-analysis/SKILL.md`

## Step 2: Gather context
Ask the user:
- Which feature are we analyzing?
- What stage of maturity is the feature? (recently launched, 3-6 months old, established)
- What data is available? (usage events, DAU/MAU breakdown, NPS mentions, support tickets)
- Is there a specific concern? (low initial adoption, usage drop after first try, low frequency, or segment gap)

## Step 3: Run the analysis
Following the feature-adoption-analysis skill:
1. Measure adoption across 3 dimensions: Breadth (% of eligible users who ever used), Depth (frequency of use per active user), Frequency (sessions/week among users who used it)
2. Map the 4-stage adoption funnel: Aware → Activated → Adopted → Habitual
3. Identify Aha moment: the action that most predicts moving from Activated to Adopted
4. Diagnose bottleneck stage: where is the largest drop-off in the funnel?
5. Segment analysis: which user segments over/under-adopt vs baseline?
6. Check retirement signals: declining DAU among adopters, negative NPS mentions, support ticket spike

## Step 4: Deliver the output
Produce a **Feature Adoption Report** containing:
- Adoption dimensions table (breadth %, depth score, frequency/week)
- 4-stage funnel table with conversion rates between stages
- Aha moment hypothesis with supporting data
- Bottleneck stage diagnosis with root cause
- Segment analysis: top 2 over/under-performing segments
- Improvement roadmap: top 3 interventions with expected impact per stage
- SQL template for the adoption funnel
