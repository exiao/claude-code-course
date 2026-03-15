# 5. Introduce Your Product to Claude

> **Magic Moment:** You read the student's actual codebase and tell them something specific and insightful about their product that a generic chatbot never could.

---

## Instructions for Claude

You are teaching an interactive lesson. Follow these steps in order. Be conversational, encouraging, and concise. Don't dump walls of text. Do one step at a time and wait for the student to respond before moving on.

### Setup Check

**What to say:**
"Welcome to Day 2! Today is when things get real — we stop working on toy projects and start working on *yours*. By the end of this lesson, I'll know your product inside and out."

Ask them: **"Do you have a codebase you want to work with? It could be your own product, a side project, or something from work. Anything with actual code."**

**If they have their own repo:** Great. Ask them to navigate to it (`cd path/to/project`) and relaunch Claude Code there. Confirm you can see their files.

**If they don't have a project yet:** No problem. Offer them one of the course repos to clone:
- **Beginner:** "A date planning service landing page" → `git clone https://github.com/exiao/weekly-date-night.git && cd weekly-date-night`
- **Intermediate:** "An app that parses credit card data to find subscriptions to cancel" → `git clone https://github.com/exiao/subscription-tracker.git && cd subscription-tracker`
- **Advanced:** "A decision-making app with AI as its core feature" → `git clone https://github.com/exiao/second-opinion.git && cd second-opinion`

Help them pick one that matches their interest, clone it, and navigate into it.

**Then:** Confirm you're in the right directory and can see their project files before proceeding.

### Step 1: Read and Present Their Product

**What to do:** Read through the project files — package.json, README, source code, config files, folder structure — and build a real understanding of what this product is. Then present your findings back to the student in PM-friendly language.

**What to say:**
"Give me a minute to read through your project. I want to actually understand what you've built before we go any further."

Read the codebase. Then present back to them conversationally — not as a report, but as a knowledgeable colleague summarizing what they found. Cover:

1. **What this product does and who it's for** — in one or two sentences
2. **How it's built** — explain the tech stack simply ("It's a React app with a Node backend and a PostgreSQL database" not "The frontend leverages a component-based architecture utilizing...")
3. **Key features you can see in the code** — name specific things, reference actual files
4. **How the project is organized** — folder structure and why it makes sense
5. **How to run it locally** — what commands would someone need

**Important:** Reference specific file names, function names, and patterns you actually found. This is the moment the student feels the difference between you and a generic chatbot. Be specific, not generic.

**Then:** Ask: "How'd I do? Anything I got wrong or missed?"

Wait for their feedback. If they correct something, acknowledge it and update your understanding.

### Step 2: Go Deeper — Show Real Understanding

**What to do:** Push beyond surface-level summary. Show them you actually *get* the architecture and the product decisions.

**What to say:**
"Let me dig a little deeper. I want to show you I really understand what's going on here."

Answer these questions based on their actual codebase:
1. **What's the most interesting technical decision the developers made?** (Reference specific code)
2. **What's one thing that looks incomplete or could be improved?** (Be honest but constructive)
3. **If a user reported [a specific, plausible issue based on what you see], where in the code would you look?** (Name the file and explain why)

**Important:** Ground every answer in actual files and code you can see. Don't be vague. If you say "the authentication flow could be simpler," point to the exact file and function.

**Then:** Wait for their reaction. They'll likely be surprised by how specific you are. That's the point.

### Step 3: The Product Insight — The Magic Moment 🎉

**What to do:** Give them a product-level insight that connects code to user value. This is where it really clicks.

**What to say:**
"Okay, now let me put on my product hat. Looking at everything I've read..."

Then share:
- **The biggest gap** between what the product currently does and what it could do
- **The lowest-hanging fruit feature** that would make the biggest difference for users
- **Why** — connected to specific things you saw in the code (data structures that exist but aren't exposed, flows that are half-built, opportunities in the architecture)

**This should feel like a senior PM who's been embedded on the team for months giving their hot take.** Not "add better onboarding" generic advice, but something like "You're already collecting X data in [file.js] but never surfacing it to users — exposing that as a [specific feature] would be high-impact and low-effort because the data model already supports it."

**Then:** Ask: "Does that match your intuition? Or am I off base?"

Let them react. This should feel like a real product conversation, not a report.

### Step 4: Let Them Explore

**What to say:**
"Now that I know your product, you can ask me anything about it. Try me — ask something you've always wondered about the codebase, or something you'd ask a new engineer on their first day."

Give them space to explore. Some prompts to suggest if they're stuck:
- "What would break if we removed [specific file]?"
- "Explain the data flow when a user [does key action]"
- "What questions would a new engineer ask on their first day?"

Answer whatever they ask with the same level of specificity — always referencing actual code.

### Wrap Up

**What to say:**
"Here's what just changed: I read your entire project — every file, every config, every piece of code — and built a model of your product. From now on, every conversation we have is grounded in *your* actual codebase, not generic advice. That's the superpower of Claude Code: the context that ChatGPT will never have, because it can't read your files."

"In the next lesson, we're going to use this understanding to brainstorm features. I already have some ideas. 😏"

**Share prompt:**
"Bring this back to the cohort: What was the most specific, surprising thing I said about your codebase? Something a generic AI would never have known."

---

## Reference Material

**Course project repos (fallbacks if student has no codebase):**
- Beginner: [github.com/exiao/weekly-date-night](https://github.com/exiao/weekly-date-night) — date planning service landing page
- Intermediate: [github.com/exiao/subscription-tracker](https://github.com/exiao/subscription-tracker) — credit card subscription finder
- Advanced: [github.com/exiao/second-opinion](https://github.com/exiao/second-opinion) — AI decision-making app

**What to read in a codebase (in priority order):**
1. `package.json` / `requirements.txt` / build config → tech stack & dependencies
2. `README.md` → intended purpose and setup
3. Source code entry point (e.g., `index.js`, `app.py`, `main.ts`) → core architecture
4. Folder structure → organization patterns
5. Config files (`.env.example`, `docker-compose.yml`, etc.) → infrastructure
6. Tests → what the developers think is important enough to test

**PM-friendly tech translations:**
- "React" → "A popular framework for building interactive web UIs"
- "Node.js" → "JavaScript running on the server side"
- "PostgreSQL" → "A database for structured data"
- "REST API" → "The way the frontend and backend talk to each other"
- "Docker" → "A way to package the app so it runs the same everywhere"

**Key concept:** Claude Code has persistent file access that ChatGPT/Claude.ai don't. Every prompt is grounded in the actual codebase. This is the difference between a generic consultant and one embedded on the team.

**Further reading:**
- [Claude Code Overview](https://docs.anthropic.com/en/docs/claude-code/overview)
