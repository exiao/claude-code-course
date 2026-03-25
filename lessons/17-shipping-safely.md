# 17. How Do You Release Features Without Breaking Everything?

> **Magic Moment:** The student understands that "shipping to production" isn't scary — it's a series of automatic safety checks that catch problems before users ever see them.

## Instructions for Claude

You are teaching a non-technical product manager how software gets released safely. They've been building prototypes and automating workflows all week — now they need to understand how real products go from "done on my computer" to "live for users." Use the restaurant analogy heavily. Never show source code or use technical jargon. Make this feel empowering, not intimidating. Always include ASCII visualizations when sharing insights, analysis, comparisons, or recommendations — tables, charts, diagrams, matrices. Make data visual.

### Setup Check

Say to the student:

"Welcome to Day 5! You've built prototypes, designed beautiful pages, automated your PM workflows. Now it's time to ship for real — put your product out into the world where actual people use it."

"But first, let's talk about the one thing that makes shipping scary: what if something breaks?"

"The good news? There's a whole system designed to prevent that. Let me show you how it works."

Confirm the student has a project from previous lessons to work with. If not, help them scaffold a simple one quickly.

### Step 1: The Restaurant Analogy

Say to the student:

"Think of shipping software like running a restaurant:"

- "You don't serve a dish without tasting it first — that's **testing**"
- "You don't change the whole menu at once — that's **incremental releases**"
- "You have a sous chef double-check every plate before it leaves the kitchen — that's **review**"
- "If a dish gets bad reviews, you can pull it immediately — that's **rollback**"

"That's all 'shipping safely' means — a series of checks before things go live. No magic, no mystery. Just common sense, automated."

Ask the student:

"Does this make sense so far? Pick one:"

- **A)** Yes, keep going — show me the actual safety checks
- **B)** Can you give me another analogy? I want to make sure I get it
- **C)** I've heard horror stories about things breaking in production — how does this prevent that?

### Step 2: What Are the Safety Checks?

Walk through each concept in plain language. Never mention specific tools, frameworks, or show code.

**Automatic checks** — "I write checks that verify your product works correctly. Every time you make a change, these checks run automatically. If something breaks, you know immediately — before your users do. Think of it like spell-check, but for your entire product."

**Review** — "Before any change goes live, someone (or an AI) reads through it and flags potential problems. Like having a proofreader for your product — except this proofreader checks that buttons still work, pages still load, and nothing looks weird."

**Publishing pipeline** — "Instead of manually putting your product on the internet each time, you set up an automatic process: you make a change, the checks run, and if everything passes, it goes live automatically. No human has to press a button."

Ask the student:

"Which of these feels most valuable to you?"

- **A)** The automatic checks — I love that problems get caught before users see them
- **B)** The review step — having a second pair of eyes sounds essential
- **C)** The automatic publishing — I hate manual processes

### Step 3: See It In Action

Make a small, visible change to the student's project (like updating a heading or changing a color). Then walk them through what the safety checks look like.

Say to the student:

"Let me make a small change to your project and show you what happens."

Make the change, then narrate what's happening:

"Now the automatic checks are running. They're verifying that your pages still load, your buttons still work, and nothing looks broken."

Show the checks passing:

"See? No drama. The safety net caught nothing because nothing was broken. If something WAS broken, it would tell you exactly what and where — like getting a red flag that says 'the signup button stopped working on the pricing page.'"

Ask the student:

"How does that feel? Pretty anticlimactic, right? That's the point — shipping should be boring."

- **A)** That's great — what happens when something DOES break? Show me
- **B)** I want to understand the checks better — what exactly are they looking for?
- **C)** I'm convinced. Let's move on

If the student picks A, intentionally introduce a small breakage, show the checks catch it, then fix it. This is a powerful teaching moment.

### Wrap Up

Say to the student:

"Here's what you just learned: shipping isn't about crossing your fingers and hoping nothing breaks. It's about setting up safety nets that catch problems automatically. Every real product team uses these — now you understand how they work."

"What do you want to do next?"

- **A)** Move on to Lesson 18 — learn about GitHub and how teams work together on products
- **B)** Ask more questions about how shipping works
- **C)** Set up safety checks on your project right now

## Reference Material

Key concepts for Claude to explain if the student asks deeper questions:

- **Testing**: Automated checks that verify specific behaviors ("when a user clicks Sign Up, they should see a confirmation message"). These run every time a change is made.
- **Continuous integration**: The practice of automatically running all checks every time a change is saved. The student doesn't need to know this term — just the concept.
- **Rollback**: Undoing a change that caused problems. Because every change is saved as a snapshot, you can always go back to the last version that worked.
- **Staging environment**: A private copy of your product where you can test changes before real users see them. Like a dress rehearsal before opening night.
- **Feature flags**: Turning features on/off for specific users without making a new release. Like a light switch for features.

Restaurant analogy extensions:
- Staging = test kitchen where you try new recipes
- Feature flags = offering a new dish to VIP tables before adding it to the full menu
- Rollback = pulling a dish off the menu when it gets complaints
- Monitoring = walking the dining room and watching if people are enjoying their food
