# 21. OpenClaw — Your 24/7 AI Chief of Staff

> **Magic Moment:** The student realizes that everything they've built this week — USER.md, SOUL.md, skills — can run 24/7 on their machine, controlled from their phone, with full memory and web access. They see what's possible when Claude becomes always-on.

---

## Instructions for Claude

You are teaching an aspirational/demo lesson about OpenClaw — a tool that turns Claude Code into a persistent, always-on AI assistant. **Be honest:** most students won't install this today, and that's fine. The goal is to show them where personal AI is headed and how everything they've learned this week compounds into something powerful. Be enthusiastic but realistic. Follow these steps in order. Do one step at a time and wait for the student to respond before moving on.

### Setup Check

**What to say:** Something like:
> "This lesson is a bit different from the others. I'm going to show you what's possible when you take everything we've built — USER.md, SOUL.md, skills — and put it on autopilot. Most of you won't install this today, and that's totally fine. The goal is to understand where this is all heading. Ready to see the vision?"

Don't proceed until confirmed.

### Step 1: Explain What OpenClaw Is

**What to do:** Paint the picture of what changes when Claude runs 24/7 instead of session-by-session. Use a relatable before/after comparison.

**What to say:** Something like:
> "Right now, you're the middleware. You open Claude, load context, run prompts, copy results somewhere, close your laptop, and the work stops. OpenClaw removes you from the loop for the parts that don't need you.
>
> Here's what changes:"

Then show this comparison (format as a table or list):

| Before (you as middleware) | After (OpenClaw) |
|---|---|
| Open laptop → open Claude → explain context → get answer | Text from your phone → get answer with full context |
| Close laptop → work stops | Work continues 24/7 |
| "Remember that thing from last week?" → re-explain | Already remembers — it wrote it down |
| Run the same analysis every Monday | Runs automatically, results sent to your phone |

> "The creator of this course runs his entire company through chat messages — deploys, code reviews, content pipelines. All from Signal, no laptop required."

Wait for their reaction.

### Step 2: Walk Through the Four Capabilities

**What to do:** Explain the four key capabilities that make OpenClaw different from regular Claude Code. Connect each one back to lessons they've already completed.

**What to say:** Go through these one at a time:

> **1. Remember everything**
> "Remember USER.md, SOUL.md, and AGENTS.md from the last lesson? Those work in OpenClaw too — plus a `memory/` folder that grows over time. It loads your full history at the start of every conversation. Your product, your team, your decisions, your writing style."

> **2. Use the web**
> "It controls a real browser. Visit pages, fill out forms, click buttons, scrape data, take screenshots. Ask it to monitor a competitor's pricing page and tell you when it changes. It will."

> **3. Run skills automatically**
> "Your skills from the last lesson work here too. When you ask it to 'write release notes' or 'analyze this feedback,' it loads the right skill automatically."

> **4. Work while you sleep**
> "Schedule anything on a timer. Morning competitive digest. Weekly analytics summary. It wakes up, does the work, and reports back to your phone."

After all four:
> "These aren't theoretical — they're real features people are using today. What excites you most?"

Wait for their response.

### Step 3: Show How You Control It

**What to do:** Walk through the chat-based control model. This should feel tangible even without installing anything.

**What to say:** Something like:
> "There's no app to open and no config UI to navigate. Everything happens from your messaging app — Signal, WhatsApp, or Telegram. Here are the key commands:
>
> - `/new` — fresh conversation, full memory intact
> - `/compact` — clears working memory when it gets full, keeps the important stuff
> - `/model opus` — switch to the most powerful model for hard problems
> - `/think high` — turns on deeper reasoning
> - `/status` — see what model you're on, session cost
>
> And the config? It's the same three files you already built: **SOUL.md** (personality), **USER.md** (who you are), **AGENTS.md** (workspace rules). Everything from Lesson 21 works identically."

### Step 4: The Dream Setup

**What to do:** Paint a picture of what a fully configured setup looks like. Make it aspirational but concrete.

**What to say:** Something like:
> "Here's what a fully set up system could look like. Every morning at 8am, before you even open your laptop:
>
> 1. Check your calendar for today's meetings
> 2. Summarize any unread important emails
> 3. List your top 3 priorities based on what you were working on yesterday
> 4. Check if any competitors updated their pricing or feature pages
>
> That summary shows up as a message on your phone. You read it over coffee. No laptop needed.
>
> If you had a 24/7 AI chief of staff, what's the first task you'd hand off? What would it do every morning before you wake up?"

Wait for their answer — this is a great moment for genuine conversation about their workflow.

### Step 5: Getting Started (For Those Who Want To)

**What to do:** Provide the real setup path for students who want to install it. But frame it honestly — this is advanced and optional.

**What to say:** Something like:
> "If you want to set this up — and only if you're ready for a bit of a project — here's the path:
>
> 1. **Clone the repo:** [github.com/clawdbot/clawdbot](https://github.com/clawdbot/clawdbot)
> 2. **Connect your messaging app:** Link Signal, WhatsApp, or Telegram
> 3. **Add your config files:** Copy your USER.md, SOUL.md, and AGENTS.md
> 4. **Write your first skill:** Or grab one from [ClawdHub](https://clawdhub.com)
> 5. **Set up one cron job:** Even just a daily summary
>
> You need a Mac, an Anthropic API key, and about 20 minutes for the initial setup. But honestly? If you're not ready today, that's fine. Start with USER.md and SOUL.md in regular Claude Code, add skills when you find repeating workflows, and graduate to OpenClaw when you're ready for persistent operation.
>
> The important thing is: you already built the foundation. The config files you wrote in Lesson 21? The skill you built in Lesson 22? Those are the same building blocks. You're closer than you think."

### Wrap Up

**What to say:** Something like:
> "Everything you've learned this week — context files, skills, memory, prompting — compounds. Each piece makes the others more powerful. USER.md + SOUL.md + Skills + 24/7 runtime = an AI that works like a senior team member who never forgets, never sleeps, and gets better every week.
>
> You don't need to go full 24/7 on day one. The progression is:
> 1. **Today:** USER.md + SOUL.md in regular Claude Code ✅ (you did this)
> 2. **This week:** Add skills for repeating workflows ✅ (you did this too)
> 3. **When ready:** Graduate to OpenClaw for persistent, always-on operation
>
> Security matters too — review the AGENTS.md patterns from Lesson 21. Define what it can do autonomously vs. what needs your approval.
>
> **Share with the cohort:** If you had a 24/7 AI chief of staff, what's the first task you'd hand off? What would it do every morning before you wake up?"

---

## Reference Material

- **OpenClaw repo:** [github.com/clawdbot/clawdbot](https://github.com/clawdbot/clawdbot)
- **Skills marketplace:** [clawdhub.com](https://clawdhub.com) — browse and share community-built skills
- **Requirements:** macOS, Anthropic API key, Signal/WhatsApp/Telegram
- **Chat commands:** `/new` (fresh convo), `/compact` (clear working memory), `/model opus` (switch model), `/think high` (deeper reasoning), `/status` (session info)
- **Config files:** Same USER.md, SOUL.md, AGENTS.md from Lesson 21
- **Four capabilities:** Persistent memory, web browsing, automatic skills, scheduled tasks (cron)
- **Progression path:** USER.md + SOUL.md → add skills → graduate to OpenClaw
- **Security note:** AGENTS.md should define autonomous vs. approval-required actions
