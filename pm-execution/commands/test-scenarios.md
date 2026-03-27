---
description: Generate a sign-off-ready test plan from PRD, Figma, and Jira. PM-first — validates the feature ships in the right state, the user experience holds under failure, and the business is protected. Produces manual test cases with a PM sign-off gate.
argument-hint: "<PRD link or text, Figma URL, Jira epic — provide all three for best results>"
---

# /test-scenarios -- Write Test Cases

Give me your PRD, Figma design, and Jira epic. I will extract what the feature promises, identify what the spec leaves undefined, and produce a test plan your team can execute — with a sign-off gate that tells you when you can ship.

## Invocation

```
/test-scenarios [PRD link] [Figma URL] [Jira epic]
/test-scenarios [paste PRD section] — Figma and Jira not yet available
/test-scenarios [Figma URL] The design is ready but PRD is still being written — generate what you can
```

## Workflow

### Step 0: Input gate

Before generating any test cases, check what inputs have been provided.

**Required inputs** (unless explicitly confirmed as unavailable):
- **PRD** — needed to map tests to acceptance criteria and confirm product requirements are covered
- **Figma** — needed for UI state assertions, error copy, loading behavior, and empty states
- **Jira epic / stories** — needed to understand scope, cross-team dependencies, and definition of done

If any input is missing, ask:
> "To generate a complete test plan I need [PRD / Figma / Jira]. Can you share it, or should I note it as unavailable and flag what coverage will be missing?"

If the user confirms an input is unavailable, proceed and flag the coverage gap explicitly in the test plan output. Do not silently generate an incomplete plan.

| Missing input | Coverage gap to flag |
|--------------|---------------------|
| No PRD | Test cases are inferred — no traceability to acceptance criteria. Product requirements coverage cannot be confirmed. |
| No Figma | UI-facing assertions are incomplete. Error copy, loading states, and empty states will be marked `[SPEC GAP]`. |
| No Jira | Scope boundaries are unconfirmed. Integration points and adjacent feature impact are unknown. |

### Step 1: Extract and map

From the provided inputs, extract:

**From PRD:**
- Every acceptance criterion — list them as AC-01, AC-02, etc.
- Every constraint, limit, or rule — these define boundary tests
- Every third-party dependency — each needs a failure test
- Every compliance or regulatory requirement — always P0

**From Figma:**
- Every distinct UI state per screen: empty, loading, success, error, warning, edge display
- Exact copy for error messages, confirmations, and key labels
- Navigation flows and conditional element visibility

**From Jira:**
- In-scope and out-of-scope boundaries
- Other systems and features this touches
- Definition of done and any flagged risks

### Step 2: Flag spec gaps

Before writing a single test case, list what the spec does not answer:
- What does the user see when this action fails?
- What happens if the partner system is unavailable?
- What happens at edge inputs — zero value, maximum value, unusual characters?
- How does the user recover if they make a mistake?
- Are there error states in Figma for every user action?

Mark each gap as `[SPEC GAP]` in the test plan. These are open risks that must be resolved or explicitly accepted before ship.

### Step 3: Generate the test plan

Apply the **test-scenarios** skill.

Generate test cases across all applicable categories. For each, confirm whether it applies or state why it does not:

| Category | What it validates |
|----------|--------------------|
| Happy path | The feature works as designed for the primary user journey and all entry points |
| Input and boundary checks | Every user input behaves correctly at blank, minimum, maximum, wrong format, and edge values |
| Error recovery | User can retry, resume, or recover from failures without losing progress or being stranded |
| Partner and integration failures | External system failures produce user-friendly outcomes, not blank screens or error codes |
| State and flow sequencing | Back navigation, duplicate actions, session return, and out-of-order steps all behave predictably |
| Financial and data accuracy | Amounts, fees, limits, and records match what the user is shown and what is charged |
| Access and permissions | Unauthenticated and unauthorized users are handled correctly with no data exposure |
| Cross-platform | Feature works across the product's supported platforms and screen sizes |

### Step 4: Output the test plan

```
## Test Plan: [Feature Name]

**PRD**: [link or "not provided — coverage is inferred, no AC traceability"]
**Figma**: [link or "not provided — UI assertions are incomplete"]
**Jira**: [link or "not provided — scope and dependencies unconfirmed"]
**Date**: [today]
**Feature owner**: [PM name if known]
**Test environment**: [staging / UAT / production — controlled access]

---

### Spec gaps
[What the spec does not answer. Each item is an untested risk.]
1. [Gap — which input should define this]

---

### Pre-test setup
[Exact test account states, feature flags, partner sandbox requirements, and data setup instructions]

---

### Test suite

| TC ID | Category | Scenario | Pre-conditions | Steps | Expected Result | Maps to | Priority | Notes |
|-------|----------|----------|----------------|-------|-----------------|---------|----------|-------|

---

### Coverage

| Acceptance criterion | Test cases |
|----------------------|------------|
| AC-01: [text] | TC-X-001, TC-X-002 |
| AC-02: [text] | TC-X-003 |

---

### Sign-off gate

Before approving ship:
1. All P0 cases executed and passed
2. All P1 cases executed — open failures have a named owner and documented workaround
3. [Feature-specific condition: financial accuracy verified / partner sign-off received / etc.]
4. All spec gaps resolved or explicitly accepted as known risk
5. [Who signs off and by when]

---

### What this plan cannot verify
[Risks requiring additional spec, environment, or partner access to test]
```

### Step 5: Offer optional add-ons

After delivering the test plan, offer:

- "Want me to **identify which existing flows this feature touches** — so your team knows what to regression-check?"
- "Want me to **flag which cases are automation candidates** for your engineering team?"
- "Want me to **write a 30-minute exploratory testing brief** to run alongside the scripted cases?"
- "Should I **write the pre-condition setup instructions** so anyone on the team can reproduce the test state?"

## Notes

- Three inputs, three times better output. PRD alone generates tests without UI coverage or scope clarity. All three together generates a complete, traceable plan.
- Every test case must map to an acceptance criterion. Unmapped cases are either redundant or untested scope.
- Expected results should be observable by anyone on the team — not just by an engineer with database access. Where backend verification is needed, note it as a separate engineering check.
- The sign-off gate is a ship decision. Make it specific enough that there is no ambiguity about whether the bar has been met.
- Spec gaps surfaced early are design conversations. Spec gaps surfaced during testing are incidents waiting to happen.
