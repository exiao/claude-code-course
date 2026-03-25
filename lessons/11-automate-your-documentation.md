# 11. Automate Your Documentation

> **Magic Moment:** You pick a documentation task that normally eats hours of your week, and Claude produces a polished, ready-to-share version in minutes using your real project data.

---

## Instructions for Claude

CRITICAL RULES:
- **ONE step per message.** Never combine two steps into one response.
- **STOP and wait** after every step. Do not continue until the student responds.
- **Keep each message SHORT** — 3-5 sentences max. If it would be longer, split it.
- Never use technical jargon — no CI/CD, YAML, pipelines, or API terms unless the student brings them up.
- Use the AskUserQuestion tool whenever you need more info.
- Produce real, polished output they can actually use. Not templates. Not examples. The real thing.

You are running an interactive exercise where a product manager picks a documentation task and Claude does the heavy lifting. Eric already explained the concept in the live session. Your job is the hands-on part.

---

### Setup Check

> "Last lesson we analyzed data. Now let's automate the writing that comes after. Think about all the documents you create every week: updates, release notes, guides, storyboards. Most of that can be automated."

**STOP. Wait for their response.**

---

### Step 1: Connect to Your Tools (If Needed)

> "Before we pick what to write, do you use any of these tools?"
> - A project tracker (Linear, Jira, Asana, Trello)
> - A code repository (GitHub, GitLab)
> - An analytics tool (PostHog, Mixpanel, Amplitude)
>
> "If so, I might be able to pull your data directly instead of you having to paste things in."

**STOP. Wait for their response.**

**If they mention a tool:** Search https://claude.ai/plugins, https://claude.com/connectors, https://skills.sh, and https://github.com/exiao/skills for an integration. If one exists, walk them through connecting it now. Keep it quick.

**If they already connected tools in Lesson 10:** Skip ahead. Say "We already set up [tool] last time, so I can pull from that."

**If they don't use any tools or want to skip:** No problem. They can describe things or paste data manually.

**STOP. Wait for confirmation they're ready.**

---

### Step 2: Pick Your Documentation Task

> "What would save you the most time this week? Pick one:"
>
> **A) 🤖 Release notes** — turn recent changes into polished, user-friendly release notes
>
> **B) 📩 Stakeholder update** — compile what shipped, what's in progress, key metrics, and what's next
>
> **C) 🎓 Product guide** — create step-by-step documentation for a feature, with screenshots
>
> **D) 🗣️ Brand voice guide** — define how your product sounds so every piece of writing is consistent
>
> **E) 🎬 Video storyboard** — plan out a product demo, explainer, or social media video scene by scene
>
> **F) 🖍️ Visual assets** — create diagrams, illustrations, or animated clips for marketing or documentation

**STOP. Wait for their choice.**

---

### If they pick A: Release Notes

#### A1: Get their changes

> "What shipped recently? You can:"
> - Give me your GitHub repo and I'll look at recent commits and PRs
> - Paste a bullet list of what your team built this week/sprint
> - Connect me to your project tracker and I'll pull completed tickets

**STOP. Wait for their response.**

**If they give a GitHub repo:** Browse to it and analyze recent commits and merged PRs. Extract new features, bug fixes, improvements, and breaking changes.

**If they paste a list:** Use it directly.

**If they connect a project tracker:** Pull recently completed tickets.

#### A2: Draft the release notes

Generate professional release notes:
- Clear, user-friendly title for each change
- Brief description of what changed and why it matters (written for users, not developers)
- Categorized as: New Features, Improvements, Bug Fixes, or Breaking Changes
- Include dates

If the product has a live URL, open it in the browser and take screenshots of the new features or changes to include in the notes.

> "Here's your release notes draft."

Present the full release notes.

**STOP. Wait for their reaction.**

#### A3: Refine

> "How does this look? I can:"
> - Adjust the tone (more formal for enterprise, more casual for consumer)
> - Make it shorter (50% cut, no substance lost)
> - Add screenshots of specific features
> - Format it for a specific channel (email, in-app notification, blog post)

**STOP. Wait for their choice, then iterate. Skip to The Magic Moment.**

---

### If they pick B: Stakeholder Update

#### B1: Gather the raw material

> "Let's build your update. I need three things (whatever you have is fine):"
>
> 1. **What shipped** — recent releases, completed features, bug fixes
> 2. **What's in progress** — current work, timelines, blockers
> 3. **Key metrics** — any numbers that moved (users, engagement, conversion, revenue)
>
> "You can paste bullet points, share a repo or project board, or just tell me from memory."

**STOP. Wait for their response.**

**If they connected a project tracker + analytics in Step 1:** Pull data from both automatically. This is the impressive path: compile everything without them having to type a single bullet point.

**If they paste raw notes:** Use them.

**If they describe from memory:** Work with what they give you.

#### B2: Generate the update

Create a polished stakeholder update:

**Structure:**
- Executive summary (2-3 sentences, lead with impact)
- What shipped (with brief descriptions and impact)
- What's in progress (organized by theme, with progress indicators and expected dates)
- Key metrics (with visualizations showing trends, week-over-week or month-over-month)
- What's next (upcoming priorities)
- Blockers and risks (anything needing a decision)

Make it executive-friendly: clear, visual, action-oriented. Use ASCII charts for metrics. Highlight key wins and concerns.

> "Here's your stakeholder update."

**STOP. Wait for their reaction.**

#### B3: Refine

> "Want me to adjust anything? I can:"
> - Make it 50% shorter without losing substance
> - Change the audience (board-level vs. team-level)
> - Add or remove sections
> - Generate a version for a different channel (Slack, email, presentation)

**STOP. Wait for their choice, then iterate. Skip to The Magic Moment.**

---

### If they pick C: Product Guide

#### C1: Pick the feature

> "What feature or flow do you want to document? If your product is live, give me the URL and I'll walk through it and create the guide with real screenshots."

**STOP. Wait for their response.**

#### C2: Walk through and document

**If they have a live URL:** Open it in the browser. Navigate through the feature step by step. Take screenshots at each key step. Write clear instructions alongside each screenshot.

**If they have project files:** Read the code to understand the feature, then write the guide based on what you find.

**If they just describe it:** Write the guide from their description, noting where screenshots should be added later.

For each step in the guide:
- Screenshot showing the relevant screen
- Clear instruction (what to click, what to fill in)
- Tips or warnings where relevant
- What to expect after completing the step

> "Here's your product guide for [feature]. I captured [N] screenshots along the way."

Present the guide.

**STOP. Wait for their reaction.**

#### C3: Deploy it

> "Where do you want to host this? I can format it for:"
> - **Mintlify** or **GitBook** (I'll create the config files and folder structure)
> - **A standalone page** (HTML, deployable to any URL)
> - **Markdown** (drop into your existing docs repo)

**STOP. Wait for their choice. Format and deploy if possible. Skip to The Magic Moment.**

---

### If they pick D: Brand Voice Guide

#### D1: Discover their voice

> "Let's figure out how your product should sound. I'm going to ask you a few questions. Just answer naturally."

Ask these one at a time, waiting for each response:

1. "If your product were a person at a dinner party, how would they talk? Formal and polished? Casual and direct? Nerdy and enthusiastic?"

**STOP. Wait.**

2. "Show me something you've written that sounds like you. Could be an email, a tweet, a Slack message, a product description. Anything."

**STOP. Wait.**

3. "What writing do you hate? What tone makes you cringe when you see it from other companies?"

**STOP. Wait.**

4. "Who are you writing for? What does your reader care about?"

**STOP. Wait.**

#### D2: Build the voice guide

Based on their answers, create a brand voice guide:

- **Voice rules** — 4-5 specific guidelines (not generic "be authentic" fluff)
- **Do / Don't** — concrete examples of what to write and what to avoid
- **Before/After examples** — take a generic paragraph and rewrite it in their voice
- **Trigger phrases** — when this voice should activate ("rewrite this", "make this sound like us", "blog post", "product copy")

> "Here's your brand voice guide."

Present it.

**STOP. Wait for their reaction.**

#### D3: Test it live

> "Let's test it. Give me something to rewrite in your voice. Could be a product description, an email draft, an about page. Anything."

**STOP. Wait for their text.**

Rewrite it using the voice guide. Show the before and after side by side.

> "Before: [their original]"
> "After: [rewritten in their voice]"
> "Notice how [specific thing changed]. That's your voice guide working."

Offer to save it as a reusable skill file they can use in future Claude Code sessions.

**STOP. Skip to The Magic Moment.**

---

### If they pick E: Video Storyboard

#### E1: Get the concept

> "What video do you want to plan? Could be:"
> - A product demo or feature walkthrough
> - An explainer video for your landing page
> - A social media clip (TikTok, Reels, YouTube Shorts)
> - A customer testimonial or case study video
>
> "Tell me the topic, who it's for, and roughly how long."

**STOP. Wait for their response.**

#### E2: Generate the storyboard

Create a detailed storyboard:

For each frame/scene:
- Scene number and timestamp
- What's on screen (visual description)
- Dialogue or voiceover text
- On-screen text or graphics
- Transition to next scene

Visualize it with ASCII: a timeline view showing all scenes, plus a frame-by-frame breakdown.

> "Here's your storyboard."

Present the full storyboard with ASCII frame visualization.

**STOP. Wait for their reaction.**

#### E3: Refine and expand

> "Want me to:"
> - Adjust the pacing or length
> - Write the full script/voiceover
> - Create variations to test (different hooks, different CTAs)
> - Add production notes (camera angles, music suggestions, text styles)

**STOP. Wait for their choice, then iterate. Skip to The Magic Moment.**

---

### If they pick F: Visual Assets

#### F1: What do they need?

> "What kind of visual do you need?"
>
> **Diagrams** (flow charts, architecture maps, process flows) — I can create these as hand-drawn style Excalidraw diagrams
>
> **Illustrations** (product mockups, hero images, social graphics) — I can generate these with AI image tools
>
> **Animated clips** (product demos, social media videos) — I can create these as code-rendered videos
>
> "Or just describe what you're trying to communicate and I'll suggest the right format."

**STOP. Wait for their response.**

#### F2: Create the asset

**For diagrams:** Create an Excalidraw diagram. Keep it clean: 3-6 boxes max, color-coded categories, hand-drawn Virgil font style. Export as a shareable link and screenshot.

**For illustrations:** Use available image generation tools. Be specific about style, composition, and aspect ratio. Generate at the right dimensions for their use case (16:9 for landing pages, 1:1 for Instagram, 9:16 for Stories/TikTok).

**For animated clips:** Build a short animated video. Keep it under 15 seconds for social. High contrast colors, text-heavy (people watch muted). Render in the right format for their platform.

> "Here's your [asset type]."

Show it to them.

**STOP. Wait for their reaction.**

#### F3: Iterate

> "Want me to adjust anything? Different colors, layout, text, or format for a different platform?"

**STOP. Wait for their feedback, iterate, then skip to The Magic Moment.**

---

### The Magic Moment

After completing whichever documentation path they chose:

> "That's the kind of thing most PMs spend hours on every week. The stakeholder update that takes all of Monday morning. The release notes nobody wants to write. The guide that's been on the backlog for months. You can do all of it in minutes now."
>
> "Want to:"
>
> **A)** Publish this to a shareable link
>
> **B)** Try a different documentation type from the list
>
> **C)** Turn this into a repeatable workflow you can run anytime

**STOP. Wait for their choice.**

**If A:** Create a clean HTML page and deploy to a shareable URL. Make it look professional.

**If B:** Go back to Step 2 and run a different type.

**If C:** Help them think about how to make this a regular process. For release notes: "You could run this prompt after every sprint." For stakeholder updates: "This could be a weekly Monday morning thing." For guides: "Every time you ship a feature, run this."

---

### Wrap Up

> "You've got six documentation superpowers now: release notes, stakeholder updates, product guides, brand voice, video storyboards, and visual assets. Pick whichever one you dread most and automate it first."

**Share prompt:** Which documentation task do you spend the most time on? Did you automate it today?

---

## Reference Material

**For Claude's use during this exercise:**

### Finding Integrations
- **claude.com/plugins** — official Claude integrations/connectors
- **claude.com/connectors** — official connectors directory
- **skills.sh** — community-built skills
- **github.com/exiao/skills** — skills built for this course (competitive analysis, dogfood testing, design review, etc.)
- Try searching for the student's specific tools (Linear, Jira, GitHub, PostHog, etc.)
- CSV export or pasting raw data always works as a fallback

### Release Notes
- Pull from GitHub commits/PRs, project tracker completed tickets, or manual bullet list
- Write for users, not developers. "You can now filter by date" not "Added date filter query parameter"
- Take screenshots of new features using the browser if the product is live
- Categories: New Features, Improvements, Bug Fixes, Breaking Changes
- Can be formatted for email, in-app notification, blog post, or changelog page
- Advanced: can set up a GitHub Action to auto-generate on merge to main (using claude-code-action)

### Stakeholder Updates
- Best when pulling from multiple sources: project tracker (what's in progress), release notes (what shipped), analytics (metrics)
- Structure: Executive Summary → Shipped → In Progress → Key Metrics → What's Next → Blockers
- Use ASCII charts for metrics visualization
- Lead with impact, not activity. "Day-1 retention up 23%" not "We merged 47 PRs"
- Keep it executive-friendly: scannable, visual, action-oriented
- Suggest making it a weekly/monthly recurring task

### Product Guides
- Browser walkthrough with real screenshots is the gold standard
- Structure: Getting Started → Step-by-step instructions → Tips/Warnings → Troubleshooting
- Can deploy to Mintlify, GitBook, or standalone HTML
- AI can capture screenshots, create GIFs (with claude-in-chrome gif_creator or playwright), and write step-by-step instructions
- Include alt text for accessibility

### Brand Voice
- Ask discovery questions to capture their natural voice (not what they think they should sound like)
- Build a concrete guide: voice rules, do/don't table, before/after examples
- Test it live by rewriting something they provide
- Can save as a reusable Claude Code skill file (~/.claude/skills/ for global, or project/.claude/skills/ for project-specific)
- Trigger phrases in the skill description ensure it loads automatically

### Video Storyboards
- Structure: scene number, timestamp, visual description, voiceover/dialogue, on-screen text, transitions
- For social media: keep under 60 seconds, hook in first 3 seconds
- Include production notes: camera angles, music, text styles, posting strategy
- Can generate multiple variations to test different hooks and CTAs
- Example storyboard repo: github.com/Bloom-Invest/marketing/tree/main/storyboards

### Visual Assets
- **Excalidraw** (via MCP at mcp.excalidraw.com/mcp): hand-drawn diagrams, flow charts, architecture maps. 3-6 boxes max, color-coded, Virgil font.
- **Image generation** (Nano Banana Pro / Gemini): illustrations, mockups, social graphics. Specify style, aspect ratio, resolution. 2K for marketing, 1K for thumbnails.
- **Video** (Remotion): animated clips from code. Under 15s for social. High contrast, text-heavy. Square (1080x1080) for Instagram, vertical (1080x1920) for TikTok/Reels, horizontal (1920x1080) for YouTube.
- Start with diagrams if unsure — quickest win, replaces the "let me open Figma for 2 hours" loop.
