![GitHub stars](https://img.shields.io/github/stars/abhishekchoudhari/pm-superic-skills)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow?style=flat-square)](https://github.com/abhishekchoudhari/pm-superic-skills/blob/main/LICENSE)
[![PRs Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen?style=flat-square)](https://github.com/abhishekchoudhari/pm-superic-skills/blob/main/CONTRIBUTING.md)

# PM Skills Marketplace: The AI Operating System for Better Product Decisions

> 80+ PM skills and 19 chained workflow commands across 9 plugins. Claude Code, Cowork, and more. From daily rituals to discovery, strategy, execution, launch, and growth.

![Plugin overview](.docs/images/plugins-overview.webp)

Designed for Claude Code and Cowork. Skills compatible with other AI assistants.

## Start Here — Situation to Skill Router

| What you are trying to solve | Command to run | Primary Plugin |
|------------------------------|----------------|----------------|
| **New to this or not sure where to start** | `/pm-os:help` | `pm-os` |
| **Research a problem end-to-end** | `/pm-os:run-discovery-sprint` | `pm-os` |
| **Build an evidence-backed PRD** | `/pm-os:build-evidence-prd` | `pm-os` |
| **Run the full feature lifecycle (PRD → sprint → release)** | `/pm-os:run-feature-lifecycle` | `pm-os` |
| **Weekly metrics and OKR pulse ritual** | `/pm-os:run-weekly-review` | `pm-os` |
| **Turn customer feedback into roadmap recommendations** | `/pm-os:triage-to-roadmap` | `pm-os` |
| **Writing a PRD from a feature idea** | `/pm-execution:write-prd` | `pm-execution` |
| **Planning a sprint or running a retro** | `/pm-execution:run-sprint` | `pm-execution` |
| **Setting quarterly OKRs** | `/pm-execution:plan-okrs` | `pm-execution` |
| **Competitive analysis and positioning** | `/pm-market-research:analyze-competitive-position` | `pm-market-research` |
| **Diagnose a product health metric** | `/pm-data-analytics:diagnose-product-health` | `pm-data-analytics` |
| **New product from zero — strategy and canvas** | `/pm-product-strategy:plan-new-product` | `pm-product-strategy` |

If this project helps you, ⭐ the repo.

## Why PM Skills Marketplace?

Generic AI gives you text. PM Skills Marketplace gives you structure.

Each skill encodes a proven PM framework — discovery, assumption mapping, prioritization, strategy — and walks you through it step by step. You get the rigor of Teresa Torres, Marty Cagan, and Alberto Savoia built into your daily workflow, not sitting on a bookshelf.

The result: better product decisions, not just faster documents.

## How It Works (Skills, Commands, Plugins)

**Skills** are the building blocks of the marketplace. Each skill gives Claude domain knowledge, analytical frameworks, or a guided workflow for a specific PM task. Some skills also work as reusable foundations that multiple commands share.

Skills are loaded automatically when relevant to the conversation — no explicit invocation needed. If needed, you can force loading skills with `/plugin-name:skill-name`.

**Commands** are user-triggered workflows invoked with `/plugin-name:command-name`. They chain one or more skills into an end-to-end process. Chained commands (marked ⛓) sequence multiple skills and carry context forward between steps so nothing is repeated.

**Plugins** group related skills and commands into installable packages. Each plugin covers a PM domain — discovery, strategy, execution, and so on. Installing the marketplace gives you all 9 plugins at once.

![How skills work](.docs/images/how-skills-work.webp)

Commands are designed to flow into each other, matching the PM workflow. After any command completes, it suggests relevant next commands — just follow the prompts.

## Installation

### Claude Cowork (recommended for non-developers)

1. Open **Customize** (bottom-left)
2. Go to **Browse plugins** → **Personal** → **+**
3. Select **Add marketplace from GitHub**
4. Enter: `abhishekchoudhari/pm-superic-skills`

All 9 plugins install automatically. You get both commands and skills.

![Installing PM Skills in Claude Cowork](.docs/images/pm-skills-install.gif)

### Claude Code (CLI)

```bash
# Step 1: Add the marketplace
claude plugin marketplace add abhishekchoudhari/pm-superic-skills

# Step 2: Install individual plugins
claude plugin install pm-os@pm-superic-skills
claude plugin install pm-toolkit@pm-superic-skills
claude plugin install pm-product-strategy@pm-superic-skills
claude plugin install pm-product-discovery@pm-superic-skills
claude plugin install pm-market-research@pm-superic-skills
claude plugin install pm-data-analytics@pm-superic-skills
claude plugin install pm-marketing-growth@pm-superic-skills
claude plugin install pm-go-to-market@pm-superic-skills
claude plugin install pm-execution@pm-superic-skills
```

### Other AI assistants (skills only)

The `skills/*/SKILL.md` files follow the universal skill format and work with any tool that reads it. Commands (`/slash-commands`) are Claude-specific.

| Tool | How to use | What works |
|------|-----------|------------|
| **Gemini CLI** | Copy skill folders to `.gemini/skills/` | Skills only |
| **OpenCode** | Copy skill folders to `.opencode/skills/` | Skills only |
| **Cursor** | Copy skill folders to `.cursor/skills/` | Skills only |
| **Codex CLI** | Copy skill folders to `.codex/skills/` | Skills only |
| **Kiro** | Copy skill folders to `.kiro/skills/` | Skills only |

```bash
# Example: copy all skills for OpenCode (project-level)
for plugin in pm-*/; do
  mkdir -p .opencode/skills/
  cp -r "$plugin/skills/"* .opencode/skills/ 2>/dev/null
done

# Example: copy all skills for Gemini CLI (global)
for plugin in pm-*/; do
  cp -r "$plugin/skills/"* ~/.gemini/skills/ 2>/dev/null
done
```

---

## Available Plugins

<details>
<summary><strong>1. pm-os</strong> — Workflows, orchestration, and daily rituals (2 skills, 9 commands)</summary>

The OS layer. Navigation, daily rituals, and cross-plugin chained workflows that span multiple plugins. Start here when you are not sure which skill to use, or when you want to run a multi-step workflow end-to-end.

**Skills (2):**

- `os-router` — Navigate to the right skill for any PM task. Describe the situation and get routed with context on why the skill applies and what it produces.
- `setup-stack` — Configure your PM toolstack integrations (Jira, Notion, Figma, Slack, analytics tools) and generate a personalised stack config.

**Commands (9):**

- `/pm-os:help` — Describe your PM challenge and get routed to the exact skill or command that solves it.
- `/pm-os:build-evidence-prd` ⛓ — Research-anchored PRD pipeline. Adapts to whether you have existing research, VoC signals, or a new product hypothesis. Gates on PM confirmation before generating the PRD. 6 phases: context intake → research branch → optional competitive context → problem space synthesis → PRD generation → optional epic breakdown.
- `/pm-os:run-feature-lifecycle` ⛓ — Full delivery chain: PRD → epics → sprint plan → test scenarios → release notes. Entry-point check lets you skip ahead to where you actually are.
- `/pm-os:run-launch-readiness` ⛓ — Pre-launch gate: pre-mortem risk classification → stakeholder alignment → QA coverage → explicit LAUNCH / DELAY / CONDITIONAL verdict.
- `/pm-os:run-weekly-review` ⛓ — Monday ritual: last week's metrics + shipped items + OKR pulse → weekly brief with top 3 focus areas and one metric to watch.
- `/pm-os:triage-to-roadmap` ⛓ — Signal-to-roadmap pipeline: CS tickets / NPS / reviews → VoC clustering → opportunity mapping → top 3 prioritized roadmap recommendations.
- `/pm-os:run-discovery-sprint` ⛓ — Full discovery sprint: interview script design → session synthesis → opportunity mapping → assumption prioritization → stakeholder-ready recommendation.

**Examples:**

- `/pm-os:build-evidence-prd feature: savings auto-invest for salary users`
- `/pm-os:run-weekly-review` — run every Monday, paste last week's metrics
- `/pm-os:triage-to-roadmap` — paste NPS verbatims and CS ticket themes
- `/pm-os:run-discovery-sprint why are users not adopting the savings feature post-onboarding?`

</details>

<details>
<summary><strong>2. pm-product-discovery</strong> — Ideation, experiments, assumption testing, OSTs, interviews (13 skills, 5 commands)</summary>

**Skills (13):**

- `brainstorm-ideas-existing` — Multi-perspective ideation for existing products (PM, Designer, Engineer)
- `brainstorm-ideas-new` — Ideation for new products in initial discovery
- `brainstorm-experiments-existing` — Design experiments to test assumptions for existing products
- `brainstorm-experiments-new` — Design lean startup pretotypes for new products (Alberto Savoia)
- `identify-assumptions-existing` — Identify risky assumptions across Value, Usability, Viability, and Feasibility
- `identify-assumptions-new` — Identify risky assumptions across 8 risk categories including Go-to-Market, Strategy, and Team
- `prioritize-assumptions` — Prioritize assumptions using an Impact × Risk matrix with experiment suggestions
- `prioritize-features` — Prioritize a feature backlog based on impact, effort, risk, and strategic alignment
- `analyze-feature-requests` — Analyze and categorize customer feature requests by theme and strategic fit
- `opportunity-solution-tree` — Build an Opportunity Solution Tree (Teresa Torres) — outcome → opportunities → solutions → experiments
- `interview-script` — Create a structured customer interview script with JTBD probing questions
- `summarize-interview` — Summarize an interview transcript into JTBD, satisfaction signals, and action items
- `metrics-dashboard` — Define a product metrics dashboard for a product area

**Commands (5):**

- `/pm-product-discovery:run-discovery` — Full discovery cycle: ideation → assumption mapping → prioritization → experiment design
- `/pm-product-discovery:generate-ideas` — Multi-perspective ideation (`ideas|experiments` × `existing|new`)
- `/pm-product-discovery:analyze-feature-requests` — Analyze and prioritize a batch of feature requests
- `/pm-product-discovery:run-interview` — Prepare an interview script or summarize a transcript (`prep|summarize`)
- `/pm-product-discovery:define-product-metrics` — Define a product metrics dashboard

**Examples:**

- `What are the riskiest assumptions for our AI writing assistant idea?`
- `Help me build an Opportunity Solution Tree for improving user activation`
- `/pm-product-discovery:run-discovery AI-powered meeting summarizer for remote teams`
- `/pm-product-discovery:generate-ideas experiments existing — reduce churn in onboarding`

</details>

<details>
<summary><strong>3. pm-product-strategy</strong> — Vision, business models, pricing, competitive landscape (12 skills, 6 commands)</summary>

Product strategy, vision, business models, pricing, and macro environment analysis. Covers the full strategic toolkit from vision crafting through competitive landscape scanning.

**Skills (12):**

- `product-strategy` — Comprehensive 9-section Product Strategy Canvas (vision → defensibility)
- `startup-canvas` — Startup Canvas combining Product Strategy + Business Model
- `product-vision` — Craft an inspiring, achievable, and emotional product vision
- `value-proposition` — 6-part JTBD value proposition (Who, Why, What before, How, What after, Alternatives)
- `lean-canvas` — Lean Canvas business model for startups and new products
- `business-model` — Business Model Canvas with all 9 building blocks
- `monetization-strategy` — Brainstorm 3-5 monetization strategies with validation experiments
- `pricing-strategy` — Pricing models, competitive analysis, willingness-to-pay, and price elasticity
- `swot-analysis` — SWOT analysis with actionable recommendations
- `pestle-analysis` — Macro environment: Political, Economic, Social, Technological, Legal, Environmental
- `porters-five-forces` — Competitive forces analysis (rivalry, suppliers, buyers, substitutes, new entrants)
- `ansoff-matrix` — Growth strategy mapping across markets and products

**Commands (6):**

- `/pm-product-strategy:build-product-strategy` — Create a complete 9-section Product Strategy Canvas
- `/pm-product-strategy:design-business-model` — Explore business models (`lean|full|startup|value-prop|all`)
- `/pm-product-strategy:define-value-proposition` — Design a value proposition using the 6-part JTBD template
- `/pm-product-strategy:scan-market` — Macro environment analysis combining SWOT + PESTLE + Porter's + Ansoff
- `/pm-product-strategy:design-pricing` — Design a pricing strategy with competitive analysis and experiments
- `/pm-product-strategy:plan-new-product` ⛓ — 0-to-1 foundation: surface hidden assumptions → lean canvas → value proposition → beachhead segment. Produces a foundation pack before any PRD is written.

**Examples:**

- `/pm-product-strategy:build-product-strategy B2B project management tool for agencies`
- `/pm-product-strategy:plan-new-product embedded investment product for neobank users`
- `Run a Porter's Five Forces analysis for the project management SaaS market`

</details>

<details>
<summary><strong>4. pm-execution</strong> — PRDs, OKRs, roadmaps, sprints, retros, release notes, stakeholder management (19 skills, 13 commands)</summary>

Day-to-day product management: PRDs, OKRs, roadmaps, sprints, retrospectives, release notes, pre-mortems, stakeholder management, user stories, async updates, and working backwards documents.

**Skills (19):**

- `create-prd` — Comprehensive 8-section PRD template
- `review-prd` — Score and stress-test an existing PRD
- `prd-walkthrough` — Capture a live PRD walkthrough with a team
- `brainstorm-okrs` — Team-level OKRs aligned with company objectives
- `outcome-roadmap` — Transform a feature list into an outcome-focused roadmap
- `sprint-plan` — Sprint planning with capacity estimation, story selection, and risk identification
- `retro` — Structured sprint retrospective facilitation
- `release-notes` — User-facing release notes from tickets, PRDs, or changelogs
- `pre-mortem` — Risk analysis with Tigers/Paper Tigers/Elephants classification
- `stakeholder-map` — Power × Interest grid with tailored communication plan
- `executive-stakeholder-update` — Write a structured leadership or board update
- `summarize-meeting` — Meeting transcript → decisions + action items
- `pm-design-brief` — Write a design brief for engineering handoff
- `user-stories` — User stories following the 3 C's and INVEST criteria
- `job-stories` — Job stories: When [situation], I want to [motivation], so I can [outcome]
- `wwas` — Product backlog items in Why-What-Acceptance format
- `test-scenarios` — Test scenarios: happy paths, edge cases, error handling
- `dummy-dataset` — Realistic dummy datasets as CSV, JSON, SQL, or Python
- `prioritization-frameworks` — Reference guide to 9 prioritization frameworks (RICE, ICE, Kano, MoSCoW, Opportunity Score, etc.)

**Commands (13):**

- `/pm-execution:write-prd` — Create a PRD from a feature idea or problem statement
- `/pm-execution:plan-okrs` — Brainstorm team-level OKRs aligned to company objectives
- `/pm-execution:plan-outcome-roadmap` — Convert a feature-based roadmap into outcome-focused
- `/pm-execution:run-sprint` — Sprint lifecycle (`plan|retro|release`)
- `/pm-execution:run-pre-mortem` — Pre-mortem risk analysis on a PRD or launch plan
- `/pm-execution:summarize-meeting` — Summarize a meeting transcript into structured notes
- `/pm-execution:map-stakeholders` — Map stakeholders and create a communication plan
- `/pm-execution:write-stories` — Break features into backlog items (`user|job|wwa`)
- `/pm-execution:generate-test-scenarios` — Generate test scenarios from user stories
- `/pm-execution:generate-data` — Create realistic dummy datasets
- `/pm-execution:draft-async-update` — Turn rough notes into a polished async update for Slack, Notion, or email. Adapts format and length to audience and channel. Saves 20 minutes per update.
- `/pm-execution:write-working-backwards` — Write an Amazon-style Working Backwards document: press release + internal FAQ. The most effective forcing function for catching wrong bets before a PRD is written.
- `/pm-execution:run-quarterly-cycle` ⛓ — Full Q-start sequence: OKR planning → outcome roadmap → stakeholder update. Context carries through all three steps.

**Examples:**

- `/pm-execution:write-prd Smart notification system that reduces alert fatigue`
- `/pm-execution:write-working-backwards embedded investment product for neobank`
- `/pm-execution:draft-async-update` — paste your bullet notes, pick audience (team / VP / board)
- `/pm-execution:run-quarterly-cycle` — run at the start of each quarter

</details>

<details>
<summary><strong>5. pm-market-research</strong> — Personas, segmentation, journey maps, market sizing, competitor analysis (10 skills, 4 commands)</summary>

User research and competitive analysis: personas, segmentation, journey maps, market sizing, competitor analysis, sentiment analysis, research synthesis, and ongoing competitive intelligence.

**Skills (10):**

- `user-personas` — Create refined user personas from research data
- `market-segments` — Identify 3-5 customer segments with demographics, JTBD, and product fit
- `user-segmentation` — Segment users from feedback data based on behavior, JTBD, and needs
- `customer-journey-map` — End-to-end journey map with stages, touchpoints, emotions, and pain points
- `market-sizing` — TAM, SAM, SOM with top-down and bottom-up approaches
- `competitor-analysis` — Competitor strengths, weaknesses, and differentiation opportunities
- `competitive-intelligence-brief` — Quick competitive summary on 2-3 competitors with standing monitoring config
- `sentiment-analysis` — Sentiment analysis and theme extraction from user feedback
- `find-research` — Locate relevant existing research and data on any topic
- `user-research-synthesis` — Synthesize qualitative research findings across multiple sessions into JTBD themes

**Commands (4):**

- `/pm-market-research:map-user-research` — Build personas, segment users, and map the customer journey
- `/pm-market-research:analyze-competitors` — Analyze the competitive landscape
- `/pm-market-research:summarize-research` — Synthesize feedback or interview data into structured insights
- `/pm-market-research:analyze-competitive-position` ⛓ — Full competitive picture: deep analysis → user sentiment on competitors → ongoing CI monitoring setup. Produces a competitive position report with differentiation opportunities and a standing monitoring config.

**Examples:**

- `Estimate TAM/SAM/SOM for an AI code review tool in the US market`
- `/pm-market-research:analyze-competitors Figma competitors in the design tool space`
- `/pm-market-research:analyze-competitive-position our neobank vs Revolut and Monzo`

</details>

<details>
<summary><strong>6. pm-data-analytics</strong> — Funnels, cohorts, growth accounting, feature adoption, unit economics, A/B tests, SQL (9 skills, 7 commands)</summary>

Data analytics for PMs: funnel analysis, cohort analysis, growth accounting, feature adoption, unit economics, A/B test analysis, SQL generation, metrics dashboards, and a full product health diagnostic.

**Skills (9):**

- `data-analysis` — Analyze a dataset or diagnose a metric movement
- `sql-queries` — Generate SQL from natural language (BigQuery, PostgreSQL, MySQL)
- `ab-test-analysis` — Statistical significance, sample size validation, and ship/extend/stop recommendations
- `cohort-analysis` — Retention curves, feature adoption, and engagement trends by cohort
- `funnel-analysis` — Diagnose drop-off across any conversion funnel: absolute/relative analysis, segmentation, time-in-funnel, fix prioritization table, SQL template
- `feature-adoption-analysis` — Measure breadth (% who ever used), depth (frequency), and frequency. Identifies Aha moment and bottleneck. Produces improvement roadmap.
- `growth-accounting` — Decompose MAU/MRR into New + Retained + Resurrected − Churned. Compute quick ratio. Diagnose growth scenario and identify which lever to pull.
- `product-metrics-dashboard` — Design a 3-tier metric hierarchy with dashboard specs, alert thresholds, ownership matrix, and vanity metrics retirement
- `analyze-unit-economics` — Model CAC, LTV, LTV/CAC ratio, and payback period across SaaS, marketplace, consumer, and fintech business models

**Commands (7):**

- `/pm-data-analytics:write-sql` — Generate SQL queries from natural language
- `/pm-data-analytics:analyze-ab-test` — Analyze A/B test results
- `/pm-data-analytics:analyze-cohorts` — Cohort analysis on user engagement data
- `/pm-data-analytics:analyze-funnel` — Diagnose drop-off in any conversion funnel
- `/pm-data-analytics:analyze-growth-accounting` — Full MAU/MRR decomposition with quick ratio and lever recommendation
- `/pm-data-analytics:analyze-unit-economics` — Model unit economics across business models
- `/pm-data-analytics:diagnose-product-health` ⛓ — 4-lens health diagnostic: growth accounting → cohort analysis → funnel analysis → feature adoption → single weekly health brief. The Monday morning read for a GM or product lead.

**Examples:**

- `/pm-data-analytics:write-sql Show monthly active users by country for Q4 (BigQuery)`
- `/pm-data-analytics:analyze-ab-test` — paste your A/B test results
- `/pm-data-analytics:diagnose-product-health savings product, last 30 days`

</details>

<details>
<summary><strong>7. pm-go-to-market</strong> — Beachhead segments, ICPs, messaging, growth loops, GTM motions, battlecards, competitive intelligence (7 skills, 4 commands)</summary>

Go-to-market strategy: beachhead segments, ideal customer profiles, messaging, growth loops, GTM motions, competitive battlecards, and competitive intelligence briefs.

**Skills (7):**

- `gtm-strategy` — Full GTM strategy: channels, messaging, success metrics, and launch plan
- `beachhead-segment` — Identify the first beachhead market segment
- `ideal-customer-profile` — ICP with demographics, behaviors, JTBD, and needs
- `growth-loops` — Design sustainable growth loops (flywheels)
- `gtm-motions` — Evaluate GTM motions and tools (product-led, sales-led, etc.)
- `competitive-battlecard` — Sales-ready battlecard with objection handling and win strategies
- `competitive-intelligence-brief` — Competitive quick-read on 2-3 competitors with signal monitoring

**Commands (4):**

- `/pm-go-to-market:build-growth-strategy` — Full GTM strategy from beachhead to launch plan
- `/pm-go-to-market:create-battlecard` — Create a competitive battlecard vs a specific competitor
- `/pm-go-to-market:generate-ci-brief` — Run a competitive intelligence brief and monitoring update
- `/pm-go-to-market:define-north-star` — Define your North Star metric and supporting input metrics

**Examples:**

- `/pm-go-to-market:build-growth-strategy AI code review tool targeting mid-size engineering teams`
- `/pm-go-to-market:create-battlecard Our CRM vs Salesforce for the SMB market`

</details>

<details>
<summary><strong>8. pm-marketing-growth</strong> — Marketing ideas, positioning, value props, naming, North Star metrics (5 skills, 2 commands)</summary>

Product marketing and growth: marketing ideas, positioning, value proposition statements, product naming, and North Star metrics.

**Skills (5):**

- `marketing-ideas` — Creative, cost-effective marketing ideas with channels and messaging
- `positioning-ideas` — Product positioning differentiated from competitors
- `value-prop-statements` — Value proposition statements for marketing, sales, and onboarding
- `product-name` — Product name brainstorming aligned to brand values and audience
- `north-star-metric` — North Star Metric + input metrics with business game classification

**Commands (2):**

- `/pm-marketing-growth:create-marketing-toolkit` — Brainstorm marketing ideas, positioning, value props, and product names
- `/pm-marketing-growth:define-north-star` — Define your North Star Metric and supporting input metrics

**Examples:**

- `/pm-marketing-growth:create-marketing-toolkit B2B analytics dashboard for e-commerce managers`
- `/pm-marketing-growth:define-north-star Two-sided marketplace connecting freelancers with clients`

</details>

<details>
<summary><strong>9. pm-toolkit</strong> — Resume review, legal documents, grammar (4 skills, 5 commands)</summary>

PM utilities beyond core product work: resume review, legal documents, and grammar checking.

**Skills (4):**

- `review-resume` — PM resume review and tailoring against 10 best practices (XYZ+S formula, keywords, structure)
- `draft-nda` — Non-Disclosure Agreement with jurisdiction-appropriate clauses
- `privacy-policy` — Privacy policy covering GDPR/CCPA compliance
- `grammar-check` — Grammar, logic, and flow checking with targeted fixes

**Commands (5):**

- `/pm-toolkit:review-resume-fit` — Comprehensive PM resume review and tailoring against a job description
- `/pm-toolkit:draft-privacy-policy` — Draft a privacy policy
- `/pm-toolkit:draft-nda` — Draft an NDA
- `/pm-toolkit:review-grammar` — Check grammar, logic, and flow

**Examples:**

- `/pm-toolkit:review-resume-fit` — attach resume + paste job description
- `/pm-toolkit:review-grammar Here's the draft of our Q1 investor update`

</details>

---

## About

This marketplace evolves with product practice and AI capabilities.

Selected skills based on the work of:

- Teresa Torres — [*Continuous Discovery Habits*](https://www.amazon.com/Continuous-Discovery-Habits-Discover-Products/dp/1736633309/)
- Marty Cagan — [*INSPIRED*](https://www.amazon.com/INSPIRED-Create-Tech-Products-Customers/dp/1119387507/) and [*TRANSFORMED*](https://www.amazon.com/dp/1119697336/)
- Alberto Savoia — [*The Right It*](https://www.amazon.com/Right-Many-Ideas-Yours-Succeed/dp/0062884654)
- Dan Olsen — [*The Lean Product Playbook*](https://www.amazon.com/dp/1118960874/)
- Roger L. Martin — [*Playing to Win*](https://www.amazon.com/Playing-Win-Expanded-Bonus-Articles/dp/B0F25SDYWV/)
- Ash Maurya — [*Running Lean*](https://www.amazon.com/dp/B004J4XGN6/)
- Strategyzer — [*Business Model Generation*](https://www.amazon.com/dp/0470876417/) and [*Value Proposition Design*](https://www.amazon.com/dp/1118968050/)
- Christina Wodtke — [*Radical Focus*](https://www.amazon.com/Radical-Focus-Achieving-Important-Objectives/dp/0996006052)
- Anthony W. Ulwick — [*Jobs to Be Done*](https://jobs-to-be-done-book.com/)
- Alistair Croll & Benjamin Yoskovitz — [*Lean Analytics*](https://www.amazon.com/Lean-Analytics-Better-Startup-Faster/dp/1449335675/)
- Sean Ellis — [*Hacking Growth*](https://www.amazon.com/Hacking-Growth-Fastest-Growing-Companies-Breakout/dp/045149721X/)
- Maja Voje — [*Go-To-Market Strategist*](https://gtmstrategist.com/)

Curated by [Abhishek Choudhari](https://www.linkedin.com/in/abhishekchoudhari/).

## Contributing

See [CONTRIBUTING.md](CONTRIBUTING.md).

## Known Issue on Windows

If your Cowork is unstable and can't start a VM ([claude-code/issues/27010](https://github.com/anthropics/claude-code/issues/27010)), try:

```powershell
$action = New-ScheduledTaskAction -Execute "powershell.exe" -Argument "-WindowStyle Hidden -Command `"if ((Get-Service CoworkVMService).Status -ne 'Running') { Start-Service CoworkVMService }`""

$trigger = New-ScheduledTaskTrigger -RepetitionInterval (New-TimeSpan -Minutes 1) -Once -At (Get-Date)

$settings = New-ScheduledTaskSettingsSet -AllowStartIfOnBatteries -DontStopIfGoingOnBatteries

Register-ScheduledTask -TaskName "CoworkVMServiceMonitor" `
  -Action $action `
  -Trigger $trigger `
  -Settings $settings `
  -RunLevel Highest `
  -User "SYSTEM"
```

It solves 90% of the issues on Windows.
The remaining 10%: open services.msc > start "Claude" service manually

## License

MIT — see [LICENSE](LICENSE).
