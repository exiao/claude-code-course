# 6. Build Many Prototypes at Once

> **Magic Moment:** You give Claude several ideas, it sketches them all as ASCII wireframes, you pick which ones to build, and Claude builds them all simultaneously — then you compare them side by side.

## Instructions for Claude

CRITICAL RULES:
- **ONE step per message.** Never combine two steps into one response.
- **STOP and wait** after every step. Do not continue until the student responds.
- **Keep each message SHORT** — 3-5 sentences max.
- Use the AskUserQuestion tool whenever you need more info.
- **Always include ASCII visualizations** when sharing insights, analysis, comparisons, or recommendations. Tables, charts, diagrams, matrices — make data visual. Don't just describe findings in prose when a visualization would be clearer.

---

### Step 1: What Do You Want to Build?

> "Now that we've learned to plan, let's go big. What ideas do you want to build? Give me a few — at least 3. They can be features, pages, tools, anything."

If they're stuck, offer:

> **A)** Tell me what problems your users have — I'll suggest ideas
> **B)** I'll look at your project and suggest what's missing
> **C)** Let me brainstorm 5 ideas based on what I know about your product

**STOP. Wait for their response.**

---

### Step 2: Sketch Them All

Generate an ASCII wireframe for each idea (up to 5). Keep each sketch small (5-8 lines). Label what each one does.

> "Here are sketches for each idea. Which ones do you want me to actually build? Pick as many as you want."

**STOP. Wait for their choices.**

---

### Step 3: Build Them All at Once

> "Here's the fun part. I'm going to build all of these at the same time using **subagents** — think of them as mini-Claudes that each work on a separate task simultaneously."

```
You pick 3 ideas
      │
      ├──► Subagent 1 → builds prototype A
      ├──► Subagent 2 → builds prototype B
      └──► Subagent 3 → builds prototype C
      │
All three finish → you compare them side by side
```

Build each prototype as a separate file. Open them all in the browser.

> "Open all of them. Don't think too hard — just notice your gut reaction. Which one pulls you in?"

**STOP. Wait for their reaction.**

---

### Step 4: Pick and Combine

> "You're not picking a winner — you're shopping for the best parts. What did you like from each one?"

**STOP. Wait for their response.**

Combine the best elements into a final version.

> "Here's your final version — the best parts of everything combined."

---

### Wrap Up

> **What would you like to do next?**
> - **A)** Move on to Day 3 — make everything look beautiful and match your brand
> - **B)** Build more prototypes
> - **C)** Publish your favorite version

**Share prompt:** Show the cohort your prototypes — which direction did you pick and why?

---

## Reference Material

**Subagents:**
- Fresh, isolated sessions Claude spins up for focused tasks
- Each gets one clear set of instructions and returns results when done
- Each prototype should be a separate file so students can compare side by side

**Prototyping mindset:**
- Prototypes are disposable — their purpose is learning, not shipping
- Speed matters more than polish at this stage
- Reacting to something real is faster than imagining it
- The real skill is combining A + B + C into D
