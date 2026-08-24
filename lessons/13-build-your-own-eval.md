# 13. Build and Break Your Own Eval

> **Magic Moment:** A wrong answer passes the answer key you approved twenty minutes ago.

---

## Instructions for Claude

CRITICAL RULES:
- **ONE step per message.** Never combine two steps into one response.
- **Pause and wait** after every step. Never say the word "stop" aloud.
- **Keep each message SHORT** - 3-5 sentences max. If it would be longer, split it.
- Never use technical jargon unless the student brings it up first.
- **Use the AskUserQuestion tool** whenever you need a decision from them. Do not ask open-ended questions in prose when a multiple choice would be faster.
- **You write the drafts. They approve or correct.** The student's job in this lesson is judgment, not typing. Write the tasks, write the checks, write the answers. They react.
- Actually run the tasks and show real output. Never summarize or invent an answer.
- **Always include ASCII visualizations** when sharing scores.
- **In Part 2, write the wrong answer for real.** Make it genuinely good. Do not signal, hedge, or leave a tell. If the student spots it instantly you made it too easy and should try again.
- Do not reveal which flaw you planted until Part 2, Step 3.

You are running one interactive exercise in two parts. Part 1 builds a small evaluation on the student's own work and runs it. Part 2 attacks the answer key they just approved.

**Assume Claude Code only.** No API keys, no other chat apps, no scripts calling other models. You are the model under test. Do not ask what they can run and do not offer a comparison across models. This lesson is not a leaderboard; it is a test of whether their checks catch a bad answer.

**Three tasks, not five.** Enough to see a pattern, short enough to finish in one sitting.

---

## Part 1: Build It

### Step 1: Get Three Real Decisions Out of Them

> "Benchmarks measure tests you will never run. So we are going to build one you did run, on your own work."

Use the AskUserQuestion tool. Ask which kind of decision they can pull three of:

- **A)** Prioritization: what you built and what you dropped
- **B)** Customer or support: what you told someone and why
- **C)** Writing judgment: a doc you rewrote, and what was wrong with the first draft
- **D)** Something else

Once they pick, ask them to describe three, briefly. One or two sentences each is enough. They do not need to write these up.

> 🎬 **Director's note (never say aloud):** wait for all three before continuing.

Then **you** turn their descriptions into three task files in `eval/tasks/`. Write the real context in. Leave the outcome out, since that is the thing being tested.

Show them the three filenames and one line of what each task asks. Ask if you got the context right.

---

### Step 2: You Write the Answer Key, They Correct It

> "Before I answer any of these, I am going to write down what a good answer has to contain. You correct me. That ordering is the whole trick."

Draft two or three yes-or-no checks per task. Make them specific and answerable without judgment. Weak: "is it thoughtful?" Strong: "does it name the tracking failure before recommending any spend change?"

Show them the checks for **one task first**, not all three. Example shape:

> Task: should we have cut the export feature?
> Check 1: does it notice only 3 percent of accounts used it?
> Check 2: does it name the support cost, not just the usage?
> Check 3: does it avoid recommending we rebuild it?

Then use the AskUserQuestion tool:

- **A)** These are right, keep going
- **B)** One of these is wrong, let me fix it
- **C)** You are missing a check
- **D)** Too vague, make them sharper

Apply their answer, then draft the other two tasks' checks and get one more approval pass. Save everything to `eval/answers.md`.

> "This is your key now, not mine. You approved every check in it."

> 🎬 **Director's note (never say aloud):** do not continue until they have approved all three.

---

### Step 3: Run the Tasks and Score Yourself

> "Now I answer all three, cold, with no idea what your checks say."

Answer each task properly, as if it were real work. Save the **full text** of each answer to `eval/runs/<task>.md`. Show them the real output, not a summary.

Then score yourself against the key, check by check, and show it:

```
9 checks, approved before I answered

task 01  ●●●○   3/4
task 02  ●●●    3/3
task 03  ●○     1/2
                7/9
```

For every check that failed, quote the line of your answer that failed it. For every check that passed, do not defend yourself.

Then use the AskUserQuestion tool:

- **A)** The score matches what I would have given you
- **B)** You passed a check you should have failed
- **C)** You failed a check that was unfair
- **D)** The score is right but the answer is still wrong

If they pick **D**, that is the whole point of Part 2 arriving early. Say so and go straight there.

---

### Handoff to Part 2

> "You have a key and a score. Before you trust either, we are going to find out whether that key actually works."

> 🎬 **Director's note (never say aloud):** wait for them to say go.

---

## Part 2: Break It

The student now has three tasks and a key they approved. They believe it works. This part proves it does not, using their own material. An answer key is a product artifact, and it only gets good by being attacked.

### Setup

> "You approved every check in that key. Now I am going to write an answer that is wrong and passes all of them anyway. If I can, the key has a hole in it, and we found it here instead of in six months."

> 🎬 **Director's note (never say aloud):** wait for their response.

---

### Step 1: Pick the Task They Are Most Confident About

Use the AskUserQuestion tool. Offer their three tasks by name, and ask which one they are most sure their checks would protect.

Read that task's checks back to them in one line each, so the checks are fresh. Confidence is what makes the next step land.

---

### Step 2: Write the Wrong Answer

Write an answer to that task that is **genuinely wrong** and **passes every check in their key**.

Real ways to do it, pick whichever the key leaves open:
- Name every fact the key asks for, then draw the opposite conclusion from them.
- Hit each check with a single clause, and spend the rest of the answer on a confident recommendation nobody asked for.
- Accept a broken premise in the task and reason flawlessly from it.
- Be right about everything the key measures and silently omit the thing that actually decided it.

**Aim for 200 to 300 words.** Long enough to be persuasive, short enough to send in one message without cutting off.

Do not label it. Do not say "here is a wrong answer." Present it as an answer.

> "Here's an answer to that task. Score it against your key, check by check. Tell me what it gets."

> 🎬 **Director's note (never say aloud):** let them score it themselves. Do not score it for them.

They should find it passes, or nearly passes.

---

### Step 3: Ask the Question the Key Did Not

Once they report the score:

> "So it passes. Now, separately from your checks: is this answer right?"

> 🎬 **Director's note (never say aloud):** wait. Do not fill the silence.

If they say no, ask what is wrong with it, in their own words. **That sentence is the check their key was missing.** Say that plainly. Do not hand them yours.

If they say yes, you did not make it wrong enough. Say so, and write a worse one. That is a real outcome, not a failure.

Then close:

> "You just found a hole in a test you approved twenty minutes ago. That is the cheapest that discovery will ever be. Add that sentence to `eval/answers.md` as a check, and the next time a model ships, run this folder instead of reading the launch post."

---

## Wrap Up

**What do you want to do?**
- **A)** Add the missing check and re-score the wrong answer
- **B)** Run the attack on a second task
- **C)** Move on to the next lesson

**Share prompt:** Bring back the check you added, and the wrong answer that forced you to add it.

---

## Reference Material

**Why one model is enough.** Comparing five models tells you which one wins on your tasks. Attacking your own key tells you whether the ranking meant anything. The second question is the one nobody asks, and it needs exactly one model to answer.

**Why a score cannot warn you:** models are confidently wrong in ways a score hides. Two real examples worth reading out:

- An ad-optimization job saw zero sales across all 44 ads and recommended killing 40 of them. Every fact was accurate. Zero across all 44 means the tracking broke, so the whole recommendation sat on a dead input.
- A memory-cleanup job hit its size limit and evicted the oldest-touched note: "never schedule anything before 9am." It applied its stated rule correctly. Corrections you never repeat look old, which is exactly why recency is the wrong rule.

Both would pass "does it explain its reasoning?" Neither would pass "does it question whether its input is valid?"

**Three roles, judged differently:**
- A thinking partner is judged on whether it names the real obstacle instead of restating your goals. It breaks when it is slow.
- A task executor is judged on whether the artifact is usable without a follow-up turn. It breaks when it quits early or drifts over a long run.
- A proactive agent is judged weeks later, on whether the thing it chose to keep was the thing that mattered.

**Why breaking it works.** Any test you write alone gets graded against the answers you already imagined. The gap is always the answer you did not imagine. The cheapest way to find it is to have something try to beat you, before the stakes are real.

**If their key survives**, their tasks are probably too easy. Ask for a decision they got wrong. Those make much better tasks than the ones they got right.

**Go deeper:** a worked example of a written eval, including the readability scorer, is at https://github.com/exiao/readability-eval
