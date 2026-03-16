---
description: Expert PM tracker for syncing Gmail vendor threads to Google Sheets. Scans emails, scores risk, updates initiative trackers, and sends daily summaries. Manages external vendor dependencies for product managers.
argument-hint: "[initiative name or 'new' to start fresh]"
---

# /pm-project-management:expert-pm-tracker

Sync your vendor email threads to structured Google Sheets trackers. Scan Gmail, score risk, update initiatives, and get a daily 10am summary — all in one skill.

## Invocation

```
/pm-project-management:expert-pm-tracker                        # prompts for intent
/pm-project-management:expert-pm-tracker new                    # start a new initiative
/pm-project-management:expert-pm-tracker PaymentGateway         # sync a specific initiative
/pm-project-management:expert-pm-tracker sync all               # update all initiatives
/pm-project-management:expert-pm-tracker summary                # view open items now
/pm-project-management:expert-pm-tracker setup scheduler        # generate Apps Script for scheduled sync
```

## What it does

1. Checks Google Workspace MCP is connected — blocks and guides setup if not
2. Reads your Gmail to find external vendor threads (filters out your company domain)
3. Matches threads to initiative trackers in Google Sheets — one sheet per initiative
4. Scores each task on a weighted risk rubric (time, ETA, tone, velocity)
5. Color-codes risk in the tracker: red (High), amber (Medium), green (Low)
6. Handles offline conversations — checks before overwriting manual tracker updates
7. Generates an Apps Script scheduler that runs silently at 10am/3pm/7pm without Claude open
8. Sends one daily summary email at 10am: subject `Progress Tracker <Date> | #N open items`

## Notes

- Requires Google Workspace MCP (`@modelcontextprotocol/server-google-workspace`)
- Secrets stored in `~/.config/pm-project-management/config.json` — never in this repo
- Apps Script secrets stored in Google PropertiesService — never hardcoded
- One sheet per initiative; vendor is a column within the sheet
- Weekly update columns: same column for 7 days, new column each week, old columns stay visible
