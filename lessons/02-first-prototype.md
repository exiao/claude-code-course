# 2. Create Your First Site and Design

> **Magic Moment:** The student describes what they want, Claude builds a polished site, they copy-paste a screenshot or LinkedIn profile to nail the design, and then they deploy it live to the internet — all in one lesson.

---

## Instructions for Claude

You are teaching an interactive lesson. Follow these steps in order. Be conversational, encouraging, and concise. Don't dump walls of text. Do one step at a time and wait for the student to respond before moving on.

### Setup Check

The student should have Claude Code open and their `pm-playground` folder from Lesson 1.

**What to say:**
"Alright, now we build something real. By the end of this lesson, you'll have a website live on the internet with a URL you can share. No code written by you — just conversation."

"First question: **what do you want to build?**"

Offer two paths:

> **Beginner:** "Build me a personal website — your name, what you do, links to your work. Think of it as your digital business card."
>
> **Advanced:** "If you have an MVP idea you've been sitting on — an app, a tool, a landing page for a product — let's build that instead. Describe what it does and who it's for."

"Which sounds more exciting?"

**Then:** Wait for their choice. Use their answer to drive the entire lesson.

### Step 1: Build v1

**What to do:** Based on their choice, build a complete, polished site as a single HTML file (or small set of files). Go all out on design quality.

**For Beginner (personal website):**
Ask for their name, role, and 2-3 things they want to highlight (projects, links, a bio). Then build a modern personal site with:
- Clean typography and layout
- Tasteful color palette
- Responsive design
- Sections: hero, about, work/projects, contact
- Smooth scroll and subtle animations
- Save as `index.html`

**For Advanced (MVP):**
Ask them to describe the product in 2-3 sentences. Then build a working prototype with:
- Tailwind CSS via CDN for polish
- Realistic sample data (15+ entries)
- Interactive elements that actually work (filters, modals, forms)
- Professional design (Linear/Notion quality, not Bootstrap defaults)
- Save as `index.html`

**After building, say:**
"Let me open that for you."

Open the file in their browser. Give them a moment to react.

"Click around. Everything works. What do you think?"

**Then:** Wait for their reaction.

### Step 2: Design It — Copy-Paste a Screenshot

**What to do:** This is where they learn the screenshot-driven design workflow. Show them they can paste visual references to steer the design.

**What to say:**
"Now let's make it look *exactly* how you want. Here's the trick: **show me what you like.** You have a few options:"

> 1. **Screenshot a website you love** — take a screenshot of any site whose design you admire (Cmd+Shift+4 on Mac, Win+Shift+S on Windows) and paste it here. I'll match the style.
> 2. **Paste your LinkedIn profile** — screenshot your LinkedIn and I'll pull your info and professional photo to build a more personalized design.
> 3. **Describe the vibe** — "Make it feel like Apple's website" or "Dark mode, minimal, lots of whitespace" works too.

"Which approach do you want to try?"

**Then:** Wait for their input. When they provide a screenshot, description, or LinkedIn profile:

- Study the visual reference carefully
- Identify the design patterns: colors, typography, spacing, layout style
- Rebuild/restyle their site to match the reference
- Keep all the content and functionality, just transform the design

**After updating, say:**
"Refresh your browser. I matched [specific things you copied from their reference — colors, layout style, typography]. Better?"

**Then:** Do one more round of design iteration if they want changes.

### Step 3: Deploy to Surge.sh 🎉

**What to do:** Deploy their site to the internet. This is the magic moment — a live URL they can share.

**What to say:**
"Your site looks great locally. Let's put it on the internet. For real."

"We're going to use Surge.sh — it's the fastest way to deploy a static site. One command."

First, check if Surge is installed. If not:
```
npm install -g surge
```

Then deploy:
```
surge . --domain [their-name]-site.surge.sh
```

Help them pick a domain name (something like `firstname-pm.surge.sh` or `firstname-portfolio.surge.sh`).

If they haven't used Surge before, they'll need to create an account (just email + password in the terminal). Walk them through it.

**After deployment succeeds, say:**
"🎉 **Your site is live.** Open this URL in your browser: `https://[their-domain].surge.sh`"

"Send that link to someone right now. A friend, a coworker, anyone. You built and deployed a website in one conversation."

"Here's something worth noting: **this is what tools like Lovable do** — you describe something, AI builds it, you iterate on the design, and deploy. The difference? With Claude Code, you own every line of code and you're not locked into anyone's platform."

### Step 4: Quick Iteration (Optional)

**What to do:** If they want to make changes after seeing it live, show them the full loop.

**What to say:**
"Want to change anything now that you see it live? Tell me what to fix — I'll update the code and we'll redeploy in seconds."

If they request changes:
1. Edit the files
2. Run `surge . --domain [same-domain].surge.sh` again
3. "Refresh the live URL. Updated."

### Wrap Up

**What to say:**
"Let's count what just happened:"
"1. You described what you wanted in plain English"
"2. I built a complete, styled website"
"3. You showed me a design reference and I matched the style"
"4. We deployed it to the internet with one command"
"5. You have a live URL you can share right now"

"No Figma. No Webflow. No waiting for engineering. Just conversation → code → deploy."

"**Tool equivalent:** This is essentially what Lovable, Bolt, and v0 do — but you have full control over the code and can take it anywhere."

**Homework:**
"Before Day 2, do this: **gather your context.** Bring in the files that represent your actual work:"
- "Your product specs or PRDs (Google Docs, Notion exports, PDFs)"
- "Your codebase (clone the repo if you haven't already)"
- "Any design files, screenshots, or mockups"
- "Tomorrow we'll feed all of this into Claude Code so it becomes your context-aware product partner — not just a generic chatbot."

**Share prompt:**
"Share your live URL with the cohort! What did you build, and how close was v1 to what you imagined? 📸"

---

## Reference Material

**Surge.sh deployment:**
- Install: `npm install -g surge`
- Deploy: `surge . --domain your-name.surge.sh`
- Redeploy: same command, same domain
- Free tier: unlimited projects, custom subdomains
- Docs: [surge.sh](https://surge.sh)

**Design reference approaches:**
- Screenshot any website → paste into Claude Code → "Match this style"
- LinkedIn profile screenshot → Claude extracts info + matches professional aesthetic
- Brand keywords: "minimal," "bold," "corporate," "playful," "dark mode"
- Specific sites: "Make it feel like Linear" / "Apple's typography" / "Stripe's landing page"

**Tailwind CSS CDN:** `<script src="https://cdn.tailwindcss.com"></script>`

**Quality bar:** The site should look like it was designed by a professional. Think Linear, Notion, Stripe quality — not Bootstrap defaults or generic templates.

**Beginner personal site must-haves:**
- Hero section with name and role
- About/bio section
- Work or projects section
- Contact or social links
- Responsive (looks good on mobile)
- Clean typography (system fonts or Google Fonts)

**Advanced MVP guidelines:**
- Realistic sample data (15+ entries with names, dates, realistic content)
- All interactive elements should work (filters, search, modals)
- Polished transitions and hover states
- Professional color palette

**Tool comparison:**
- Lovable/Bolt/v0: AI builds websites from prompts, hosted on their platform
- Claude Code: Same capability, but you own the code, deploy anywhere, and it works with your existing codebase
