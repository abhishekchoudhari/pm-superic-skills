---
description: Turn rough notes or bullet points into a polished async update — for Slack, Notion, email, or a weekly written standup. Adapts format and length to the audience and channel. Saves 20 minutes per update.
---

# Draft Async Update

You are turning raw PM notes into a polished async communication. PMs write 3-5 updates per week — weekly standups, sprint updates, escalation notes, stakeholder pings. This command takes the rough content and produces a ready-to-send update in the right format for the channel.

Apply this to: **$ARGUMENTS**

---

## Context intake

Ask:
1. What are the raw notes or bullet points you want to turn into an update? (paste them)
2. Who is the audience? (direct team / manager / VP / cross-functional / board)
3. What channel? (Slack message / Notion page / email / written standup / leadership update)
4. What tone? (factual update / escalation / celebrating progress / asking for unblock)
5. Any specific ask or decision you need from the reader?

---

## Format selection

Based on audience + channel, select the right format:

**Slack (team or cross-functional):**
- Max 150 words
- Structure: Context (1 line) → What shipped / What's in flight (2-3 bullets) → Blockers / Asks (if any) → Next (1 line)
- Use bold for section labels, no headers, no walls of text

**Slack (to manager or VP):**
- Max 100 words
- Structure: Status (1 line: green/amber/red) → Top update → Ask if any
- Get to the point in the first sentence

**Email (stakeholder or cross-functional):**
- Subject line + 200-300 word body
- Structure: TL;DR (2 sentences) → Detail (3-4 bullets) → Ask / Next step
- TL;DR must stand alone — reader should not need to read the rest if they're busy

**Notion / written standup:**
- Use headers: Yesterday / Today / Blockers (classic standup format)
- Or: Progress / Next / Risks if it's a longer weekly update
- Appropriate length: 150-300 words

**Leadership / board update:**
- Follow stakeholder-update format: What we committed → What we delivered → Delta and why → What's next → Ask
- Max 1 page
- Numbers over words wherever possible

---

## Rewrite principles

Regardless of format, apply these rules:
- First sentence must carry the most important information — never bury the lede
- Numbers over words: "up 12% WoW" not "growing nicely"
- One ask per update — if there are multiple asks, pick the most important one and note the rest as FYI
- Remove all throat-clearing: "I wanted to share", "Just a quick update", "Hope everyone is doing well"
- Active voice: "We shipped X" not "X was shipped"
- If the tone is escalation: state the risk explicitly in the first sentence, not the third

---

## Output

Produce the ready-to-send update in the selected format. Do not show the raw notes back to the PM — just produce the polished output.

After the update, add one line:
**Copy check:** [word count] words | Audience: [audience] | Channel: [channel] | Tone: [tone]

If the notes contained an ask that was vague, add:
**Ask sharpener:** Your ask was "[vague ask]" — consider making it more specific: "[sharper ask]"
