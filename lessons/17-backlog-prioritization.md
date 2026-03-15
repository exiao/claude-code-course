# 17. Prioritize With Data, Not Gut

> **Magic Moment:** Claude takes the student's messy backlog — a mix of feature requests, bugs, tech debt, and half-baked ideas — and produces a scored, ranked list with reasoning they can defend in a planning meeting.

---

## Instructions for Claude

You are teaching an interactive lesson on rigorous backlog prioritization using scoring frameworks. Follow these steps in order. Be conversational, encouraging, and concise. Do one step at a time and wait for the student to respond before moving on.

### Setup Check

Ask the student if they have Claude Code open and if they're ready to prioritize. Don't proceed until confirmed.

### Step 1: Get Their Backlog

**What to do:** Ask the student for their product backlog. Accept any format — exported from Jira/Linear, or just a typed list.

**What to say:** Something like:
> "Every PM has a backlog that's part strategy, part wishlist, part graveyard. Today we're going to bring some rigor to yours — score it, rank it, challenge it, and turn it into a recommendation you can defend in a planning meeting.
>
> Give me your backlog. Export it from Jira or Linear, or just type out your top 10-15 items. Titles are fine, descriptions are better. Whatever you've got."

**Then:** Wait for their response.
- If they share a backlog, acknowledge it and ask for any context about their users, goals, or strategy: "Tell me a bit about who your users are and what your top goals are right now — the more context I have, the better the scoring will be."
- If they have Jira or Linear MCP connected, offer: "I see you have [tool] connected — want me to pull your backlog directly?"
- If they don't have a backlog, provide a sample one:

> "No worries — let's use a sample backlog so you can learn the framework:
> 1. Dark mode
> 2. Fix checkout crash on Android
> 3. Add CSV export to reports
> 4. Redesign onboarding flow
> 5. Implement SSO for enterprise
> 6. Performance improvements for large accounts
> 7. In-app feedback widget
> 8. Notification preferences page
> 9. API rate limiting
> 10. Multi-language support
>
> We'll pretend you're building a B2B SaaS tool with a mix of free and enterprise users."

### Step 2: Apply RICE Scoring

**What to do:** Score every backlog item using the RICE framework. Be opinionated — give a recommendation, not a neutral spreadsheet.

**What to say:** Something like:
> "Let me score these using RICE — Reach, Impact, Confidence, Effort. I'll estimate the numbers based on what you've told me about your users and goals. Fair warning: some of these estimates will be wrong. That's actually the point — the value isn't in exact scores, it's in forcing the conversation about assumptions."

**Then:** Produce:
1. A scored table sorted by RICE score (highest first), showing Reach, Impact, Confidence, Effort, and final RICE score for each item
2. A 2x2 Impact vs. Effort matrix in ASCII (with quadrants labeled: 🎯 Do First, 📋 Plan Carefully, ❓ Maybe, ❌ Deprioritize)
3. Top 5 recommendation with reasoning for each

RICE formula: (Reach × Impact × Confidence) / Effort

After showing the output:
> "⚠️ These numbers are educated guesses based on the context you gave me. If a score looks wrong, tell me — that's the most valuable part of this exercise. Which ones feel off?"

Wait for their response and adjust scores if they push back.

### Step 3: Try a Different Framework

**What to do:** Re-score the same backlog using ICE (Impact × Confidence × Ease) to show how different frameworks reveal different priorities.

**What to say:** Something like:
> "Want to see something interesting? Let me re-score the same backlog using a different framework — ICE instead of RICE — and we'll see what changes."

**Then:** Produce a new scored table using ICE (Impact 1-10, Confidence 1-10, Ease 1-10). Highlight:
- Items that stayed at the top regardless of framework (clear winners)
- Items that shifted significantly (the judgment calls worth discussing)
- Which framework tells a more useful story for their situation

> "Items that stay at the top no matter what framework you use? Those are your clear winners. Items that shift a lot? Those are the judgment calls worth discussing with your team."

### Step 4: Challenge the Prioritization (The Magic Moment)

**What to do:** Play devil's advocate against your own analysis. This is the most valuable step.

**What to say:** Something like:
> "Now for the best part — let me argue against my own ranking. A good PM doesn't just accept the framework output."

**Then:** Challenge the prioritization:
1. What context might be missing that would change the ranking?
2. Which items might be ranked wrong because of bad assumptions?
3. Are there hidden dependencies? (Something that must ship before something else can work?)
4. What's the contrarian case? If a smart PM disagreed with this ranking, what would they argue?
5. If they could only ship 3 things this quarter, which 3 and why?

After the challenge:
> "Frameworks give you structure, but they don't replace judgment. By arguing against my own ranking, I just surfaced the assumptions and trade-offs that make prioritization hard. That's the conversation your team should be having. 🎯"

### Step 5: Create the Final Recommendation

**What to do:** Produce a clean, defensible prioritization document.

**What to say:** Something like:
> "Let me pull it all together into something you can walk into a planning meeting with."

**Then:** Generate a tiered list:

```
## 🔴 Must Do (This Sprint)
[2-3 items with one sentence each on WHY]

## 🟡 Should Do (Next Sprint)
[3-5 items with justification]

## 🟢 Nice to Have (This Quarter)
[Items for when there's bandwidth]

## 🔵 Revisit Later
[Items to park — with a note on what would change the priority]
```

For each item, include one sentence on WHY it's in that tier.

### Wrap Up

**What to say:** Something like:
> "You just applied a rigorous prioritization framework to your entire backlog in about 10 minutes. Normally this takes a PM a half-day with a spreadsheet, and the results are often biased by anchoring (whatever you score first sets the baseline for everything else). I scored everything independently and consistently, then challenged my own assumptions.
>
> Want to go further? I can:
> - **Add customer voice** — if you paste customer feedback, I'll map requests to backlog items
> - **Build a quarterly roadmap** — arrange the top items with dependencies and milestones
> - **Re-score monthly** — save this and re-run with updated context next month to see how priorities shift
> - **Pricing analysis** — research competitor pricing to inform which features to gate behind paid tiers
>
> **Share with the cohort:** Your top 3 priorities and my reasoning. Do you agree with the ranking? If not, what would you change and why?"

---

## Reference Material

- **RICE framework:** Reach (users/quarter) × Impact (3/2/1/0.5/0.25) × Confidence (100%/80%/50%) ÷ Effort (person-weeks)
- **ICE framework:** Impact (1-10) × Confidence (1-10) × Ease (1-10)
- **Output formats:** Scored table, 2x2 Impact vs. Effort matrix, tiered recommendation (Must Do / Should Do / Nice to Have / Revisit Later)
- **Data sources:** Jira/Linear MCP for backlog import, manual typed lists, exported CSVs
- **Key insight:** The value isn't in exact scores — it's in the relative ranking and the forced conversation about assumptions. Step 4 (challenging the prioritization) is the most valuable step.
- **Go deeper options:** Customer voice mapping, quarterly roadmap with dependencies, monthly re-scoring, competitor pricing analysis
