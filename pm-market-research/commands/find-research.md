---
description: Search your team's research library on Google Drive and surface relevant findings for a topic, PRD, or question
argument-hint: "<topic, question, or product area>"
---

# /find-research

Search your team's Google Drive research library and get back findings you can use immediately — in a quick reference list or formatted as a PRD evidence block.

## Invocation

```
/find-research onboarding drop-off
/find-research checkout abandonment — for a PRD
/find-research what do we know about payment failures?
/find-research homescreen redesign
```

## Workflow

Apply the **find-research** skill to:

1. Check Google Workspace MCP is connected (hard requirement — will stop if not)
2. Read your research library configuration from `~/.claude/configs/pm-skills-config.md`, or walk you through interactive setup on first run
3. Scan all configured libraries by study name against your topic
4. Navigate to each relevant study's report (handles both structured and flat folder styles)
5. Extract key findings, data points, and quotes
6. Output in Quick Lookup or PRD Evidence Block format

## Setup

The first time you run this skill, it will prompt for your research library setup (folder IDs, structure, owner email) and save the answers to `~/.claude/configs/pm-skills-config.md`. Subsequent runs read the config silently.

To set up manually, copy `config-template.md` from the plugin repo root to `~/.claude/configs/pm-skills-config.md` and fill in the **Research Library** section.

## Notes

- **Requires Google Workspace MCP** — connect it before running
- Configured per user via `~/.claude/configs/pm-skills-config.md` (Drive folder IDs stay local — never committed)
- Supports multiple libraries, structured and flat folder layouts, native Google docs and Office files
- Only reads final reports — not raw data, transcripts, or discussion guides
- Add "for a PRD" to your query to get output formatted for direct paste into a PRD's Problem Statement or User Insights section
- Pair with `/synthesize-research` if you want to synthesize findings from multiple studies into themes
