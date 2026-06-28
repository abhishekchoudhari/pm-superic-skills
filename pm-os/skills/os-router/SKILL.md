---
name: os-router
description: "Navigate to the right skill for any PM task. Describe what you are working on — strategy, discovery, execution, go-to-market, analytics, or research — and the OS will identify the exact skill to use and offer to run it. Invoke with 'help', 'what skill should I use', or describe your situation."
---

# PM OS Router: Find the Right Skill

## Purpose

Apply this framework to: **$ARGUMENTS**

You are the navigation layer of the pm-superic-skills operating system. When a PM describes a situation, challenge, or task, you identify the most relevant skill across all 9 plugins and provide a direct path to run it — with context on why it applies and what it will produce.

---

## The Full Skill Map

```
pm-superic-skills
│
├── pm-execution                 Build and ship product
│   ├── create-prd               Write a comprehensive PRD (8-section template)
│   ├── review-prd               Score and stress-test an existing PRD
│   ├── prd-walkthrough          Capture live PRD walkthrough with a team
│   ├── prd-to-epics             Break a PRD into epics and stories
│   ├── write-stories            User stories / job stories / WWA format
│   ├── job-stories              JTBD-style backlog items
│   ├── wwas                     Why-What-Acceptance backlog items
│   ├── sprint-plan              Plan a sprint with capacity + risk
│   ├── retro                    Structured sprint retrospective
│   ├── release-notes            User-facing release notes from tickets
│   ├── pre-mortem               Risk analysis before a launch
│   ├── brainstorm-okrs          Team-level OKRs aligned to company goals
│   ├── quarterly-planning       Full quarterly planning session
│   ├── outcome-roadmap          Reframe feature roadmap as outcomes
│   ├── prioritization-frameworks  RICE, ICE, Kano, MoSCoW reference guide
│   ├── stakeholder-map          Power/Interest grid + comms plan
│   ├── executive-stakeholder-update  Write a leadership update
│   ├── summarize-meeting        Structured meeting notes + action items
│   ├── pm-design-brief          Write a design brief for a feature
│   ├── test-scenarios           QA test cases from user stories
│   └── dummy-dataset            Generate realistic test data
│
├── pm-product-discovery         Understand the problem space
│   ├── brainstorm-ideas-new     Generate ideas for a new product area
│   ├── brainstorm-ideas-existing  Generate ideas to improve an existing product
│   ├── brainstorm-experiments-new  Experiments to validate a new idea
│   ├── brainstorm-experiments-existing  Experiments to improve an existing feature
│   ├── identify-assumptions-new  Surface hidden assumptions for new products
│   ├── identify-assumptions-existing  Surface hidden assumptions for existing
│   ├── prioritize-assumptions   Rank assumptions by risk and testability
│   ├── prioritize-features      Stack-rank features with structured criteria
│   ├── analyze-feature-requests  Extract signal from raw feature requests
│   ├── opportunity-solution-tree  Map problem space to opportunity areas
│   ├── interview-script         Write a user research interview script
│   ├── summarize-interview      Synthesize interview notes into insights
│   ├── voc-analysis             Voice of Customer — themes from feedback
│   └── metrics-dashboard        Define a metrics dashboard for a product area
│
├── pm-product-strategy          Set direction and make big bets
│   ├── product-strategy         Full product strategy document
│   ├── product-vision           3-year product vision narrative
│   ├── business-model           Business model design and analysis
│   ├── lean-canvas              Lean Canvas for a new product or startup
│   ├── startup-canvas           Startup business canvas
│   ├── value-proposition        Value proposition design
│   ├── monetization-strategy    How to make money from the product
│   ├── pricing-strategy         Pricing model design and optimization
│   ├── ansoff-matrix            Growth direction (market/product matrix)
│   ├── swot-analysis            SWOT analysis
│   └── pestle-analysis          PESTLE macro analysis
│       porters-five-forces       Industry competitive forces analysis
│
├── pm-market-research           Know your market and customers
│   ├── competitor-analysis      Deep competitive analysis
│   ├── competitive-intelligence-brief  Quick competitive summary
│   ├── market-sizing            TAM/SAM/SOM market size estimation
│   ├── market-segments          Segment a market by needs and behavior
│   ├── user-personas            Create detailed user personas
│   ├── user-segmentation        Segment users for targeting
│   ├── customer-journey-map     Map the full customer journey
│   ├── find-research            Locate relevant research and data
│   ├── sentiment-analysis       Analyze sentiment in feedback / reviews
│   └── user-research-synthesis  Synthesize qualitative research findings
│
├── pm-go-to-market              Launch and position in market
│   ├── gtm-strategy             Full go-to-market strategy
│   ├── gtm-motions              Define GTM motion (PLG, sales, partner)
│   ├── ideal-customer-profile   ICP definition and scoring
│   ├── beachhead-segment        Which segment to win first
│   ├── competitive-battlecard   Sales battlecard vs a competitor
│   ├── competitive-intelligence-brief  Competitive quick-read
│   └── growth-loops             Design viral and product-led growth loops
│
├── pm-marketing-growth          Tell the story and drive acquisition
│   ├── positioning-ideas        Positioning statements and differentiation
│   ├── value-prop-statements    Value proposition copy variants
│   ├── product-name             Product and feature naming
│   ├── marketing-ideas          Campaign and channel ideas
│   └── north-star-metric        Define the North Star metric
│
├── pm-data-analytics            Measure and learn
│   ├── data-analysis            Analyze a dataset or metric trend
│   ├── ab-test-analysis         Design or interpret an A/B test
│   ├── cohort-analysis          Retention and cohort breakdown
│   ├── sql-queries              Write SQL for product analytics
│   ├── funnel-analysis          Diagnose drop-off in any conversion funnel
│   ├── feature-adoption-analysis  Measure breadth, depth, frequency, Aha moment
│   ├── growth-accounting        Decompose MAU/MRR into new/retained/churned
│   └── product-metrics-dashboard  Design 3-tier metric hierarchy + dashboard spec
│
├── pm-project-management        Run the program
│   └── expert-pm-tracker        Track and manage a product initiative
│
└── pm-toolkit                   Essential PM utilities
    ├── grammar-check            Improve clarity and flow of any text
    ├── draft-nda                Draft an NDA
    ├── privacy-policy           Generate a privacy policy
    └── review-resume            Review and improve a PM resume

── pm-fintech-skills (companion plugin set — fintech-specific)
    See: pm-fintech-os:os-router for full fintech skill map
    Install: pm-fintech-skills plugin for fintech-specific work
```

---

## Situation → Skill Routing

### Discovery and Research

| If you need to... | Use this skill | Plugin |
|------------------|---------------|--------|
| Understand what problem to solve | `opportunity-solution-tree` | pm-product-discovery |
| Generate ideas for a new product area | `brainstorm-ideas-new` | pm-product-discovery |
| Generate ideas to improve an existing feature | `brainstorm-ideas-existing` | pm-product-discovery |
| Find out what experiments to run | `brainstorm-experiments-new` / `brainstorm-experiments-existing` | pm-product-discovery |
| Surface what you're assuming but haven't validated | `identify-assumptions-new` / `identify-assumptions-existing` | pm-product-discovery |
| Rank which assumptions are riskiest | `prioritize-assumptions` | pm-product-discovery |
| Prepare for a user research session | `interview-script` | pm-product-discovery |
| Process raw interview notes | `summarize-interview` | pm-product-discovery |
| Extract signal from support tickets, reviews, or NPS verbatims | `voc-analysis` | pm-product-discovery |
| Analyze app store reviews or competitor feedback | `sentiment-analysis` | pm-market-research |
| Understand your competitive landscape | `competitor-analysis` | pm-market-research |
| Size a market for a new initiative | `market-sizing` | pm-market-research |
| Understand who your customer is | `user-personas` | pm-market-research |
| Map the full customer experience | `customer-journey-map` | pm-market-research |
| Find existing research or data on a topic | `find-research` | pm-market-research |

### Strategy

| If you need to... | Use this skill | Plugin |
|------------------|---------------|--------|
| Write a full product strategy | `product-strategy` | pm-product-strategy |
| Write a 3-year product vision | `product-vision` | pm-product-strategy |
| Define your business model | `business-model` | pm-product-strategy |
| Design your monetization approach | `monetization-strategy` | pm-product-strategy |
| Design or optimize pricing | `pricing-strategy` | pm-product-strategy |
| Decide which market to go after first | `beachhead-segment` | pm-go-to-market |
| Decide where to grow (new market vs new product) | `ansoff-matrix` | pm-product-strategy |
| Audit competitive threats | `swot-analysis` / `porters-five-forces` | pm-product-strategy |
| Build a lean canvas for a new idea | `lean-canvas` | pm-product-strategy |

### Execution and Delivery

| If you need to... | Use this skill | Plugin |
|------------------|---------------|--------|
| Write a PRD from scratch | `create-prd` | pm-execution |
| Review or score an existing PRD | `review-prd` | pm-execution |
| Facilitate a PRD walkthrough with your team | `prd-walkthrough` | pm-execution |
| Break a PRD into engineering epics | `prd-to-epics` | pm-execution |
| Write user stories or backlog items | `write-stories` | pm-execution |
| Write JTBD-style job stories | `job-stories` | pm-execution |
| Plan a sprint with capacity and risk | `sprint-plan` | pm-execution |
| Run a retrospective | `retro` | pm-execution |
| Write release notes for a shipped feature | `release-notes` | pm-execution |
| Stress-test a launch plan for what could go wrong | `pre-mortem` | pm-execution |
| Prioritize a backlog | `prioritize-features` | pm-product-discovery |
| Choose a prioritization method (RICE vs ICE vs MoSCoW) | `prioritization-frameworks` | pm-execution |
| Write a design brief for engineering handoff | `pm-design-brief` | pm-execution |
| Generate test cases for a feature | `test-scenarios` | pm-execution |
| Create dummy data for testing or demos | `dummy-dataset` | pm-execution |

### Planning and Alignment

| If you need to... | Use this skill | Plugin |
|------------------|---------------|--------|
| Set team OKRs for the quarter | `brainstorm-okrs` | pm-execution |
| Run a quarterly planning session | `quarterly-planning` | pm-execution |
| Convert a feature-list roadmap to outcomes | `outcome-roadmap` | pm-execution |
| Map stakeholders and build a comms plan | `stakeholder-map` | pm-execution |
| Write a leadership / exec update | `executive-stakeholder-update` | pm-execution |
| Turn meeting notes into action items | `summarize-meeting` | pm-execution |

### Go-to-Market and Launch

| If you need to... | Use this skill | Plugin |
|------------------|---------------|--------|
| Build a full GTM plan | `gtm-strategy` | pm-go-to-market |
| Define your GTM motion (PLG vs sales vs partner) | `gtm-motions` | pm-go-to-market |
| Define your ideal customer profile | `ideal-customer-profile` | pm-go-to-market |
| Build a sales battlecard vs a specific competitor | `competitive-battlecard` | pm-go-to-market |
| Design a viral or product-led growth loop | `growth-loops` | pm-go-to-market |
| Position the product in the market | `positioning-ideas` | pm-marketing-growth |
| Write a value proposition | `value-prop-statements` | pm-marketing-growth |
| Name a product or feature | `product-name` | pm-marketing-growth |
| Define the North Star metric | `north-star-metric` | pm-marketing-growth |

### Analytics and Measurement

| If you need to... | Use this skill | Plugin |
|------------------|---------------|--------|
| Define the metrics dashboard for a product area | `metrics-dashboard` | pm-product-discovery |
| Design a production metrics dashboard with alert thresholds | `product-metrics-dashboard` | pm-data-analytics |
| Analyze a dataset or understand a metric movement | `data-analysis` | pm-data-analytics |
| Design or interpret an A/B test | `ab-test-analysis` | pm-data-analytics |
| Run a retention or cohort analysis | `cohort-analysis` | pm-data-analytics |
| Write SQL for a product analytics query | `sql-queries` | pm-data-analytics |
| Diagnose drop-off in an onboarding or conversion funnel | `funnel-analysis` | pm-data-analytics |
| Measure how well a feature is being adopted | `feature-adoption-analysis` | pm-data-analytics |
| Decompose MAU or revenue growth into new/retained/churned | `growth-accounting` | pm-data-analytics |

### Utilities

| If you need to... | Use this skill | Plugin |
|------------------|---------------|--------|
| Improve the clarity of a doc or email | `grammar-check` | pm-toolkit |
| Draft an NDA | `draft-nda` | pm-toolkit |
| Generate a privacy policy | `privacy-policy` | pm-toolkit |
| Review a PM resume | `review-resume` | pm-toolkit |

---

## Instructions

### Step 1: Understand the Situation

Read **$ARGUMENTS**.

- If blank or the user typed "help" with no context: show the full Situation → Skill routing table above. Ask: "What are you working on right now?"
- If the user described a task or challenge: proceed to Step 2.
- If ambiguous: ask ONE clarifying question — "Are you trying to [Option A] or [Option B]?"

### Step 2: Route to the Right Skill

Match the user's situation to the routing tables above. Identify the primary skill and up to 2 alternatives if the situation could go multiple ways.

**Fintech-specific situations:** if the user's work involves payments, lending, KYC, banking partnerships, BNPL, credit underwriting, or financial regulation, route them to the companion plugin:
> "This looks like fintech-specific work. The `pm-fintech-skills` plugin has purpose-built skills for this. Make sure it is installed and use `/pm-fintech-os:help` to navigate it."

### Step 3: Deliver the Routing Output

Respond in this format — concise, direct, no preamble:

---
**Situation understood:** [1-sentence summary]

**Recommended skill:** `[plugin-name]` → `[skill-name]`

**What it produces:** [1 sentence on the output]

**Why this one:** [1-2 sentences on the match]

**Also consider:**
- `[alternative skill]` — if [alternative situation]
- `[alternative skill]` — if [alternative situation]

**Ready to run it?** Share your context and I'll start now.

---

### Step 4: Offer to Run the Skill

If the user confirms or shares context, load and execute the recommended skill immediately. Do not ask for permission again — just run it.

---

## Notes

- The OS router is the front door. Any time a user is unsure which skill to use, this is the starting point.
- For multi-phase work (e.g., "I need to discover the problem AND write the PRD AND plan the sprint"), route to the first skill now and sequence the others: "After this, we'll move to `create-prd`, then `sprint-plan`."
- Fintech-specific tasks belong in pm-fintech-skills. General PM tasks belong here. If both apply, start here and link to fintech for the domain-specific layer.
