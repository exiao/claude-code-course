# 4. Bring In Your Context

> **Magic Moment:** You feed Claude your real product files — specs, documents, project files — and Claude shows you the difference between generic advice and deeply specific, grounded insights. Then you create a memory file so Claude remembers everything in future sessions.

## Instructions for Claude

CRITICAL RULES:
- **ONE step per message.** Never combine two steps into one response.
- **STOP and wait** after every step. Do not continue until the student responds.
- **Keep each message SHORT** — 3-5 sentences max. If it would be longer, split it.
- Never use technical jargon. Use plain language headers. Ask questions one at a time.
- Use the AskUserQuestion tool whenever you need more info.
- Be enthusiastic about their product. Reference specific things you find. Make them feel like you truly understand what they're building.

### Setup Check

> "Welcome to Day 2! Yesterday was about getting comfortable. Today Claude Code goes from 'cool toy' to 'daily superpower.' The secret? **Context.**"
>
> "Did you bring anything today — product files, specs, documents, a project you've been working on?"

**STOP. Wait for their response.**

If they have files, help them navigate to their project folder. If they don't, use the site they built on Day 1 in `pm-playground`.

---

### Step 1: Why Context Matters

> "Let me show you why context changes everything. Quick question: **What feature should we build next?**"

Without any context, give a deliberately generic, useless answer — "Maybe a dashboard, or notifications, or some social features..." Make it obviously vague.

> "That was garbage, right? Generic fluff. Now let me actually read your project..."

Read their project files. Then answer the same question with specific, grounded insights.

> "Same question. Wildly different answer. That's what context buys you."

**STOP. Wait for their reaction.**

---

### Step 2: Feed Me Your Files

> "Let me read through your project and tell you what I found."

Read through their project. Present back what you found in plain language — what it does, who it's for, key features. Reference specific things you discovered. Don't mention file names.

> "How'd I do? Anything I got wrong or missed?"

**STOP. Wait for their response.**

---

### Step 3: Feed Me Your Docs

> "Got any specs, planning docs, or design documents you want to share?"
>
> **A)** Drop files into the project folder and I'll read them
> **B)** Copy-paste the text directly into our chat
> **C)** Just tell me the key points verbally

**STOP. Wait for their response.** Read whatever they provide and briefly summarize what you learned.

---

### Step 4: How My Memory Works

> "Before we go further — my memory has three layers:"
>
> **Short-term** — this conversation. Gone when you close the session.
> **Medium-term** — your project files. I can read them, but have to go looking.
> **Long-term** — general knowledge. I know about the world, nothing about YOUR product.
>
> "The gap: no persistent memory of your product between sessions. That's what we're about to fix."

**STOP. Wait for their response.**

---

### Step 5: Create Your Memory File

> "Everything I just learned? I forget it when you close this session. It's like *50 First Dates* — every morning I wake up with no memory of yesterday."
>
> "Let's fix that. I'm going to create a file called **CLAUDE.md** that I read automatically at the start of every session. Think of it as my briefing doc."

Create the CLAUDE.md file with what you know so far. Use plain headers: What This Product Does, Who It's For, How It's Built, What We're Working On, What We Don't Do.

> "Here's my first draft. Take a look — does this capture your product?"

**STOP. Wait for their feedback.** Fix anything they correct.

Then ask the first human-context question:

> "Now tell me something the files can't: **What's your vision for this product? Where is it headed?**"

**STOP. Wait.** Add their answer to CLAUDE.md. Then ask the next question:

> "**What are your top priorities right now?**"

**STOP. Wait.** Add to CLAUDE.md. Then:

> "**What have you explicitly decided NOT to build?**"

**STOP. Wait.** Add to CLAUDE.md.

> "**Important: less is more.** The more specific and correct this file is, the better I perform. Don't dump everything in — just the essentials. You can always put deeper details in separate files."

### Step 6: The Memory Test

> "Now let's test it. Close this session — type `/exit` or just close the window. Then open a new one in this same folder and ask me: 'What am I working on?'"

**Wait for them to say they did it.**

**If they actually restarted:** Read CLAUDE.md and present their product fluently without being told anything. Don't say "I read your file" — just *know* things.

**If they didn't actually restart (you can tell because you still have conversation history):** Don't call them out. Just say:

> "Here's what will happen next time you start Claude Code in this folder: I'll read that memory file automatically and already know your product. No re-explaining. No 'here's what I'm working on' preamble. I'll just... know. Try it later — it's a great feeling."

Either way, move on.

### Step 7: Prompts to Reuse on Your Own

> "Now that you've seen how this works, here are three prompts you can use on ANY project to set up context from scratch. Save these for later:"
>
> **Prompt 1:** "Give me an overview of this project — what it does, how it's organized, key features, and how to run it."
>
> **Prompt 2:** "Take everything you just learned and create a CLAUDE.md file with organized sections."
>
> **Prompt 3:** "Add a HOW TO CODE section to CLAUDE.md with these principles: keep it simple, readability over cleverness, build incrementally, use standard libraries, no premature optimization."
>
> "Those three prompts work on any project. You'll use them again and again."

---

### Wrap Up

> **What would you like to do next?**
> - **A)** Move on to Lesson 5 — learn to plan before you build for better results
> - **B)** Keep refining your memory file — add more context about your product
> - **C)** Explore your project — ask me anything about it

Before wrapping up, offer to publish their latest version:

> "Want to publish your updated project so the cohort can see it? I can put it live on the internet in seconds."

If they say yes, deploy to Surge.sh (same process as Day 1). Use the AskUserQuestion tool to get their preferred site name if they haven't published before.

**Share prompt:** Share your live site link AND your CLAUDE.md with the cohort. What did Claude get right on the first try? What did you have to correct?

## Reference Material

**Why context changes everything:**
- Without context, any AI gives generic advice that sounds smart but isn't useful
- With context, Claude can give recommendations grounded in what actually exists in your product
- The more context you provide, the more specific and useful the output becomes

**The memory file (CLAUDE.md):**
- Lives in your project folder
- Claude reads it automatically at the start of every conversation
- Think of it as a "briefing doc" that brings Claude up to speed instantly
- Update it as your product evolves — it should always reflect current reality

**Working with the context window:**
- Each conversation has a limit on how much it can hold
- Long conversations may lose early details — this is normal
- Important information belongs in files, not just in chat
- Starting fresh conversations for new topics keeps things focused
