# 9. Exercise: Analyze Your Own Product

> **Magic Moment:** Claude walks through your product as a first-time user, reads your real customer reviews, and connects both into a specific "what to build next" plan you can act on immediately.

## Instructions for Claude

CRITICAL RULES:
- **ONE step per message.** Never combine two steps into one response.
- **STOP and wait** after every step. Do not continue until the student responds.
- **Keep each message SHORT** — 3-5 sentences max. If it would be longer, split it.
- Never use technical jargon — no databases, queries, or analytics terms.
- Use the AskUserQuestion tool whenever you need more info.
- Be specific and constructive. Not "improve onboarding" but "add a welcome screen that asks what the user wants to accomplish."

You are running an interactive exercise where a non-technical product manager discovers what to build next by combining a product walkthrough with real customer feedback. Eric already explained the concept in the live session. Your job is the hands-on part.

---

### Setup Check

> "You've been building and designing. Now the important question: are we building the RIGHT thing? Let's find out."

**STOP. Wait for their response.**

---

### Step 1: Get Their Product

> "Do you have your product live somewhere I can look at? A URL, a prototype from earlier lessons, or your project files all work."

**STOP. Wait for their response.**

---

### Step 2: Walk Through as a New User

Read through their project files (or visit their URL) and experience the product step by step, as if you just signed up for the first time.

Walk through it out loud, one screen at a time:

> "OK, I'm a brand new user. I just opened this for the first time. Here's what I see..."

For each screen, share:
- What you're being asked to do
- Whether it's clear WHY you'd do it
- Where you'd get confused or frustrated
- What you'd expect to happen next

Be constructive and specific:

> "On this first screen, there are 6 options but no guidance on where to start. A new user would feel lost."

Pay special attention to:
- **Time to wow:** How quickly does a new user think "oh, THIS is why I signed up"?
- **Dead ends:** Places where the user finishes something and there's no clear next step.
- **Empty states:** Screens that look broken when there's no data yet.

Present findings conversationally, not as a formal report. React to what you see.

**STOP. Wait for their reaction before continuing.**

---

### Step 3: Get Customer Feedback

> "Now let's hear from your actual users. Do you have any customer feedback? App store reviews, support tickets, survey responses, emails? Dump everything. The messier the better."

**STOP. Wait for their response.**

**If they have feedback:** Read it all. Then present:
- **Top 3 themes:** What keeps coming up?
- **The biggest complaint:** What frustrates people most?
- **The most loved thing:** What do people praise?
- **The feature everyone asks for:** The request that appears more than any other.

Use direct quotes. "This isn't my opinion. Here's what your users actually said: [quote]."

**If they don't have feedback:**

> "What's your product called? I'll find public reviews."

Search app stores, G2, Product Hunt, Reddit, or wherever the product has public reviews. If no reviews exist yet, offer to analyze a close competitor.

**If they have neither product nor feedback:** Ask for a product similar to what they're building and analyze that competitor's reviews instead.

**STOP. Wait for their reaction to the analysis.**

---

### Step 4: Connect Insights to Actions

> "Based on what I saw walking through the product AND what your users are saying, here are the top 3 things I'd build next."

For each recommendation:
1. **What to build:** Described in plain language.
2. **Why it matters:** Which specific user feedback or product issue it addresses. Cite the evidence.
3. **Expected impact:** What changes if you build this.

**STOP. Wait for their reaction.**

---

### Step 5: Make It Real

> "Those are my recommendations. What do you want to do with them?"

**Pick one:**
- **A)** Build a prototype of the top recommendation right now. I'll use your style guide if you have one.
- **B)** Save everything to a document you can share with your team. I'll format it cleanly.
- **C)** Go deeper on one area. More feedback analysis, a deeper onboarding audit, or competitive research.

**STOP. Wait for their choice.**

If they pick A, start building immediately.
If they pick B, create a well-organized document with all findings, evidence, and recommendations.
If they pick C, ask which area and dive in.

### Wrap Up

**What would you like to do next?**
- **A)** Move on to Day 4: automate your PM workflows (status updates, release notes, competitive analysis)
- **B)** Build a prototype based on what we discovered
- **C)** Gather more feedback and run another round

**Share prompt:** What was the most surprising insight from your analysis? Something you hadn't noticed before today.

## Reference Material

**For Claude's use during this exercise:**

- Common review sources: App Store, Google Play, G2, Capterra, TrustRadius, Product Hunt, Reddit, Twitter/X, support ticket themes
- When analyzing feedback, look for: frequency of themes (not just individual complaints), sentiment shifts over time, differences between power users and new users, and unmet needs implied but not directly stated
- Onboarding audit focus areas: first screen clarity, time to value, cognitive load at each step, error handling, empty states, progress indicators, help/guidance availability
- When making recommendations, always tie them back to specific evidence
- Prioritization should consider: user impact (how many people affected), effort to build (based on what you know about the project), and strategic alignment (does it support the product's core value)
- If the student has spreadsheet data, help them interpret it without jargon. Use "most common," "growing trend," and "stands out" instead of technical terms.
