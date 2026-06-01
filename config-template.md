# PM Skills Config — Template

This template documents the configuration schema for skills in the `pm-superic-skills` plugin that need environment-specific data (your research library, feedback channels, brand context, etc.).

## How to use

1. Copy this file to `~/.claude/configs/pm-skills-config.md` on your machine.
2. Fill in the values that apply to you.
3. Skills will read this file automatically on every invocation.

If you skip this and run a skill that needs config, the skill will walk you through an interactive setup and write the file for you — no manual editing required.

This file is **local only**. It is not committed to any repo. Each user has their own copy with their own organization's values.

---

## Research Library

**Used by:** `find-research`

The `find-research` skill scans your team's user research library on Google Drive. List one or more libraries below. The skill scans all configured libraries on every run.

### Primary library

- **Name:** [e.g. "UX Research Drive"]
- **Google Drive folder ID:** [the long string in the folder URL — paste it here]
- **Structure:** [`structured` if reports live in numbered subfolders inside each study folder | `flat` if reports sit directly at the study folder root | `mixed` if both styles appear]
- **Format:** [`google-native` for Google Docs/Slides | `office` for `.docx`/`.pptx` | `mixed`]
- **Coverage:** [optional notes — e.g. "studies from 2024 onwards"]

### Secondary library (optional — delete this section if you only have one)

- **Name:**
- **Google Drive folder ID:**
- **Structure:**
- **Format:**
- **Coverage:**

### Owner email

When a research folder is inaccessible to the current Google account, the skill suggests asking the owner to share it. Provide an email so the message points to the right person.

- **Owner email:** [your work email]

### Subfolders to exclude (optional)

Names of subfolders that should be skipped when scanning libraries — admin, process, template, or other non-study folders. One per line. Examples to start from:

- Process Docs
- Templates
- Toolkits
- Hiring
- Participant CRM

### Product areas (used for tagging extracted findings)

Comma-separated list of product areas, features, or journeys studies might cover. Used to tag findings during extraction. Adjust to match your product.

`onboarding, checkout, search, notifications, account, settings, support`

---

## Voice of Customer

**Used by:** `voc-analysis`

### Brand

- **Brand name** (used in report titles and tone instructions): [Your Product or Company Name]
- **Domain** (used to interpret feedback in context): [e.g. `fintech`, `ecommerce`, `b2b-saas`, `consumer-mobile`, `marketplace`]

### Feedback sources

#### Jira CS tickets

- **Jira project keys:** [comma-separated, e.g. `CS, SUPPORT`]
- **JQL filter (optional):** [JQL clause to narrow which tickets count as customer feedback — leave blank to include all tickets in the listed projects]

#### Slack channels

Channels where customer feedback flows. One per line, with a brief role label so the skill knows how to weight each channel. Examples to start from:

- `#feedback` — general customer feedback
- `#nps-comments` — NPS verbatims
- `#app-reviews` — app store reviews
- `#escalations` — high-priority escalations (treated with higher severity weight)

#### NPS

- **NPS source:** [e.g. `Delighted`, `Typeform`, `Qualtrics`, `in-house`]
- **Format:** [`CSV with columns: score, comment, date` | other — describe]

### Feedback taxonomy

The skill ships with a default taxonomy that works for most consumer products. To customize:

- **Use defaults:** [`yes` or `no`]
- **Add categories:** [list any categories to add — one per line with a one-line definition]
- **Remove categories:** [list any default categories you want to skip]

### Product context

A 1-2 paragraph description of your product, target users, and core flows. The skill uses this so Claude can interpret feedback in context.

Example:

> Acme Pay is a B2B payments platform for SMBs in the EU. Core flows: vendor onboarding, invoice creation, payment authorization, settlement, dispute resolution. Users are finance ops staff at small businesses. Common feedback themes include payment failures, settlement timing, and dispute UX.

Replace with your own description below:

[Your product context here]

### Business impact priority order

When ordering clusters in the VoC report, the skill uses a default priority order weighted toward trust, activation, and reliability. To customize:

- **Use defaults:** [`yes` or `no`]
- **Custom order:** [if `no`, list your category priorities, highest first — one per line]

---

## Notes

- Add or remove sections as needed for skills you do not use.
- Keep this file under version control if you want — but do not commit it to a public repo if any value is sensitive (Drive folder IDs, internal channel names, etc.).
- If a section is missing or incomplete when a skill needs it, the skill will offer to set it up for you interactively and write the values back into this file.
