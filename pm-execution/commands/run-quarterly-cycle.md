---
description: Run the end-to-end quarterly planning cycle — sets team OKRs, translates them into an outcome roadmap, and produces a stakeholder update. Sequences three commands that always run together at the start of each quarter.
---

# Run Quarterly Cycle

You are running the Q-start planning sequence. Three skills in order: OKRs first (what we're committing to), outcome roadmap second (how the backlog supports those OKRs), stakeholder update third (communicating the plan). The output of each step feeds directly into the next.

Apply this workflow to: **$ARGUMENTS**

---

## Context intake

Ask before loading any skill:
1. What team / product area is this for?
2. What are the company-level objectives this quarter? (the OKRs your team OKRs must align to)
3. What is the current quarter and year?
4. What did we commit to last quarter, and how did we do? (brief summary — 2-3 sentences)
5. Who is the primary stakeholder audience for the update? (direct manager / VP / board / cross-functional)

Store as **Q-Plan Context**.

---

## Step 1: OKR planning

Read and apply: `pm-execution/skills/brainstorm-okrs/SKILL.md`

Using Q-Plan Context:
- Generate 3 OKR set options aligned to company objectives
- For each option: 1 qualitative Objective + 3 measurable Key Results
- Include baseline, target, measurement method, and owner for each KR
- Flag which OKR set is recommended and why (most aligned to company objectives)

Ask PM: "Which OKR set do you want to go with, or should we blend elements?"
Record chosen OKRs as **Q-OKRs** in Q-Plan Context.

---

## Step 2: Outcome roadmap

Read and apply: `pm-execution/skills/outcome-roadmap/SKILL.md`

Using the chosen Q-OKRs:
- Take the PM's current feature/initiative list (ask: "What is currently on your roadmap or backlog for this quarter?")
- Reframe each initiative as an outcome statement: "Enable [segment] to [outcome] so that [business impact]"
- Map each outcome to the OKR it supports
- Identify any backlog items that don't map to any OKR (candidates for deferral)
- Flag gaps: OKRs with no roadmap initiative backing them

Output: Outcome roadmap table with OKR mapping and a "no OKR" list.

---

## Step 3: Stakeholder update

Read and apply: `pm-execution/skills/executive-stakeholder-update/SKILL.md`

Using Q-Plan Context (audience) + Q-OKRs + Outcome roadmap:
- Detect audience seniority level and adapt format:
  - Direct manager / VP: 1-page update with OKRs, top 3 initiatives, risks, asks
  - Board / CPO: 2-page QBR with last quarter recap, this quarter bets, P&L/metric context
- Pre-populate with: last quarter result (from Q-Plan Context), this quarter OKRs, roadmap highlights
- Ask PM for: top 2 risks this quarter, what help/unblocking you need from stakeholders

Output: Formatted stakeholder update ready to send.

---

## Completion

After Step 3: "Quarterly cycle complete. Your Q-plan pack:
- OKRs: [summary]
- Outcome roadmap: [attached]
- Stakeholder update: [attached]

For sprint planning within this quarter, run `/pm-execution:run-sprint` in plan mode."
