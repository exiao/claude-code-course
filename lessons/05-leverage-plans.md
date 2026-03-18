# 5. Leverage Plans to Improve Quality

> **Magic Moment:** You see the difference between asking Claude to "just build it" vs. asking Claude to plan first — and realize that 30 seconds of planning prevents 30 minutes of rebuilding.

## Instructions for Claude

You are teaching a non-technical product manager the most important quality habit in this entire course: planning before building. Show them the difference viscerally — don't just tell them planning is good, make them feel the difference. When you create plans, write them in plain language. When you sketch layouts, use simple text characters anyone can read.

### Setup Check

The student should be in their project with their memory file (CLAUDE.md) from Lesson 4.

> "Today's lesson is the single biggest quality upgrade you'll get in this course. The difference between 'AI slop' and genuinely useful output usually comes down to one thing: did you plan first, or did you just wing it?"

### Step 1: Switch to Plan Mode

> "Remember the **Shift + Tab** shortcut from Lesson 1? It switches between modes. Right now you're in Normal mode. I want you to press **Shift + Tab** until you see **Plan** at the bottom of your screen."
>
> "In Plan mode, I'll show you what I *would* do without actually doing it. It's like a preview — perfect for what we're about to learn."

**Wait for them to confirm they're in Plan mode before continuing.**

> "Great! Now — what would you like to build?"
>
> **A)** A new page or section for your product
> **B)** A feature that helps your users do something better
> **C)** Something you've been putting off because it seemed complicated

Once they pick, write a plan and save it to `plan.md` in their project folder. The plan should cover:
- **What we're building** — in one sentence
- **Our approach** — the steps we'll take, in plain language
- **What could go wrong** — potential issues to watch for
- **How big this is** — is this a 5-minute thing or a 30-minute thing?

> "I've saved the plan to `plan.md` so we can reference it later. Take a look — does this match what you had in mind? Now is the cheap moment to change direction. Redirecting a plan takes seconds. Rebuilding something that's already built takes forever."

Update `plan.md` with any changes they request. Do NOT build anything yet.

### Step 2: Sketch Before You Design (Text Wireframes)

> "Before I build anything visual, let me sketch it out with text characters. Think of it as a napkin sketch — rough, fast, just enough to react to."

Generate 3 different ASCII wireframe sketches for their feature, each taking a genuinely different approach. Each sketch should be a visual diagram like these examples:

**Example — Layout A (sidebar navigation):**
```
┌──────┬───────────────────────┐
│ Nav  │  Page Title           │
│      ├───────┬───────┬───────┤
│ Home │ Card  │ Card  │ Card  │
│ Dash │       │       │       │
│ Set. │───────┴───────┴───────│
│      │  Detail view...       │
└──────┴───────────────────────┘
```

**Example — Layout B (top nav, card grid):**
```
┌──────────────────────────────┐
│  Logo        Nav   Nav   Nav │
├──────────────────────────────┤
│                              │
│   Big headline here          │
│   Subtitle text              │
│   [ Get Started ]            │
│                              │
├───────┬───────┬──────────────┤
│ Card  │ Card  │ Card         │
│       │       │              │
└───────┴───────┴──────────────┘
```

**Example — Layout C (single column, focused):**
```
┌──────────────────────────────┐
│         Logo + Nav           │
├──────────────────────────────┤
│                              │
│    [ Search bar         🔍 ] │
│                              │
│    ┌────────────────────┐    │
│    │ Item 1        ►    │    │
│    ├────────────────────┤    │
│    │ Item 2        ►    │    │
│    ├────────────────────┤    │
│    │ Item 3        ►    │    │
│    └────────────────────┘    │
│                              │
└──────────────────────────────┘
```

Present your 3 sketches with labels:

> **Pick the layout that feels closest:**
> - **A)** Layout A — [describe what this layout prioritizes]
> - **B)** Layout B — [describe the different approach]
> - **C)** Layout C — [describe another angle]

> "Which feels closest to what you imagined? Or grab elements from multiple — like 'I like the header from A but the flow from C.'"

### Step 3: Build It

> "Now press **Shift + Tab** to switch back to **Normal** mode (or **Auto-Accept** if you're feeling brave). We're done planning — time to build for real."

**Wait for them to switch modes.**

Now build the feature following the plan and their chosen layout direction.

Open it in the browser so they can see it. Let them react. Do one round of changes based on their feedback.

> "Notice how we didn't have to start over? The plan and sketch caught the big stuff early. We're just fine-tuning now."

### Wrap Up

> "Plan, then sketch, then build. Each step prevented us from building the wrong thing. Plans catch bad ideas. Sketches catch bad layouts. By the time you build, you're just executing a decision you already made."

> **What would you like to do next?**
> - **A)** Move on to Lesson 6 — brainstorm new features grounded in your product
> - **B)** Add another feature using the plan-first approach
> - **C)** Practice sketching layouts for a different idea

**Share prompt:** What feature did you plan and build? Was the planning step worth it, or did it feel like extra work?

## Reference Material

**The Plan-Sketch-Build workflow:**
1. **Plan** — Write down what you're building, your approach, and what could go wrong. This takes 30 seconds and saves 30 minutes.
2. **Sketch** — Create rough text layouts to compare approaches. Reacting to something visual is faster than debating in the abstract.
3. **Build** — Now that you know what you want, build it. Changes at this stage are small tweaks, not full rebuilds.

**Why planning matters so much with AI:**
- AI is fast at building, which means it's fast at building the wrong thing too
- A plan gives you a checkpoint before effort is spent
- It's psychologically easier to change a plan than to throw away something that's already built
- Plans also help Claude give better results — clear direction leads to better output

**Text sketches (wireframes):**
- Use simple text characters to show layout and structure
- The goal is "just enough to react to" — not pixel-perfect
- Always create at least 2-3 options so you can compare
- Mix and match elements from different sketches
