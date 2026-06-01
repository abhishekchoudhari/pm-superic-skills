---
description: Adaptive PRD review — pick the style up front. Score-based diagnostic (CPO scorecard out of 100) or CEO stress-test (adversarial scope review with 4 postures).
argument-hint: "<paste PRD, file path, or Confluence link>"
---

# /review-prd -- Adaptive PRD Review

Rigorous, honest review of any PRD. Picks one of two review styles up front based on what you actually need.

## Invocation

```
/review-prd [paste PRD content]
/review-prd [upload a PRD markdown or doc file]
/review-prd This is a pre-engineering PRD for our new KYC flow [paste content]
/review-prd use the PRD we just wrote
```

## Pick a review style first

| Mode | What it does | Use when |
|---|---|---|
| **A — Score-based diagnostic** | Scores PRD out of 100 across 8 dimensions, hunts assumptions and biases, runs adversarial perspectives from Eng / QA / Compliance, finishes with growth coaching for the PM. | You want to know *how good* the PRD is and where to invest the next hour. |
| **B — CEO stress-test** | Challenges premises, surfaces 2-3 implementation alternatives, runs 11 review sections with one-question-at-a-time scope decisions. You pick a posture (expansion / selective / hold / reduction). | You want to *challenge ambition and scope* before going to engineering or leadership. |

Not sure? Pick A for a diagnostic. Pick B if you want pushback.

## Workflow

Apply the **review-prd** skill at `pm-execution/skills/review-prd/SKILL.md`. The skill runs:

1. **Step 0** — asks which mode you want (A or B)
2. **Mode A** runs domain classification → assumption/bias hunt → 8-dimension scoring → adversarial perspectives → coaching output with priority fixes
3. **Mode B** runs premise challenge → existing leverage check → dream state mapping → implementation alternatives → posture selection → 11 review sections with one question per finding → completion summary and failure modes registry

The PRD content can be passed as the argument, taken from the current conversation context, or fetched from a Confluence link.

## Notes

- A score above 85 in Mode A should feel rare and earned. Most PRDs land between 60 and 80.
- Mode B never makes silent scope changes. Every scope addition or cut is an explicit opt-in.
- If the PRD is very early stage, Mode A focuses on problem definition and why now, not missing ACs.
- Mode B adapted from [garrytan/gstack plan-ceo-review](https://github.com/garrytan/gstack/tree/main/plan-ceo-review).
