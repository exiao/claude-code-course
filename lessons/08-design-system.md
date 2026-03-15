# 8. Give Claude Your Design System

> **Magic Moment:** The student creates a DESIGN.md file — from brand personality to specific design tokens — you rebuild their prototype, and it transforms from "generic Claude output" to something that looks like it belongs in THEIR product.

---

## Instructions for Claude

You are teaching an interactive lesson. Follow these steps in order. Be conversational, encouraging, and concise. Don't dump walls of text. Do one step at a time and wait for the student to respond before moving on.

### Setup Check

**What to do:** Check if they have a prototype from earlier lessons and learn about their product's visual identity.
**What to say:**
> Hey! Today we're going to fix the biggest problem with AI-generated UI: **it all looks the same.** Blue buttons, gray backgrounds, the same Tailwind defaults everyone gets. Fine for a throwaway prototype — but the moment you show it to a stakeholder, they'll say "this doesn't look like us."
>
> The fix takes 10 minutes and pays off forever. By the end, you'll have a personal design system that makes every future build match your brand automatically.
>
> Quick check:
> 1. Do you have a prototype from an earlier lesson? (If not, we'll build a quick one)
> 2. Here's the important one: **What does YOUR product look like?** Do you know your brand colors, fonts, or visual style? Even a vague sense — "we're kind of like Linear" or "our brand color is purple" — works great.

**Then:** Wait for their response. Adapt based on what they know about their brand. If they have no product/brand yet, help them pick an aesthetic direction.

### Step 1: See the Problem

**What to do:** If they have a prototype, have them open it. If not, quickly build a simple one. Point out the generic design.
**What to say:**
> Open your prototype and look at it with your "brand eyes." Notice anything?
>
> - The colors are generic — probably blue and gray
> - The spacing follows Tailwind defaults, not your product's rhythm
> - The typography has no personality
> - It looks like *a* product, not *your* product
>
> This is what happens when I have zero design context. Let's fix that right now.

**Then:** Move to the next step. If they don't have a prototype, quickly build a simple dashboard HTML page with generic styling so they can see the before/after contrast.

### Step 2: Browse for Inspiration

**What to do:** Guide them to find a design system they connect with. Make this feel like shopping, not homework.
**What to say:**
> Before we build your design system, let's go shopping for your aesthetic. Open [designstyles.vercel.app](https://designstyles.vercel.app/) in your browser.
>
> This site catalogs design systems from real brands — Zara, AllTrails, Linear, Stripe, and dozens more. Browse a few and find one that matches the *feeling* you want for your product:
>
> - **Professional & clean?** Check out Linear or Stripe
> - **Bold & editorial?** Try Zara
> - **Warm & adventurous?** Look at AllTrails
> - **Minimal and calm?** Check out Things or iA Writer
>
> Click into one and read the style guide. Notice how specific it is — exact hex codes, font families, border-radius values. That specificity is what makes it work.
>
> Tell me which one resonates, or describe the vibe you want if none of them are quite right.

**Then:** Wait for their response. They might name a brand from the site, describe a vibe in their own words, or say they already know what they want.

### Step 3: Create Their DESIGN.md

**What to do:** Build a comprehensive design system file interactively based on their answers and inspiration. Ask targeted questions and fill it in.

**If they picked a brand from designstyles.vercel.app:**
**What to say:**
> Great choice. Let me build your DESIGN.md based on that aesthetic, adapted for your product. A couple quick questions to customize it:
> 1. **Primary brand color?** Hex code if you have it, or just say "deep purple" / "ocean blue" and I'll pick a good one.
> 2. **What does your product do?** (One sentence — so I can tune the mood)

**If they want to create from scratch:**
**What to say:**
> Let's build one from scratch. A few quick questions:
> 1. **What does your product do?** (One sentence)
> 2. **Pick the personality:** Clean and professional (like Linear), Warm and friendly (like Notion), Bold and energetic (like Figma), or Minimal and calm (like iA Writer)?
> 3. **Primary brand color?** Hex code if you have it, or just "deep purple" / "forest green" and I'll pick a good one.
> 4. **Name 2-3 products whose visual style you admire.** These become our design inspiration.

**Then:** Wait for their answers.

**After getting their answers, say:**
> Perfect — let me build your design system.

**Then:** Create a `DESIGN.md` file in their project root with all the proper sections:
- Design philosophy (mood, audience, reference the inspiration they chose)
- Colors (primary, primary hover, secondary, accent, background, surface, text primary/secondary, border, success/warning/error — all with specific hex codes)
- Typography (font families, weights, size hierarchy for h1, h2, body, labels, UI elements)
- Spacing (base unit, card padding, section gaps, page margins)
- Components (buttons with padding/border-radius/shadows, cards, inputs, tables, modals)
- Patterns (elevation approach, hover states, empty states, loading, transitions)

Fill in all values based on their answers. Choose specific hex codes, Tailwind classes, and values that match the personality and inspiration they described.

**If they don't know their brand colors:** Offer to help: "Want to screenshot your product's homepage or marketing site? I can extract the colors for you." If they paste a screenshot, extract hex codes from it.

### Step 4: Wire It Up to CLAUDE.md

**What to do:** Add a reference to `DESIGN.md` in their `CLAUDE.md` file so it's automatically loaded every session.
**What to say:**
> Now let me make sure I always read this. I'll add a reference to your `CLAUDE.md` so every future session starts with your design context loaded.

**Then:** Update their `CLAUDE.md` file (create it if it doesn't exist) to include a line like: "Read DESIGN.md for all visual design decisions. Follow the design system for every UI component you build."

**After updating, say:**
> Done. From now on, every time you start a session with me, I'll automatically know your visual style. No more generic blue buttons.

### Step 5: The Magic Moment — Rebuild and Compare

**What to do:** Rebuild an existing prototype using the design system. Save as a separate file so they can compare.
**What to say:**
> Now watch this. I'm going to rebuild the exact same prototype — same features, same data — but this time I'll follow every design token in your DESIGN.md exactly. Let's see the difference.

**Then:** Read `DESIGN.md`, then build `prototype-styled.html` with the same features as their original prototype but following the design system exactly. Match the colors, typography, spacing, and component styles.

**After building, say:**
> Open both files side by side:
> - `prototype.html` — the generic version
> - `prototype-styled.html` — YOUR version
>
> **Same feature, completely different feel.** The second one looks like it belongs in your product. That's not me being creative — that's me following specific design tokens. Constraints make better design.

**Then:** Wait for their reaction. Let them absorb the difference.

### Step 6: The Screenshot Workflow (Power Move)

**What to do:** Teach them how to use screenshots to enrich their design system over time. If they can provide a screenshot of their product, do this live.
**What to say:**
> Here's the power move for ongoing design iteration: anytime your product's design evolves, screenshot it and paste it to me. I'll update your `DESIGN.md` automatically.
>
> Want to try it? If you have any screenshot of your product — your best screen, your marketing site, a Figma comp — paste it in and I'll extract the design details.

**Then:** If they paste a screenshot, analyze it for specific details (border-radius values, shadow styles, spacing patterns, color usage, typography weights) and update `DESIGN.md` with anything new. If they don't have a screenshot, explain the workflow and move on.

### Step 7: The Figma Bridge (Bonus)

**What to do:** Show them how to close the design-to-code loop with html.to.design and Figma MCP. This is optional — only go here if they're engaged and interested.
**What to say:**
> Want to see something cool? If you need to share your prototype with a designer in Figma, there's a bridge for that.
>
> **Option 1: HTML to Figma**
> [html.to.design](https://html.to.design/) converts any webpage into editable Figma layers. If your prototype is running locally, you'll need their Chrome extension. Public URLs can use the Figma plugin directly.
>
> **Option 2: Figma to Code (with Figma MCP)**
> If you connect the Figma MCP server, I can read your Figma designs directly — no screenshots needed. Set it up with:
> ```
> claude mcp add --transport http figma https://mcp.figma.com/mcp
> ```
> Then restart Claude Code and authenticate.
>
> Want to try either of these? Or would you prefer to keep iterating on the design itself?

**Then:** If they want to try Figma MCP, walk them through the setup. If they want html.to.design, explain the Chrome extension vs. Figma plugin distinction. If they want to keep going with design iteration, wrap up.

### Wrap Up

**What to say:**
> Here's what you built today: a **personal design system that lives in your codebase.** Every time I start a session, I read CLAUDE.md, find the reference to DESIGN.md, and follow your design tokens automatically. Every new screen, every new component, every iteration matches your brand.
>
> The before/after tells the whole story: without a design system, you get generic AI output. With one, you get something that looks like it has a real designer behind it.
>
> The maintenance is dead simple — whenever your design evolves, paste a screenshot of the new look and tell me to update DESIGN.md. Takes 30 seconds.
>
> Want to go deeper? I can:
> - **Apply your design system to multiple pages** — build a full set of screens that all feel cohesive
> - Do a **design audit** of your current product — screenshot it and I'll tell you what looks off and what 3 changes would have the biggest impact
> - **Extract a design system from any product** you admire — screenshot their site and I'll reverse-engineer their design tokens
> - **Evaluate your UI against Jakob Nielsen's 10 usability heuristics**
> - **Set up the Figma MCP** so I can read your designs directly

**Share prompt:**
> Bring back your before-and-after — the same screen without DESIGN.md vs. with it. What brand style did you choose and why?

---

## Reference Material

Resources Claude might need during this lesson:

- **Design system source:** [designstyles.vercel.app](https://designstyles.vercel.app/) — 100+ brand design systems
- **Design inspiration sources:** Products to reference for personality types — Linear (clean/professional), Notion (warm/friendly), Figma (bold/energetic), iA Writer (minimal/calm), Stripe (polished/trustworthy)
- **Color palette generators:** If the student gives a single brand color, generate a complementary palette (hover states, backgrounds, text, accents) using standard color theory
- **Jakob Nielsen's 10 Usability Heuristics:** [NN/g article](https://www.nngroup.com/articles/ten-usability-heuristics/) — reference for design philosophy section:
  1. Visibility of system status
  2. Match between system and real world
  3. User control and freedom
  4. Consistency and standards
  5. Error prevention
  6. Recognition rather than recall
  7. Flexibility and efficiency of use
  8. Aesthetic and minimalist design
  9. Help users recognize, diagnose, and recover from errors
  10. Help and documentation
- **UX Mapping Methods:** [NN/g cheat sheet](https://www.nngroup.com/articles/ux-mapping-cheat-sheet/) — design thinking methods
- **Typography best practices:** Inter is the safe default (system-ui fallback). For more personality: DM Sans (friendly), Space Grotesk (techy), Instrument Serif (editorial)
- **Good font pairings for design systems:**
  - Clean/professional: Inter + system-ui
  - Friendly/warm: DM Sans + system-ui
  - Techy/modern: Space Grotesk + JetBrains Mono (for code)
  - Editorial/bold: Instrument Serif + Inter
- **Common DESIGN.md mistake:** Being too vague. "Blue accent color" is bad. "#2563EB with hover:#1D4ED8" is good. Push for specificity.
- **Screenshot color extraction:** When analyzing screenshots, provide exact hex codes, not just color names
- **HTML to Figma:** [html.to.design](https://html.to.design/) — localhost needs Chrome extension, public URLs use Figma plugin
- **Figma MCP setup:** `claude mcp add --transport http figma https://mcp.figma.com/mcp` then restart and authenticate
- **DESIGN.md vs design.md:** Either filename works. If the student already has a lowercase `design.md`, work with that — don't create a duplicate.
