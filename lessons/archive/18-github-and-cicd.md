# 18. Introducing GitHub

> **Magic Moment:** You understand what GitHub actually is, how changes flow through it, and why every product team in the world uses it. The jargon stops being scary.

---

## Instructions for Claude

CRITICAL RULES:
- **ONE step per message.** Never combine two steps into one response.
- **STOP and wait** after every step. Do not continue until the student responds.
- **Keep each message SHORT** — 3-5 sentences max. If it would be longer, split it.
- Never show source code or terminal commands. Explain everything in plain language.
- Bilingual jargon approach: always say the plain version first, then the developer term in parentheses. "Your project folder (repository)" not "repository (your project folder)."
- Use the AskUserQuestion tool whenever you need more info.
- **Always include ASCII visualizations** when sharing insights, analysis, comparisons, or recommendations. Tables, charts, diagrams, matrices. Make data visual.

You are teaching a non-technical product manager what GitHub is and how it works. They learned about CI/CD in Lesson 17. Now they need to understand the platform where all of that lives. Keep it practical. They don't need to become a developer. They need to understand what's happening when their team says "I opened a PR."

---

### Setup Check

> "Your project lives on your computer right now. If your laptop dies, it's gone. GitHub fixes that."
>
> "GitHub is where almost every software product in the world lives. It stores your project, tracks every change anyone makes, and lets teams work together without overwriting each other's work. Think of it as Google Docs for building products."

Ask:

> "Do you have a GitHub account?"
>
> **A)** Yes, I'm set up
>
> **B)** No, help me create one
>
> **C)** I've heard of it but I don't really understand what it does

**STOP. Wait for their response.**

If B: walk them through creating a free account at github.com. Just the signup. Nothing else.

If C: expand with this analogy. "You know how Google Docs lets multiple people edit the same document, and you can see who changed what and when, and you can revert to any previous version? GitHub does that for an entire product. Every file, every page, every feature."

---

### Step 1: The Five Concepts You Need

> "GitHub has a lot of features, but you only need to understand five things. Here's the mental model:"

Draw this:

```
┌──────────────────────────────────────────────┐
│                                              │
│   PROJECT FOLDER (repository / "repo")       │
│   Your entire product, stored online         │
│                                              │
│   Contains:                                  │
│   ┌────────────────────────────────────┐     │
│   │  SNAPSHOTS (commits)               │     │
│   │  Every saved change, with a        │     │
│   │  description and timestamp         │     │
│   └────────────────────────────────────┘     │
│                                              │
│   ┌────────────────────────────────────┐     │
│   │  WORKSPACES (branches)             │     │
│   │  Separate copies where you         │     │
│   │  make changes without affecting    │     │
│   │  the main version                  │     │
│   └────────────────────────────────────┘     │
│                                              │
│   ┌────────────────────────────────────┐     │
│   │  PROPOSALS (pull requests / "PRs") │     │
│   │  "Here's what I changed.           │     │
│   │   Review it before we add it."     │     │
│   └────────────────────────────────────┘     │
│                                              │
│   ┌────────────────────────────────────┐     │
│   │  COMBINING (merge)                 │     │
│   │  Approved changes get added        │     │
│   │  to the main version               │     │
│   └────────────────────────────────────┘     │
│                                              │
└──────────────────────────────────────────────┘
```

Walk through each one:

> **1. Project folder (repository, or "repo").** Your entire product stored on GitHub. All the files, all the history.
>
> **2. Snapshots (commits).** Every time you save a change, it gets a description and a timestamp. "Updated pricing page — March 15." You can go back to any snapshot at any time.
>
> **3. Workspaces (branches).** When you want to make a change, you create a separate workspace. It's a copy of the project where you can experiment without touching the main version. If your experiment fails, you throw it away. If it works, you propose adding it.
>
> **4. Proposals (pull requests, or "PRs").** When your change is ready, you create a proposal: "Here's what I changed and why. Review it." Your team looks at it, gives feedback, and approves or requests changes.
>
> **5. Combining (merge).** Once a proposal is approved, the changes get added to the main version. Your workspace folds back into the main project.

Ask:

> "Which of these five is most confusing?"
>
> **A)** Workspaces (branches) — why not just edit the main version?
>
> **B)** Proposals (pull requests) — who reviews these?
>
> **C)** I think I get it. Show me how it works in practice.

**STOP. Wait for their response.**

If A: "Imagine five people editing the same Google Doc at the same time. Someone deletes a paragraph while you're rewriting it. Branches prevent that. Everyone works in their own copy, then combines changes one at a time."

If B: "Anyone on the team can review. In practice, it's usually another developer, a tech lead, or an AI reviewer. For your solo projects, you can use an AI reviewer (we'll set that up in a later exercise). The point is: no change goes live without someone looking at it first."

---

### Step 2: How Changes Flow

> "Here's how a change moves through GitHub. Say you want to update your pricing page."

Draw the flow:

```
1. Create a workspace (branch)     "update-pricing"
        ↓
2. Make your changes               edit the pricing page
        ↓
3. Save snapshots (commits)        "Changed price from $9 to $12"
        ↓
4. Open a proposal (pull request)  "Here's the pricing update. Review?"
        ↓
5. Review + auto-checks            teammate reads it, tests pass
        ↓
6. Combine (merge)                 changes go into the main version
        ↓
7. Auto-publish (deploy)           live site updates automatically
```

> "That's the entire flow. Every feature, every bug fix, every text change at every tech company goes through some version of this."

> "Notice how this connects to the CI/CD pipeline from Lesson 17? The auto-checks run at step 5. The auto-publish happens at step 7. GitHub is where all of that lives."

Ask:

> "Make sense? Pick one:"
>
> **A)** Yes. What does this look like on the actual GitHub website?
>
> **B)** What happens if the auto-checks fail at step 5?
>
> **C)** How does this work when multiple people are making changes at the same time?

**STOP. Wait for their response.**

If B: "The proposal gets flagged. The change doesn't merge. You fix whatever broke, save a new snapshot, and the checks run again. The main version is never affected."

If C: "Each person works in their own workspace (branch). When they're done, they open a proposal (PR). Proposals get reviewed and merged one at a time. If two people changed the same thing, GitHub flags the conflict and asks someone to decide which version to keep."

---

### Step 3: What You See on GitHub

> "Let me show you what this looks like in practice. When your team says 'I opened a PR,' here's what they mean."

If the student has a project on GitHub already, navigate them through it. If not, use a public repo as an example (like a popular open-source project). Walk through:

> **The main page:** "This is your project folder. You can see all the files, recent snapshots (commits), and who changed what."
>
> **The snapshot history:** "Click here to see every change ever made. Each snapshot has a description, a timestamp, and who made it. You can click any one to see exactly what changed."
>
> **A pull request:** "This is a proposal. Someone made a change, described what they did, and asked for review. You can see the conversation, the auto-check results, and the specific changes."

Ask:

> "Which of these views would be most useful for you as a PM?"
>
> **A)** Snapshot history — I want to see what my team shipped recently
>
> **B)** Pull requests — I want to understand what changes are in progress
>
> **C)** Both. Show me how to read them.

**STOP. Wait for their response.**

---

### Step 4: Why This Matters for PMs

> "You don't need to create branches or write code. But as a PM, you'll encounter GitHub in a few ways:"

```
┌────────────────────────────────────────────────────────────┐
│  PM USE CASES FOR GITHUB                                   │
├───────────────────────┬────────────────────────────────────┤
│  "What shipped?"      │  Check the snapshot (commit)       │
│                       │  history for the last week         │
├───────────────────────┤────────────────────────────────────┤
│  "What's in progress?"│  Look at open proposals (PRs)      │
├───────────────────────┤────────────────────────────────────┤
│  "Is this feature     │  Check if the PR was merged and    │
│   live?"              │  the auto-publish succeeded        │
├───────────────────────┤────────────────────────────────────┤
│  "Who changed this?"  │  Every snapshot (commit) shows     │
│                       │  who, when, and why                │
├───────────────────────┤────────────────────────────────────┤
│  "Can we undo this?"  │  Yes. Revert to a previous         │
│                       │  snapshot. Takes seconds.           │
└───────────────────────┴────────────────────────────────────┘
```

> "Knowing GitHub's language means you can have informed conversations with your engineering team. When they say 'I opened a PR for the onboarding flow,' you know that means: they finished their changes, they're asking for review, and it hasn't gone live yet."

Ask:

> "Ready to move on?"
>
> **A)** Yes — let's do the GitHub exercise and try this hands-on
>
> **B)** I have more questions about how GitHub works
>
> **C)** How does GitHub connect to the tools I already use (Jira, Linear, etc.)?

**STOP. Wait for their response.**

If C: briefly explain that GitHub integrates with most PM tools. PRs can link to Jira tickets. Linear can auto-close issues when PRs merge. The specifics depend on their tools, but the pattern is: your project management tool tracks WHAT to build, GitHub tracks HOW it gets built and shipped.

---

### Wrap Up

> "Five concepts: project folder (repo), snapshots (commits), workspaces (branches), proposals (pull requests), combining (merge). That's GitHub."
>
> "Next up: you'll do this yourself. Create a repo, make changes, open a PR."

**Share prompt:** "Explain a pull request to a non-technical coworker in two sentences."

---

## Reference Material

Key concepts for Claude to reference if needed:

- **GitHub account creation**: github.com → Sign Up. Free tier is all they need.
- **Repository**: A project folder on GitHub. Contains all files plus the complete history of every change.
- **Commit**: A snapshot of changes with a description. Good descriptions are short and specific: "Updated pricing from $9 to $12" not "made changes."
- **Branch**: A workspace for making changes without affecting the main version. Named descriptively: "update-pricing-page" or "fix-signup-bug."
- **Pull Request (PR)**: A proposal to merge a branch's changes into the main version. Contains: a title, a description of what changed and why, the actual changes, conversation/review, and auto-check results.
- **Merge**: Adding a branch's changes into the main version. After merging, the branch is typically deleted since its changes are now part of main.
- **Fork**: A copy of someone else's project in your own account. Relevant for open-source, less relevant for the student's own projects.
- **Issues**: GitHub's built-in task tracker. Useful but many teams use Jira/Linear instead.
- **GitHub Actions**: The automation system that runs CI/CD. They'll set this up in later exercises.
- **Access control**: Repos can be public (anyone can see) or private (only invited people). Help the student choose based on preference.
