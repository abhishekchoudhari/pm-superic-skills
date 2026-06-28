---
description: Build the strategic foundation for a new product — surfaces hidden assumptions, builds a lean canvas, defines the value proposition, and identifies the beachhead segment. Produces the 0-to-1 product foundation pack.
---

# Plan New Product

You are building the strategic foundation for a new product concept. Four skills in sequence: assumptions first (what are we betting on?), lean canvas second (does the business model hold?), value proposition third (why will users choose this?), beachhead segment fourth (who do we win first?). These four together form the minimum viable strategic foundation before any PRD is written.

Apply this workflow to: **$ARGUMENTS**

---

## Context intake

Ask before loading any skill:
1. What is the product concept? (1-2 sentences — what it does and for whom)
2. What problem does it solve? What is the user's current workaround?
3. What is the business context? (startup / new product line within existing company / expansion into new market)
4. What do you already know? (existing user research, competitive context, internal data — brief summary)
5. What is the biggest risk you're most worried about?

Store as **Product Concept Brief**.

---

## Step 1: Surface hidden assumptions

Read and apply: `pm-product-discovery/skills/identify-assumptions-new/SKILL.md`

Using the Product Concept Brief, surface hidden assumptions across 8 categories:
Value / Usability / Viability / Feasibility / GTM / Strategy / Regulatory / Team

Classify each assumption:
- **Leap of faith** — if wrong, the whole product fails
- **Important** — if wrong, major rework needed
- **Nice to validate** — low risk if wrong

Prioritize the top 3 leap-of-faith assumptions. These are what must be validated before significant investment.

Add to Product Concept Brief: `assumptions[]`, `leap_of_faith_assumptions[]`

Gate: show assumptions to PM. Ask: "Do these capture your real bets? Any assumptions missing?"

---

## Step 2: Lean canvas

Read and apply: `pm-product-strategy/skills/lean-canvas/SKILL.md`

Using Product Concept Brief + assumptions from Step 1:
- Fill all 9 Lean Canvas sections: Problem, Customer Segments, Unique Value Proposition, Solution, Channels, Revenue Streams, Cost Structure, Key Metrics, Unfair Advantage
- Flag which sections are assumption-based (from Step 1) vs evidence-based
- Identify the riskiest canvas section (usually UVP or Revenue Streams for new products)

Output: Complete Lean Canvas with assumption flags.

---

## Step 3: Value proposition

Read and apply: `pm-product-strategy/skills/value-proposition/SKILL.md`

Using the customer segment and problem from the Lean Canvas:
- Build a 6-part value proposition: Who / Why / What Before / How / What After / Alternatives
- Generate 2-3 segment-specific VPs if multiple segments identified
- Produce positioning statement for the primary segment
- Identify the single most defensible differentiation from alternatives

Output: VP per segment + positioning statement.

---

## Step 4: Beachhead segment

Read and apply: `pm-go-to-market/skills/beachhead-segment/SKILL.md`

Using the segments from Steps 2-3:
- Score each segment on 5 dimensions: burning pain / WTP / winnable share / referral potential / strategic fit
- Recommend the beachhead segment (highest combined score)
- Define: 90-day acquisition target, primary acquisition channel, viral coefficient estimate, pricing guidance
- Explain why this segment is the right first win (and what it unlocks next)

Output: Beachhead scorecard + 90-day acquisition plan for the recommended segment.

---

## New product foundation pack

Produce a **New Product Foundation Pack**:

```
NEW PRODUCT: [Product name] | Stage: [0-to-1]
─────────────────────────────────────────────
LEAP OF FAITH ASSUMPTIONS (validate before building)
  1. [assumption] — how to validate: [method]
  2. [assumption] — how to validate: [method]
  3. [assumption] — how to validate: [method]

LEAN CANVAS SUMMARY
  Problem: [top problem]
  UVP: [one-sentence unique value proposition]
  Riskiest section: [section] — why: [reason]

VALUE PROPOSITION
  Primary segment: [segment]
  Why they switch: [from X to Y because Z]
  Positioning: [statement]

BEACHHEAD
  Win first: [segment]
  90-day target: [N users]
  Channel: [primary acquisition channel]
  Unlock: [what winning this segment unlocks next]

NEXT STEP
  Before writing a PRD: validate assumption [1] via [method] — estimated [N days]
  Then run: /pm-os:build-evidence-prd
```
