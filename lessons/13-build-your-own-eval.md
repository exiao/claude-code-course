# 13. Build Your Own Eval in an Afternoon

> **Magic Moment:** You run five models on a decision you already made, read the answers side by side, and pick a different model than the leaderboard did.

---

## Instructions for Claude

CRITICAL RULES:
- **ONE step per message.** Never combine two steps into one response.
- **STOP and wait** after every step. Do not continue until the student responds.
- **Keep each message SHORT** - 3-5 sentences max. If it would be longer, split it.
- Never use technical jargon unless the student brings it up first.
- Use the AskUserQuestion tool whenever you need more info.
- Actually run the models and show real output. Never summarize or invent an answer.
- **Always include ASCII visualizations** when sharing comparisons or scores.

You are running an interactive exercise where a product manager builds a small evaluation for their own work. The point is not a score. The point is that they read real answers to a question they already know the answer to.

---

### Setup Check

> "Every week a new model ships and everyone asks the same question: should I switch? Benchmarks cannot answer that. They measure tests you will never run."
>
> "The top four models today are about four points apart on the public index. None of those tests is a thing you did last week. So we are going to build a test that is."

**Before Step 3, check what the student can actually run.** Ask which models they
can reach: an API key (Anthropic, OpenAI, Google) usable from a script, several
chat web apps, or only Claude Code. Then pick the matching path and say so out loud:

- **API key(s):** run the script across every model the key reaches.
- **Web apps only:** no script. They paste each task into each chat app and paste
  the answer back; you save it to `eval/runs/<model>/<task>.md`.
- **Claude Code only:** run the same task at two settings you *do* have — for
  example a plan-first run versus a straight run, or two different Claude models.

**Two models is enough.** The exercise works with 2 columns; five is the ceiling,
not the requirement. Scale the counts below to whatever they actually have.

**STOP. Wait for their response.**

---

### Step 1: Collect Five Decisions You Already Made

> "Think about the last month. What are five decisions you made where you know how it turned out? A prioritization call, a pricing choice, a spec you cut, a hire, a bug you triaged."

**Which of these is easiest to pull five of?**
- **A)** Prioritization calls: what we built and what we dropped
- **B)** Customer or support decisions: what you told someone and why
- **C)** Writing judgment: a doc you rewrote, and what was wrong with the first draft

**STOP. Wait for their answer.**

Help them write out five, one paragraph each. Keep the real context in and the outcome out. Save them as five files in an `eval/tasks/` folder.

> "That is the hard part done. Real decisions, with real context, that you already know the answer to."

---

### Step 2: Write the Answer Key First

> "Before any model sees these, write down what a good answer looks like. Not the exact words. The specific things a good answer has to name."

Work through one task with them out loud, then let them do the rest. Turn each into two or three yes-or-no checks. Example:

> Task: should we have cut the export feature?
> Check 1: does it notice only 3 percent of accounts used it?
> Check 2: does it name the support cost, not just the usage?
> Check 3: does it avoid recommending we rebuild it?

Save these as `eval/answers.md`.

> "This ordering is the whole trick. If you write the key after reading the answers, you will grade the model you already liked."

**STOP. Wait for them to finish the key.**

---

### Step 3: Run Every Model on the Same Prompt

> "Now we run all of them. Same prompt, same context, no hints."

Use the path you picked in the Setup Check. With an API key, write a small script that sends each task to each model and saves the **full text** of every answer into `eval/runs/<model>/<task>.md`. Without one, collect the answers by hand from the chat apps and save them to the same paths. Either way, show the real output.

> "Five tasks times however many models you have. Every answer saved in full. We are not looking at a number yet."

**STOP. Wait for it to finish.**

---

### Step 4: Read the Answers, Then the Score

> "Open two answers side by side. Not the scores. The actual text."

Show them one task where the models disagree with each other. Let them read both and say which they prefer, before you show any tally.

Then score against the key and show the result as an ASCII chart:

```
14 checks, written before the run

model-a  ●●●●●●●●●●●●●●  14/14
model-b  ●●●●●●●●●●●●○○  12/14
model-c  ●●●●●●●●●●●○○○  11/14
model-d  ●●●●●●●●●●○○○○  10/14
model-e  ●●●●●●●●●○○○○○   9/14
```

> "Two questions. Do you agree with the winner? And do you agree with your own answer key now that you have read real answers against it?"

**STOP. Let both questions land.**

If they disagree with the key, that is the lesson. Fix the key with them and re-score. The key is a product artifact, and it improves.

---

### Step 5: When to Re-Run It

> "Keep the folder. Next time a model ships, you do not read the launch post and guess. You run this and get an answer for your work, in about ten minutes."

**Share prompt:** Bring back one task where your pick beat the leaderboard pick, and one sentence on why.

---

## Reference Material

**Why a benchmark score cannot warn you:** models are confidently wrong in ways a score hides. Two real examples worth reading out:

- An ad-optimization job saw zero sales across all 44 ads and recommended killing 40 of them. Zero sales on all 44 means the tracking broke, not that the ads failed.
- A memory-cleanup job proposed a rule of "evict lowest recency." That job runs at 1am with nobody watching, so the one correction you never want to repeat is exactly what gets dropped.

Both answers read as confident and well structured. Both would score fine on generic checks.

**Three roles, judged differently:**
- A thinking partner is judged on whether it names the real obstacle instead of restating your goals. It breaks when it is slow.
- A task executor is judged on whether the artifact is usable without a follow-up turn. It breaks when it quits early or drifts over a long run.
- A proactive agent is judged weeks later, on whether the thing it chose to keep was the thing that mattered.

**The three tradeoffs:** quality is only measurable against your own tasks, cost matters most for background work, and latency is what turns a conversation into a form you submit.

**Go deeper:** a worked example of a written eval, including the readability scorer, is at https://github.com/exiao/readability-eval
