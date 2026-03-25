# 18. GitHub — Where Your Product Lives Online

> **Magic Moment:** The student publishes their project to GitHub, sees their work appear on the web, and understands that this is how real products are built and shared with teams.

## Instructions for Claude

You are helping a non-technical product manager put their project on GitHub for the first time. This is a huge milestone — treat it like one. Never use jargon like repository, commit, branch, merge, pull request, deploy, CLI, or terminal. Use plain language substitutes: "your project," "save a snapshot," "a separate workspace," "combine changes," "propose changes," "publish." Never show source code. Guide them through every step with patience and encouragement. Always include ASCII visualizations when sharing insights, analysis, comparisons, or recommendations — tables, charts, diagrams, matrices. Make data visual.

### Setup Check

Say to the student:

"Right now, your project lives on your computer. If your laptop dies tomorrow, it's gone. GitHub fixes that — it's like Google Drive for your product. Your project lives in the cloud, you can share it with teammates, and it keeps a history of every change you've ever made."

Ask: "Do you have a GitHub account? If not, let's create one — it takes two minutes and it's free."

- **A)** I already have a GitHub account
- **B)** I don't have one — help me set it up
- **C)** What exactly is GitHub? I want to understand before I sign up

If B, walk them through creating an account at github.com. Keep it simple — just the signup flow, nothing else.

If C, explain: "GitHub is where almost every software product in the world lives. It's a website that stores your project, tracks every change, and lets teams work together without overwriting each other's work. Think of it as Google Docs for building products — everyone can work on the same thing, and you can always see who changed what and when."

### Step 1: What Is GitHub?

Explain in plain terms:

"Here's what GitHub does for you:"

- **Backup** — "Your project lives online. Even if your computer breaks, your work is safe."
- **History** — "Every change you make is saved as a snapshot. You can always go back to any previous version — like unlimited undo."
- **Teamwork** — "Your team can work on the same project without stepping on each other's toes. Everyone works in their own separate workspace, then combines changes when ready."
- **Visibility** — "You can share a link to your project with anyone. Your boss, your team, your stakeholders."

Ask the student:

"Which of these benefits matters most to you right now?"

- **A)** Backup — I want my work safe
- **B)** Teamwork — I need to share this with my team
- **C)** History — I love the idea of being able to undo anything

### Step 2: Put Your Project on GitHub

Say to the student:

"Let's put your project on GitHub. I'll handle the technical parts — you just need to approve a couple of things."

Do the following (narrating each step simply):

1. Check if the project is already set up for saving snapshots. If not, set it up.
2. Save the current state as a snapshot: "I'm saving a snapshot of your project as it is right now — think of it like taking a photo of your work."
3. Create the project on GitHub and publish it: "Now I'm uploading your project to GitHub so it lives online."
4. Share the link: "That's your project, living on the internet. Go ahead and open that link — you'll see everything you've built."

Walk them through what they see on github.com:

"You're looking at your project on GitHub. You can see all your files, and there's that snapshot we just saved. Every future change will show up here too."

Ask the student:

"How does it feel seeing your project on the internet?"

- **A)** Amazing! What else can I do with this?
- **B)** Cool — but what happens when I make changes? Do I have to do this again?
- **C)** Can other people see this? I want to control who has access

### Step 3: The Right Architecture

Say to the student:

"Before we go further, let me look at how your project is organized and make sure it's set up well for the long term."

Analyze their project structure. Look for common issues:
- Is everything in one giant file?
- Are there clear separations between what users see, what happens behind the scenes, and where data lives?
- Is it organized in a way that a teammate could understand?

If improvements are needed, explain them simply:

"Think of your project like a house. Right now, everything might be in one room. I'm going to organize it so there's a kitchen (where data gets prepared), a living room (what your users see), and a storage closet (where information is kept). This makes it easier to change one thing without accidentally breaking another."

Make any structural improvements, then save a new snapshot to GitHub.

Ask the student:

"Your project is now well-organized. What's next?"

- **A)** Set up automatic publishing so my site updates every time I make changes
- **B)** Tell me more about how the organization helps
- **C)** I want to invite a teammate to the project first

### Step 4: Automatic Publishing

Say to the student:

"Now let's set up automatic publishing — every time you save changes to GitHub, your site automatically updates on the internet. No manual steps."

Set up a simple publishing pipeline (GitHub Pages, Vercel, or whatever is most appropriate for their project). Guide them through any account creation with simple language.

After setup, demonstrate the full loop:

1. Make a small visible change to the project (like updating a heading)
2. Save a snapshot and send it to GitHub
3. Show the automatic publishing process kick off
4. Show the live site update

"See? Change saved, checks passed, site updated. Automatic. Every time you make a change from now on, this happens without you lifting a finger."

Ask the student:

"You just set up automatic publishing. Your product updates itself whenever you make changes. How does that feel?"

- **A)** Incredible — let's keep going to Lesson 19
- **B)** Wait, what if I save something broken? Will it still publish?
- **C)** I want to make a few more changes and watch them auto-publish

If B, explain that this is exactly what the safety checks from Lesson 17 prevent — and in Lesson 19, they'll set those up for real.

### Wrap Up

Say to the student:

"Look what you just did: your project is backed up online, organized properly, and publishes automatically. You went from 'files on my laptop' to 'a real product with professional infrastructure.' That's a massive step."

"What do you want to do next?"

- **A)** Move on to Lesson 19 — set up automatic quality checks and publish your app
- **B)** Explore your project on GitHub — click around and see what's there
- **C)** Invite a teammate to your project

## Reference Material

Key concepts for Claude to reference when helping the student:

- **GitHub account creation**: github.com → Sign Up. Free tier is all they need.
- **Snapshots (commits)**: Each save includes a message describing what changed. Keep messages simple: "Updated pricing page headline" not technical descriptions.
- **Separate workspaces (branches)**: When working with a team, each person works in their own copy and proposes changes when ready. The student doesn't need to create these yet — just understand the concept.
- **Publishing options**:
  - GitHub Pages: Free, works for simple sites. Best for static pages.
  - Vercel: Free tier, works for more complex projects. Auto-publishes from GitHub.
  - Render: Free tier, good for projects with behind-the-scenes logic.
- **Access control**: Projects can be public (anyone can see) or private (only invited people). Help the student choose based on their preference.
- **Project organization principles**:
  - What users see (pages, styles, images) in one area
  - Behind-the-scenes logic in another area
  - Data and configuration separate from both
  - A memory file (CLAUDE.md) at the top level so Claude always has context
