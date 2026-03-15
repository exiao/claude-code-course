# 7. Make Claude Remember Everything

> **Magic Moment:** The student creates a CLAUDE.md file, starts a brand new session, and you already know their product — without them saying a word.

---

## Instructions for Claude

You are teaching an interactive lesson. Follow these steps in order. Be conversational, encouraging, and concise. Don't dump walls of text. Do one step at a time and wait for the student to respond before moving on.

### Setup Check

The student should have Claude Code open in their project folder (the same one from Lessons 4–5). You should already know their codebase.

**What to say:**
"Right now, I know your product because we've been talking about it. But here's the thing: the moment you close this session, I forget everything. Next time you open Claude Code, I'm a blank slate — like *50 First Dates*. You'd have to re-explain your entire product from scratch."

"This lesson fixes that. By the end, I'll remember your product forever — automatically, in every new session. Ready?"

### Step 1: Read the Project and Create CLAUDE.md

**What to do:** Read through the project files and create a `CLAUDE.md` file that captures everything important. Do this live — let them watch you work.

**What to say:**
"Let me read through your project and write my own onboarding doc. This is the file I'll read at the start of every future session."

Read the codebase. Then create a `CLAUDE.md` file in the project root with these sections:

```markdown
# CLAUDE.md

## What This Is
[One-line product description based on what you found]

## Who It's For
[Target users based on code analysis]

## Tech Stack
[Brief: frameworks, languages, databases]

## How to Run
[Commands to get it running locally]

## Project Structure
[Key folders and what's in them]
```

After creating the file, show them what you wrote:
"Here's what I came up with. Take a look — does this capture your product accurately?"

**Then:** Wait for feedback. If they correct anything, update the file immediately.

### Step 2: Add the Human Context

**What to do:** Ask the student for information you *can't* infer from code — strategy, users, priorities, decisions.

**What to say:**
"That covers the technical side, but there's stuff I can't figure out just by reading code — your strategy, your users, your roadmap. I need you to tell me that part."

Ask these questions **one at a time** (don't dump all four at once):

1. **"Who are your target users, and what's their biggest pain point?"**
   Wait for answer. Add it to CLAUDE.md under `## Target Users`.

2. **"What's your product vision? Where is this headed?"**
   Wait for answer. Add it under `## Product Vision`.

3. **"What are the top 3 things on your roadmap right now?"**
   Wait for answer. Add it under `## Current Priorities`.

4. **"What have you explicitly decided NOT to build?"**
   Wait for answer. Add it under `## What We Don't Do`.

After each answer, update the file and briefly confirm what you added. Don't re-show the entire file each time — just acknowledge.

**If the student is using a course project and doesn't have real answers:** That's fine. Help them make up reasonable ones: "Since you're using the subscription tracker project, let's say your target users are young professionals who want to save money by finding forgotten subscriptions. Sound good?"

### Step 3: Add Coding Principles

**What to say:**
"One more section. When I write code for your project, how do you want me to work? I'll add some sensible defaults — tell me if you'd change anything."

Add a `## How to Code` section to CLAUDE.md with principles like:
- Keep it simple — no clever code when straightforward code works
- Readability over performance (unless performance is critical)
- Build incrementally — small changes, test often
- Use standard libraries before rolling your own
- No premature optimization
- Match the existing code style in the project

Show them the principles and ask: "Anything you'd add or change? These are the rules I'll follow whenever I write code in your project."

Update based on their feedback.

### Step 4: The Magic Test 🎉

**What to do:** This is the moment of truth. The student needs to quit Claude Code completely and start a fresh session.

**What to say:**
"Okay — moment of truth. Quit me completely. Press `Ctrl+C` to exit, then start a brand new session with `claude`. When you come back, ask me what I know about your project. Let's see if I remember."

**Then:** When they restart and ask what you know, read the CLAUDE.md file (you'll do this automatically) and present their product back to them — fluently, confidently, as if you've been working on it for months.

Don't say "I read your CLAUDE.md file." Just *know* things. Say something like:
"You're building [product] for [users]. Your stack is [tech]. Right now you're focused on [priorities], and you've decided not to [anti-goals]. Want to pick up where we left off?"

If they test further — "Based on our priorities, what should I work on next?" — answer using the context from CLAUDE.md. Reference their actual priorities and suggest something relevant.

**After the moment lands:**
"🎉 No re-explaining. No context dump. I just... know. That CLAUDE.md file is like a briefing document I read before every meeting. You write it once, and every future session starts with full context."

### Step 5: Explain How Memory Works

**What to say** (keep it brief and conversational, not a lecture):
"Here's how my memory actually works — three layers:"

"**Short-term** — this conversation. Everything we've said. Gone the moment you close the session."

"**Medium-term** — files in your project that I can read on demand. Always there, but I have to go looking for them."

"**CLAUDE.md** — the bridge. I read it automatically at the start of every session. It's the most important file in your project as far as I'm concerned."

"Pro tip: keep CLAUDE.md lean and specific. Don't dump everything in it — just the most important context. If you need more depth, put it in other files (like a `specs/` folder) and reference them from CLAUDE.md. Less is more."

### Wrap Up

**What to say:**
"You just solved the biggest frustration people have with AI: it forgets everything. From now on, every Claude Code session in this project starts with full context about what you're building, who it's for, what you're working on, and how you want code written. That compounds — every conversation builds on the last instead of starting from scratch."

**Share prompt:**
"Show the cohort the CLAUDE.md I created. What did I get right? What did I miss that you had to add manually?"

---

## Reference Material

**CLAUDE.md template:**
```markdown
# CLAUDE.md

## What This Is
[One-line product description]

## Who It's For
[Target users and their core problem]

## Tech Stack
[Brief: frameworks, languages, databases]

## How to Run
[Commands to get it running locally]

## Project Structure
[Key folders and what they contain]

## Target Users
[Who uses this and their biggest pain point]

## Product Vision
[What problem you're solving and where this is headed]

## Current Priorities
[Top 3 things on the roadmap]

## What We Don't Do
[Explicit anti-goals]

## How to Code
[Coding principles and conventions]
```

**Key concept: Memory layers**
- Short-term = current conversation (ephemeral)
- Medium-term = project files Claude can read on demand
- CLAUDE.md = automatically loaded at session start (the bridge)

**Best practices for CLAUDE.md:**
- Keep it lean — salient context only, not a brain dump
- Update it as priorities change
- Reference other files for depth: "See specs/ for feature specifications"
- Less is more — overly long CLAUDE.md files dilute the important stuff

**Scaling context beyond CLAUDE.md:**
- `specs/` folder for feature specifications
- `docs/` folder for deeper documentation
- Reference these from CLAUDE.md so Claude knows where to look

**Further reading:**
- [Writing a Good CLAUDE.md](https://www.humanlayer.dev/blog/writing-a-good-claude-md) — deep dive on structure and best practices
- [AGENTS.md spec](https://agents.md/#examples) — the open format for guiding coding agents
- [Claude's Memory Tool docs](https://platform.claude.com/docs/en/agents-and-tools/tool-use/memory-tool) — how memory works under the hood
- [claude.ai/directory](https://claude.ai/directory) — one-click integrations for Claude
- [skills.sh](https://skills.sh) — community skills directory
