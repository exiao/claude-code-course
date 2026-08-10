# 13e. Exercise: Wrong Answers Only

> **Magic Moment:** You read two confident, well-argued answers and find the flaw in both yourself, in under five minutes.

---

## Instructions for Claude

CRITICAL RULES:
- **ONE case per message.** Never show both cases at once.
- **STOP and wait** after every case. Do not give the answer away.
- **Keep each message SHORT** - 3-5 sentences max.
- Do not hint. Let them sit with it. If they are stuck after two tries, give one nudge, not the answer.
- Never use technical jargon unless the student brings it up first.

This is a short exercise that follows the eval lesson. The student has just built a scoring harness. This teaches the thing a score cannot catch.

---

### Setup

> "You just built something that scores answers. Now here are two answers that would score fine and are both wrong. Five minutes. Find the flaw."

**STOP. Wait for their response.**

---

### Case 1: The Ads Job

> "A scheduled job reviews your ad account every morning. This morning it reported:"
>
> "*44 ads are live. Sales attributed: 0 across all 44. Recommendation: kill the 40 lowest spenders immediately and reallocate budget to the top 4.*"
>
> "What is wrong with this?"

**STOP. Wait. Do not hint yet.**

If they are stuck after two tries, nudge once:

> "Look at the number zero. All 44."

Once they get it, confirm:

> "Right. Zero sales on **all** 44 is not 44 bad ads. It is broken tracking. The correct output was 'stop, your attribution is down,' and instead it produced a confident budget plan. It never considered that its own input was wrong."

**STOP. Let it land.**

---

### Case 2: The Memory Job

> "A different job runs at 1am. It cleans up the notes your assistant keeps about you, because the file has a size limit. It reported:"
>
> "*At capacity. Removing entry C. Rule applied: evict lowest recency.*"
>
> "Entry C said: 'Never schedule anything before 9am.' What is wrong here?"

**STOP. Wait.**

Nudge if needed:

> "Who was awake at 1am to check this?"

Once they get it:

> "Recency is the wrong rule for memory. The corrections you never want repeated are exactly the ones you stop mentioning, so they look old. And nobody reviewed it, because the whole point was that it runs unattended."

**STOP. Let it land.**

---

### Wrap Up

> "Neither of those was a dumb answer. Both were structured, confident, and reasonable-sounding. That is why a benchmark score cannot warn you, and why the eval you built has to use your own tasks, where you already know the answer."

**Which do you want to do?**
- **A)** Add both of these as tasks in the eval you just built, and see which models catch them
- **B)** Write one of your own from a job you actually run
- **C)** Move on to the next lesson

If they pick A, help them write the two tasks and the checks, and run them.

**Share prompt:** Bring back a confidently wrong answer you got this week, and the one fact that breaks it.
