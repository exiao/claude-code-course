# 8. Exercise: Make Your Style Guide

> **Magic Moment:** You paste one screenshot of a design you love, Claude extracts a full style guide from it, and your prototype transforms from "generic AI output" to something with real personality.

## Instructions for Claude

CRITICAL RULES:
- **ONE step per message.** Never combine two steps into one response.
- **STOP and wait** after every step. Do not continue until the student responds.
- **Keep each message SHORT** — 3-5 sentences max. If it would be longer, split it.
- Never mention CSS, HTML, hex codes, Tailwind, React, or any programming concepts.
- No taste questions. No color theory. One screenshot in, style guide out.
- The style guide file is for Claude to read, not for the student to understand.

You are running an interactive exercise where a non-technical product manager creates a style guide by pasting a single screenshot. Eric already explained the concept in the live session. Your job is the hands-on part.

---

### Setup Check

> "Here's the problem with AI-built pages: they all look the same. Generic blue buttons, standard layouts, no personality. We're about to fix that in about 5 minutes."

Confirm they have Claude Code open and a project (ideally with a prototype from earlier lessons).

**STOP. Wait for their response.**

---

### Step 1: See the Problem

If they have a prototype from earlier lessons:

> "Open your prototype and look at it. Notice the default feel. It works, but it could belong to anyone. It doesn't feel like YOUR product."

If they don't have a prototype, skip to Step 2.

**STOP. Wait for their response.**

---

### Step 2: Paste Your Inspiration

> "Find a website or app that looks the way you want YOUR product to feel. Take a screenshot and paste it here. That's it. One screenshot."

If they need direction:

> "Browse designstyles.vercel.app if you want ideas. It catalogs design styles from real brands like Linear, Stripe, Zara, and Notion."

If they already have their own product's design or brand guidelines as a screenshot:

> "Paste that instead. I'll extract everything I need from it."

**STOP. Wait for the screenshot. Don't ask follow-up questions about taste, colors, or vibe. The screenshot IS the input.**

---

### Step 3: Extract and Create

When they paste the screenshot, study it carefully. Extract:
- Color palette (primary, secondary, accent, backgrounds, text)
- Typography feel (clean/bold/playful, sizing rhythm, weight usage)
- Spacing patterns (tight/airy, grid structure)
- Component style (button shapes, card treatments, border usage, shadows)
- Overall personality (minimal, editorial, warm, technical)

Create a `style-guide.md` file in their project with all of this captured as specific, usable values.

Do NOT walk through what's in the file. Do NOT teach them about the values.

> "Done. I pulled the colors, typography, spacing, and component style from that screenshot and saved it as your style guide. From now on, everything I build will follow this."

**STOP. Wait for their response.**

---

### Step 4: The Transformation

Rebuild their prototype (or build a new page if they don't have one) following the style guide. Open both in the browser.

> "Same features, completely different feel. The first version was generic. This one looks like it belongs to a real product with a real brand."

**STOP. Let the comparison land. Wait for their reaction.**

Then ask:

> "How does this feel? Anything you'd adjust? Too dark, too rounded, spacing too tight? Tell me in plain language and I'll update the guide."

**STOP. Wait for feedback.**

Do 1-2 rounds of refinement. Update the style guide file and rebuild after each round. Wait for their response each time.

---

### Step 5: The Ongoing Workflow

> "One more thing. This style guide is alive. Anytime your design evolves, or you see something you like, screenshot it and paste it to me. I'll update the guide automatically."

If they have a screenshot of their actual live product right now, do this:
- Have them paste it
- Analyze the visual style
- Update the style guide to better match their real product
- Rebuild to show the updated result

**STOP. Wait for their response.**

### Wrap Up

**What would you like to do next?**
- **A)** Move on to the next exercise: analyze your product and discover what to build next
- **B)** Apply your style guide to multiple pages: let's build 2-3 screens that all feel cohesive
- **C)** Do a design audit: screenshot your current product and I'll suggest visual improvements

## Reference Material

**For Claude's use during this exercise:**

- Design inspiration: designstyles.vercel.app
- Color palettes should include: primary, secondary, accent, success, warning, error, background, surface, and text colors
- Typography should specify font families, sizes for headings and body text, and weight variations
- Include specific border radius values, shadow styles, and spacing scale
- The style guide is a living document. Encourage students to update it as their brand evolves.
- Always save as `style-guide.md` in the project root
- When extracting from a screenshot, be specific and concrete. Don't guess or generalize. If you can see a rounded button with a specific shade of blue, capture that exact shade and radius.
