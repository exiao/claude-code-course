# 3. Iterate, Improve, and Share Your Site

> **Magic Moment:** The student picks a design improvement from a menu of real UX techniques, applies it to their site with Claude's help, then publishes the updated version live — all in one lesson.

---

## Instructions for Claude

This is an interactive lesson. Go one step at a time. Wait for the student to respond before moving on. The student has a site from Lesson 2. This lesson is about making it better using proven design techniques, then publishing and sharing it. Keep the energy high — they're about to level up their site and put it in front of real people.

**Whenever you need information from the student, use the AskUserQuestion tool.** Don't guess — ask.

**Always include ASCII visualizations** when sharing insights, analysis, comparisons, or recommendations. Tables, charts, diagrams, matrices — make data visual. Don't just describe findings in prose when a visualization would be clearer.

---

### Setup Check

The student should have their site from Lessons 1 and 2 in `pm-playground` (as `my-site.html`). Make sure you can find it. If something's off, help them get back on track quickly.

**Important:** When making improvements in this lesson, edit the existing `my-site.html` file. Do NOT create a new file or overwrite `hello.html` from Lesson 1.

Open their site in the browser so they can see the current state.

> "Your site is looking good — but we're about to make it look *great*. Today you'll learn proven design techniques that professional designers use, apply them to your site, and then publish the updated version so anyone can see it."

Confirm they have a browser open and know how to take screenshots:

> - **Mac:** Press Command + Shift + 4, then drag to select what you want to capture
> - **Windows:** Press the Windows key + Shift + S, then drag to select

---

### Step 1: Pick a Design Improvement

Look at the student's current site and pick the 3 most impactful improvements from the list below. Present ONLY those 3, with a small ASCII sketch showing what each would look like on THEIR site. Keep it short.

> "Let me suggest 3 improvements that would make the biggest difference for your site. Here's what each would look like:"

Then show 3 options, each with a small ASCII visual. For example:

> **A) Glassmorphism** — frosted glass effect
> ```
> ┌──────────────────────┐
> │ ░░░ blurred bg ░░░░░ │
> │ ┌──────────────────┐ │
> │ │  Your content     │ │
> │ │  floats on glass  │ │
> │ └──────────────────┘ │
> └──────────────────────┘
> ```
> *[Learn more](https://www.nngroup.com/articles/glassmorphism/)*
>
> **B) Micro-interactions** — hover effects & smooth transitions
> ```
> [ Button ]  →  hover  →  [ ✨ Button ✨ ]
>  static        ───►        animated
> ```
> *[Learn more](https://www.nngroup.com/articles/microinteractions/)*
>
> **C) Skeleton loading** — placeholder shapes while content loads
> ```
> ┌──────────────────────┐
> │ ████████░░░░░░░░░░░░ │
> │ ██████████████░░░░░░ │
> │ █████░░░░░░░░░░░░░░░ │
> └──────────────────────┘
>   ↓ content appears ↓
> ┌──────────────────────┐
> │ Welcome back, Sarah  │
> │ Your dashboard is... │
> │ 3 new updates        │
> └──────────────────────┘
> ```
> *[Learn more](https://www.nngroup.com/articles/skeleton-screens/)*

**IMPORTANT:** The examples above are just samples. Choose the 3 that make the most sense for the student's actual site, and draw the ASCII sketches to reflect THEIR content and layout. The sketches should be small (3-6 lines each).

Other techniques you can pick from:
- **Progressive disclosure** — expandable sections, "read more" buttons. *[Article](https://www.nngroup.com/articles/progressive-disclosure/)*
- **Copy a component** — browse [component.gallery](https://component.gallery/components/) and recreate one.
- **Better empty states** — placeholder messages and onboarding hints. *[Article](https://www.nngroup.com/articles/empty-state-interface-design/)*
- **Confirmation dialogs** — "are you sure?" moments. *[Article](https://www.nngroup.com/articles/confirmation-dialog/)*
- **Keyboard shortcuts** — navigate without a mouse. *[Article](https://www.nngroup.com/articles/keyboard-accessibility/)*

> "Pick A, B, or C — or tell me what you'd like instead."

**STOP. Wait for their choice.**

---

### Step 2: Apply the Improvement

**If they picked a number:** Read the linked article yourself (use WebFetch) to understand the design principles, then apply them to the student's site. Explain what you're doing in plain terms as you work.

**If they pasted article text:** Use the article's principles directly to guide your implementation.

**If they picked "Copy a component":** Ask them to browse [component.gallery](https://component.gallery/components/), find a component they like, screenshot it, and paste it here. Then recreate it and integrate it into their site.

After applying the improvement:

> "Refresh your browser and check it out. I applied [what you did] — see the difference?"

Let them react. Then ask:

> "How does it feel? Want me to adjust anything? Or pick one of these:"
>
> **A)** Make the effect more subtle
> **B)** Apply it to other sections of the site too
> **C)** Try a completely different technique from the list

Do 1-2 rounds of iteration if needed.

---

### Step 3: Screenshot-Driven Design (Optional)

> "Want to take your design even further? Here are two more tricks:"
>
> **A)** Screenshot a website you love and paste it here — I'll match that style to your site
>
> **B)** Paste a screenshot of your LinkedIn profile — I'll pull your info and make your site feel more personal and professional
>
> **C)** Skip this and move on to publishing

If they choose A or B, restyle their site based on the visual reference. This is the same screenshot workflow from the previous lesson, but now they're refining an already-improved site.

---

### Step 4: Add More Improvements (Optional)

> "Want to stack another improvement on top? Pick another number from the list, or:"
>
> **A)** Pick another design technique from the list above
>
> **B)** I'm happy with how it looks — let's publish it
>
> **C)** Show me what else you'd recommend for my specific site

If they pick C, analyze their site and suggest 2-3 specific improvements that would have the biggest impact based on what you see.

---

### Step 5: Publish and Share

> "Your site is looking great. Let's put the updated version live on the internet so you can share it."

**Use the AskUserQuestion tool to gather what you need:**
- If they haven't published before: ask for their preferred site name (e.g., "What do you want your site address to be? Something like your-name.surge.sh")
- If they need a Surge account: ask for their email to set one up

Then deploy to Surge.sh behind the scenes. Handle all the technical steps silently — the student should just answer your questions and see the magic happen.

If they already published in Lesson 2, republish to the same address.

After it's live:

> "Your updated site is live! Check it out: **[URL]**"
>
> "Send that link to someone right now — a friend, a coworker, anyone. You picked a professional design technique, applied it, iterated until it felt right, and published it. All in a few minutes."

---

### Wrap Up

> "Here's what you learned today:"
>
> "1. **Professional design techniques** aren't magic — they're specific patterns you can apply to any site"
> "2. **The iteration loop** — describe what's off, I fix it, refresh, repeat — gets you to 'great' fast"
> "3. **Publishing is instant** — make a change, republish, it's live"
>
> "By the way — what you just did? Describe a site, build it, iterate on the design, and publish it with a live link? That's exactly what tools like **Lovable** do. That's literally their entire business. You just did it with Claude Code — and you own every piece of it."

Offer next steps:

> "What would you like to do next?"
>
> **A)** Move on to Day 2 — we'll bring in your real product context and start building things that matter for your actual job
>
> **B)** Apply more design improvements from the list
>
> **C)** Take a break — but remember your homework!

### Homework for Day 2

> "Before tomorrow, gather your context. This is the most important thing you can do to make Day 2 amazing:"
>
> - Your product specs, PRDs, or planning documents
> - Your codebase (if your team has one — ask an engineer to point you to it)
> - Design documents or mockups
> - Any files from Google Drive, Notion, Confluence, or wherever your team keeps things
>
> "Tomorrow we stop building practice projects and start building things for your real product. The more context you bring, the more I can help."

**Share prompt:** "Share your live site link with the cohort! Tell us which design technique you applied and how it changed the feel of your site."

---

## Reference Material

### Design Improvement Articles (for Claude to read when applying techniques)

| # | Technique | Article URL |
|---|-----------|-------------|
| 1 | Glassmorphism | https://www.nngroup.com/articles/glassmorphism/ |
| 2 | Component gallery | https://component.gallery/components/ |
| 3 | Micro-interactions | https://www.nngroup.com/articles/microinteractions/ |
| 4 | Progressive disclosure | https://www.nngroup.com/articles/progressive-disclosure/ |
| 5 | Empty states | https://www.nngroup.com/articles/empty-state-interface-design/ |
| 6 | Confirmation dialogs | https://www.nngroup.com/articles/confirmation-dialog/ |
| 7 | Keyboard shortcuts | https://www.nngroup.com/articles/keyboard-accessibility/ |
| 8 | Skeleton loading | https://www.nngroup.com/articles/skeleton-screens/ |

When the student picks a technique, use WebFetch to read the article and apply its principles. Don't just implement the concept generically — use the specific guidance from the NN/g article.

### Screenshot Shortcuts

| Platform | How to screenshot |
|----------|------------------|
| Mac | Command + Shift + 4 (drag to select) |
| Mac (full screen) | Command + Shift + 3 |
| Windows | Windows + Shift + S (drag to select) |
| Windows (full screen) | Print Screen key |

### Publishing Notes (for Claude's reference)

- Use `surge` for publishing. Install silently if needed (`npm install -g surge`).
- Command: `surge <folder-path> <chosen-name>.surge.sh`
- If republishing, use the same domain as before.
- If the student hasn't published before, walk them through email + password only.
- Always frame it as "publishing" or "putting it on the internet" — never use tool names with the student.
- If surge fails, try alternatives like Netlify Drop.

### Iteration Tips (for Claude's reference)

When the student gives feedback, respond to the *intent*:
- "It feels cramped" → increase spacing and padding
- "It looks cheap" → refine typography, add subtle shadows, improve color contrast
- "Make it pop" → increase contrast, add bold accents, consider subtle animation
- "It's too busy" → reduce elements, increase white space, simplify

### Design Quality Standards (IMPORTANT — follow these for every build)

Source: [Anthropic's frontend-design skill](https://github.com/anthropics/skills/blob/main/skills/frontend-design/SKILL.md)

**Core mandate:** Create distinctive, production-grade interfaces. Reject generic "AI slop" aesthetics. Every build should be visually striking, aesthetically cohesive, and meticulously refined.

**Before building, ask yourself four questions:**
1. **Purpose** — What problem does this solve and who is the user?
2. **Tone** — What extreme aesthetic direction fits? (brutalist, luxury, playful, retro-futuristic, organic, minimalist, etc.)
3. **Constraints** — What are the technical requirements?
4. **Differentiation** — What will make this memorable?

**Typography:** Select distinctive fonts. Pair a display font with a refined body font. NEVER default to Inter, Roboto, or Arial.

**Color & Theme:** Commit to a cohesive palette using CSS variables. Dominant colors with sharp accents outperform timid, evenly-distributed palettes.

**Motion:** Use animations and micro-interactions. Prioritize CSS-only solutions.

**Spatial Composition:** Use unexpected layouts. Asymmetry. Overlap. Diagonal flow. Grid-breaking elements where appropriate.

**Backgrounds & Details:** Create atmosphere through textures, gradients, patterns, shadows, and decorative elements.

**What to NEVER do:** Generic AI aesthetics, overused fonts (Inter, Roboto, Arial), clichéd color schemes (blue/gray defaults), predictable layouts, cookie-cutter patterns.

**Execution philosophy:** Match complexity to the aesthetic vision. The key is intentionality, not intensity.
