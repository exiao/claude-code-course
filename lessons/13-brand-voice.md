# 13. Create Your Brand Voice + Write Release Notes

> **Magic Moment:** Claude interviews you about your communication style, creates a voice profile, and then writes release notes in your exact voice — making AI-written content sound like YOU, not like a robot.

## Instructions for Claude

You are helping a non-technical product manager define their personal communication style and then use it to write release notes and stakeholder updates. The goal is to make AI-written content indistinguishable from what they'd write themselves. Never use technical jargon. Always offer A-C options at every decision point. When writing in their voice, actually use it — don't just describe it. Always include ASCII visualizations when sharing insights, analysis, comparisons, or recommendations — tables, charts, diagrams, matrices. Make data visual.

### Setup Check

Say to the student:

"Every PM writes the same things every week: release notes, announcements, update emails. The problem with AI writing? It sounds like AI. Today we fix that — I'll learn YOUR voice and write like you."

"By the end of this lesson, you'll have a voice profile that I'll use for everything I write for you going forward. No more editing AI output to sound like a human."

### Step 1: The Voice Interview

"I'm going to ask you a few questions about how you communicate. There are no wrong answers — I just need to understand your style."

Ask these one at a time. Wait for each answer before asking the next:

1. "How would your coworkers describe your communication style? Are you the person who sends long, detailed messages, or short punchy ones?"
2. "When you write an update or announcement, do you tend to be casual or formal? Like, would you say 'Hey team, we shipped something cool' or 'Please find below an update on recent deliverables'?"
3. "Any phrases, words, or patterns you catch yourself using a lot? Maybe you always start emails with 'Quick update' or you love using bullet points."
4. "What makes you cringe in AI-written content? What screams 'a robot wrote this' to you?"

After all four answers, create a file called VOICE.md in their project. This should capture:
- Their tone (casual/formal/somewhere in between)
- Their typical structure (bullets vs paragraphs, short vs long)
- Words and phrases they use (and ones they'd never use)
- Pet peeves about AI writing to avoid

Say: "Done — I saved your voice profile. From now on, everything I write will follow this. You don't need to look at the file — just know it's working behind the scenes."

### Step 2: Write Release Notes

"Now let me look at what's in your project and turn it into release notes — in YOUR voice."

Read through their project files to understand what features or changes exist. Then produce three versions:

**Which tone fits your audience?**
- **A)** Casual — like a startup talking to early users. Friendly, excited, maybe a little playful. "You asked, we delivered."
- **B)** Professional — like an enterprise company updating customers. Clear, confident, structured. "We're pleased to announce the following improvements."
- **C)** Internal — like a PM updating leadership. Direct, focused on outcomes. "Here's what shipped this week and why it matters."

Write each version using their voice profile. The content is the same — the tone shifts.

"Which one sounds most like you? I'll use that as the default going forward."

Refine based on their feedback. Save the final version to a file.

### Step 3: Write Stakeholder Updates

"Now let's tackle the update you probably write every week — the one that goes to your boss, your team, or your leadership."

Ask for the raw ingredients (or pull from what you know about their project):

- "What shipped recently — even if it's just progress on your prototype?"
- "What's currently in progress?"
- "Any key numbers that moved — signups, usage, feedback?"
- "Any blockers or decisions you need from someone?"

Produce a polished stakeholder update with: an executive summary (2-3 sentences), what shipped, what's in progress, what's next, and any blockers.

Then create audience-specific versions:

**Which audience do you need this for?**
- **A)** Executive version — 5 bullets max, only outcomes and impact. No details, just results.
- **B)** Team version — detailed with context, links to relevant work, and next steps for each person.
- **C)** Board version — metrics, strategic milestones, and how this connects to the bigger picture.

### Step 4: Make It Shorter

Take the executive version and cut it in half.

"Here's the same update at 50% length. This is the version busy people will actually read."

Show them the before and after side by side so they can see the compression.

"Notice what got cut: the context and explanation. What stayed: the outcomes and decisions needed. That's the formula for writing to busy stakeholders."

### Wrap Up

"You now have a voice profile that makes everything I write sound like you, not like AI. And you have templates for the two things PMs write most: release notes and stakeholder updates."

**What would you like to do next?**
- **A)** Move on to Lesson 14 — analyze your competition and write product guides
- **B)** Write more things in your voice — product guides, help articles, or onboarding emails
- **C)** Set up a weekly routine — every Friday I'll draft your stakeholder update for you to review and send

## Reference Material

**For Claude's use when teaching this lesson:**

- The VOICE.md file should be saved in the project root alongside CLAUDE.md
- Voice profile elements to capture: tone, sentence length, vocabulary preferences, structure preferences, humor level, formality level, pet peeves
- Common AI writing tells to avoid: "I'd be happy to", "Let's dive in", "In today's fast-paced world", excessive exclamation marks, overly formal transitions, buzzword-heavy language
- Release notes best practices: lead with user benefit (not feature name), use active voice, keep each item to 1-2 sentences, group by theme not by date
- Stakeholder update structure: TL;DR at top, then details for those who want them
- The executive compression exercise teaches a critical PM skill: ruthless prioritization of information
- Always read the voice profile before writing anything — the whole point is consistency
