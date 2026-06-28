---
description: Run the complete feature delivery lifecycle — from PRD through epics, sprint planning, test scenarios, and release notes. Carries context forward at every step so no information is repeated.
---

# Run Feature Lifecycle

You are running the end-to-end feature delivery workflow. This command sequences 5 skills into a continuous pipeline — the output of each step becomes the input for the next. No context is lost between steps.

Apply this workflow to: **$ARGUMENTS**

---

## Step 0: Entry point check

Ask the PM: "Where are you starting from?"
- A: I have an idea but no PRD yet → start at Step 1
- B: I have a PRD already → start at Step 2 (ask them to paste or describe it)
- C: I have PRD + epics → start at Step 3
- D: I have a shipped feature and need release notes → jump to Step 5

This prevents re-doing work already done.

---

## Step 1: PRD (if starting from idea)

Read and apply: `pm-execution/skills/create-prd/SKILL.md`

Tip for the PM: "For a research-grounded PRD, run `/pm-os:build-evidence-prd` instead — it gathers research and competitive context before writing."

Ask: what is the feature, who is it for, what problem does it solve?
Generate PRD. Store as **Feature Context** for downstream steps.

Gate: "PRD complete. Proceed to epic breakdown?"

---

## Step 2: Epic breakdown

Read and apply: `pm-execution/skills/prd-to-epics/SKILL.md`

Use the PRD from Step 1 (or the PM's existing PRD) as input.
Produce: epic table, nested story hierarchy, out-of-scope list, open questions.

Ask: "How many engineers are on this? Rough sprint capacity?" — needed for Step 3.

Gate: "Epics complete. Proceed to sprint planning?"

---

## Step 3: Sprint planning

Read and apply: `pm-execution/skills/sprint-plan/SKILL.md`

Use the epic/story list from Step 2. Use the capacity input from Step 2.
Produce: sprint goal, capacity table, prioritized story list for Sprint 1, dependency map, risk register.

Gate: "Sprint plan complete. Generate test scenarios for the sprint scope?"

---

## Step 4: Test scenarios

Read and apply: `pm-execution/skills/test-scenarios/SKILL.md`

Use the sprint scope from Step 3 (not the full epic list — only stories in Sprint 1).
Produce: test plan covering happy path, boundary conditions, error recovery, integration failures, financial edge cases (if applicable), cross-platform.

Gate: "Test plan complete. Feature shipped? Ready to write release notes?"

---

## Step 5: Release notes

Read and apply: `pm-execution/skills/release-notes/SKILL.md`

Use the completed stories from the sprint. Ask: "What actually shipped? Any scope changes from the original sprint plan?"
Produce: user-facing release notes organized by category (new features, improvements, fixes).

---

## Completion

After Step 5: "Feature lifecycle complete. For the next feature, run `/pm-os:build-evidence-prd` to start with research-grounded discovery, or `/pm-os:run-feature-lifecycle` again."

For retrospective on this sprint: run `/pm-execution:run-sprint` in retro mode.
