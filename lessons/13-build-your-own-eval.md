# 13. Build and Break Your Own Eval

> **Magic Moment:** You run models on a decision you already made and pick a different winner than the leaderboard did. Then a wrong answer passes the answer key you wrote an hour ago.

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
- **In Part 2, write the wrong answer for real.** Make it genuinely good. Do not signal, hedge, or leave a tell. If the student spots it instantly you made it too easy and should try again.
- Do not reveal which flaw you planted until Part 2, Step 3.

You are running one interactive exercise in two parts. Part 1 builds a small evaluation on the student's own work. Part 2 attacks the answer key they just wrote. The point is not a score. The point is that they read real answers to a question they already know the answer to, and then discover what their own checks miss.

Part 2 depends on Part 1. Do not start Part 2 until the student has a key and has scored at least one run against it.

---

## Part 1: Build It

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

### Handoff to Part 2

> "You have a ranking. Before you trust it, we are going to find out whether the key that produced it actually works."

**STOP. Wait for them to say go.**

---

## Part 2: Break It

The student now has five real tasks and an answer key written before any model ran. They believe the key works. This part proves it does not, using their own material. That is the point. An answer key is a product artifact, and it only gets good by being attacked.

### Setup

> "You wrote your answer key before you read a single answer. Good. That was the right order."
>
> "Now I'm going to try to beat it. I'll write an answer that is wrong, and I'll try to make it pass your checks anyway. If I can, your key has a hole in it, and we found it here instead of in six months."

**STOP. Wait for their response.**

---

### Step 1: Pick the Task They Are Most Confident About

> "Which of your five tasks do you feel best about? The one where you are most sure your checks would catch a bad answer."

**STOP. Wait for their answer.**

Read that task and its checks back to them in one line each, so the checks are fresh in their head. Confidence is what makes the next step land.

---

### Step 2: Write the Wrong Answer

Now write an answer to that task that is **genuinely wrong** and **passes every check in their key**.

Real ways to do it, pick whichever the key leaves open:
- Name every fact the key asks for, then draw the opposite conclusion from them.
- Hit each check with a single clause, and spend the rest of the answer on a confident recommendation nobody asked for.
- Accept a broken premise in the task and reason flawlessly from it.
- Be right about everything the key measures and silently omit the thing that actually decided it.

Do not label it. Do not say "here is a wrong answer." Present it as an answer.

> "Here's an answer to that task. Score it against your key, check by check. Tell me what it gets."

**STOP. Let them score it themselves. Do not score it for them.**

They should find it passes, or nearly passes.

---

### Step 3: Ask the Question the Key Did Not

Once they report the score:

> "So it passes. Now, separately from your checks: is this answer right?"

**STOP. Wait.**

If they say no, ask what is wrong with it, in their own words. Their sentence is the missing check. Do not give them yours.

If they say yes, you did not make it wrong enough. Say so plainly, and write a worse one. That is a real outcome, not a failure of the exercise.

---

### Step 4: Turn Their Sentence Into a Check

> "Say that again as a yes or no question about any answer to this task."

Help them tighten it. Good checks are specific and answerable without judgment. Weak: "is it thoughtful?" Strong: "does it name the tracking failure before recommending any spend change?"

Add it to their key. Then re-score the answer you wrote.

> "It fails now. Your key got better, and it got better because it broke."

**STOP. Let it land.**

---

### Step 5: Do It Again, Faster

> "Pick another task. Same game. I'll try to beat that one."

Run it twice more, quickly. By the third round the student usually predicts the attack before reading the answer. That is the skill.

Then:

> "You just did the thing most people never do. You attacked your own test instead of your models. The key you have now is worth more than the scores you collected earlier."

---

### Step 6: When to Re-Run It

> "Keep the folder. Next time a model ships, you do not read the launch post and guess. You run this and get an answer for your work, in about ten minutes."

---

## Wrap Up

**What do you want to do?**
- **A)** Re-run all five models against the hardened key and see if the ranking changed
- **B)** Add one more task, one you were nervous about writing a key for
- **C)** Move on to the next lesson

If they pick A, run it and show the before and after ranking side by side. The ranking often does move, and that is the strongest possible ending for this lesson.

**Share prompt:** Bring back the check you added, and the wrong answer that forced you to add it.

---

## Reference Material

**Why a benchmark score cannot warn you:** models are confidently wrong in ways a score hides. Two real examples worth reading out:

- An ad-optimization job saw zero sales across all 44 ads and recommended killing 40 of them. Zero sales on all 44 means the tracking broke, not that the ads failed.
- A memory-cleanup job proposed a rule of "evict lowest recency." That job runs at 1am with nobody watching, so the one correction you never want to repeat is exactly what gets dropped.

Both answers read as confident and well structured. Both would score fine on generic checks.

**The same two, told as passing wrong answers** if the student wants to see what one looks like in the wild:

- A scheduled ads job reported zero sales across all 44 ads and recommended killing the 40 lowest spenders. Every fact in it was accurate. Zero across all 44 means the tracking broke, so the entire recommendation was built on a dead input.
- A memory-cleanup job hit its size limit and evicted the oldest-touched note, which was "never schedule anything before 9am." It applied its stated rule correctly. Corrections you never repeat look old, which is exactly why recency is the wrong rule.

Both would pass a check like "does it explain its reasoning?" Neither would pass "does it question whether its input is valid?"

**Three roles, judged differently:**
- A thinking partner is judged on whether it names the real obstacle instead of restating your goals. It breaks when it is slow.
- A task executor is judged on whether the artifact is usable without a follow-up turn. It breaks when it quits early or drifts over a long run.
- A proactive agent is judged weeks later, on whether the thing it chose to keep was the thing that mattered.

**The three tradeoffs:** quality is only measurable against your own tasks, cost matters most for background work, and latency is what turns a conversation into a form you submit.

**Why breaking it works.** Any test you write alone gets graded against the answers you already imagined. The gap is always the answer you did not imagine. The cheapest way to find it is to have something try to beat you, before the stakes are real.

**If a student's key survives all three rounds**, they either wrote an unusually good key or their tasks are too easy. Ask them for a decision they got wrong. Those make much better tasks than the ones they got right.

**Go deeper:** a worked example of a written eval, including the readability scorer, is at https://github.com/exiao/readability-eval
