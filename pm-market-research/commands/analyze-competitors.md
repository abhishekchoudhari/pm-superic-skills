---
description: Principal-PM-grade competitor research. Three depth tiers (Quick Scan / Standard / Forensic). Cost-aware, source-tiered, no assumptions, PRD-embeddable. Asks before spending tokens.
argument-hint: "<competitor name or category>"
---

# /analyze-competitors -- Competitor Research

Principal-PM-grade competitor research that finds insights basic searches miss. Cost-disciplined: asks which depth tier you want and shows the research plan before spending tokens. Output is PRD-embeddable — every claim cited, every unknown labelled, no assumptions.

## Invocation

```
/analyze-competitors Oolka                              # deep profile, you pick tier
/analyze-competitors AI-powered credit apps in India    # landscape, you pick tier
/analyze-competitors Jupiter vs Cred and Paytm          # landscape with set defined
```

## Workflow

### Step 1: Pick the mode

Ask (or infer from the argument and confirm):
- **Landscape sweep** — 5 direct + 2-3 indirect competitors, comparison-led. Use when mapping a category or finding white space.
- **Deep profile** — one competitor, full stack: product, rails, partnerships, revenue model, ARPU math, SWOT, PM readout. Use when prepping a PRD, benchmark, or investor brief.

Single company name → default to deep profile. Category or versus-list → default to landscape. Confirm before proceeding.

### Step 2: Pick the depth tier — show the cost menu

Always show the user this menu and get an explicit pick. Recommend a tier based on what they've said.

```
Three depth tiers — pick based on the decision this will inform:

T1 — Quick Scan      ~5 min   ~20k tokens   800-1200 words   2-3 sources
   Low-impact decisions, validation, "is this even a real competitor"

T2 — Standard        ~15 min  ~60k tokens   2000-3000 words  6-8 sources
   Mid-impact PRDs, roadmap input, quarterly competitive refresh

T3 — Forensic        ~35 min  ~150k tokens  4000-6000 words  15+ sources
   High-impact PRDs, year-defining bets, M&A, investor briefs
   Includes non-obvious sources: Glassdoor, ad libraries, archive.org,
   hiring graphs, regulatory filings, ToS dissection.
   Includes self-critique pass, stress test, founder thesis reconstruction.

Modular: pick a base tier and upgrade specific sections (e.g. T1 overall
but T3 on revenue model and rails) — pay deep cost only where it matters.
```

Wait for the user's pick.

### Step 3: Clarifying questions (before any search)

Ask these. Suggest defaults based on what the user has already said. Never start searching until you have answers.

1. **Competitor name + primary URL** (required)
2. **Why this competitor?** (benchmark / threat / inspiration / M&A target)
3. **What decision will this inform?** (sharpens tier recommendation)
4. **Geography focus** (default: user's home market)
5. **Lens priority** — rank these from most to least important: product, personas, rails, partnerships, revenue model, unit economics, GTM, regulatory, hiring, recent moves
6. **What do you already know?** (avoids re-researching)
7. **Hard exclusions** — sections to skip to save tokens
8. **Output destination** — local markdown / Confluence / paste-in-chat / Google Doc

### Step 4: Research plan (before any search)

Output a numbered research plan grouped by source category (T1 primary / T2 reputable secondary / T3-only non-obvious sources). Show estimated tokens and time. Wait for approval. The user may prune, add, or reorder.

### Step 5: Execute and write

Apply the **competitor-analysis** skill at the chosen tier. The skill enforces:
- Mandatory citation tier and confidence on every claim
- Confirmed / Estimated / Unknown labels — never assume
- Dated metrics, currency hygiene
- 19-section structure with depth varied by tier
- Self-critique pass (T2 and T3)
- Insight quality gate — at least 3 non-obvious insights required (T2 and T3)

### Step 6: Save and offer next steps

Save to default path: `~/competitor-research/<competitor>-<tier>-<YYYY-MM-DD>.md`.

Offer concretely:
1. "Want me to **stack-rank this profile against 2-3 peers** in landscape mode?"
2. "Want me to **draft the PRD** using the PRD-ready blocks?" → `/pm-execution:write-prd`
3. "Want me to **upgrade specific sections** (e.g. T1 → T3 on revenue model)?"

## Hard rules

- **No assumptions, ever.** Unknown is a respected and valid answer.
- **No token burn without a plan.** Always show the research plan and get approval first.
- **Web search is mandatory.** Tier sets the minimum search count.
- **Citations on every non-obvious claim.** With source tier (T1-T4) and confidence (Strong / Moderate / Weak).
- **Output is PRD-embeddable** at T2 and T3 — pre-formatted paste-in blocks included.

## Notes

- Refresh quarterly. ARR, partnerships, pricing move fast.
- For Indian fintech, always check Bharat Connect / BBPS rail status, RBI licence type, and lender partner roster — usually the load-bearing dependencies.
- If web search returns thin results, say so. Do not paper over gaps with inference.
- The skill works best when the user is clear about what decision the research informs — that's what lets the skill align cost to impact.
