---
description: Build a PRD grounded in research and evidence — gathers existing research or synthesizes VoC signals, maps the competitive landscape, synthesizes the problem space, then generates a fully populated PRD. Adapts to what the PM already has.
---

# Build Evidence PRD

You are running a 6-phase evidence-to-PRD pipeline. Each phase builds a shared **Product Brief** that carries context forward — no phase asks the PM to repeat information already gathered. The PRD is generated last, pre-populated with evidence from all prior phases.

Apply this workflow to: **$ARGUMENTS**

---

## Phase 1: Context intake

Ask the PM these 4 questions before loading any skill. Wait for answers before proceeding.

1. What are you building and for whom? (feature name + target user, 1-2 sentences)
2. What problem does this solve? What is the user's current workaround or pain?
3. Do you have existing research, VoC data, interview notes, or competitive intel? Answer: yes / no / some / it's a new product concept
4. What stage is this? Answer: new product from scratch / new feature on existing product / improvement to existing feature

Record all 4 answers as the **Product Brief** — this brief will grow through every phase.

---

## Phase 2: Research intake (adaptive — branch on Q3 answer)

Load and apply the appropriate skill based on the Q3 answer:

**If "yes" (has existing research):**
Read and apply: `pm-market-research/skills/user-research-synthesis/SKILL.md`
- Ask: "Where does your research live? Share the key findings, interview notes, NPS themes, or point me to the Drive folder."
- Extract: top JTBD themes, user segments, pain points, confidence per insight
- Add to Product Brief: `jtbd_themes[]`, `user_segments[]`, `pain_points[]`, `confidence_ratings[]`

**If "no" (no existing research):**
Read and apply: `pm-product-discovery/skills/voc-analysis/SKILL.md`
- Ask: "What signals do you have available? (Jira CS tickets, NPS verbatims, Slack channels, app store reviews, support emails)"
- Run VoC clustering on whatever signals the PM can provide
- Add to Product Brief: `jtbd_themes[]`, `user_segments[]`, `pain_points[]` (flag confidence as "signal-based, not interview-validated")

**If "some" (partial research):**
Run both paths above. Start with find-research for what exists, then VoC to fill gaps.
Read: `pm-market-research/skills/find-research/SKILL.md` then `pm-product-discovery/skills/voc-analysis/SKILL.md`

**If "new product concept":**
Read and apply: `pm-product-discovery/skills/identify-assumptions-new/SKILL.md`
- Surface hidden assumptions across Value / Usability / Viability / Feasibility / GTM / Strategy
- Add to Product Brief: `assumptions[]` with risk rating per assumption, `leap_of_faith_assumptions[]`
- Note: assumptions replace validated JTBD — the PRD will flag these explicitly

---

## Phase 3: Competitive context (optional — user-gated)

Ask: "Do you want competitive context included? It strengthens the problem framing and differentiation section — adds ~5 minutes. Answer: yes (deep), yes (quick scan), or skip."

**If "yes (deep)":**
Read and apply: `pm-market-research/skills/competitor-analysis/SKILL.md`
- Identify 3-5 relevant competitors, build feature matrix, pricing benchmark, differentiation gaps
- Add to Product Brief: `competitor_profiles[]`, `differentiation_gaps[]`, `positioning_opportunities[]`

**If "yes (quick scan)":**
Read and apply: `pm-go-to-market/skills/competitive-intelligence-brief/SKILL.md`
- Run quick-scan mode on 2-3 competitors
- Add to Product Brief: `competitive_signals[]`, `key_differentiators[]`

**If "skip":**
Add note to Product Brief: "Competitive context: not gathered — mark as to-be-completed in PRD"

---

## Phase 4: Problem space synthesis + PM gate

Read and apply both skills in sequence:

Step 4a — `pm-market-research/skills/user-research-synthesis/SKILL.md`
(If already run in Phase 2, use that output — do not repeat. Skip to 4b.)
Synthesize all gathered signals into: top 3 JTBD themes (ranked by frequency + pain intensity), key segment divergences, highest-confidence pain points.

Step 4b — `pm-product-discovery/skills/opportunity-solution-tree/SKILL.md`
Map the synthesized JTBD → opportunity nodes → solution candidates. Produce an opportunity hierarchy with 3-5 opportunity areas.

**GATE — present synthesis to PM and require confirmation before proceeding:**

Show:
```
PRODUCT BRIEF SYNTHESIS
─────────────────────
Feature: [from Phase 1]
Problem: [from Phase 1]
Primary user segment: [from Phase 2]
Top 3 JTBD themes:
  1. [theme] — confidence: [high/medium/low]
  2. [theme] — confidence: [high/medium/low]
  3. [theme] — confidence: [high/medium/low]
Key pain point: [highest confidence pain]
Top 3 opportunity areas: [from OST]
Competitive context: [summary or "not gathered"]
```

Ask: "Does this accurately capture what we're solving and for whom? Confirm to proceed to PRD, or correct anything that's wrong."

Do NOT proceed to Phase 5 until the PM confirms. If they correct something, update the Product Brief and re-show the synthesis.

Add to Product Brief: `validated_jtbd[]`, `opportunity_hierarchy[]`, `target_segment`, `primary_pain`, `solution_candidates[]`, `pm_confirmed: true`

---

## Phase 5: PRD generation

Read and apply: `pm-execution/skills/create-prd/SKILL.md`

Use the Product Brief to pre-populate these PRD sections — do NOT ask the PM for information already in the brief:

- **Problem statement** → from Product Brief `primary_pain` + `jtbd_themes[0]`
- **Target user / segments** → from Product Brief `user_segments[]`
- **Why now** → from Phase 1 stage + Phase 3 competitive signals (if gathered)
- **Success metrics** → derived from Product Brief `jtbd_themes[]` outcomes
- **Competitive context** → from Phase 3 (or flag as "to be completed")
- **Solution options** → from Product Brief `solution_candidates[]`
- **Assumptions** → from Product Brief `assumptions[]` (if new product path)

Ask the PM ONLY for information not in the brief:
- Scope decisions (what's in v1, what's explicitly out)
- Timeline / delivery constraints
- Engineering / infrastructure constraints
- Go/no-go criteria

If any PRD section cannot be filled from the brief and the PM doesn't provide it, mark it `[TO BE COMPLETED]` — do not block generation.

---

## Phase 6: Epic breakdown (optional — offered at end)

After PRD is generated, ask: "Ready to break this into epics and stories? I can convert the PRD into a sprint-ready backlog now."

If yes: Read and apply `pm-execution/skills/prd-to-epics/SKILL.md` using the generated PRD as input. Do not re-ask for context.

If no: Remind the PM: "Run `/pm-execution:plan-prd-to-epics` when ready. Run `/pm-os:run-feature-lifecycle` to continue the full delivery chain."

---

## Notes

- The Product Brief is the core of this workflow. Every skill reads it and writes to it. Never ask the PM to repeat information already in the brief.
- If the PM invokes this command with $ARGUMENTS (e.g., "build-evidence-prd feature: savings auto-invest for users who receive salary"), use the arguments to pre-fill Phase 1 answers and skip straight to confirming them rather than asking cold.
- Quality signal: a PRD where more than 3 sections are marked [TO BE COMPLETED] means insufficient context was gathered. Recommend the PM gather more signals before proceeding.
- This command connects to `/pm-os:run-feature-lifecycle` — after PRD + epics are complete, that command handles sprint planning, test scenarios, and release notes.
