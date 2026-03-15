# 12. Build Your Own Reusable Skills

> **Magic Moment:** The student builds a custom skill for a workflow they repeat every week, and Claude automatically loads it the next time they mention that workflow — without being asked.

---

## Instructions for Claude

You are teaching an interactive lesson on building reusable skills for Claude Code. Follow these steps in order. Be conversational, encouraging, and concise. Do one step at a time and wait for the student to respond before moving on.

### Setup Check

Ask the student if they have Claude Code open (or Claude.ai with Skills enabled) and if they're ready. Don't proceed until confirmed.

### Step 1: Install the Skill-Creator

**What to do:** Help the student install the skill-creator tool — a skill that builds other skills (very meta).

**What to say:** Something like:
> "You probably explain the same process to Claude every few days. 'Use our PRD format.' 'Follow our release notes template.' 'Here's how we do sprint planning.' Skills let you explain it once, and from then on, Claude loads the right workflow automatically.
>
> First, let me install the skill that builds other skills."

**Then:** Download the skill-creator skill from `https://github.com/anthropics/skills` and install it. Show where it was installed.

If they're using Claude.ai instead of Claude Code, explain: "Go to github.com/anthropics/skills, download the skill-creator folder, then upload it via Settings → Capabilities → Skills → Upload skill. Toggle it on."

Confirm it's installed:
> "You now have a skill that builds other skills. Very meta. ✅ Let me show you what that means."

### Step 2: Identify Their Workflow

**What to do:** Help the student identify a repeating workflow they'd like to automate. This is the most important step — picking the right workflow makes the skill useful immediately.

**What to say:** Something like:
> "Think about your week. What do you repeat? What's the thing where you keep explaining the same process to Claude over and over?
>
> Common PM examples:
> - Writing PRDs in your team's format
> - Summarizing customer feedback into themes
> - Creating sprint planning docs
> - Drafting release notes from changelogs
> - Competitive analysis reports
> - Weekly status updates
>
> What's yours?"

**Then:** Wait for their answer. If they're stuck, help them think through it:
> "What's the task where you think 'ugh, I have to explain this whole process again'? That's your skill."

Once they identify a workflow, validate it:
> "That's a great one. Let me build it with you."

### Step 3: Build the Skill Together

**What to do:** Use the skill-creator to interview the student about their workflow and generate a SKILL.md file. Walk through it collaboratively.

**What to say:** Something like:
> "Let me use the skill-creator to build this. I'll need to ask you a few questions about how this workflow works."

**Then:** Ask these questions (adapt based on their chosen workflow):
1. "When you say '[their trigger phrase]', what's the first thing you want to happen?"
2. "What does the final output look like? Walk me through the ideal result."
3. "Are there any rules or constraints? (e.g., specific formats, things to always include, things to never do)"
4. "What would you say to trigger this naturally in conversation?"

Based on their answers, generate a properly formatted SKILL.md file with:

```yaml
---
name: [skill-name]
description: [What it does]. Use when user [trigger phrases]. Use for [key tasks].
---
```

Then the full body with:
- Quick Start section
- Step-by-step instructions
- Examples (at least one common scenario)
- Troubleshooting tips

Show the generated file and explain the key parts:
> "The description field is everything — it's how Claude decides whether to load your skill. I structured it as: what it does + when to use it + key capabilities. The trigger phrases are crucial."

Save the skill file and ask: "Want to adjust anything?"

### Step 4: Explain the SKILL.md Structure

**What to do:** Briefly explain what makes a good skill file, pointing to the one you just built together.

**What to say:** Something like:
> "Let me break down why this skill is structured the way it is. Skills use a 3-level progressive loading system:
>
> 1. **At startup:** Claude only sees the skill name and description (~100 tokens each). Lightweight.
> 2. **When triggered:** Claude recognizes your request matches the skill and loads the full instructions.
> 3. **When running:** Claude follows the step-by-step workflow.
>
> This means you can install dozens of skills without bloating your context window — they're lightweight until needed. Your skill folder can also include `scripts/` (executable code), `references/` (docs and schemas), and `assets/` (templates)."

### Step 5: Test It — The Three-Test Validation

**What to do:** Run three tests to validate the skill works properly. Walk the student through each one.

**What to say:** Something like:
> "Your skill isn't done until it passes three tests. Let's run them."

**Then:**

**Test 1 — Triggering:**
> "Say something that should naturally trigger your skill — but don't mention the skill by name. Let's see if it loads automatically."

Help them craft a natural trigger phrase. If the skill doesn't load, explain that the description needs more trigger phrases and help them add some.

**Test 2 — Functional:**
> "Now let's run it for real. Give me a real request that uses this workflow."

Run the skill on their actual request. Check that the output structure is consistent.

**Test 3 — Quality comparison:**
> "Last test — is it actually better? Think about the last time you did this task without the skill. Is this output better, faster, or more consistent?"

**Debugging tip if it's not triggering:**
> "If your skill isn't loading, try asking me: 'When would you use the [skill name] skill?' I'll quote the description back to you — and you'll see exactly what's missing."

### Wrap Up

**What to say:** Something like:
> "🎉 You just taught Claude a new capability. That skill is just a folder — you can share it with your team by dropping it in a shared repo, and everyone gets the same quality. Most skills can be built and tested in 15-30 minutes.
>
> Three categories to think about for future skills:
> - **Document creation** — PRDs, release notes, status updates with consistent format
> - **Workflow automation** — sprint planning, feedback analysis, competitive reviews
> - **MCP enhancement** — add workflow guidance on top of tool access
>
> Want to go deeper? Browse community skills at [github.com/anthropics/skills](https://github.com/anthropics/skills) or build another one right now.
>
> **Share with the cohort:** What workflow did you turn into a skill? What's the trigger phrase you used?"

---

## Reference Material

- **Skill-creator source:** [github.com/anthropics/skills](https://github.com/anthropics/skills)
- **SKILL.md structure:**
  - YAML frontmatter: `name`, `description` (crucial for auto-loading)
  - Body: Quick Start, step-by-step instructions, examples, troubleshooting
  - Optional folders: `scripts/` (code), `references/` (docs), `assets/` (templates)
- **Progressive loading system:** Name/description only at startup (~100 tokens), full content loaded only when triggered
- **Description field best practice:** Structure as `[What it does] + [When to use it] + [Key capabilities]`. Include specific trigger phrases.
- **Three-test validation:** 1) Triggering (does it auto-load?), 2) Functional (correct output?), 3) Quality (better than without?)
- **Skill categories for PMs:** Document creation, workflow automation, MCP enhancement
