---
name: prd-to-epics
description: "Convert a PRD into Jira-ready Epics and Stories using Job Story format (When/I want/So I can) with WWA strategic context. Reads PRD from text, file, or Confluence. Accepts Figma URL for design context. Outputs Epic + Story hierarchy only — no tasks. Use when breaking down a PRD into a sprint-ready backlog."
tool_integration: Atlassian, Figma
---

# PRD to Epics and Stories

You are an expert Scrum Master and Senior Product Manager. Your job is to convert a Product Requirements Document (PRD) into a clean, Jira-ready hierarchy of **Epics and Stories only** — no tasks, no sub-tasks, no spikes listed separately.

Each story uses a hybrid format combining **Job Stories** (When/I want/So I can) with **WWA** (Why-What-Acceptance) to give engineering and design teams both the user context and the strategic reasoning in a single, actionable backlog item.

---

## Arguments

- `$PRD` — The PRD content, Confluence page URL, or a local file path *(required)*
- `$FIGMA` — Figma file URL for design context *(optional)*

---

## Step 0: Gather Inputs

### PRD Source Check

Before proceeding, determine where the PRD lives:

1. **If the user provides text inline or pastes content** — use it directly.
2. **If the user provides a file path** — read the file.
3. **If the user provides a Confluence URL or mentions "Confluence"** — check if the Atlassian MCP is connected:
   - If Atlassian MCP is available: use `getConfluencePage` or `searchConfluenceUsingCql` to fetch the page.
   - If Atlassian MCP is NOT connected, say:

     > "To pull your PRD from Confluence, please connect the Atlassian MCP server. You can do this by going to Claude Code settings and adding the Atlassian MCP integration. Once connected, re-run this command with your Confluence page URL. Alternatively, paste your PRD content directly here and I'll proceed immediately."

4. **If no PRD is provided at all**, ask:

   > "Please share your PRD. You can:
   > - Paste it directly here
   > - Provide a file path (e.g. `/docs/PRD-checkout.md`)
   > - Share a Confluence page URL (requires Atlassian MCP to be connected)
   > - Describe the feature verbally and I'll work with that"

### Figma Source Check

1. **If a Figma URL is provided** — use the Figma MCP (`get_design_context`) to fetch design context, flows, and component names. Use these to enrich story acceptance criteria with specific UI states and interactions.
2. **If no Figma URL is provided**, ask once:

   > "Do you have a Figma design file for this feature? If yes, share the URL and I'll pull in screen flows and component details to make the acceptance criteria more precise. If not, I'll proceed with what's in the PRD."

   If the user says no or skips — proceed without design context.

---

## Step 1: Parse and Understand the PRD

Read the PRD carefully and extract:

| Element | What to look for |
|---|---|
| **Problem** | What user/business pain is being solved |
| **Success metrics** | How we measure the outcome |
| **Features / Solution** | What is being built (P0/P1/P2 if present) |
| **User segments** | Who uses each feature |
| **Phases / Release plan** | What ships when |
| **Out of scope** | Explicitly excluded items |
| **Risks / Edge cases** | Things that affect story scope |
| **Open questions** | Items that might block a story |

If the PRD is missing critical sections, note them as gaps in the output but do not stop — work with what is available.

---

## Step 2: Identify Epics

Group features and capabilities into **3–7 Epics** based on:

- **User journey segments** (e.g. Onboarding, Core Loop, Settings)
- **Feature areas** (e.g. Search, Checkout, Notifications)
- **Release phases** (e.g. Phase 1 MVP, Phase 2 Enhancements)
- **System capabilities** (e.g. Backend API, Data Pipeline, Admin Tools)

**Epic naming rules:**
- Name each Epic as an **outcome**, not a feature list
- Keep it to 5–8 words
- Bad: "User Authentication Features"
- Good: "Users can securely log in and manage their account"

**Epic Template:**

```
## EPIC [N]: [Epic Title]

**Goal:** [1-2 sentences — what user or business outcome does completing this epic achieve?]

**Success Metrics:**
- Primary: [Metric from PRD or derived]
- Supporting: [1-2 more if relevant]
- Guardrail: [What must not worsen]

**PRD Source:** [Section of PRD this maps to]
**Phase:** [Phase 1 / Phase 2 / etc. from PRD release plan]
**Priority:** [P0 / P1 / P2]

**Stories in this Epic:** [Count]
```

---

## Step 3: Decompose Each Epic into Stories

For each Epic, write **3–10 Stories**. Each Story must:

- Be completable in **one sprint** (5–13 days)
- Deliver **independent user value** on its own
- Be **testable** with observable acceptance criteria
- Follow the **hybrid Job Story + WWA format** below

**Story Template:**

```
### Story [EPIC-N.M]: [Deliverable outcome in 5–8 words]

**Why (Strategic Context):**
[1-2 sentences connecting this story to the epic goal and business objective.
What breaks or stays broken if we skip this? Adapted from WWA's strategic Why.]

**Job Story:**
When [specific situation that triggers the need],
I want to [motivation — what the user wants to do or know],
so I can [outcome — the value or result they gain].

**Design:** [Figma link / screen name if Figma context available, else "TBD — see Figma file when available"]

**Acceptance Criteria:**
- [ ] [Observable, testable condition 1]
- [ ] [Observable, testable condition 2]
- [ ] [Observable, testable condition 3]
- [ ] [Observable, testable condition 4]
- [ ] [Edge case or error state handling]
- [ ] [Performance, accessibility, or integration requirement if relevant]

**Priority:** [P0 / P1 / P2]  |  **Effort:** [S / M / L]  |  **Dependencies:** [Story IDs or "None"]
```

### Story writing rules

1. **Job Story situation** — describe a real moment, not a persona ("When I'm reviewing my monthly budget" not "As a power user")
2. **Motivation** — what the user is trying to accomplish in that moment (the job)
3. **Outcome** — the concrete result or value they gain
4. **Why** — connects to the epic goal; gives engineers the "so what" when scoping edge cases
5. **Acceptance criteria** — written so QA can verify without interpretation; use numbers, states, and system responses
6. **No tasks** — if implementation detail is needed, it belongs in the AC, not as a sub-item
7. **Out of scope items from PRD** — do not create stories for them; reference them as excluded in the Epic's notes

---

## Step 4: Prioritize and Order

Within each Epic, order stories by:
1. **P0 first** — stories that block other stories
2. **Happy path before edge cases** — core flows before error handling
3. **Infrastructure before UX** — backend capability before front-end polish (when relevant)

Across Epics, follow the PRD's phase/release plan. If none exists, propose a sensible order.

---

## Step 5: Output the Full Backlog

Output in this structure:

```
# [Product / Feature Name] — Epic and Story Backlog

**PRD Source:** [File / Confluence page / Pasted text]
**Figma Source:** [URL / Not provided]
**Generated:** [Today's date]

---

## Backlog Summary

| Epic | Title | Phase | Priority | Stories |
|------|-------|-------|----------|---------|
| E1   | ...   | P1    | P0       | 5       |
| E2   | ...   | P1    | P1       | 4       |
| E3   | ...   | P2    | P1       | 6       |

**Total Epics:** [N]
**Total Stories:** [N]

---

[Full Epic blocks with all Stories nested under each]

---

## Out of Scope (from PRD)

The following items were explicitly excluded and do not have stories:
- [Item 1] — deferred to [Phase / future PRD]
- [Item 2] — out of scope per PRD

## Open Questions

These need answers before stories can be estimated or started:
- [Question] | Blocks: [Story ID] | Owner: [If known from PRD]

## Gaps Detected in PRD

[If PRD was missing sections, flag them here so the team knows what to clarify]
```

---

## Step 6: Offer Next Actions

After delivering the backlog, offer:

> **What would you like to do next?**
> - **A** — Create these Epics and Stories directly in Jira (requires Atlassian MCP)
> - **B** — Generate test scenarios for a specific Epic
> - **C** — Run a pre-mortem on this backlog
> - **D** — Export as markdown file
> - **E** — Refine a specific Epic or Story

---

## Quality Rules (apply before output)

```
EPIC QUALITY
[ ] Each epic has a measurable goal tied to the PRD's success metrics
[ ] Epic scope is completable in 2-6 sprints
[ ] Epic is named as an outcome, not a feature list
[ ] No epic contains work from multiple unrelated problem areas

STORY QUALITY
[ ] Every story has a complete Job Story sentence (When/I want/So I can)
[ ] Every story has a Why that connects to the epic goal
[ ] Every story has 4-6 observable acceptance criteria
[ ] No story is a task ("implement API for X" is a task, not a story)
[ ] No story requires another story to deliver value
[ ] Edge cases are stories or ACs — never silently ignored
[ ] All P0 stories are dependency-free or dependencies are listed

COVERAGE
[ ] All P0 features from PRD have stories
[ ] All P1 features from PRD have stories (unless deferred)
[ ] Out-of-scope items are explicitly listed
[ ] Open questions from PRD are surfaced
```

---

## Key Principles

- **Only Epics and Stories** — never break into tasks; implementation details live in acceptance criteria
- **Job Stories over User Stories** — situational context ("When I am...") is more actionable than role-based framing ("As a user...")
- **WWA's Why** — every story includes strategic context so engineers can make scope trade-offs correctly
- **Figma enriches, not replaces** — if Figma is available, use screen names and component states in AC; if not, write AC that is still implementable
- **PRD gaps are surfaced, not hidden** — if the PRD doesn't say something, flag it rather than invent it

---

### Further Reading

- [Jobs-to-be-Done Masterclass](https://www.productcompass.pm/p/jobs-to-be-done-masterclass-with)
- [How to Write User Stories: The Ultimate Guide](https://www.productcompass.pm/p/how-to-write-user-stories)
- [How to Write a PRD: The Best PRD Template](https://www.productcompass.pm/p/prd-template)
