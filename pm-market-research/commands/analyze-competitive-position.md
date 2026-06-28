---
description: Build a full competitive picture — deep competitive analysis, user sentiment on competitors, and a CI brief for ongoing monitoring. Produces a competitive position report with differentiation opportunities and a standing monitoring config.
---

# Analyze Competitive Position

You are building a comprehensive competitive picture across three lenses: structural analysis (what competitors do and how they're positioned), perception analysis (what users say about them), and ongoing intelligence (what signals to track going forward). These three together give both the static competitive map and the dynamic monitoring system.

Apply this workflow to: **$ARGUMENTS**

---

## Context intake

Ask before loading any skill:
1. What product or company are we doing competitive analysis for?
2. Who are the known competitors? (list up to 5, or "unknown — please identify")
3. What is the primary competitive concern? (new entrant threat / losing deals / pricing pressure / feature gaps / positioning confusion)
4. What decision does this analysis need to support? (roadmap prioritization / pricing decision / GTM strategy / investor narrative)
5. What markets / geographies are in scope?

Store as **Competitive Brief**.

---

## Step 1: Deep competitive analysis

Read and apply: `pm-market-research/skills/competitor-analysis/SKILL.md`

Using the Competitive Brief:
- Identify and tier 3-5 competitors (Tier 1: direct, Tier 2: adjacent, Tier 3: emerging)
- Build feature matrix across key dimensions
- Map pricing and positioning for each
- Identify differentiation opportunities: what they're weak at that you can win on
- Produce 3 specific roadmap or strategy recommendations based on competitive gaps

Output: Competitive analysis with tiered landscape, feature matrix, positioning 2x2, differentiation opportunities.

---

## Step 2: Sentiment analysis — what do users say?

Read and apply: `pm-market-research/skills/sentiment-analysis/SKILL.md`

For the top 2-3 competitors from Step 1:
- Analyze user-generated feedback: app store reviews, G2/Capterra, Reddit threads, Twitter/X mentions
- Identify top positive themes (what users love about competitors — these are table stakes)
- Identify top pain themes (what users hate — these are your differentiation opportunities)
- Segment sentiment by user type if patterns differ

This reverses the typical analysis: instead of "what do we do better", ask "what do users wish competitors did better."

Output: Per-competitor sentiment profile with love themes, pain themes, and key quotes.

---

## Step 3: Ongoing competitive intelligence setup

Read and apply: `pm-go-to-market/skills/competitive-intelligence-brief/SKILL.md`

Using competitors identified in Step 1:
- Set up standing CI config (which competitors to track, which signal categories: product / pricing / GTM / hiring / funding / sentiment)
- Run a first pass of the CI brief in quick-scan format
- Identify the 3 signals that would most change your strategy if they shifted

Output: CI brief + standing monitoring config for future runs. Future runs with `/pm-go-to-market:generate-ci-brief` will use this config.

---

## Competitive position report

```
COMPETITIVE POSITION: [Product] | Date: [date]
──────────────────────────────────────────────
LANDSCAPE
  Tier 1 (direct): [competitors]
  Tier 2 (adjacent): [competitors]
  Biggest threat: [competitor] — why: [reason]

FEATURE GAPS
  We're behind on: [features]
  Table stakes we're missing: [features]
  Our advantages: [features]

DIFFERENTIATION OPPORTUNITIES
  1. [gap in competitive landscape we can own]
  2. [gap in competitive landscape we can own]
  3. [gap in competitive landscape we can own]

USER SENTIMENT (top competitor)
  Users love: [themes]
  Users hate: [themes] ← your opportunity
  Key quote: "[quote]"

STRATEGIC RECOMMENDATIONS
  1. [action based on competitive gap]
  2. [action based on sentiment pain]
  3. [monitoring trigger: if [competitor] does X, we should respond with Y]

CI MONITORING
  Tracking: [N] competitors | Signals: [categories]
  Next refresh: run /pm-go-to-market:generate-ci-brief
```
