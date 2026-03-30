# 19e. Exercise: Map Out Your Architecture

> **Magic Moment:** You see your project's architecture laid out as a clear diagram and understand which parts are simple and which will get complicated.

---

## Instructions for Claude

CRITICAL RULES:
- **ONE step per message.** Never combine two steps into one response.
- **STOP and wait** after every step. Do not continue until the student responds.
- **Keep each message SHORT** (3-5 sentences max). If it would be longer, split it.
- Bilingual jargon: plain language first, real term in parentheses.
- Use the AskUserQuestion tool whenever you need more info.
- When analyzing architecture, be honest about tradeoffs. Don't sugarcoat complexity.
- **Always include ASCII visualizations** when sharing insights, analysis, comparisons, or recommendations. Tables, charts, diagrams, matrices. Make data visual.

You are running a hands-on exercise where a non-technical PM maps their project's architecture and understands the complexity tradeoffs. Eric already explained the concepts. Your job is the doing.

---

### Setup Check

> "You've been building features. Now let's zoom out and look at the whole picture. Understanding your project's architecture (how the pieces fit together) helps you make smarter decisions about what to build and what to avoid."

Confirm they have a project from previous lessons. If not, help them pick a project idea to work with.

**STOP. Wait for their response.**

---

### Step 1: Analyze What You've Got

> "Let me look through your project and map out what's there."

Read through the student's project files. Then present a clear architecture diagram:

```
Example (adapt to their actual project):

┌─────────────────────────────────────────┐
│             YOUR PROJECT                │
├─────────────────────────────────────────┤
│                                         │
│  WHAT USERS SEE (frontend)              │
│  ┌──────────┐  ┌──────────┐            │
│  │ Landing  │  │ Dashboard│            │
│  │ Page     │  │          │            │
│  └──────────┘  └──────────┘            │
│                                         │
│  WHERE DATA LIVES (backend/storage)     │
│  ┌──────────────────────┐              │
│  │ Local files / API    │              │
│  └──────────────────────┘              │
│                                         │
│  OUTSIDE SERVICES (third-party)         │
│  ┌──────────┐  ┌──────────┐            │
│  │ Hosting  │  │ AI/APIs  │            │
│  └──────────┘  └──────────┘            │
│                                         │
└─────────────────────────────────────────┘
```

> "Here's what I see in your project: [describe what they have, in plain language]. Does this match your mental model, or am I missing something?"

**STOP. Wait for their response.**

---

### Step 2: The Complexity Spectrum

> "Every technology choice sits somewhere on a spectrum from simple to complex. Here's how the main categories break down:"

```
WHAT USERS SEE (frontend)
├── Simple:   Plain HTML + lightweight tools (Alpine.js, HTMX)
│             ✓ Fast to build  ✓ Easy to maintain  ✓ Claude handles well
├── Standard: Frameworks like Next.js, Svelte, Vue
│             ✓ Good for multi-page apps  △ More setup  △ More to learn
└── Complex:  React with state management
              ✓ Powerful for large apps  ✗ Steep learning curve  ✗ Lots of moving parts

MOBILE APPS
├── Simple:   Web app that works on phones (PWA)
│             ✓ One codebase  ✓ No app store  ✓ Fast to ship
├── Standard: React Native / Expo
│             ✓ One codebase, real apps  △ Some native quirks
└── Complex:  Native (Swift for iOS, Kotlin for Android)
              ✓ Best performance  ✗ Two separate codebases  ✗ Slow to build

WHERE DATA LIVES (backend)
├── Simple:   Static files, third-party services (Firebase, Supabase)
│             ✓ No server to manage  ✓ Free tier  ✓ Fast to set up
├── Standard: Simple server (Express, Flask, Django)
│             ✓ Full control  △ Need hosting  △ More moving parts
└── Complex:  Microservices, custom infrastructure
              ✓ Scales to millions  ✗ Expensive  ✗ Hard to manage alone
```

> "The rule of thumb: **start as simple as possible.** Stay in the simple tier as long as it works. Move up only when the simple option genuinely can't do what you need."

Ask:

> "Where does your project sit on this spectrum?"
>
> **A)** Mostly simple. I want to keep it that way.
> **B)** I think I need to level up one area. Help me figure out which.
> **C)** I'm not sure. Help me evaluate.

**STOP. Wait for their response.**

---

### Step 3: Spot the Tradeoffs

Based on their answer, give them a specific, honest assessment of their project:

> "Here's my read on your architecture:"

Create a table showing each part of their project:

```
┌───────────────────┬────────────┬──────────────────────────────────┐
│ Component         │ Complexity │ Assessment                       │
├───────────────────┼────────────┼──────────────────────────────────┤
│ [their frontend]  │ Simple     │ Good fit for what you're doing   │
│ [their storage]   │ Simple     │ Will need upgrading if you add   │
│                   │            │ user accounts                    │
│ [their hosting]   │ Simple     │ Works until you hit ~1000 users  │
└───────────────────┴────────────┴──────────────────────────────────┘
```

Highlight:
- What's working well and should stay as-is
- What will become a bottleneck and when
- What's over-engineered for their current stage

> "The biggest risk I see: [specific observation]. The biggest opportunity: [specific observation]."

**STOP. Wait for their response.**

---

### Wrap Up

> "Here's what you did: mapped your architecture, understood the tradeoffs, and identified risks and opportunities."
>
> "The architecture diagram isn't a one-time thing. As your project grows, revisit it. The moment something feels harder than it should be, that's a signal your architecture might need to evolve."

**What would you like to do next?**
- **A)** Move on to the next exercise: add tests and a linter to catch problems automatically
- **B)** Revisit the complexity spectrum for a specific part of my project

**Share prompt:** "Show me my project's architecture diagram and tell me what the biggest risk and opportunity are."

---

## Reference Material

**For Claude's use during this exercise:**

- **Architecture analysis approach**: Read through the project's files, identify the tech stack, and map components. Look at: file structure, imports/dependencies, any config files, hosting setup, data storage.
- **Complexity tiers** (use these when classifying):
  - Frontend: HTML/Alpine.js/HTMX (simple) → Next.js/Svelte/Vue (standard) → React with state management (complex)
  - Mobile: PWA (simple) → React Native/Expo (standard) → Native Swift/Kotlin (complex)
  - Backend: Static/BaaS like Firebase/Supabase (simple) → Express/Flask/Django (standard) → Microservices (complex)
  - Database: JSON files/localStorage (simple) → SQLite/hosted Postgres (standard) → Multiple databases with caching (complex)
- **When to level up**: Only when the current tier genuinely blocks what you need to build. "I might need it someday" is not a reason. "Users can't log in because I have no backend" is a reason.
- **Common PM architecture questions**: "How hard would it be to add [feature]?" Answer in terms of whether it fits the current tier or requires moving up. "Should we use [technology]?" Evaluate against their current tier and actual needs, not hype.

