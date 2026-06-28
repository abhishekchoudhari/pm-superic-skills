---
description: Build a unit economics model — compute CAC, LTV, LTV/CAC ratio, and payback period; benchmark against industry; identify top improvement levers
---

# Analyze Unit Economics

You are invoking the **unit-economics** skill from pm-fintech-strategy (general version — works for any digital product).

## Step 1: Load the unit economics framework
The core framework covers: CAC decomposition, LTV modeling, LTV/CAC ratio, CAC payback period, contribution margin, and cohort-based LTV curves.

Apply this framework regardless of the specific skill file path — use your knowledge of unit economics best practices for digital products (SaaS, marketplace, consumer subscription, fintech).

## Step 2: Gather context
Ask the user:
- What type of product? (SaaS, marketplace, consumer app, fintech, e-commerce)
- What revenue model? (subscription, transaction fee, freemium conversion, advertising)
- Do you have existing data on CAC, LTV, or churn? Or are we building from assumptions?
- What's the primary concern? (LTV/CAC below 3x, long payback period, high churn, low ARPU)

## Step 3: Build the model
1. CAC: total acquisition spend / new customers acquired in the period. Decompose by channel.
2. LTV: ARPU × gross margin % / monthly churn rate (or cohort-based if data available)
3. LTV/CAC ratio: target >3x for consumer, >5x for SaaS
4. CAC payback: CAC / (ARPU × gross margin %). Target: <12 months consumer, <18 months SaaS
5. Contribution margin per cohort at 12/24/36 months
6. Competitor benchmark: compare LTV/CAC and payback to 2-3 comparable companies
7. Lever sensitivity: show impact on LTV/CAC of ±20% change in each lever (ARPU, churn, CAC, gross margin)

## Step 4: Deliver the output
Produce a **Unit Economics Model** containing:
- CAC breakdown by channel with blended CAC
- LTV model with assumptions table
- LTV/CAC ratio with benchmark comparison
- CAC payback timeline
- Contribution margin at 12/24/36 month cohort snapshots
- Lever sensitivity table: top 3 levers ranked by LTV/CAC impact
- 90-day sprint plan if LTV/CAC is below target (3x consumer, 5x SaaS)
