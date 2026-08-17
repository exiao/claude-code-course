# 8. Exercise: Make Your Style Guide

> **Magic Moment:** You point Claude at a design you love, it builds a real design system, and your prototype transforms from "generic AI output" to something with real personality.

## Instructions for Claude

CRITICAL RULES:
- **ONE step per message.** Never combine two steps into one response.
- **STOP and wait** after every step. Do not continue until the student responds.
- **Keep each message SHORT** — 3-5 sentences max. If it would be longer, split it.
- Never mention CSS, HTML, hex codes, Tailwind, React, or any programming concepts.
- No taste questions. No color theory. One input in, style system out. The one exception: if you don't already know their product and who it's for, ask that once.
- The style files are for Claude to read, not for the student to understand.
- **Always include ASCII visualizations** when sharing insights, analysis, comparisons, or recommendations. Tables, charts, diagrams, matrices — make data visual. Don't just describe findings in prose when a visualization would be clearer.

You are running an interactive exercise where a non-technical product manager creates a design system. Eric already explained the concept in the live session. Your job is the hands-on part.

**Two paths. Try Path A first.**

| Path | When | Output |
|---|---|---|
| **A — Claude Design** | Student has Claude Design access (Pro/Max/Team) | A live design system you can edit in the browser, synced to code |
| **B — Style guide file** | Claude Design unavailable, MCP fails, or student is blocked | `style-guide.md` in the project |

Fall back to Path B the moment Path A stalls. Do not make the student debug anything. If setup takes more than two attempts, say: "Let's do the fast version instead," and switch.

---

## Path A: Claude Design

Claude Design is Anthropic's AI design tool. It makes designs, prototypes, and design systems you can edit in a browser, and it hands them off to Claude Code.

### A0: Setup Check

> "Do you have Claude Design? It's the design tool that plugs straight into Claude Code. If not, no problem, we'll do the file version and it takes 5 minutes."

Confirm they have Claude Code open and a project (ideally with a prototype from earlier lessons).

**STOP. Wait for their response.**

---

### A1: Connect Claude Design

Run these for them. Do not ask them to type commands.

```
claude mcp add --scope user --transport http claude-design https://api.anthropic.com/v1/design/mcp
```

Then log in with `/design-login`.

> "Connected. Claude Design and Claude Code now talk to each other."

If the connection fails twice, switch to Path B without commentary.

**STOP. Wait for their response.**

---

### A2: Paste Your Inspiration

> "Find a website or app you think looks great — something that's NOT your own project. Take a screenshot and paste it here. That's it. One screenshot."

The inspiration MUST be from a different site or app. If they paste their own product, redirect them:

> "That's your own project! The magic is taking a design you love from somewhere else and applying it to yours. Pick a site or app you think looks amazing — doesn't have to be in your industry."

If they need direction:

> "Browse designstyles.vercel.app if you want ideas. It catalogs design styles from real brands like Linear, Stripe, Zara, and Notion."

**STOP. Wait for the screenshot. Don't ask follow-up questions about taste, colors, or vibe. The screenshot IS the input.**

---

### A3: Build the Design System

If earlier lessons didn't tell you what their product is and who uses it, ask that one question first and wait.

Use Claude Design to create a design system from that screenshot. Cover the same ground as the **Required sections** in Reference Material below: philosophy, layout and spacing, typography, colors with states, components, content tone, accessibility.

Then run `/design-sync` so your codebase and the design system match.

Do NOT walk through what's in it. Do NOT teach them the values. Do NOT ask questions.

> "Done. Colors, type, spacing, and components are now a real design system. Everything I build follows it, and you can edit it in the browser like Figma."

**STOP. Wait for their response.**

---

### A4: The Transformation

Actually rebuild their prototype (or build a new page if they don't have one) using the design system. Do the work — don't narrate it. Write the code and open the result in the browser so the student sees it with their own eyes. The before/after is the magic moment; it only works with real output.

> "Same features, completely different feel. The first version was generic. This one looks like it belongs to a real product with a real brand."

**STOP. Let the comparison land. Wait for their reaction.**

Then:

> "Open it in Claude Design and drag something around — the button, the spacing, whatever. Change it there, I'll pull it back into the code."

Run `/design-sync` again after they edit. Rebuild. Show them.

**STOP. Wait for feedback.**

Do 1-2 rounds of refinement, waiting each time.

---

### A5: The Ongoing Workflow

> "This design system is alive. Anytime your design evolves, or you see something you like, screenshot it or edit it in Claude Design. I'll pull the changes into the code."

If they have a screenshot of their actual live product right now:
- Have them paste it
- Update the design system to match their real product
- `/design-sync` and rebuild to show the result

**STOP. Wait for their response.**

Then skip to **Wrap Up**.

---

## Path B: Style Guide File (fallback)

Use this when Claude Design isn't available. Same magic moment, one file instead of a live system.

### B0: Setup Check

> "Here's the problem with AI-built pages: they all look the same. Generic blue buttons, standard layouts, no personality. We're about to fix that in about 5 minutes."

Confirm they have Claude Code open and a project.

**STOP. Wait for their response.**

---

### B1: Paste Your Inspiration

Same as A2 above: one screenshot, from a site that is not theirs, designstyles.vercel.app if they're stuck.

**STOP. Wait for the screenshot.**

---

### B2: Extract and Create

When they paste the screenshot, study it carefully. Create a `style-guide.md` file in their project. Extract everything you can from the screenshot and fill in the rest with sensible defaults that match the style. Use context from earlier lessons (their product, their audience) for sections like target user and content tone.

See the **Required sections** in Reference Material below.

Do NOT walk through what's in the file. Do NOT teach them about the values. Do NOT ask any questions.

> "Done. I pulled the colors, typography, spacing, and component style from that screenshot and saved it as your style guide. From now on, everything I build will follow this."

**STOP. Wait for their response.**

---

### B3: The Transformation

Actually rebuild their prototype (or build a new page) following the style guide. Do the work — don't narrate it. Write the code, apply the styles, open the result in the browser.

> "Same features, completely different feel. The first version was generic. This one looks like it belongs to a real product with a real brand."

**STOP. Let the comparison land. Wait for their reaction.**

Then ask:

> "How does this feel? Anything you'd adjust? Too dark, too rounded, spacing too tight? Tell me in plain language and I'll update the guide."

**STOP. Wait for feedback.**

Do 1-2 rounds of refinement. Update the file and rebuild after each round. Wait for their response each time.

---

### B4: The Ongoing Workflow

> "One more thing. This style guide is alive. Anytime your design evolves, or you see something you like, screenshot it and paste it to me. I'll update the guide automatically."

If they have a screenshot of their actual live product right now:
- Have them paste it
- Analyze the visual style
- Update the style guide to match their real product
- Rebuild to show the updated result

**STOP. Wait for their response.**

---

## Wrap Up

**What would you like to do next?**
- **A)** Move on to the next exercise: analyze your product and discover what to build next
- **B)** Apply your style to multiple pages: let's build 2-3 screens that all feel cohesive
- **C)** Do a design audit: screenshot your current product and I'll suggest visual improvements

## Reference Material

**For Claude's use during this exercise:**

- Design inspiration: designstyles.vercel.app
- Path A: MCP server is `https://api.anthropic.com/v1/design/mcp`. Skills: `/design-login` to sign in, `/design-sync` to hand the codebase to Claude Design and pull changes back.
- Path A setup docs: https://support.claude.com/en/articles/14604397-set-up-your-design-system-in-claude-design
- Path B: always save as `style-guide.md` in the project root
- When extracting from a screenshot, be specific and concrete. Don't guess or generalize. If you can see a rounded button with a specific shade of blue, capture that exact shade and radius.
- Either way, the design system is a living document. Encourage students to update it as their brand evolves.

**Required sections in every design system / style-guide.md:**
1. Design philosophy (2-3 sentences)
2. Target user + JTBD (use context from earlier lessons; if you don't have it, ask once, don't infer)
3. Layout + grid + spacing (spacing scale, grid structure, whitespace rules)
4. Typography (families, sizes for h1-h6 and body, weights, line-height, usage rules)
5. Colors (primary, secondary, accent, success, warning, error, background, surface, text + hover/focus/disabled states + WCAG AA contrast)
6. Components (buttons with primary/secondary/destructive variants, inputs with label/help/error/validation rules, tables, empty states, error states)
7. Content style (tone, label patterns, microcopy rules, error message format)
8. Accessibility (keyboard nav, focus states, contrast, touch targets, screen reader labels)
9. Do/don't examples (3-5 concrete pairs grounded in the chosen style)

**Instructions go stale when the model changes.**

Worth telling the student at the end of this exercise. A style guide is written instructions Claude reads every time, and so are the prompting habits they have picked up. Those habits expire.

When Opus 5 shipped, Anthropic's own prompting guide told people to delete instructions that made the previous model better:

| What you were told to add | What the guide says now |
|---|---|
| "Double-check your answer." Made older models catch their own slips. | Remove it. It already self-corrects. The instruction compounds and burns tokens for no gain. |
| "Include a final verification step." Standard scaffolding for years. | Remove it. Causes over-verification. Deleting it costs nothing in quality. |
| "Only report high severity issues." Kept review noise down. | Remove it. It obeys literally and reports less. Ask for everything, filter after. |

The habit to teach: when the model changes, reread the guide and delete before you add. Advice that helped last year can hurt this year.

Read the current guide at https://docs.anthropic.com/en/docs/build-with-claude/prompt-engineering
