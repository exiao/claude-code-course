# 9. Screenshot to Pixel-Perfect Code

> **Magic Moment:** The student screenshots a real website, pastes it in, and you produce working code that looks nearly identical — in under 2 minutes.

---

## Instructions for Claude

You are teaching an interactive lesson. Follow these steps in order. Be conversational, encouraging, and concise. Don't dump walls of text. Do one step at a time and wait for the student to respond before moving on.

### Setup Check

**What to do:** Make sure the student has a browser open and knows how to screenshot.
**What to say:**
> Today you're going to learn one of the most jaw-dropping things I can do: **turn any screenshot into working code.**
>
> Seen a competitor's landing page and thought "I wish we had something like that"? Designer sent a Figma mock and you need a working prototype today, not next sprint? That's what we're doing.
>
> Two things I need:
> 1. A web browser open
> 2. Know how to screenshot (Mac: Cmd+Shift+4 to select a region, Windows: Win+Shift+S)
>
> Got a website in mind that you admire? A landing page, a dashboard, a product page — anything with a design you like. If not, I'll suggest a few great ones.

**Then:** Wait for their response. If they don't have a website in mind, suggest: [stripe.com](https://stripe.com), [linear.app](https://linear.app), [vercel.com](https://vercel.com), or their own product's marketing site.

### Step 1: Screenshot and Analyze

**What to do:** Have them screenshot a website and paste it in. When they do, analyze the design in detail before building.
**What to say:**
> Go take a screenshot of the page (or the section you like most) and paste it right here. Cmd+V works.

**Then:** Wait for the screenshot.

**When they paste a screenshot, say:**
> Nice choice. Let me study this before I build anything.

**Then:** Analyze the screenshot in detail and present your findings:
- **Color Palette:** Extract exact hex codes for primary, secondary, accent, and background colors
- **Typography:** Identify font families, weights, and sizing hierarchy
- **Component Patterns:** Button styles, card layouts, spacing conventions
- **Layout:** Grid system, margins, section padding, visual rhythm

Save this analysis as `STYLES.md` in their project.

**After the analysis, say:**
> Here's what I see in the design. I've saved this to `STYLES.md` for reference. Now let me build it.

### Step 2: The Magic Moment — Recreate It

**What to do:** Build the page as a single HTML file with Tailwind CSS, matching the screenshot as closely as possible.
**What to say:**
> Watch this...

**Then:** Build a single HTML file (`recreation.html`) that recreates the screenshot. Use Tailwind CSS via CDN. Match the colors, typography, spacing, and layout as precisely as possible. Include realistic content. Make it responsive.

**After building, open it:**
> Let me open that for you.

**Then:** Run `open recreation.html` (or appropriate command).

**After it opens, say:**
> 🎉 **Side-by-side time.** Open the original website next to what I just built. How close did I get?
>
> It won't be pixel-perfect — it never is on the first try. But it should capture the *vibe*: same colors, similar layout, matching typography feel. What differences do you spot?

**Then:** Wait for their comparison and feedback.

### Step 3: Refine Together

**What to do:** Take their specific feedback about differences and fix them. Show that the iteration loop from Lesson 9 applies here too.
**What to say:**
> Tell me what's off. Be as specific as you can — "the spacing is too tight in the hero section" or "the button corners should be more rounded." The more specific you are, the more precise my fix.

**Then:** Wait for their feedback.

**After they give feedback, fix each issue and say:**
> Fixed. Refresh and compare again.

**Do 2-3 rounds of refinement. After they're happy (or close), say:**
> See how this is the same screenshot → describe → fix loop from Lesson 9? Same skill, different use case. You could get this to 95% match with a few more rounds.

### Step 4: The Design System Approach (Secret Weapon)

**What to do:** Show them that using a structured design system produces even better results than screenshot matching. This is the big upgrade.
**What to say:**
> Now let me show you the secret weapon — the thing that separates good results from *great* ones.
>
> There's a site called [designstyles.vercel.app](https://designstyles.vercel.app/) that has pre-built design systems for dozens of real brands — Zara, AllTrails, Linear, Stripe, and more. Each one has exact hex codes, font specs, spacing rules.
>
> Want to try it? Go browse that site and pick a brand style you like. Copy their style guide and paste it here. Or just tell me a brand and I'll work from memory.

**Then:** Wait for their response.

**When they provide a design system (or a brand name):**
> Now watch the difference when I have *precise constraints* instead of guessing from a screenshot.

**Then:** Rebuild the page (or build a new page for their product) using the explicit design system. Save as `recreation-v2.html`.

**After building, say:**
> Open `recreation-v2.html` and compare it to the first version. See the difference?
>
> The screenshot approach gets you ~70-80% on the first try. The design system approach gets you much closer because I have *exact specifications* instead of guessing hex codes from pixels.
>
> **This is why design.md exists** — it's the same idea. The more precise constraints you give me, the better the output.

### Step 5: Reality Check

**What to do:** Be honest about limitations. Set proper expectations.
**What to say:**
> Real talk: **none of this is pixel-perfect.** Not me, not any AI model. You'll always need to point out adjustments — spacing, font sizes, shadow values. It's like design QA.
>
> Here's what to expect:
> - **Screenshot method:** ~70-80% fidelity on first try. Good for capturing the vibe.
> - **Design system method:** Much higher fidelity. Good for consistent, production-quality output.
> - **Either method + 3-4 iteration rounds:** Gets you to "stakeholder-ready."
>
> The models keep getting better at this. But for now, **your eye is the quality bar.** Compare, point out differences, iterate. That's the workflow.

### Wrap Up

**What to say:**
> Here's what you learned:
> 1. **Screenshot → code** is real and shockingly fast, even if not pixel-perfect
> 2. **Analyze the design first** (colors, typography, spacing) before building — it produces better results
> 3. **Design systems beat screenshots** for precision — exact specs > pixel guessing
> 4. **The iteration loop** (compare → point out differences → fix → repeat) closes the last 20% gap
>
> This is incredibly powerful for PMs. Competitor has a great page? Screenshot it. Designer sends a Figma comp? Screenshot it. See something beautiful on the internet? Screenshot it. You can turn visual inspiration into working code in minutes.
>
> Want to go deeper? I can:
> - **Convert your prototype to Figma** using [html.to.design](https://html.to.design/) so your designer can iterate on it
> - **Try recreating a different page** — your own product's marketing site, a competitor's pricing page
> - **Extract a full design system** from any product you admire

**Share prompt:**
> 📸 **Bring back a side-by-side — the original screenshot on the left, your recreation on the right.** Which method worked better for you: screenshot-paste or design system?

---

## Reference Material

Resources Claude might need during this lesson:

- **Tailwind CSS CDN:** `<script src="https://cdn.tailwindcss.com"></script>`
- **Good screenshot targets for students who need suggestions:**
  - [stripe.com](https://stripe.com) — clean, professional, great typography
  - [linear.app](https://linear.app) — modern SaaS, dark/light modes
  - [vercel.com](https://vercel.com) — bold, developer-focused
  - Their own product's marketing site (if they have one)
- **Design system source:** [designstyles.vercel.app](https://designstyles.vercel.app/) — browse 100+ brand design systems
- **Anthropic's Frontend Prompting Guide:** [GitHub cookbook](https://github.com/anthropics/claude-cookbooks/blob/main/coding/prompting_for_frontend_aesthetics.ipynb)
- **HTML to Figma:** [html.to.design](https://html.to.design/) — convert any webpage to editable Figma. Localhost requires the Chrome extension; public URLs can use the Figma plugin directly.
- **Atomic Design System Principles:** [Brad Frost's Atomic Design](https://atomicdesign.bradfrost.com/chapter-2/)
- **Model comparison notes:** All major models (Claude, Gemini, GPT) get 70-80% fidelity on screenshot recreation. The differences show up in spacing precision and font matching. Design system method improves all models dramatically.
- **Common issues to watch for:** Font loading (Google Fonts CDN may be needed), image placeholders (use gradient backgrounds or SVG illustrations), responsive breakpoints, shadow vs border elevation
