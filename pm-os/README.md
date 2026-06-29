# pm-os — PM Operating System

The navigation layer for pm-superic-skills. Routes any PM situation to the right skill or command across all 9 plugins.

## Overview

pm-os is the entry point to the marketplace. It replaces the experience of asking "which skill do I need?" with a direct, context-aware routing layer. Describe your situation and the OS router maps it to the exact command or skill that solves it — with context on why that skill applies and what it produces.

It also provides chained workflow commands that span multiple plugins, running multi-step processes end-to-end so you never have to re-explain context between steps.

## Install

```bash
claude plugin install pm-os@pm-superic-skills
```

Or install the full marketplace:

```bash
claude plugin marketplace add github:abhishekchoudhari/pm-superic-skills
claude plugin install pm-os@pm-superic-skills
```

## Skills

- **os-router** — Routes any PM situation to the right skill across all 9 plugins. Describe your challenge and get a direct path with context on why the skill applies and what it produces.

## Commands

| Command | What it does |
|---------|-------------|
| `/pm-os:help` | Describe your PM challenge and get routed to the exact skill or command that solves it |
| `/pm-os:build-evidence-prd` ⛓ | Research-anchored PRD pipeline. Adapts to whether you have research, VoC signals, or a new product hypothesis |
| `/pm-os:run-feature-lifecycle` ⛓ | Full delivery chain: PRD → epics → sprint plan → test scenarios → release notes |
| `/pm-os:run-launch-readiness` ⛓ | Pre-launch gate: pre-mortem → stakeholder alignment → QA coverage → LAUNCH / DELAY / CONDITIONAL verdict |
| `/pm-os:run-weekly-review` ⛓ | Monday ritual: last week's metrics + shipped items + OKR pulse → weekly brief with top 3 focus areas |
| `/pm-os:triage-to-roadmap` ⛓ | Signal-to-roadmap: CS tickets / NPS / reviews → VoC clustering → opportunity mapping → top 3 roadmap recommendations |
| `/pm-os:run-discovery-sprint` ⛓ | Full discovery sprint: interview script → session synthesis → OST → assumption prioritization → stakeholder recommendation |

## Examples

```
/pm-os:help I need to diagnose why our activation rate dropped last month

/pm-os:build-evidence-prd feature: savings auto-invest for salary users

/pm-os:run-weekly-review  ← run every Monday, paste last week's metrics

/pm-os:triage-to-roadmap  ← paste NPS verbatims and CS ticket themes

/pm-os:run-discovery-sprint why are users not adopting the savings feature post-onboarding?
```
