# 12. Create Your Chief of Staff

> **Magic Moment:** You set up Claude to do real work on a schedule without you at the keyboard, then control it from your phone.

---

## Instructions for Claude

CRITICAL RULES:
- **ONE step per message.** Never combine two steps into one response.
- **STOP and wait** after every step. Do not continue until the student responds.
- **Keep each message SHORT** — 3-5 sentences max. If it would be longer, split it.
- Never use technical jargon unless the student brings it up first.
- Use the AskUserQuestion tool whenever you need more info.
- Actually run the commands and show real output. Don't just describe what would happen.

You are running an interactive exercise where a product manager sets up their first AI automation. Eric already explained the concept in the live session. Your job is the hands-on part.

---

### Setup Check

> "You've been running analysis and writing documentation by hand. Now let's make Claude do that stuff on its own, on a schedule, without you touching the keyboard."

**STOP. Wait for their response.**

---

### Step 1: Check Permissions

> "For this lesson, Claude needs to run without asking you to approve every single action. You need to be running in `--dangerously-skip-permissions` mode."
>
> "Are you currently in this mode? If not, close this session, restart Claude Code with `claude --dangerously-skip-permissions` in your project folder, and then come back to this lesson."

**STOP. Wait for them to confirm they're in the right mode.**

If they're not sure, help them check. If they need to restart, wait for them to come back.

---

### Step 2: Set Up Safety

> "Running without permission prompts is powerful, but we need guardrails. Let's install two safety skills."

#### 2a: Install /freeze

> "First: `/freeze`. This restricts Claude to only editing files in one directory. If you're working on billing code, you don't want Claude accidentally changing your auth system."

Walk them through installing the `/freeze` skill. Then demo it:

> "Let's test it. I'll freeze to a specific folder, then try to edit something outside it."

Run `/freeze` on a directory in their project. Then attempt to edit a file outside that boundary. Show them the block message.

> "See that? Anything outside the boundary gets blocked. Run `/unfreeze` when you want full access back."

**STOP. Wait for their reaction.**

#### 2b: Install /careful

> "Next: `/careful`. This catches dangerous commands before they run. Things like deleting files recursively, dropping database tables, or force-pushing to git."

Walk them through installing the `/careful` skill. Then demo it:

> "Watch what happens when I try something dangerous."

Attempt a command that `/careful` would catch (like `rm -rf` on a test directory, or `git push --force`). Show them the warning.

> "It caught it. You can still approve if you actually meant to do it, but it won't happen silently."

**STOP. Wait for their reaction.**

---

### Step 3: Build Your First Automation

> "Now let's build something Claude can run on its own. What recurring task eats up your time? Pick one, or tell me yours:"
>
> - 🌅 **Morning briefing** — pull your calendar, recent emails, project updates into one summary
> - 🤖 **Release notes** — generate user-friendly release notes from recent commits or completed tickets
> - 📩 **Weekly stakeholder update** — compile what shipped, what's in progress, key metrics
> - 🔍 **Feature QA** — open your product in the browser and walk through a flow, report issues
> - 📊 **Metrics check** — pull analytics data and flag anything that changed significantly
>
> "If you already have a skill installed from an earlier lesson that you want to automate, we can use that too."

**STOP. Wait for their choice.**

Build the automation based on their choice. Use their real project, real data, real tools wherever possible. The goal is a prompt or script that produces useful output every time it runs, with no human input needed.

After building it, run it once and show them the output.

> "Here's what this produces when it runs."

Show the real output.

**STOP. Wait for their reaction. Iterate if they want changes.**

---

### Step 4: Schedule It

> "Your automation works. Now let's make it run on its own. There are three ways to schedule it:"
>
> **A) `/loop`** — repeats on an interval right here in your terminal. Good for "run this every 30 minutes while I work." Stops when you close the terminal.
>
> **B) `/schedule`** — runs in the cloud on a timer. Persists even when your computer is off. More setup involved.
>
> **C) Desktop app scheduling** — if you're using the Claude Code desktop app, you can set up recurring tasks there. Your computer needs to stay awake (apps like Amphetamine help), and you'll want bypass-permissions mode enabled.
>
> "Which one do you want to try?"

**STOP. Wait for their choice.**

#### If they pick A: /loop

Walk them through setting up `/loop` with their automation. Show them how to set the interval. Run it and let them see it execute at least once automatically.

> "It'll keep running every [interval] until you stop it or close the terminal. Simple, but only works while your terminal is open."

#### If they pick B: /schedule

Walk them through `/schedule`. This requires more configuration. Help them set the cron expression for their desired frequency (daily, weekly, etc.) and configure it.

> "This runs in the cloud, so it works even when your laptop is closed. Check on it anytime to see what it produced."

#### If they pick C: Desktop app

Walk them through:
1. Setting up the recurring task in the desktop app
2. Enabling bypass-permissions mode in settings (so tasks run without approval prompts)
3. Recommend installing Amphetamine (free Mac app) to keep their computer awake

> "Your Mac needs to stay awake for this to work. Amphetamine keeps it running. With bypass-permissions on, Claude will execute tasks without waiting for you to click approve."

**STOP. Wait for confirmation it's set up.**

---

### Step 5: Control Claude From Your Phone

> "One more thing. You don't have to be at your computer to talk to Claude. Run `claude --remote-control` and you get a URL you can open on your phone."

Walk them through:
1. Running `claude --remote-control`
2. Opening the URL on their phone (or scanning a QR code if one is provided)
3. Sending Claude a message from their phone and seeing it execute on their computer

> "Try it. Send me a message from your phone right now."

**STOP. Wait for them to try it.**

> "That's it. You can send Claude tasks from your phone, and it runs them on your machine. Voice notes, screenshots, quick requests. You don't need to be sitting at your laptop anymore."

**STOP. Wait for their reaction.**

---

### The Magic Moment

> "Let's recap what you just set up:"
> - Safety guardrails so Claude doesn't break things when running unsupervised
> - An automation that produces real output without you lifting a finger
> - A schedule so it runs on its own
> - Phone access so you can send Claude work from anywhere
>
> "You went from 'I paste prompts into a terminal' to 'I have an AI employee that works on a schedule and I manage it from my phone.'"

**STOP. Wait for their reaction.**

---

### Wrap Up

> "You now have a chief of staff. Start with one automation. Once you trust it, add more. Morning briefings, weekly updates, QA runs, metrics alerts. Each one saves you hours."

**Share prompt:** What's the first task you automated? Would you trust it to run every day without checking?

---

## Reference Material

**For Claude's use during this exercise:**

### Safety Skills
- **/freeze [directory]** — restricts all file edits to the specified directory. Run `/unfreeze` to remove. Use when working on a specific area and you want protection against unintended changes elsewhere.
- **/careful** — checks every bash command against dangerous patterns before executing:
  - `rm -rf` / `rm -r` (recursive delete)
  - `DROP TABLE` / `DROP DATABASE` / `TRUNCATE` (data loss)
  - `git push --force` / `git push -f` (history rewrite)
  - `git reset --hard` (discard commits)
  - `git checkout .` / `git restore .` (discard uncommitted work)
  - `kubectl delete` (production resource deletion)
  - `docker rm -f` / `docker system prune` (container/image loss)
- Reference: https://github.com/garrytan/gstack/blob/main/docs/skills.md#safety--guardrails

### Scheduling Options
- **/loop** — repeats a prompt at an interval within the current terminal session. Stops when terminal closes. Best for short-lived repeating tasks.
- **/schedule** — cloud-based scheduling. Persists across sessions. More setup required. Docs: https://code.claude.com/docs/en/scheduled-tasks
- **Desktop app scheduling** — set recurring tasks in the Claude Code desktop app. Requires:
  - Bypass-permissions mode enabled (Settings → Permissions)
  - Computer staying awake (recommend Amphetamine: https://apps.apple.com/us/app/amphetamine/id937984704)

### Remote Control
- `claude --remote-control` — generates a URL you can open on your phone to send Claude messages remotely
- Works for sending text, voice notes, screenshots, and quick tasks
- Claude executes everything on the local machine

### Automation Ideas
- **Morning briefing:** Pull calendar events, recent emails/Slack, project tracker updates, analytics summary. Compile into a single digest.
- **Release notes:** On merge to main, analyze commits/PRs, generate user-friendly changelog with screenshots.
- **Stakeholder update:** Weekly compilation of shipped features, in-progress work, key metrics, blockers.
- **Feature QA:** Open product URL in browser, walk through a specific user flow, screenshot each step, report issues found.
- **Metrics check:** Pull from analytics tool (PostHog, Mixpanel, CSV), compare to previous period, flag significant changes.
- **Any existing skill:** If they installed a skill in earlier lessons (competitive analysis, feedback analysis, etc.), they can schedule it to run regularly.

### Additional Reading
- Setup guide: https://amankhan1.substack.com/p/how-to-get-clawdbotmoltbotopenclaw
- Making it useful: https://amankhan1.substack.com/p/how-to-make-your-openclaw-agent-useful
- The wow moment: https://mycrystalball.substack.com/p/the-wow-moment-with-openclaw
