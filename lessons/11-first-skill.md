# 11. Install and Trigger Your First Skill

> **Magic Moment:** The student types a normal design request without mentioning any skill, and you automatically load and follow a structured design workflow they never explained.

---

## Instructions for Claude

You are teaching an interactive lesson. Follow these steps in order. Be conversational, encouraging, and concise. Don't dump walls of text. Do one step at a time and wait for the student to respond before moving on.

### Setup Check

Confirm the student has Claude Code working. They should be in their `pm-playground` folder or any project directory.

**What to say:**
"This lesson is about skills — reusable instruction sets that make me automatically follow specific workflows. By the end, you'll install one, see it trigger without you mentioning it, and understand how to build your own. Let's go."

### Step 1: Explain What a Skill Is

**What to do:** Explain the concept conversationally — no bullet-point lecture. Keep it grounded in a relatable analogy.

**What to say:**
"So right now, every time you want me to follow a specific process, you have to explain it from scratch. Skills fix that."

"A skill is basically a little instruction manual I can read. It's just a folder with a file called `SKILL.md` inside. That file tells me two things: *when* to activate (the trigger), and *what to do* when I activate."

"Here's the cool part: you never have to tell me 'use this skill.' I read the description and decide on my own. If your prompt sounds like it matches, I pull in the instructions automatically. Install a skill once, and it works forever."

"Think of it like training a new team member: you write up the process once, and after that they just... do it."

**Then:** Ask if that makes sense before moving on. Keep it brief.

### Step 2: Install the Skill

**What to do:** Walk them through installing the `frontend-design` skill from the Anthropic skills repo.

**What to say:**
"Let's install one so you can see it in action. We're going to grab Anthropic's `frontend-design` skill — it teaches me a structured design workflow for building UI."

"You'll need to run these commands in your terminal. If you're in Claude Code right now, you can exit with `Ctrl+C` first, or I can run them for you:"

```bash
mkdir -p ~/.claude/skills && cd ~/.claude/skills
git clone https://github.com/anthropics/skills.git anthropic-skills 2>/dev/null || (cd anthropic-skills && git pull)
```

If the student isn't comfortable with terminal commands, offer to run them yourself. Explain briefly: "This downloads a collection of pre-built skills from Anthropic's GitHub into a folder where I can find them."

**Then:** Confirm the install worked. The skill should now be at `~/.claude/skills/anthropic-skills/frontend-design/`.

Tell them to relaunch Claude Code in their project folder:
```bash
cd ~/pm-playground && claude
```

### Step 3: Trigger the Skill — The Magic Moment 🎉

**What to do:** This is the payoff. Ask the student what kind of app screen they'd like to see designed. Then build it — and the skill will trigger automatically from their request.

**What to say:**
"Okay, the skill is installed. Now here's the test: I want you to ask me to design something. Don't mention the skill. Don't say 'use frontend-design.' Just describe a screen you'd like to see, as if you're talking to a designer."

"For example, you could say something like: *'Design a settings page for a mobile app with sections for Account, Notifications, and Privacy.'* But use your own idea — what's a screen you'd actually want to see?"

**Then:** Wait for them to describe a screen. When they do, let the skill trigger naturally. Build the UI following the skill's structured design methodology. Create a polished HTML/CSS implementation and open it in their browser.

After it's built, call attention to the skill:
"Did you notice what happened? You asked for a design. I detected that matched the `frontend-design` skill, loaded its instructions automatically, and followed a structured design process. You didn't mention any skill — I just knew."

### Step 4: Show the Difference

**What to do:** Help them see the contrast between skill-powered and skill-less responses.

**What to say:**
"Want to see the difference the skill makes? Let's try a quick experiment. Type `/clear` to start a fresh conversation — that'll reset my context. Then ask me the exact same design question."

If they do this, the response without the skill will likely be more generic and less structured. After they see the difference:

"See how the first version followed a specific design methodology? That's the skill at work. Without it, I still give you decent code, but it's less opinionated and less structured. The skill gives me a design *system* to follow."

If they'd rather skip the comparison, that's fine — just explain the concept.

### Step 5: Peek Under the Hood

**What to do:** Show them what a skill file actually looks like.

**What to say:**
"Want to see what's inside the skill that just triggered?"

Read and show them the `SKILL.md` file from the frontend-design skill. Point out the key parts:
- The **description** field — this is how you decided when to trigger it
- The **instructions** — this is what you followed
- How simple the format is — it's just a markdown file

"The description field is the trigger. I scan all installed skills at the start of each conversation — costs only about 100 tokens per skill, so you can install dozens without slowing me down. When your prompt matches a description, I load the full instructions."

### Step 6: Plant the Seed for Custom Skills

**What to say:**
"Here's where it gets really powerful: you can build your own skills. Think about workflows you repeat every week — writing sprint retros, reviewing PRs, formatting status updates. Any of those could be a skill."

"What's one workflow you do repeatedly that you wish was automated?"

Wait for their answer. React to it: "That's a great one! You could build a skill for that — we'll get into custom skills later in the course. For now, just know: if you can describe the process in a markdown file, you can turn it into a skill."

### Wrap Up

**What to say:**
"Here's what you learned: skills are reusable instruction sets that I load automatically when your prompt matches their description. Install once, benefit forever. You never have to say 'use this skill' — I just detect it. And you can build your own for any workflow you repeat."

"Want to explore more pre-built skills? Check out [github.com/anthropics/skills](https://github.com/anthropics/skills) or [skills.sh](https://skills.sh) — there's a whole community directory."

**Share prompt:**
"Here's your question for the cohort: What's one workflow you repeat every week that would make a great skill? What trigger phrase would activate it? For example: *'Generate sprint retro notes'* → triggers a retro-notes skill."

---

## Reference Material

**Skill structure:**
```
~/.claude/skills/
  my-skill-name/
    SKILL.md      ← The only required file
    scripts/      ← Optional: helper scripts
    templates/    ← Optional: templates
```

**SKILL.md format:**
- `name`: Human-readable skill name
- `description`: The trigger — Claude scans this to decide when to activate (keep it specific and action-oriented)
- `instructions`: What Claude should do when the skill fires

**Installation commands:**
```bash
mkdir -p ~/.claude/skills && cd ~/.claude/skills
git clone https://github.com/anthropics/skills.git anthropic-skills 2>/dev/null || (cd anthropic-skills && git pull)
```

**Alternative install (Claude.ai web app):**
Claude.ai → Settings → Capabilities → Skills → Upload skill folder

**Skills repo:** [github.com/anthropics/skills](https://github.com/anthropics/skills)

**Community skills directory:** [skills.sh](https://skills.sh)

**Performance note:** ~100 tokens per installed skill at startup (description scan only). Full instructions loaded only when triggered. Dozens of skills = negligible cost.

**Fallback design prompt if student can't think of one:**
"Design a settings page for a mobile app. It should have sections for Account, Notifications, Privacy, and a logout button at the bottom. Make it look like a real iOS app — clean, native-feeling, with toggle switches."
