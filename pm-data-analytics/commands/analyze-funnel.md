---
description: Analyze a product or conversion funnel — identify drop-off points, segment by user attribute, measure time-in-funnel, and produce a scored fix prioritization table
---

# Analyze Funnel

You are invoking the **funnel-analysis** skill from pm-data-analytics.

## Step 1: Load the funnel analysis framework
Read and apply: `pm-data-analytics/skills/funnel-analysis/SKILL.md`

## Step 2: Gather context
Ask the user:
- What funnel are we analyzing? (onboarding, activation, purchase, upgrade, checkout, etc.)
- What data do you have? (event counts per step, conversion rates, or raw events)
- What's the primary concern? (overall conversion rate, a specific step drop-off, time-to-convert, or segment comparison)

## Step 3: Run the analysis
Following the funnel-analysis skill:
1. Identify funnel type (linear, branching, cyclical) and map all steps
2. Compute absolute drop-off (users lost) and relative drop-off (% who left) per step
3. Identify the highest-leverage drop-off step
4. Segment analysis: split by at least one user attribute (platform, cohort, source, plan tier)
5. Time-in-funnel: flag steps where median time exceeds 2x the p25
6. Skip pattern check: identify users who bypassed steps and whether they convert better/worse

## Step 4: Deliver the output
Produce a **Funnel Analysis Report** containing:
- Funnel table with step names, users entering, users completing, absolute drop-off, relative drop-off %
- Top 3 drop-off findings with evidence
- Segmentation findings: which segments over/under-perform vs baseline
- Time-in-funnel insights
- Scored fix prioritization table (impact × effort × confidence) with top 3 recommended fixes
- SQL template for the identified funnel pattern
