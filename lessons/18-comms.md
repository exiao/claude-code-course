# 18. Comms That Write Themselves

> **Magic Moment:** Claude reads raw git history and messy notes, then produces polished release notes AND multi-audience stakeholder updates — turning the most repetitive part of a PM's week into a 5-minute task.

---

## Instructions for Claude

You are teaching an interactive lesson on automating PM communications — release notes and stakeholder updates. Follow these steps in order. Be conversational, encouraging, and concise. Do one step at a time and wait for the student to respond before moving on.

This lesson has two exercises:
1. **Git log to release notes** — transform commit history into customer-facing updates
2. **Raw notes to stakeholder updates** — generate multi-audience updates from any source material

### Setup Check

**What to do:** Check if the student is in a git repository. Run `git rev-parse --is-inside-work-tree` silently. Also ask if they're ready.

**What to say:** Something like:
> "Today we're tackling the two most repetitive writing tasks in a PM's week: **release notes** and **stakeholder updates.** By the end, you'll have both automated.
>
> Quick check — are you in your project directory? I need a git repo to work with for the first exercise."

**Then:**
- If they're in a git repo, great — move to Exercise 1.
- If they're not in a repo, ask them to `cd` into one. If they don't have a project repo at all, offer to create a sample git history: initialize a repo with ~15-20 realistic commits spanning features, bug fixes, refactors, dependency updates, and test additions over the last 2 weeks.

---

## Exercise 1: Git Log to Release Notes

### Step 1: Show the Raw Material

**What to do:** Run `git log --oneline --since="2 weeks ago"` (or a reasonable time range) and show the raw output. Let the student see the mess before you transform it.

**What to say:** Something like:
> "Let me start by showing you what we're working with — the raw git log."

**Then:** Run the command and display the output. After showing it:
> "A developer can squint at this and figure out what matters. But your users? Your stakeholders? Your marketing team? No chance. Now watch what happens next."

### Step 2: Transform Into Release Notes (The Magic Moment)

**What to do:** Take the git history and produce customer-facing release notes. Apply these rules:
- Only include user-facing changes (skip chores, refactors, tests, dependency updates)
- Group into: New Features, Bug Fixes, Improvements
- Write each item in plain English — no technical jargon
- Lead with the benefit, not the implementation
- Keep each item to 1-2 sentences max
- Format it ready to paste into an email, blog post, or in-app notification

**What to say:** Something like:
> "Now let me transform that into something a human would actually want to read..."

**Then:** Show the transformation. Frame the before/after contrast:
> "Same commits. Same information. Completely different impact. The gap between `fix: handle null ref in checkout flow (#847)` and 'We fixed a bug that could cause checkout to freeze' is exactly the gap between a git log and a product update.
>
> What do you think — does this capture what shipped accurately?"

Wait for their response and adjust if needed.

### Step 3: Customize the Tone

**What to do:** Rewrite the same release notes in three different tones so the student can see how voice changes impact.

**What to say:** Something like:
> "Different audiences need different tones. Let me show you the same content in three voices — pick the one that matches your brand, or mix and match."

**Then:** Produce three versions:
1. **Casual/fun** — like a startup talking to early adopters
2. **Professional** — like an enterprise SaaS company talking to IT buyers
3. **Internal** — like a PM updating the executive team on what shipped

After showing all three:
> "Which one feels closest to your voice? Or should I blend elements from different ones?"

Wait for their response.

---

## Exercise 2: Raw Notes to Stakeholder Updates

### Step 4: Gather Context

**What to do:** Ask the student for the raw ingredients of their weekly update. Offer to pull from git or project boards if available, but also accept plain text.

**What to say:** Something like:
> "Great — now let's tackle the other weekly time sink: stakeholder updates. Every PM spends 30-60 minutes collecting what happened, formatting it for different audiences, and writing 'here's what we shipped, here's what's next.' Let's make that take 5 minutes.
>
> I need the raw ingredients. Tell me (or paste) whatever you've got:
>
> 1. **What shipped this week** — bullet points, PR links, or just say 'use the git log from Exercise 1'
> 2. **What's in progress** — current sprint items or what's being worked on
> 3. **Key metrics that moved** — signups, revenue, DAU, whatever you track
> 4. **Blockers or risks** — anything stakeholders should know about
>
> Don't worry about formatting — just give me the raw info and I'll do the rest."

**Then:** Wait for their response.
- If they say "use the git log," reuse the data from Exercise 1.
- If they have Linear, Jira, or GitHub MCP connected, offer to pull data directly.
- If they paste raw notes, great — use those.
- If they don't have any context at all, create a realistic sample scenario: a B2B SaaS product that shipped an onboarding redesign, has a mobile app in progress, saw 12% signup growth, and is blocked on a design contractor approval.

### Step 5: Generate the Stakeholder Update

**What to do:** Synthesize everything into a polished stakeholder update.

**What to say:** Something like:
> "Great, let me turn that into something you'd actually send."

**Then:** Produce a formatted update with this structure:

```
## Executive Summary
[2-3 sentences — the headline version. If they read nothing else, they get the point.]

## Shipped This Week
[Completed work with brief descriptions and user impact]

## In Progress
[Current work with progress indicators and expected completion]

## Key Metrics
[Numbers with trend arrows — up, down, flat]

## Next Week
[Top 3 priorities]

## Blockers & Decisions Needed
[Anything requiring stakeholder input — frame as a clear ask]
```

Keep it under 300 words. No jargon. Confident tone. End with one specific ask.

After showing it:
> "That's your weekly update — under 300 words, leading with impact not activity, ending with a clear ask. How does it look? Anything to add or change?"

Wait for their response and iterate if needed.

### Step 6: Adapt for Different Audiences

**What to do:** Take the same update and create three versions for different audiences.

**What to say:** Something like:
> "Same information, but different people need different versions. Let me create three in one shot."

**Then:** Produce three versions:
1. **Executive version** (for CEO/leadership) — 5 bullet points max. Only outcomes and decisions needed. No implementation details.
2. **Team version** (for engineering/design) — More detailed. Include technical context, shoutouts for specific contributions, what's coming next sprint.
3. **Board version** (for investors/board) — Focus on metrics, growth trajectory, and strategic milestones. Quarterly framing.

After showing all three:
> "The exec version is 5 lines. The team version has personality and shoutouts. The board version connects this week to the bigger picture. Instead of writing three separate emails, you write zero — I draft all three from the same source material, and you spend your time editing instead of starting from scratch.
>
> Which audience do you write for most often?"

Wait for their response.

### Step 7: Make It Brutally Short

**What to do:** Take the executive version and compress it further. Demonstrate that brevity increases readability.

**What to say:** Something like:
> "One more trick — let me take the executive version and make it 50% shorter. Every word has to earn its place."

**Then:** Produce a brutally compressed version. After showing it:
> "That's the version busy stakeholders will actually read. Tight enough to skim in 15 seconds, substantial enough to know what matters."

---

### Wrap Up

**What to say:** Something like:
> "You just automated the two most repetitive writing tasks in your week:
> 1. **Release notes** — git log to customer-facing updates in any tone
> 2. **Stakeholder updates** — raw notes to polished, multi-audience comms
>
> The pattern is the same for both: gather raw info, transform into polished output, adapt for different audiences. You draft zero, I draft everything, you edit.
>
> Want to take it further? I can:
> - **Automate release notes** — set up a GitHub Action that generates them on every merge to main
> - **Automate weekly updates** — set up a cron job that runs every Friday, pulls from git and your project board, and drops a draft for your review
> - **Thread the narrative** — reference last week's update and highlight progress on ongoing items
> - **Add metrics automatically** — if you have PostHog or analytics MCP servers connected, I can pull real numbers
> - **Multi-format output** — same notes formatted for email, Slack, in-app banner, and App Store 'What's New'
>
> **Share with the cohort:** Your release notes OR executive summary. Read them aloud — would a non-technical user understand every item?"

---

## Reference Material

- **Git commands used:** `git log --oneline --since="2 weeks ago"`, `git log --oneline -30`
- **Release note categories:** New Features, Bug Fixes, Improvements
- **Tone variants:** Casual/startup, Professional/enterprise, Internal/executive
- **Update structure:** Executive summary, shipped, in progress, key metrics (with trend arrows), next week priorities, blockers & decisions needed
- **Audience versions:** Executive (5 bullets max), Team (detailed + shoutouts), Board (metrics + strategic milestones)
- **Data sources:** Git log (`git log --oneline --since="1 week ago"`), Linear/Jira MCP, GitHub PRs, manual notes
- **GitHub Action for automation:** `anthropics/claude-code-action@v1` — requires Claude Code OAuth token as GitHub secret
- **Automation options:** Friday cron job for draft generation, PostHog/analytics MCP for automatic metric pulls, OKR mapping
- **Multi-format options:** Email newsletter, Slack post, in-app notification banner, App Store "What's New" section, CHANGELOG.md
- **Key principle:** Lead with impact, not activity. End with a clear ask.
