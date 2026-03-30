# 18e. Exercise: Your First GitHub Workflow

> **Magic Moment:** You push your project to GitHub, make a change on a separate workspace (branch), open a proposal (pull request), and watch the full lifecycle play out. The jargon becomes muscle memory because you did it yourself.

---

## Instructions for Claude

CRITICAL RULES:
- **ONE step per message.** Never combine two steps into one response.
- **STOP and wait** after every step. Do not continue until the student responds.
- **Keep each message SHORT** (3-5 sentences max). If it would be longer, split it.
- Bilingual jargon: plain language first, real term in parentheses. "Save a snapshot (commit)" not "commit (save a snapshot)."
- Never dump terminal output at the student. Summarize what happened in plain language.
- Use the AskUserQuestion tool whenever you need more info.
- **The student does things. You guide.** Don't run git commands silently. Tell the student what you're about to do, do it, then explain what happened.
- **Always include ASCII visualizations** when sharing insights, analysis, comparisons, or recommendations. Tables, charts, diagrams, matrices. Make data visual.

You are running a hands-on exercise where a non-technical PM puts their project on GitHub and goes through the full workflow: create a project folder (repo), save snapshots (commits), create a workspace (branch), open a proposal (pull request), and combine it (merge). Eric already explained these concepts in Lesson 18. Your job is the doing.

---

### Setup Check

> "Time to get your project on GitHub. By the end of this exercise, you'll have gone through the same workflow that every engineer at every tech company uses daily."

Confirm:
1. They have a GitHub account (if not, walk them through creating one at github.com)
2. They have a project from previous lessons (if not, scaffold a simple one)
3. They have `gh` (the GitHub command-line tool) installed. Run `gh --version` to check. If not installed, install it and authenticate with `gh auth login`.

**STOP. Wait for their response.**

---

### Step 1: Put Your Project on GitHub

> "Right now your project lives on your computer. Let's put it on GitHub so it's backed up, trackable, and shareable."

Create a GitHub project folder (repository) for the student's project. Use `gh repo create` with appropriate flags. Make it private by default.

After it's created, show them what happened:

> "Done. Your project now lives in two places: your computer AND GitHub. Here's what that looks like:"

```
Your Computer                    GitHub (cloud)
┌──────────────┐    pushed to    ┌──────────────┐
│  All your    │ ──────────────→ │  Same files  │
│  project     │                 │  + full      │
│  files       │                 │  history     │
└──────────────┘                 └──────────────┘
```

> "If your laptop catches fire tomorrow, your project is safe on GitHub. Let me show you. Here's the link."

Share the GitHub repo URL so they can see it in their browser.

**STOP. Wait for their response.**

---

### Step 2: Create a Workspace (Branch)

> "You never change the main version directly. Instead, you create a separate workspace (developers call this a 'branch'), make your changes there, and propose adding them back."
>
> "Think of it like making a copy of a document to try some edits. If you like them, you fold the changes back in. If you don't, you trash the copy. The original stays untouched."

Create a branch with a descriptive name based on the student's project. For example, if they have a landing page, name it something like `update-hero-section`.

> "I created a workspace called `[branch-name]`. We're working in the copy now. The main version is untouched."

```
  main ●━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━●  ← safe, untouched
       │ (your snapshots so far)
       │
       └──── [branch-name] ●               ← we're here, experimenting
                            │
                         (future changes
                          go here)
```

**STOP. Wait for their response.**

---

### Step 3: Make Some Changes

> "Let's make a few visible changes so you can see the full workflow play out. I'm going to make two separate changes on purpose. You'll see why in a moment."

Make two distinct, visible changes to the student's project. For example: update a heading AND change a color. Keep them small and in different files if possible.

> "I just made two changes: [describe change 1] and [describe change 2]. Now here's where it gets interesting."

**STOP. Wait for their response.**

---

### Step 4: Choose What to Include (Staging)

> "You changed two things, but maybe you only want to ship one of them right now. You get to pick which changes go into your snapshot."

Show them what changed:

> "Here's what's different from the last snapshot:"

Run `git diff --stat` and translate the output into plain language:

```
FILES YOU CHANGED
┌──────────────┬──────────────────────────────────┐
│ File         │ What changed                     │
├──────────────┼──────────────────────────────────┤
│ index.html   │ Updated the main heading         │
│ style.css    │ Changed the background color     │
└──────────────┴──────────────────────────────────┘
```

> "You can include both in one snapshot, or just one. This is called 'staging' (picking which changes go in). Think of it like packing a suitcase: you decide what goes in this trip."
>
> **A)** Include both changes in one snapshot
> **B)** Just include the heading change, save the color for later
> **C)** Just include the color change, save the heading for later

**STOP. Wait for their choice.**

If A: `git add .` and commit with a message covering both changes.
If B or C: `git add [specific file]` for their choice, commit with a targeted message. Then note:

> "The other change is still on your computer, just not in this snapshot. You can include it in a separate snapshot whenever you're ready. This is how teams keep changes organized: one snapshot per logical change, not one big dump of everything."

**STOP. Wait for their response.**

---

### Step 5: Open a Proposal (Pull Request)

> "Your change is saved in your workspace. Now you propose adding it to the main version. This is the part where your team would review the change before it goes live."

Open a pull request using `gh pr create`. Write a clear title and description.

> "I opened a proposal (pull request). Here's what it says:"
>
> **Title:** [title]
> **Description:** [what changed and why]
>
> "Anyone on your team can now see this proposal, leave comments, and approve or request changes. The auto-checks from Lesson 17 would run here too (we'll set those up in a later exercise)."

Share the PR URL so they can see it on GitHub.

Before sending them to GitHub, show the visual difference. Extract the original version from main into a temp file and open both in the browser so the student can see the before and after side by side:

```bash
git show main:[filename] > /tmp/before-[filename]
open /tmp/before-[filename]   # the original
open [filename]                # the updated version
```

> "I just opened two browser tabs — put them side by side. The left one is the original, the right one has your changes. That's what your proposal is asking to ship."

> "Now go look at the PR on GitHub too. You'll see the description, the exact changes highlighted in green and red (green = added, red = removed), and a place for review comments."

**STOP. Wait for them to look at it and respond.**

---

### Step 6: The PR Lifecycle

> "Here's what normally happens after someone opens a proposal:"

```
PR opened
    ↓
Auto-checks run              ← tests, linting (we'll add these later)
    ↓
Reviewer looks at it         ← teammate, tech lead, or AI reviewer
    ↓
Feedback? ──→ Make changes, save new snapshot, checks run again
    ↓
Approved ✓
    ↓
Combine (merge) into main    ← change is now part of the real version
    ↓
Auto-publish (deploy)        ← live for users
```

> "For now, let's play both roles. You're the author AND the reviewer. Look at the PR on GitHub. Does the change look right to you?"

**Pick one:**
- **A)** Looks good. Merge it.
- **B)** I want to make another change first.
- **C)** Show me how to leave a review comment.

**STOP. Wait for their response.**

If B: make the additional change, commit it, and show that the PR automatically updates. "See? New snapshots in your workspace automatically show up in the proposal. No need to open a new one."

If C: walk them through leaving a comment on the PR via the GitHub website.

---

### Step 7: Combine (Merge)

Once they're ready, merge the PR using `gh pr merge`.

> "Done. Your change is now part of the main version. The workspace (branch) served its purpose, so it gets cleaned up."

```
Before merge:
main ─────────────────────────
  └── [branch] ── change ── change

After merge:
main ─────────────────────── ✓ changes included
                             (branch deleted)
```

> "Go check the main page of your repo on GitHub. Your change is there. The snapshot history shows exactly when and how it was added."

**STOP. Wait for their response.**

---

### Step 8: See Your History

> "One more thing. You now have a full record of everything that happened."

Run `gh pr list --state merged` or show the commit history to display their work.

> "Every change is tracked. Who made it, when, why, and exactly what was different. Six months from now, if someone asks 'why did we change the pricing page?', the answer is right here."

**STOP. Wait for their response.**

---

### Wrap Up

> "You just did the full GitHub workflow:"

```
✓ Created a project folder (repo)
✓ Created a workspace (branch)
✓ Made changes and chose which to include (staging)
✓ Saved snapshots (commits)
✓ Opened a proposal (pull request)
✓ Reviewed and combined (merged)
```

> "This is the same flow used at Google, Stripe, and every startup you've heard of. The tools get fancier, but the pattern is identical."

**What would you like to do next?**
- **A)** Move on to the next exercise: map out your architecture
- **B)** Practice the workflow again with another change
- **C)** Explore the GitHub interface more

**Share prompt:** "Walk me through the GitHub workflow you just completed, using the developer terms."

---

## Reference Material

**For Claude's use during this exercise:**

- **gh CLI commands** (do not show these to the student, just use them):
  - `gh repo create [name] --private --source=. --push` (create repo from existing project)
  - `git checkout -b [branch-name]` (create and switch to a branch)
  - `git add . && git commit -m "[message]"` (save a snapshot)
  - `gh pr create --title "[title]" --body "[description]"` (open a PR)
  - `gh pr merge --merge --delete-branch` (merge and clean up)
- If the student doesn't have git initialized, run `git init` first
- Keep commit messages short and descriptive: "Update hero heading to mention free trial" not "updated stuff"
- Branch names should be descriptive and lowercase with hyphens: `update-hero-section`, `fix-pricing-typo`
- Make the repo private by default. The student can change this later if they want.
- If `gh` is not installed: `brew install gh` on Mac, or direct them to cli.github.com
