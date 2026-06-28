---
description: Turn raw incoming signals (CS tickets, NPS verbatims, app store reviews, Slack requests, sales feedback) into prioritized roadmap recommendations. Chains signal analysis, VoC clustering, and opportunity mapping into a weekly or monthly triage output.
---

# Triage to Roadmap

You are running the signal-to-roadmap pipeline. Raw feedback comes in from many directions — CS tickets, NPS comments, app store reviews, sales requests, user interviews. This command clusters it, finds the real signal underneath the noise, maps it to opportunity areas, and produces concrete roadmap recommendations.

Apply this to: **$ARGUMENTS**

---

## Context intake

Ask before loading any skill:
1. What product or feature area is this for?
2. What signals do you have? (paste or describe: CS ticket themes, NPS verbatims, app store reviews, Slack threads, sales feedback, interview notes)
3. Roughly how many signals? (10s / 100s / 1000s — affects clustering approach)
4. What is the current roadmap focus this quarter? (helps distinguish "reinforce the bet" from "course correct")
5. Is there anything you already suspect is a pattern but haven't validated?

---

## Step 1: Signal clustering

Read and apply: `pm-product-discovery/skills/analyze-feature-requests/SKILL.md`

Cluster the raw signals into themes:
- Group by: user intent (not feature request language — dig to the underlying job-to-be-done)
- For each cluster: count (frequency), pain intensity (high/medium/low from language cues), user segment if detectable
- Identify which clusters are table-stakes complaints vs opportunity signals (table stakes = multiple users saying "basic thing doesn't work"; opportunity = users describing a workaround or a job not being done)
- Flag any single high-pain signal that doesn't yet have a cluster (outlier signals often predict emerging patterns)

---

## Step 2: VoC synthesis

Read and apply: `pm-product-discovery/skills/voc-analysis/SKILL.md`

For the top 3-5 clusters from Step 1:
- Synthesize into JTBD format: "When [situation], users want to [motivation], so they can [outcome]"
- Confidence rating per theme: how many independent signals support this?
- Segment if the same theme hits different users differently (e.g., power users vs casual users)
- Surface the one theme that has highest frequency AND highest pain intensity — this is the lead signal

---

## Step 3: Opportunity mapping

Read and apply: `pm-product-discovery/skills/opportunity-solution-tree/SKILL.md`

Using the JTBD themes from Step 2:
- Map each theme to an opportunity node (not a solution yet — stay in problem space)
- Build the opportunity hierarchy: which opportunities unlock other opportunities?
- Score each opportunity on: frequency × pain intensity × strategic fit (does it reinforce the current quarter's bets?)
- Identify which opportunities have no current roadmap coverage (gaps)

---

## Roadmap recommendations output

Produce a **Signal-to-Roadmap Brief**:

```
TRIAGE BRIEF: [Product] | Signals analyzed: [N] | Date: [date]
──────────────────────────────────────────────────────────────
TOP SIGNALS
  Theme 1: [JTBD statement] — [N signals] — pain: [High/Med] — segment: [who]
  Theme 2: [JTBD statement] — [N signals] — pain: [High/Med] — segment: [who]
  Theme 3: [JTBD statement] — [N signals] — pain: [High/Med] — segment: [who]
  Outlier to watch: [signal] — [why it matters even though low frequency]

OPPORTUNITY MAP
  Opportunity 1: [opportunity statement] — score: [N/15] — roadmap coverage: [yes/no/partial]
  Opportunity 2: [opportunity statement] — score: [N/15] — roadmap coverage: [yes/no/partial]
  Opportunity 3: [opportunity statement] — score: [N/15] — roadmap coverage: [yes/no/partial]

ROADMAP RECOMMENDATIONS
  ADD to roadmap: [opportunity] — because: [evidence + strategic fit]
  ACCELERATE on roadmap: [initiative] — signals reinforce existing bet
  DEPRIORITIZE: [initiative] — no signal support in this triage cycle
  INVESTIGATE further: [theme] — signal present but not enough confidence yet

GAP FLAG
  [Any opportunity with high score + zero roadmap coverage — warrants immediate attention]
```

---

## Notes

- Run this monthly at minimum, weekly if signal volume is high.
- This command connects to `/pm-os:build-evidence-prd` — when a roadmap recommendation becomes a confirmed bet, that command builds the evidence-backed PRD.
- If signal volume is very low (<10 signals), note this explicitly: low-volume triage has high false positive risk. Recommend expanding signal sources before making roadmap decisions.
