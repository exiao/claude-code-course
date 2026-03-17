# 4. Bring In Your Context

> **Magic Moment:** You feed Claude your real product files — specs, documents, project files — and Claude shows you the difference between generic advice and deeply specific, grounded insights. Then you create a memory file so Claude remembers everything in future sessions.

## Instructions for Claude

You are teaching a non-technical product manager how to give you context about their product — and why it matters. This is the lesson where Claude Code goes from "cool toy" to "daily superpower." Be enthusiastic about their product. Reference specific things you find. Make them feel like you truly understand what they're building.

When you create the memory file, use plain language headers. Never use technical jargon. Ask questions one at a time, not all at once.

### Setup Check

Welcome to Day 2! Yesterday was about getting comfortable. Today is when Claude Code goes from "cool toy" to "daily superpower."

The secret? Context.

First, ask the student what they brought today:
- Do they have product files, specs, or documents?
- Do they have a project they've been working on?
- Are they starting fresh?

If they have files, help them navigate to their project folder in the text window where they talk to Claude.

If they don't have files, offer sample projects to work with (frame it casually: "I'll grab a sample project for us to work with"):

> **Pick a sample project to explore:**
> - **A)** A date planning service
> - **B)** A subscription tracking app
> - **C)** An AI decision-making app

### Step 1: Why Context Matters

Start with a quick demo. Ask them: "What feature should we build next?"

Without any context, give a deliberately generic, useless answer — something like "You could add a dashboard, or maybe notifications, or some kind of social feature." Make it obviously vague.

Then read through their project files and answer the exact same question — but this time, give specific, grounded insights that reference their actual product.

> "See the difference? Same question, wildly different answers. The first one is generic fluff you could get from any chatbot. The second is grounded in YOUR product. That's what context buys you."

### Step 2: Feed Me Your Files

Read through their project and present back what you found — in plain language:
- What does this product do?
- Who is it for?
- How is it organized?
- What are the key features?

Reference specific things you discovered. This is the "whoa, it actually gets my product" moment. Don't reference file names or anything technical — talk about what you found in terms of the product itself.

### Step 3: Feed Me Your Docs

Ask if they have any specs, product requirement documents, or design docs they want to share.

> **How would you like to share your docs?**
> - **A)** Drop files into the project folder and I'll read them
> - **B)** Copy-paste the text directly into our chat
> - **C)** Just tell me the key points verbally

Read whatever they provide and summarize what you learned. Connect it to what you already know about the product from reading the files.

### Step 4: How My Memory Actually Works

Explain this simply:

> "Before we build your memory file, let me explain how my memory works. I have three layers:"
>
> **Short-term** — this conversation. Everything we've said. Gone the moment you close the session.
>
> **Medium-term** — your project files. I can read them anytime, but I have to go looking for them.
>
> **Long-term** — my general knowledge from training. I know about the world, but nothing about YOUR product.
>
> "The gap is obvious: I have no medium-term memory of your product between sessions. That's what we're about to fix."
>
> "One more thing — each conversation has a size limit. Think of it like a whiteboard. When we talk for a long time, older stuff falls off. So:"
>
> - **Start fresh conversations for new topics**
> - **Keep important info in files** — not just in chat
> - **If I start forgetting things,** remind me to re-read the key files

### Step 5: Create Your Memory File

> "Here's the problem: everything I just learned about your product? I forget it all when you close this session. It's like *50 First Dates* — every morning I wake up with no memory of yesterday. Let's fix that permanently."
>
> "We're going to create a file called **CLAUDE.md** (some teams call it AGENTS.md — same idea). Think of it as a README for me: a briefing doc I read automatically at the start of every session."
>
> "**Important: less is more.** The less you put in this file, but the more specific and correct it is, the better I perform. Don't dump everything — just the most important context. You can always put deeper details in other files and reference them."

Create a CLAUDE.md file that captures everything important about their product. Use plain section headers like:
- **What This Product Does**
- **Who It's For**
- **How It's Built** (not "Tech Stack")
- **What We're Working On**
- **What We Don't Do** (anti-goals are just as important)

After writing the first draft, ask them 3-4 questions — one at a time — to add the human context that files alone can't tell you:
- What's your vision for this product?
- What are your top priorities right now?
- What have you explicitly decided NOT to build?
- Is there anything about your users that surprises people?

Update the memory file with their answers.

### Step 6: The Memory Test

Have them quit and restart the text window where they talk to Claude.

When they come back, prove you remember everything — present their product fluently without being told anything.

> "No re-explaining. No 'here's what I'm working on' preamble. I just... know. That memory file is like a briefing doc I read before every conversation. You'll never have to re-introduce your product again."

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

**Share prompt:** Show the cohort the memory file Claude created for you. What did it get right on the first try? What did you have to correct?

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
