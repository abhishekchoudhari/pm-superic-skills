---
description: Run a structured discovery sprint end-to-end — from research script design through 5 interviews to synthesis, opportunity mapping, and a stakeholder-ready recommendation. Converts ad-hoc user research into structured learning.
---

# Run Discovery Sprint

You are running a full discovery sprint. Most PM research is ad-hoc — a few conversations, some notes, a vague sense of what users want. This command structures it: design the script first, synthesize across all sessions, map to opportunities, prioritize assumptions, and produce a recommendation that is ready to share with stakeholders.

Apply this to: **$ARGUMENTS**

---

## Context intake

Ask before loading any skill:
1. What is the discovery question? (e.g., "Why are users not adopting the savings feature after onboarding?")
2. Who are the target research participants? (segment, number of sessions planned)
3. What do you already believe to be true? (your current hypothesis — be explicit so research can challenge it)
4. What decision will this research inform? (roadmap bet / PRD / pivot / go/no-go)
5. Are you starting fresh (no interviews done) or synthesizing existing sessions?

Store as **Discovery Context**.

---

## Phase 1: Research design (if starting fresh)

Read and apply: `pm-product-discovery/skills/interview-script/SKILL.md`

Using the discovery question and hypothesis from Discovery Context:
- Write a 45-minute interview script: warm-up (5 min), context-setting (10 min), core questions (25 min), wrap-up (5 min)
- Core questions must probe the job-to-be-done, not validate the hypothesis — write questions that would disprove the hypothesis if wrong
- Include probing follow-ups for each core question
- Include one "magic wand" question and one "last time you tried" question per theme

Output: interview script ready to run.

Ask: "How many sessions are you planning? Share notes after each one and I'll synthesize as you go, or share all at once when done."

---

## Phase 2: Session synthesis (per session or batch)

Read and apply: `pm-product-discovery/skills/summarize-interview/SKILL.md`

For each session (or batch of notes):
- Extract: top JTBD, key pain points, surprising moments, quotes worth preserving
- Flag: anything that challenges the hypothesis
- Track across sessions: patterns forming, contradictions emerging

After all sessions are in, produce a cross-session synthesis:
- Themes that appeared in 3+ sessions (strong signal)
- Themes that appeared in 1-2 sessions (weak signal — note, don't act)
- Direct contradictions between participants (segment-driven, not noise)
- The one thing you did not expect to hear

---

## Phase 3: Opportunity mapping

Read and apply: `pm-product-discovery/skills/opportunity-solution-tree/SKILL.md`

Using the synthesized themes:
- Map each strong-signal theme to an opportunity node
- Build opportunity hierarchy: which opportunities are sub-problems of a bigger opportunity?
- For each opportunity: size (how many participants, how much pain) and strategic fit

---

## Phase 4: Assumption prioritization

Read and apply: `pm-product-discovery/skills/prioritize-assumptions/SKILL.md`

Using the opportunity map:
- Surface the assumptions underlying each opportunity
- Classify: validated (research confirmed), invalidated (research challenged), still open
- Prioritize open assumptions by: risk if wrong × ease of validation
- Identify the next validation action for the top 2 open assumptions

---

## Discovery sprint output

Produce a **Discovery Sprint Report**:

```
DISCOVERY SPRINT: [Topic] | Sessions: [N] | Date: [date]
──────────────────────────────────────────────────────
DISCOVERY QUESTION
  [question]

HYPOTHESIS CHECK
  Original hypothesis: [hypothesis from Context]
  Verdict: [Confirmed / Challenged / Partially supported]
  Evidence: [what supported or challenged it]

KEY FINDINGS
  Strong signal (3+ sessions):
    1. [JTBD theme] — [N/N participants] — pain: [High/Med]
    2. [JTBD theme] — [N/N participants] — pain: [High/Med]
  Unexpected finding: [the thing you didn't expect]

OPPORTUNITY MAP
  Primary opportunity: [statement]
  Sub-opportunities: [list]
  Biggest gap vs current roadmap: [gap]

OPEN ASSUMPTIONS
  Must validate next: [assumption] — method: [how] — time: [N days]
  Watch: [assumption] — lower risk, validate in parallel

RECOMMENDATION
  [1-2 sentences: what to build, validate, or decide based on this discovery sprint]
  Next step: [specific action — e.g., "write PRD for opportunity 1 via /pm-os:build-evidence-prd" or "run 3 more sessions on segment X before committing"]
```

---

## Notes

- A discovery sprint is not a usability test. It explores problem space, not solution space. If participants start asking for features, redirect to their underlying job.
- Minimum 5 sessions for a B2C product, 3 for B2B (smaller addressable population). Flag if fewer sessions are provided.
- This command feeds directly into `/pm-os:build-evidence-prd` — the discovery sprint output is the research input for evidence-backed PRD generation.
