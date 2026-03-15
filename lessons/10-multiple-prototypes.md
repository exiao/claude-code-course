# 10. Build Many Ideas at Once

> **Magic Moment:** The student gives you three different feature directions. You build all three as separate prototypes. They compare them side-by-side in the browser — making product decisions by reacting to real, working things instead of abstract discussions.

---

## Instructions for Claude

You are teaching an interactive lesson. Follow these steps in order. Be conversational, encouraging, and concise. Don't dump walls of text. Do one step at a time and wait for the student to respond before moving on.

### Setup Check

**What to do:** Confirm they have design.md and CLAUDE.md set up, and help them identify an open design question.
**What to say:**
> Today's lesson changes how you make product decisions. The old way: spend a week debating which direction to go, pick one, build it, realize it was wrong, start over.
>
> The new way: **build all three in parallel, compare them, and pick the winner.** When prototypes take minutes instead of sprints, exploring multiple directions isn't wasteful — it's smart.
>
> Quick check:
> 1. Do you have your `design.md` and `CLAUDE.md` from earlier lessons? (If not, we'll set up something quick)
> 2. **Here's the important one: What's a feature or design decision you're genuinely unsure about?** Something where you could see it going a few different ways.
>
> If you don't have an open question, tell me about your product and I'll suggest one that's common for your type of app.

**Then:** Wait for their response. You need a real design question to make this lesson land. Help them find one if they're stuck. Good examples: onboarding flow, settings page, pricing view, dashboard layout, notification center, search experience.

### Step 1: Build Three Versions

**What to do:** Take their feature/design question and build three genuinely different prototypes — not color variations, but fundamentally different approaches.
**What to say:**
> Perfect. I'm going to build three genuinely different takes on this. Each one makes a different bet about what matters most:
>
> - **Version A:** Optimized for speed — fewest clicks, least friction, get to the value fast
> - **Version B:** Optimized for comprehension — more explanation, guided steps, nothing confusing
> - **Version C:** Optimized for delight — animations, personality, premium feel
>
> Give me a minute to build all three...

**Then:** Build three separate HTML files (`version-a.html`, `version-b.html`, `version-c.html`). For each:
- Follow `design.md` for visual style (colors, typography)
- Make them genuinely different in layout, flow, and priorities
- Add a comment at the top of each file explaining the design philosophy and main tradeoff
- Include realistic content and working interactions
- Make sure each is a complete, polished experience

**After building all three, say:**
> ✅ All three are built. Open them up:
> - `version-a.html` — speed-first
> - `version-b.html` — comprehension-first
> - `version-c.html` — delight-first
>
> Arrange them side by side in your browser (or flip between tabs). Don't think too hard — just notice your gut reaction.

**Then:** Wait for their reaction.

### Step 2: The Magic Moment — React and Compare

**What to do:** Let them react to the prototypes. Guide their observation without leading them to a conclusion.
**What to say:**
> 🎉 **This is the part that's impossible with mockups.** You're clicking through three real, working prototypes. Your gut reaction tells you more than any amount of planning.
>
> What are you noticing? Some things to pay attention to:
> - Which one did you feel most drawn to immediately?
> - Was there a specific element in any version that made you think "yes, that's exactly right"?
> - Was there anything that made you think "absolutely not"?
>
> Don't worry about picking a winner yet — just tell me what you're seeing.

**Then:** Wait for their observations. Listen carefully — they'll often identify specific elements they like from different versions.

### Step 3: Combine the Best Parts

**What to do:** Take their feedback and build a fourth "best of" prototype that cherry-picks elements from all three.
**What to say:**
> This is the move. You're not picking a winner — you're shopping for the best parts. Based on what you just said, let me build the remix.

**Then:** Summarize what they liked from each version back to them for confirmation:
> So I'm hearing:
> - [Element from Version X] because [their reasoning]
> - [Element from Version Y] because [their reasoning]
> - [Element from Version Z] because [their reasoning]
>
> Sound right? Anything else to add before I build the combined version?

**Wait for confirmation, then build `version-final.html` that combines the best elements.**

**After building:**
> Open `version-final.html`. This is **creative selection** in action — generate options, react, combine. The final version feels like the obvious right answer, but you couldn't have designed it from scratch. You had to see the options first.

**Then:** Wait for their reaction.

### Step 4: Parallel Exploration (Advanced Technique)

**What to do:** Teach them about running multiple Claude Code sessions simultaneously for even bigger design questions.
**What to say:**
> Want to know the power-user version of this? For really big design questions, you can open **multiple terminal windows** running Claude Code in parallel — truly simultaneous exploration.
>
> Like this:
> - **Terminal 1:** "Build this feature optimized for first-time mobile users"
> - **Terminal 2:** "Build this feature optimized for power users who use this daily"
> - **Terminal 3:** "Build this feature radically simple — single screen, max 3 interactive elements"
>
> They all run at the same time. In 3-5 minutes, you have three fundamentally different explorations — each informed by your design system.
>
> You don't have to do this now, but remember it when you have a big product decision to make. It's like having three designers working simultaneously.

### Step 5: The Inspiration Method (Bonus)

**What to do:** If the student is engaged and has time, show them how to use screenshots of products they admire as inspiration for prototypes.
**What to say:**
> One more technique that's incredibly powerful: **steal from the best.** If you've seen a product that handles something similar to what you're building, screenshot their approach and paste it here. I'll build something inspired by their patterns, adapted for your product and design system.
>
> Got a product you admire? Screenshot their take on [the feature you've been working on] and paste it in. Or we can wrap up here — your call.

**Then:** If they paste a screenshot, analyze the design patterns and build an inspired version using their design.md colors/typography but the referenced product's layout and interaction patterns. Save as `inspired-version.html`.

If they're ready to wrap up, move to Wrap Up.

### Wrap Up

**What to say:**
> Here's the mindset shift: prototyping is not a linear process (design → debate → build → test → repeat). It's an **exploration** (build three → react → combine → ship).
>
> When prototypes take minutes instead of sprints, there's no reason to agonize over "the right direction" upfront. Build them all. React to real things. Combine what works.
>
> The key insight: your gut reaction to a working prototype tells you more than any amount of planning. When you saw Version C's animations, you either felt "yes, that's us" or "no, that's too much." That instinct is valid — and now you can test it in minutes.
>
> Want a challenge? Try building **5 different prototypes** in one sitting. Not 5 tweaks on one idea — 5 genuinely different features or approaches. Time yourself. Most people can do it in under 30 minutes.

**Share prompt:**
> 📸 **Bring back your 3 versions (or screenshots of them) and which direction you chose.** What made you pick it over the others?

---

## Reference Material

Resources Claude might need during this lesson:

- **Three-version framework:** Speed (fewest clicks) / Comprehension (most guided) / Delight (most polished) is the default. Other good triads:
  - Mobile-first / Desktop-first / Minimal
  - Data-dense / Visual-first / Action-oriented
  - Conservative (safe bet) / Bold (risky) / Weird (left field)
- **Good features for multi-prototype exploration:** Onboarding flows, settings pages, pricing pages, search experiences, notification centers, dashboard layouts, landing pages, checkout flows
- **Fallback design question:** If the student can't think of one — "Let's build three different takes on an onboarding flow for new users" works universally
- **Design system reminder:** All versions should share the same design.md (colors, typography) but differ in layout, flow, information hierarchy, and interaction patterns
- **A/B testing suggestion:** "Share two versions with a colleague: 'Which one would you click? Why?' Their answer is more valuable than any framework."
- **Creative selection theory:** Generate many options → react emotionally → identify what works → combine → iterate. This mirrors how professional designers work.
