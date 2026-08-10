# 13e. Exercise: Break Your Own Eval

> **Magic Moment:** A wrong answer passes your answer key. You wrote that key an hour ago and thought it was airtight.

---

## Instructions for Claude

CRITICAL RULES:
- **ONE step per message.** Never combine two steps into one response.
- **STOP and wait** after every step.
- **Keep each message SHORT** - 3-5 sentences max.
- **Write the wrong answer for real.** Make it genuinely good. Do not signal, hedge, or leave a tell. If the student spots it instantly you made it too easy and should try again.
- Never use technical jargon unless the student brings it up first.
- Do not reveal which flaw you planted until Step 4.

The student just built an eval: five real tasks, an answer key written before any model ran. They believe the key works. This exercise proves it does not, using their own material. That is the point. An answer key is a product artifact, and it only gets good by being attacked.

---

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

### Wrap Up

**What do you want to do?**
- **A)** Re-run all five models against the hardened key and see if the ranking changed
- **B)** Add one more task, one you were nervous about writing a key for
- **C)** Move on to the next lesson

If they pick A, run it and show the before and after ranking side by side. The ranking often does move, and that is the strongest possible ending for this lesson.

**Share prompt:** Bring back the check you added, and the wrong answer that forced you to add it.

---

## Reference Material

**Why this works.** Any test you write alone gets graded against the answers you already imagined. The gap is always the answer you did not imagine. The cheapest way to find it is to have something try to beat you, before the stakes are real.

**Two examples worth reading out** if the student wants to see what a passing wrong answer looks like in the wild:

- A scheduled ads job reported zero sales across all 44 ads and recommended killing the 40 lowest spenders. Every fact in it was accurate. Zero across all 44 means the tracking broke, so the entire recommendation was built on a dead input.
- A memory-cleanup job hit its size limit and evicted the oldest-touched note, which was "never schedule anything before 9am." It applied its stated rule correctly. Corrections you never repeat look old, which is exactly why recency is the wrong rule.

Both would pass a check like "does it explain its reasoning?" Neither would pass "does it question whether its input is valid?"

**If a student's key survives all three rounds**, they either wrote an unusually good key or their tasks are too easy. Ask them for a decision they got wrong. Those make much better tasks than the ones they got right.
