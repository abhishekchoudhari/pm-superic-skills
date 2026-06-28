---
description: Run a pre-launch readiness check — identify what could go wrong, align stakeholders, verify QA coverage, and produce a go/no-go recommendation before shipping.
---

# Run Launch Readiness

You are running a 3-part pre-launch gate. This command sequences risk identification, stakeholder alignment, and QA coverage into a single launch readiness report with a clear go/no-go recommendation.

Apply this workflow to: **$ARGUMENTS**

---

## Context intake

Ask before loading any skill:
1. What are you launching? (feature name, brief description)
2. What is the launch date / target ship date?
3. Who are the key stakeholders that need to be aligned?
4. What type of launch? (A/B test, gradual rollout, hard launch, beta, internal)
5. Any known risks or concerns going in?

Store answers as **Launch Context**.

---

## Phase 1: Pre-mortem — what could go wrong?

Read and apply: `pm-execution/skills/pre-mortem/SKILL.md`

Use Launch Context as input. Classify all identified risks as:
- **Tigers** — real, high-probability risks that need mitigation plans
- **Paper Tigers** — overblown concerns, low probability
- **Elephants** — unspoken worries the team hasn't voiced yet

For each Tiger: produce a mitigation plan and owner.
Output: risk table with classification, mitigation, and go/no-go impact.

---

## Phase 2: Stakeholder alignment

Read and apply: `pm-execution/skills/stakeholder-map/SKILL.md`

Use the stakeholder list from Context intake + any new stakeholders surfaced in Phase 1.
Map to Power × Interest grid. For launch specifically:
- Identify who must approve before launch (blockers)
- Identify who must be informed on launch day (comms list)
- Identify who could derail the launch post-ship (monitors)

Output: stakeholder grid, launch-day comms plan, approval checklist.

---

## Phase 3: QA coverage

Read and apply: `pm-execution/skills/test-scenarios/SKILL.md`

Focus on launch-critical paths only — not exhaustive QA, but the scenarios that would cause an immediate rollback if they failed.
Ask: "What are the 3 most critical user flows for this launch?"
Generate test scenarios for those flows plus: error recovery, integration failure, edge cases.

Output: launch-critical test plan with pass/fail criteria and rollback triggers.

---

## Launch readiness report

Produce a **Launch Readiness Report** containing:

```
LAUNCH READINESS: [Feature name]
Target date: [date]
─────────────────────────────────
RISK ASSESSMENT
  Launch-blocking Tigers: [count] — [list]
  Mitigated Tigers: [count]
  Elephants to monitor: [list]

STAKEHOLDER ALIGNMENT
  Approvals obtained: [list]
  Approvals outstanding: [list] ← launch blocker if any
  Launch-day comms: [list]

QA COVERAGE
  Critical paths covered: [n/n]
  Gaps: [list]

VERDICT: LAUNCH ✓ / DELAY ✗ / CONDITIONAL LAUNCH ⚠
Conditions (if conditional): [list what must be resolved]
```

If any launch-blocking Tigers remain unmitigated OR any approvals are outstanding OR critical path QA gaps exist → recommend DELAY with a specific action list to get to LAUNCH.
