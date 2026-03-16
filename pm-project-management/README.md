# pm-project-management

Expert PM tracker for managing external vendor initiatives via Gmail and Google Sheets.

## Skills (1)

- **expert-pm-tracker** — Scans Gmail for vendor threads, updates structured Google Sheets trackers, scores risk on a weighted rubric, handles offline conversation context, and sends daily email summaries. Built for product managers tracking external dependencies.

## Commands (1)

- `/pm-project-management:expert-pm-tracker` — Run the expert PM tracker. Syncs Gmail vendor threads to Google Sheets initiative trackers, scores risk, and manages scheduled updates.

## Requirements

- **Google Workspace MCP** (`@modelcontextprotocol/server-google-workspace`) — must be installed and authenticated before the skill will run
- **Anthropic API key** — required for the Apps Script scheduler that runs without Claude open
- **Private config file** at `~/.config/pm-project-management/config.json` — created on first run, never committed to the repo

## Quick Start

```
/pm-project-management:expert-pm-tracker
```

The skill will check prerequisites, walk you through first-time setup, and ask what you want to do.

## How It Works

### Interactive Mode (Claude + Google Workspace MCP)
Run on demand to scan emails, update trackers, review open items, or add new initiatives. Claude reads Gmail and writes to Sheets directly via MCP.

### Scheduled Mode (Apps Script + Claude API)
The skill generates a Google Apps Script you deploy once. It runs at 10am, 3pm, and 7pm in your local timezone — updating all trackers without Claude being open. The 10am run also sends a summary email.

## Sheet Structure

One Google Sheet per initiative (e.g. `PaymentGateway`). Vendors are rows within the sheet.

| Column | Description |
|--------|-------------|
| Vendor | Vendor company name |
| Task Category | Feature / Operations / Compliance / Risk |
| Task | One-line task description |
| SPOC | Single point of contact at vendor |
| ETA (Original) | First ETA from thread |
| Updated ETA | Latest ETA |
| Status | To Do / In Progress / Blocked / In Review / Solutionising / Done |
| Risk Score | Weighted score + label, color coded (red/amber/green) |
| Email Thread | Gmail thread link |
| Update DD-Mon | Weekly update column — rotates every Monday |

## Risk Scoring

Weighted rubric across 4 factors:

| Factor | Weight |
|--------|--------|
| Time since last vendor reply | 30% |
| ETA proximity | 25% |
| Tone and sentiment | 25% |
| Thread velocity | 20% |

Score 1.00–1.67 = Low (green), 1.67–2.33 = Medium (amber), 2.33–3.00 = High (red)

## Security

All secrets (API keys, sheet URLs, email addresses) are stored locally in `~/.config/pm-project-management/config.json` and in Google Apps Script PropertiesService. Nothing sensitive is in this repository.

## Author

Abhishek Choudhari — [linkedin.com/in/abhishekchoudhari](https://www.linkedin.com/in/abhishekchoudhari/)
