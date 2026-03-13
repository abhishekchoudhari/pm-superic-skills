---
description: Convert a PRD into Jira-ready Epics and Stories — reads from text, file, or Confluence; optional Figma URL for design context. Uses Job Story format with strategic WHY. Epic + Story level only, no tasks.
argument-hint: "<prd-text | confluence-url | file-path> [figma-url]"
---

# /prd-to-epics — PRD to Epic and Story Backlog

Convert any PRD into a sprint-ready hierarchy of **Epics and Stories**. Pulls design context from Figma when available. Creates items directly in Jira when Atlassian MCP is connected.

## Invocation

```
/pm-execution:prd-to-epics                                           # prompts for PRD source
/pm-execution:prd-to-epics [paste PRD text here]                     # inline PRD content
/pm-execution:prd-to-epics /path/to/PRD-checkout.md                 # local file
/pm-execution:prd-to-epics https://your-org.atlassian.net/wiki/...  # Confluence page
/pm-execution:prd-to-epics [PRD] https://figma.com/design/...       # PRD + Figma design
```

## What it does

Apply the **prd-to-epics** skill:

### Step 0 — Gather Inputs

**PRD source:**
- If text is pasted → use directly
- If a file path → read the file
- If a Confluence URL → fetch via Atlassian MCP (`getConfluencePage`)
- If Atlassian MCP is not connected → prompt the user to connect it, or paste the PRD

**Figma source (optional):**
- If a Figma URL is provided → call `get_design_context` to extract screen flows, component names, and interaction states to enrich acceptance criteria
- If not provided → ask once; proceed without it if skipped

### Step 1 — Parse the PRD

Extract: problem statement, success metrics, features (with P0/P1/P2), user segments, phases/release plan, out-of-scope items, risks, open questions.

### Step 2 — Identify Epics (3–7)

Group features by user journey, feature area, or release phase. Name each Epic as a **user/business outcome**, not a feature label.

### Step 3 — Write Stories under each Epic

Each story uses a **hybrid Job Story + WWA format**:

```
Why (Strategic Context): [connects to epic goal and business objective]

Job Story:
When [specific situation],
I want to [motivation],
so I can [outcome].

Acceptance Criteria:
- [ ] [Observable, testable condition]
- [ ] [Edge case or error state]
- [ ] [Performance or accessibility requirement]

Priority: P0/P1/P2 | Effort: S/M/L | Dependencies: [Story IDs]
```

**Rules:**
- Stories only — no tasks, no sub-tasks
- Every story is independent and sprint-sized
- Acceptance criteria are QA-verifiable without interpretation
- Figma screen names and states appear in AC when design context is available

### Step 4 — Output Backlog

Delivers a full markdown backlog:

```
# [Feature Name] — Epic and Story Backlog

| Epic | Title | Phase | Priority | Stories |
|------|-------|-------|----------|---------|
...

[Epics with nested Stories]

Out of Scope
Open Questions
PRD Gaps Detected
```

### Step 5 — Offer Next Actions

- Create in Jira via Atlassian MCP
- Generate test scenarios for an Epic
- Run a pre-mortem on the backlog
- Export as markdown

## Example

```
/pm-execution:prd-to-epics https://acme.atlassian.net/wiki/spaces/PROD/pages/12345 https://figma.com/design/abc123/Checkout-v2
```

→ Fetches PRD from Confluence, pulls Figma design context, outputs 5 Epics and 23 Stories with Figma screen references in acceptance criteria. Offers to create directly in Jira.

## Notes

- Epic + Story only — never tasks; implementation details belong in acceptance criteria
- The Job Story format ("When I am...") captures real user situations, not abstract roles
- The strategic Why in each story lets engineers scope edge cases correctly without checking the PRD
- Out-of-scope PRD items are listed explicitly — they do not get stories
- PRD gaps are surfaced, never silently filled with assumptions
