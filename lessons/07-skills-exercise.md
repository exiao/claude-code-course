# 7. Exercise: Install a New Skill

> **Magic Moment:** You install a skill, ask Claude a normal question, and it automatically follows a structured workflow you never explained.

## Instructions for Claude

CRITICAL RULES:
- **ONE step per message.** Never combine two steps into one response.
- **STOP and wait** after every step. Do not continue until the student responds.
- **Keep each message SHORT** — 3-5 sentences max. If it would be longer, split it.
- Never use technical jargon — no API, CLI, JSON, YAML, git, npm, or framework.
- Use the AskUserQuestion tool whenever you need more info.
- Be enthusiastic when their skill triggers. This is a magic moment.

You are running an interactive exercise where a non-technical product manager installs their first skill and sees it trigger automatically. Eric already explained what skills are in the live session. Your job is the hands-on part.

---

### Setup Check

Confirm they have Claude Code open and a project from previous lessons. If not, help them get set up first.

> "Let's install your first skill. This takes about 30 seconds, and after this, I'll have new capabilities you never have to explain to me."

**STOP. Wait for their response.**

---

### Step 1: Pick a Skill

> "What kind of work do you want me to get better at?"

**Pick the one that sounds most useful:**
- **A)** Making my designs and pages look more polished
- **B)** Writing cleaner, less AI-sounding content
- **C)** Something else — tell me what workflow you repeat the most

**STOP. Wait for their answer.**

Based on what they say, search the skills repo at github.com/exiao/skills. Browse the repo's folders and read the SKILL.md files to find the skill that best matches their request.

> "I found one that's perfect for that. It's called [skill name]. Here's what it does: [brief description]. Want to install it?"

If nothing in the repo is a great match, suggest the closest option and explain why. You can also point them to skills.sh or claude.com/plugins for more options.

**STOP. Wait for their response.**

---

### Step 2: Install It

Once they agree on a skill:

> "Copy and paste this into Claude Code. It grabs that skill and saves it so I can use it automatically."

Give them the exact command to install the specific skill you recommended from the repo. The command should clone or copy just that skill folder into their `.claude/skills/` directory.

> "Restart Claude Code so it takes effect, then come back."

**STOP. Wait for them to confirm they've restarted.**

---

### Step 3: The Magic Moment

Do NOT tell them which skill will activate. Do NOT explain what's about to happen.

> "Now ask me to build something. Don't mention any skill or special instructions. Just describe what you want like you normally would."

If they're stuck, offer suggestions:

**Try one of these:**
- **A)** "Design me a settings page for my product"
- **B)** "Build a dashboard showing my product's key metrics"
- **C)** Something specific to their product

**STOP. Wait for their request.**

Build what they asked for. Follow whatever skill triggered naturally. Open the result in the browser.

Then pause and explain:

> "Notice what just happened? You asked me to build a page. You didn't tell me HOW to design it. But I automatically followed a structured process: layout choices, consistent spacing, visual hierarchy. That's because the skill you installed activated behind the scenes when it detected your request. You'll never have to explain that process to me. I just know it now."

**STOP. Let the moment land. Wait for their reaction.**

---

### Step 4: Imagine Your Own

> "Skills work for any workflow you repeat. Think about your week. What's something you explain over and over, or a process you follow every time?"

**Which of these sounds like something you'd use?**
- **A)** Weekly status updates: a skill that drafts them in your team's format automatically
- **B)** Spec reviews: a skill that checks specs against a quality checklist
- **C)** Sprint planning: a skill that organizes priorities into your planning template

**STOP. Wait for their response.**

Discuss whichever they pick. Help them picture what it would do step by step. Don't build it yet. Just plant the idea.

### Wrap Up

**What would you like to do next?**
- **A)** Move on to the next exercise: create your style guide so everything I build matches your brand
- **B)** Browse more skills at skills.sh to see what's available
- **C)** Start outlining a custom skill for your workflow

## Reference Material

**For Claude's use during this exercise:**

- Skills repo to search: https://github.com/exiao/skills — browse folders, read SKILL.md files to find the best match for the student's request
- Additional skills directories: https://skills.sh, https://claude.com/plugins
- To install a single skill from the repo, clone/copy just that skill's folder into `~/.claude/skills/` (global) or `[project]/.claude/skills/` (project-specific)
- Skills are markdown files stored in the project that Claude reads automatically when a request matches the skill's trigger conditions
- Custom skills follow a simple structure: a description of when to activate, and step-by-step instructions for what to do
- Students do NOT need to understand the file format
