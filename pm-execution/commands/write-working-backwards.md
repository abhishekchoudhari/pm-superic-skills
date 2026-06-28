---
description: Write an Amazon-style Working Backwards document — press release first, then internal FAQ. Forces customer-first clarity before any PRD is written. The most effective forcing function for catching wrong bets early.
---

# Write Working Backwards

You are writing a Working Backwards document. Before writing a PRD, write the press release that announces the finished product — from the customer's perspective, on launch day. If you can't write a compelling press release, you don't understand the product well enough to spec it. Then write the internal FAQ that captures every hard question the team will ask.

Apply this to: **$ARGUMENTS**

---

## Context intake

Ask:
1. What is the product or feature? (name and one-sentence description)
2. Who is the primary customer? (be specific — not "users", but which users, in which situation)
3. What problem does it solve? What is their current reality without this product?
4. What is the customer's life like after using this product? (the outcome, not the feature)
5. What are you most uncertain about? (the assumptions you haven't validated)

---

## Part 1: Press release

Write a press release as if the product has just launched. Format:

**[CITY], [DATE] — [Company name] today announced [Product name], [one-sentence description of what it does for the customer].**

**[2-3 sentences: The problem as the customer experiences it, in plain language. No jargon. Write this as if explaining to someone outside the industry.]**

**[2-3 sentences: What the product does and why it works — from the customer's perspective, not the engineering perspective. Focus on outcomes, not features.]**

**Quote from a customer (fictional but realistic):**
"[Write a quote that a real customer might say. It should describe the before/after transformation. It should not sound like marketing copy. If you can't write a believable customer quote, the value proposition is not clear enough yet.]"

**[1-2 sentences: Availability and call to action.]**

**Quote from a company leader (fictional but realistic):**
"[Write a quote from the PM or CEO. It should explain why the company built this and what it means for customers. It should not be corporate boilerplate.]"

---

## Part 2: Internal FAQ

Write answers to these 10 questions. These are the questions your team WILL ask — answer them now before they stop the project in review:

**Customer questions:**
1. Who exactly is the customer? (define the segment precisely — who is in, who is explicitly out)
2. What is the customer's specific problem today? What do they do instead of using this product?
3. How does this product make their life measurably better? What is the before/after in concrete terms?
4. Why would a customer choose this over the existing alternatives?

**Business questions:**
5. How does this make money? (or, if not directly: how does it serve a product that makes money?)
6. What does success look like at 3 months, 12 months? (specific metrics, not "grow user base")
7. What would make us stop building this? (what signal would tell us this is the wrong bet?)

**Build questions:**
8. What is the simplest version of this that still delivers the core value? (v1 scope forcing function)
9. What is the hardest technical or design problem to solve?
10. What assumption, if wrong, would invalidate the entire product?

---

## Part 3: Clarity check

After writing the press release and FAQ, run this check:

- **Customer quote test:** Does the customer quote sound like something a real person would say? If it sounds like marketing copy, the value proposition needs sharpening.
- **FAQ question 10 test:** Can you answer question 10 clearly? If not, this is the assumption that should be validated before the PRD is written.
- **Press release lede test:** Is the first paragraph written entirely from the customer's perspective with no internal jargon? If company-centric language crept in, rewrite it.

Output the check results with a recommendation: "Ready to write PRD" or "Resolve [specific issue] first."

---

## Notes

- This document is not a PRD. It is the input to a PRD. After completing this, run `/pm-os:build-evidence-prd` to write the full spec.
- The most common failure: the press release is written from the company's perspective ("we built X that does Y") instead of the customer's perspective ("customers can now Z"). Rewrite until the customer is the subject of every sentence.
- If the fictional customer quote feels forced or hollow, that is a signal the value proposition is not clear. Do not paper over it with better writing — fix the underlying clarity problem first.
