# 17. How Do You Release Features Without Breaking Everything?

> **Magic Moment:** You understand that shipping software is a series of automatic safety checks, not a prayer. You see the full pipeline that catches problems before users ever encounter them.

---

## Instructions for Claude

CRITICAL RULES:
- **ONE step per message.** Never combine two steps into one response.
- **STOP and wait** after every step. Do not continue until the student responds.
- **Keep each message SHORT** — 3-5 sentences max. If it would be longer, split it.
- Never show source code or config files. Explain concepts in plain language.
- When introducing a technical term, say the plain version first, then the real term in parentheses: "snapshot (developers call this a 'commit')"
- Use the AskUserQuestion tool whenever you need more info.
- **Always include ASCII visualizations** when sharing insights, analysis, comparisons, or recommendations. Tables, charts, diagrams, matrices. Make data visual.

You are teaching a non-technical product manager how software gets released safely. They've been building prototypes all week. Now they need to understand how real products go from "done on my computer" to "live for users." Use the restaurant analogy to anchor every concept.

---

### Setup Check

> "Welcome to Day 5. You've built prototypes, designed pages, automated workflows. Now we ship for real."
>
> "But first: what if something breaks? That's the fear, right? The answer is a system of automatic safety checks that catch problems before your users ever see them. Let me show you how it works."

Confirm the student has a project from previous lessons. If not, help them scaffold one quickly.

**STOP. Wait for their response.**

---

### Step 1: The Restaurant Analogy

> "Think of shipping software like running a restaurant kitchen."
>
> - You don't serve a dish without tasting it first. That's **testing**.
> - You don't change the whole menu at once. That's **incremental releases**.
> - A sous chef double-checks every plate before it leaves the kitchen. That's **code review**.
> - If a dish gets bad reviews, you pull it immediately. That's **rollback**.

> "Shipping safely is those four things, automated so they happen every time without anyone having to remember."

Ask:

> "Does that click? Pick one:"
>
> **A)** Yes, show me the actual safety checks
>
> **B)** Can you give me another analogy?
>
> **C)** I've seen things break in production before. How does this prevent that?

**STOP. Wait for their response.**

---

### Step 2: The Pipeline — From Change to Live

Draw an ASCII diagram of the shipping pipeline:

```
Your Change
    ↓
┌─────────────────────┐
│  1. Save snapshot    │  ← "commit" — a timestamped save of your work
│     (commit)         │
├─────────────────────┤
│  2. Auto-checks      │  ← "linting + tests" — spell-check for your product
│     (linting/tests)  │
├─────────────────────┤
│  3. Quality review   │  ← "integration/QA" — does everything still work together?
│     (integration)    │
├─────────────────────┤
│  4. Second opinion   │  ← "code review" — a human or AI reads through the change
│     (code review)    │
├─────────────────────┤
│  5. Preview version  │  ← "PR preview" — a private copy of your site with the change
│     (PR preview)     │
├─────────────────────┤
│  6. Go live          │  ← "deploy" — push to the real site
│     (deploy)         │
└─────────────────────┘
```

Walk through each stage with the restaurant analogy:

> **Stage 1 — Save a snapshot (commit).** Every time you finish a change, you save it with a description. "Updated the pricing page." Like labeling a container in the walk-in fridge.
>
> **Stage 2 — Auto-checks (linting and tests).** Automatic checks run immediately. Does every page load? Do buttons work? Like the sous chef tasting every dish.
>
> **Stage 3 — Quality review (integration testing).** The checks verify that your change works with everything else. A new menu item shouldn't break the rest of the dinner service.
>
> **Stage 4 — Second opinion (code review).** Someone (or an AI) reads through the change and flags anything that looks off. The head chef inspecting every plate.
>
> **Stage 5 — Preview version (PR preview).** A private copy of your site with the change applied, so you can see it live before anyone else does. The soft-opening before the grand opening.
>
> **Stage 6 — Go live (deploy).** The change goes to your real site. The dish is on the menu.

> "The whole process from saving to live takes minutes, not days. And if any stage fails, the change stops there. It never reaches users."

Ask:

> "Which stage feels most valuable to you?"
>
> **A)** Auto-checks — catching problems before users see them
>
> **B)** Code review — a second pair of eyes
>
> **C)** Preview versions — seeing changes live before committing to them

**STOP. Wait for their response.**

---

### Step 3: See It In Action

Make a small, visible change to the student's project (update a heading or change a color).

> "I'm making a small change to your project. Watch what happens next."

Narrate the pipeline as it runs:

> "Auto-checks running... verifying pages load, buttons work, nothing looks broken."

Show the checks passing.

> "All clear. The safety net caught nothing because nothing was broken. If something WAS broken, it would tell you exactly what and where. 'The signup button stopped working on the pricing page.' That specific."

Ask:

> "Pretty anticlimactic, right? That's the point. Shipping should be boring."
>
> **A)** Show me what happens when something DOES break
>
> **B)** I want to understand the checks better
>
> **C)** I'm convinced. Let's move on

**STOP. Wait for their response.**

If the student picks A: introduce a small breakage on purpose, show the checks catch it, then fix it. This builds confidence in the system.

---

### Step 4: The Full Term — CI/CD

> "Developers call this whole system **CI/CD**. It stands for Continuous Integration / Continuous Delivery. Fancy words for a simple idea:"
>
> - **Continuous Integration (CI):** Every change gets checked automatically the moment it's saved. No one has to remember to run the checks.
> - **Continuous Delivery (CD):** When checks pass, the change goes live automatically. No one has to press a "publish" button.

> "You don't need to memorize those terms. When someone says 'CI/CD,' they mean 'automatic checks and automatic publishing.' That pipeline diagram we looked at? That's CI/CD."

Extend the restaurant analogy:

> "CI = the kitchen runs quality checks on every dish without the head chef asking. CD = finished dishes go straight to tables without a manager approving each one."

Ask:

> "Questions about any of this? Or ready to move on?"
>
> **A)** Move on to Lesson 18 — learn how GitHub makes all this work
>
> **B)** I still have questions
>
> **C)** Can you explain how rollback works?

**STOP. Wait for their response.**

If C: explain rollback. "Because every change is saved as a snapshot, you can always rewind to the last version that worked. Like pulling a dish off the menu and going back to last week's recipe. It takes seconds."

---

### Wrap Up

> "Here's what you now know: shipping software safely means running automatic checks at every stage. Save a snapshot, run checks, get a review, preview it, then go live. If anything fails, the change stops before users see it."
>
> "Next up: GitHub, where all of this actually lives."

**Share prompt:** "Explain CI/CD in one sentence using a non-tech analogy."

---

## Reference Material

Key concepts for Claude to explain if the student asks deeper questions:

- **Testing**: Automated checks that verify specific behaviors ("when a user clicks Sign Up, they should see a confirmation message"). Run every time a change is saved.
- **Linting**: Checks for formatting and common mistakes. Like spell-check and grammar-check, but for your product.
- **Continuous Integration**: Automatically running all checks every time a change is saved. The student doesn't need this term. They need the concept.
- **Continuous Delivery**: Automatically publishing changes that pass all checks. Removes the manual "push to production" step.
- **Rollback**: Reverting to a previous snapshot. Because every change is saved with a timestamp, you can always go back.
- **Staging environment**: A private copy of your product for testing. Dress rehearsal before opening night.
- **Feature flags**: Turning features on/off for specific users without a new release. Like a light switch for features.
- **PR previews**: Temporary versions of your site with a specific change applied. Each proposed change gets its own preview URL.

Restaurant analogy extensions:
- Staging = test kitchen for new recipes
- Feature flags = offering a new dish to VIP tables before adding it to the full menu
- Rollback = pulling a dish off the menu when it gets complaints
- Monitoring = walking the dining room and watching if people enjoy their food
- PR previews = letting the manager taste a new dish before it hits the menu
