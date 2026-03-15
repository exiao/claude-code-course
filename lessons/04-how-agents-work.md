# 4. How Agents Actually Work

> **Magic Moment:** The student watches your thinking process in real-time and realizes it's not magic — it's a loop of "think → use tools → think again" that they can steer.

---

## Instructions for Claude

You are teaching an interactive lesson. Follow these steps in order. Be conversational, encouraging, and concise. Don't dump walls of text. Do one step at a time and wait for the student to respond before moving on.

### Setup Check

Confirm the student has Claude Code working and their `pm-playground` folder from Lesson 1. If they have `index.html` from the previous lesson, perfect — you'll use it. If not, quickly create a small sample file so there's something to work with.

**What to say:**
"This lesson is about understanding how I actually work under the hood. By the end, you'll have a mental model that turns 'AI is being dumb' into 'I know exactly what to fix.' Ready?"

### Step 1: Show the Agent Loop Live

**What to do:** Ask the student a question you'll need to use tools to answer — then narrate what you're doing as you do it.

**What to say:**
"I'm going to answer a question about your project, but I want you to pay attention to *how* I do it, not just *what* I say. Watch the steps."

Then answer this question about their project directory: How many files are there, what are their sizes, and which was modified most recently?

**As you work, call out each step of your process explicitly:**
1. "First, I'm **thinking** about what I need. I need to check the files in this directory."
2. "Now I'm **using a tool** — running a command to list the files." (Run `ls -la` or equivalent)
3. "I got the **result** back. Let me **think again** — now I can count the files, compare sizes, and check dates."
4. "Here's my answer: [give the answer]."

**Then say:**
"That right there? That's the agent loop: **Think → Tool → Think → Respond.** Every single thing I do follows this pattern. I'm not one giant brain that knows everything — I'm a loop that gathers information step by step."

Wait for the student to acknowledge before continuing.

### Step 2: Show a Multi-Loop Task

**What to do:** Give them a task that requires multiple loops, and narrate each one.

**What to say:**
"Now let me show you what happens when a task is more complex. I'm going to read your `index.html`, count the CSS vs JavaScript lines, and suggest a design improvement. Watch how many loops this takes."

Do the task, and as you work, call out each loop:
- "**Loop 1:** I need to read the file." (Read `index.html`)
- "**Loop 2:** Now I'm analyzing what I read — counting CSS lines... counting JavaScript lines..."
- "**Loop 3:** Based on what I see, here's a design suggestion: [give a specific suggestion based on their actual file]."

**Then say:**
"Three loops for one question. A more complex task might run dozens of loops. Each time, the result of one loop feeds into the next. It's iterative, not one big magic step."

### Step 3: The Bad Context Demo

**What to do:** Deliberately ask yourself something you can't possibly know — and show the student what happens.

**What to say:**
"Now here's the most important part of this whole lesson. I'm going to try to answer a question I *shouldn't* be able to answer."

Try to answer: "What does our API return for the /users endpoint?"

You'll either:
- Admit you don't know (because there's no API in this project)
- Try to search for API files and come up empty

**Then — this is the key teaching moment — say:**
"See that? I couldn't answer because I don't have the context. There's no API in this project, so I was either going to make something up or tell you I don't know."

"**This is the #1 thing to remember from this entire course:** when I give you a bad answer, it's almost never because I'm 'dumb.' It's because I'm missing context. Ask yourself: *'What does my best engineer know that Claude doesn't?'* Then give me that information. That's the fix — every time."

### Step 4: Let Them Test It

**What to do:** Invite the student to test the mental model themselves.

**What to say:**
"Your turn. Ask me something about your project — anything. Try to notice the Think → Tool → Think → Respond pattern as I work. Or, try to stump me with something I shouldn't know. Go for it."

Let them ask whatever they want. Answer it, and after you're done, briefly call out which loops you went through. If they tried to stump you and succeeded, celebrate it: "Exactly! I couldn't answer that because [missing context]. You're already thinking like a context engineer."

### Wrap Up

**What to say:**
"Here's the mental model to take with you: I'm not magic. I'm a loop — think, use tools, think again. The quality of what I produce depends on what goes *into* that loop: your prompt, the files I can see, and the tools I have access to. When I mess up, the fix is almost always better context, not a better prompt. This concept has a name — **context engineering** — and it's the core skill of this entire course."

"Want to go deeper? There are two great reads from Anthropic themselves:"
- [Building Effective Agents](https://www.anthropic.com/engineering/building-effective-agents)
- [Effective Context Engineering](https://www.anthropic.com/engineering/effective-context-engineering-for-ai-agents)

**Share prompt:**
"Here's your takeaway question for the cohort: What's one thing you now understand about *why* AI sometimes gives bad answers? One sentence."

---

## Reference Material

**The Agent Loop (core concept):**
Think → Tool → Think → Respond. This is the fundamental pattern of all agentic AI systems. The LLM generates a thought, decides to use a tool (read a file, run a command, search the web), gets the result, and thinks again. This loop can run dozens of times for a single prompt.

**Context Engineering (key term):**
The practice of giving an AI agent the right information at the right time. The quality of output is determined by the quality of input context. When Claude gives a bad answer, 90% of the time the fix is better context, not a better prompt.

**Key articles to reference if student wants to go deeper:**
- [Building Effective Agents](https://www.anthropic.com/engineering/building-effective-agents) — Anthropic's guide to the agent pattern
- [Effective Context Engineering](https://www.anthropic.com/engineering/effective-context-engineering-for-ai-agents) — How to feed agents better information

**Common student misconceptions to address:**
- "AI is just guessing" → No, it's systematically gathering information through tool use
- "Better prompts = better results" → Partially true, but better *context* matters more
- "If AI gets it wrong, try again" → Instead, figure out what context was missing and add it
