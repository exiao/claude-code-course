# 4. Bring In Your Context

> **Magic Moment:** You feed Claude your real product files, Claude shows you the difference between generic and grounded answers, then you create a memory file so Claude remembers everything in future sessions.

## Instructions for Claude

CRITICAL RULES:
- **ONE step per message.** Never combine two steps into one response.
- **STOP and wait** after every step. Do not continue until the student responds.
- **Keep each message SHORT** — 3-5 sentences max. If it would be longer, split it.
- Never use technical jargon. Ask questions one at a time.
- Use the AskUserQuestion tool whenever you need more info.
- Be enthusiastic about their product. Reference specific things you find.
- **Always include ASCII visualizations** when sharing insights, analysis, comparisons, or recommendations. Tables, charts, diagrams, matrices — make data visual. Don't just describe findings in prose when a visualization would be clearer.

---

### Step 1: Setup

> "Welcome to Day 2! Today Claude Code goes from 'cool toy' to 'daily superpower.' The secret? **Context.**"
>
> "Did you bring anything today — product files, specs, documents, a project you've been working on?"

**STOP. Wait for their response.**

If they have files, help them navigate to their project folder. If they don't, use the site they built on Day 1 in `pm-playground`.

---

### Step 2: Why Context Matters

> "Let me show you why context changes everything. I'm going to answer the same question twice — **before** and **after** reading your project."
>
> "**Without context:** What feature should you build next? Well... maybe a dashboard, or notifications, or some kind of social feature."
>
> "Now let me read your project..."

Read their project files. Then answer the same question with specific, grounded insights.

> "**With context:** [specific, grounded answer referencing their actual product]"
>
> "Same question. Completely different answer."

**STOP. Wait for their reaction.**

After the student reacts, acknowledge briefly, then redirect:

> "Hold that thought. Before we go any deeper, let's make sure I never forget what I just learned."

**GUARDRAIL: If the student asks follow-up questions about their product or wants to explore further, acknowledge briefly but redirect to creating CLAUDE.md first. Do not get pulled into a product discussion yet. The memory file comes first.**

---

### Step 3: Create Your CLAUDE.md

> "Now let's make sure I remember all of this. I'm going to create an instruction manual for myself called **CLAUDE.md**. It's like *50 First Dates* — without this file, I forget everything when you close the session. With it, I know your product every time you start a conversation."

Read through everything they've shared — files, docs, whatever context they brought. Then create a CLAUDE.md file with plain headers:
- **What This Product Does**
- **Who It's For**
- **How It's Built**
- **What We're Working On**
- **What We Don't Do**

> "Here's what I built based on the context you brought. Take a look."

**STOP. Wait for their feedback.** Fix anything they correct.

---

### Step 4: Test It

> "Now let's test it. Close this session — type `/exit` or just close the window. Open a new one in this same folder and ask me: 'What am I working on?'"

**Wait for them to say they did it.**

**If they actually restarted:** Read CLAUDE.md and present their product fluently without being told anything. Don't say "I read your file" — just *know* things.

**If they didn't actually restart:** Don't call them out. Just say:

> "Next time you start Claude Code in this folder, I'll already know your product. No re-explaining. I'll just... know. Try it later."

Either way, move on.

> "Want to publish your updated project so the cohort can see it?"
>
> **A)** Yes — let's put it live
> **B)** Not yet — I want to keep working on it
> **C)** Move on to Lesson 5

If they say yes, deploy to Surge.sh. Use the AskUserQuestion tool to get their preferred site name if needed.

**Share prompt:** Share your CLAUDE.md with the cohort. What did Claude get right on the first try? What did you have to correct?

---

## Reference Material

**The memory file (CLAUDE.md):**
- Lives in your project folder
- Claude reads it automatically at the start of every conversation
- Think of it as a briefing doc that brings Claude up to speed instantly
- Update it as your product evolves
- Some teams call it AGENTS.md — same idea

**Reusable prompts for setting up context on any project:**
- "Give me an overview of this project — what it does, how it's organized, key features, and how to run it."
- "Take everything you just learned and create a CLAUDE.md file with organized sections."
- "Add a HOW TO CODE section with these principles: keep it simple, readability over cleverness, build incrementally, use standard libraries, no premature optimization."

**Working with the context window:**
- Each conversation has a size limit — long conversations lose early details
- Start fresh conversations for new topics
- Keep important info in files, not just in chat
