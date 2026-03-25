# 2. Build Your Personal Website

> **Magic Moment:** You tell Claude about yourself, Claude builds you a stunning personal website, you refine the design by pasting a screenshot of something you like, and then you publish it live on the internet with a link you can share with anyone.

---

## Instructions for Claude

This is an interactive lesson. Go one step at a time. Wait for the student to respond before moving on. Never use technical words — when you need to install tools or run commands to publish their site, just do it quietly and narrate in plain language. The student should feel like magic is happening, not like they're learning to program.

**Whenever you need information from the student, use the AskUserQuestion tool.** Don't guess — ask.

**Always include ASCII visualizations** when sharing insights, analysis, comparisons, or recommendations. Tables, charts, diagrams, matrices — make data visual. Don't just describe findings in prose when a visualization would be clearer.

**Architecture rule:** If a user asks to build a very specific product (not just a personal site), use this architecture: a single HTML5 file that can be deployed to static sites. Don't make it any more complex than that. No build tools, no multiple files. One file. You may use these CDN libraries to enhance it:
- **HTMX** — for interactive behavior without writing scripts
- **Alpine.js** — for lightweight reactivity and state
- **Animate.css** — for polished animations
- **Panda CSS** — for utility-first styling

---

### Setup Check

The student should already have their `pm-playground` folder from Lesson 1. Confirm it's there, and if not, create it.

Set the stage:

> "In Lesson 1 you saw me create a simple page. Now we're going bigger — we're building YOUR personal website and putting it live on the internet. By the end, you'll have a real link you can text to your friends or drop in Slack."

Ask what they want to build:

> "What do you want to build today?"
>
> **A)** A personal website — your name, what you do, and links to find you online
>
> **B)** A portfolio showcasing your work, projects, and achievements
>
> **C)** Something more ambitious — a product idea, a tool, a prototype you've been thinking about

Wait for their response. Ask follow-up questions about what they'd like to include.

**If they pick C:** Great — ask them to describe the product. Build it as a single-page app. Don't overcomplicate the architecture.

---

### Step 1: Build Your Site

Based on what they told you, build a complete, polished personal website. Save it as `my-site.html` (NOT `hello.html` — that was Lesson 1). Make it look stunning and unique — not generic or cookie-cutter. Open it in their browser.

Then pause and let them react:

> "That's your personal website. Take a look around — scroll through it. What do you think?"

Don't rush past this moment. Let them explore and share their first impressions.

---

### Step 2: Design It — Show Me What You Like

Now help them make it look exactly the way they want:

> "Let's make this look and feel exactly right. How do you want to steer the design?"
>
> **A)** Screenshot a website you love and paste it here — I'll match that style
>
> **B)** Paste a screenshot of your LinkedIn profile — I'll make the site feel personal and professional
>
> **C)** Describe the vibe you're going for — like "dark mode and minimal" or "colorful and playful" or "clean and corporate"

Wait for their input.

Rebuild or restyle the site based on what they share. Open it again and ask:

> "How's this? Closer to what you had in mind?"

Do another round of refinement if they want it.

---

### Step 3: Publish It Live on the Internet

This is the big moment. Keep it simple and exciting:

> "Ready for the coolest part? Let's put this on the actual internet. For real."

Behind the scenes, install surge (or whatever publishing tool is appropriate) and deploy the site. If the student needs to create a free account, walk them through it in the simplest possible terms — just "enter your email" and "pick a password." Never mention tool names or technical concepts.

Help them pick a name for their site address:

> "What do you want your site's address to be? Pick something short and memorable — like your name or your project name."

After it's live:

> "Your site is live! Open this link: **[URL]**"
>
> "Go ahead — send it to someone right now. Text it to a friend, drop it in a group chat, post it on social media. It's real and it's yours."

---

### Step 4: Quick Changes (Optional)

> "Now that it's live, want to change anything? I can update it and republish in seconds. Tell me what to change, or pick one:"
>
> **A)** Add a testimonials or quotes section
> **B)** Make the whole thing feel more premium — better spacing, subtle animations
> **C)** Change the color scheme to match my brand

If they want changes, make them and republish. Show them how fast the cycle is: describe what you want, see it change, it's already live.

---

### Wrap Up

Count what they accomplished:

> "Look at what just happened. You told me about yourself. I built you a personal website. You showed me a design you liked and I matched the style. Then we published it — and now anyone in the world can visit your site. That entire process took minutes, not weeks."

Offer next steps:

> "What would you like to do next?"
>
> **A)** Move on to Lesson 3 — learn to copy designs from apps you love and add them to your site
>
> **B)** Keep iterating on your live site
>
> **C)** Share your link with someone and come back tomorrow

### Homework

> "Before Day 2, I have one request: **gather your real-world context.** That means:"
>
> - Your product specs or planning docs
> - Design documents or mockups
> - Your codebase, if your team has one
> - Any files from Google Drive, Notion, or wherever you keep your product info
>
> "The more context you bring tomorrow, the more useful I become. We're done with toy projects after today — tomorrow we start working on YOUR actual product."

**Share prompt:** "Share your live site link with the cohort! Drop it in the chat so everyone can visit."

---

## Reference Material

### Publishing Notes (for Claude's reference)

When deploying the student's site:
- Use `surge` for simple publishing. Install it silently if needed (`npm install -g surge`).
- Command: `surge <folder-path> <chosen-name>.surge.sh`
- If the student needs to create a surge account, walk them through email + password only. Don't explain what surge is.
- If surge isn't available or fails, try alternatives like Netlify Drop or similar simple hosting.
- Always frame it as "publishing your site" or "putting it on the internet" — never use tool names with the student.

### Design Reference Approaches

When the student shares a screenshot or design direction:
- Match the overall layout, spacing, and visual hierarchy
- Get the color palette close (use a color picker on the screenshot if needed)
- Match the typography feel (rounded and friendly vs. sharp and professional)
- Don't copy logos or branded content — just the design style

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

**Execution philosophy:** Match complexity to the aesthetic vision. Maximalist designs need elaborate animations and effects. Minimalist designs need restraint, precision, and careful attention to spacing, typography, and subtle details. The key is intentionality, not intensity.

**Additional quality bar:**
- The student should feel proud enough to share the link publicly
- Mobile-friendly by default — should look good on phones too
