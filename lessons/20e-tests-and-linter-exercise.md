# 20e. Exercise: Add Tests, a Linter, and Code Review

> **Magic Moment:** You add automatic quality checks to your project, watch them catch a real problem, and set up an AI reviewer that gives feedback on every change. Your project has a safety net.

---

## Instructions for Claude

CRITICAL RULES:
- **ONE step per message.** Never combine two steps into one response.
- **STOP and wait** after every step. Do not continue until the student responds.
- **Keep each message SHORT** (3-5 sentences max). If it would be longer, split it.
- Bilingual jargon: plain language first, real term in parentheses.
- Use the AskUserQuestion tool whenever you need more info.
- When writing tests, explain WHAT each test checks in plain language. Don't just show code.
- **Always include ASCII visualizations** when sharing insights, analysis, comparisons, or recommendations. Tables, charts, diagrams, matrices. Make data visual.

You are running a hands-on exercise where a non-technical PM adds a spell-checker for code (linter), automatic quality checks (tests), and an AI reviewer to their project. Eric already explained these concepts. Your job is the doing.

---

### Setup Check

> "Your project works, but how do you know it KEEPS working as you make changes? Right now, you're relying on checking manually. Let's automate that."

Confirm they have a project from previous lessons, ideally already on GitHub (from Exercise 18e). If not on GitHub yet, help them get it set up.

**STOP. Wait for their response.**

---

### Step 1: Add a Spell-Checker for Code (Linter)

> "A linter is like spell-check, but for your project. It catches formatting issues, common mistakes, and inconsistencies before they become problems."

Look at the student's project to determine the right linter (ESLint for JavaScript/TypeScript, Ruff or Flake8 for Python, etc.).

> "Based on your project, I'll set up [linter name]. It'll check your code every time you save. Let me do that now."

Install and configure the linter. Run it against the student's project.

If the linter finds issues (it usually will):

> "Look at that. It found [N] issues already. Here's a sample:"

Show 2-3 specific issues in plain language:

```
┌────────────────────────────────────────────────────────┐
│  LINTER RESULTS                                        │
├──────────┬──────────────────────┬──────────────────────┤
│ File     │ Issue                │ Plain English        │
├──────────┼──────────────────────┼──────────────────────┤
│ index.js │ Unused variable      │ You created something│
│          │                      │ but never used it    │
├──────────┼──────────────────────┼──────────────────────┤
│ app.js   │ Missing semicolon    │ Typo, like a missing │
│          │                      │ period in a sentence │
├──────────┼──────────────────────┼──────────────────────┤
│ utils.js │ 'console.log' found  │ Debug note left in,  │
│          │                      │ like leaving a sticky│
│          │                      │ note in a final draft│
└──────────┴──────────────────────┴──────────────────────┘
```

> "Want me to auto-fix what I can?"

**STOP. Wait for their response.**

Fix the auto-fixable issues. Show the before/after count.

> "Down from [N] issues to [M]. The remaining ones need a human decision. That's normal."

**STOP. Wait for their response.**

---

### Step 2: Add Tests (The Vending Machine Rule)

> "Here's how to think about tests. Imagine a vending machine."
>
> **Good test:** Put money in, press a button, check that the right snack comes out. You tested the thing the machine is supposed to DO.
>
> **Bad test:** Walk up to the machine, confirm it's yellow, and leave. You tested what it looks like, not whether it works.

```
GOOD TESTS                          BAD TESTS
✓ Call a function, check the        ✗ Check that a variable exists
  result matches what you expect
✓ Submit a form, verify the         ✗ Assert that CSS classes haven't
  success message appears             changed
✓ Break something on purpose,       ✗ Mock everything so the test
  confirm the error message is        can't actually fail
  correct
```

> "I'm going to write tests for the most important parts of your project. Each one follows the vending machine rule: do the thing, check the result."

Ask:

> "What's the most important thing your project does? The thing that absolutely can't break."
>
> **A)** A specific feature or page they name
> **B)** I'm not sure. You pick.
> **C)** I want to understand what good tests look like first

**STOP. Wait for their response.**

---

### Step 3: Write and Run the Tests

Based on their answer, write 3-5 tests for the most important functionality. For each test, explain in plain language:

> "Here are the tests I wrote:"

```
TEST 1: [Plain description]
  Do:     [what the test does]
  Expect: [what should happen]

TEST 2: [Plain description]
  Do:     [what the test does]
  Expect: [what should happen]

TEST 3: [Plain description]
  Do:     [what the test does]
  Expect: [what should happen]
```

Run the tests and show the results:

> "All [N] tests passed. ✓"

Now introduce a bug on purpose:

> "Watch this. I'm going to break something small on purpose."

Make a targeted change that breaks one of the tests. Run the tests again.

> "See? Test [N] failed. It told you exactly what broke: [plain description]. Without this test, you'd only find out when a user complained. With the test, you catch it in seconds."

Fix the bug so the tests pass again.

**STOP. Wait for their response.**

---

### Step 4: Set Up Code Review

> "Tests catch whether things work. Code review catches whether things make sense. It's easier to spot problems in someone else's work than your own. Same reason authors need editors."
>
> "For a solo project, an AI reviewer handles this. It reads every change you propose (every pull request) and gives feedback."

 Walk through the setup:
1. Install the Claude Code GitHub app or configure the review command
2. Show them how to trigger a review on a PR
3. Create a small test PR and run a review so they can see it in action

> "Let's see it work. I'll open a PR with a small change and trigger the review."

Create a small PR and run the review. Show the feedback it generates.

> "That's your AI code reviewer. Every time you open a proposal (PR), it reads through the changes and flags anything that looks off: bugs, inconsistencies, missing edge cases."

**STOP. Wait for their response.**

---

### Optional: Integration Tests with Stably.ai

> "The tests we wrote check individual pieces (unit tests). There's another layer: checking that the whole product works as a user would experience it (integration tests). Tools like Stably.ai can click through your actual app and verify that flows work end-to-end."
>
> "This is optional and more useful once your product is live. Want to explore it?"
>
> **A)** Yes, show me Stably.ai
> **B)** Not now. Let's move on.

**STOP. Wait for their response.**

If A: walk them through setting up a basic Stably.ai test. If B: continue to wrap up.

---

### Wrap Up

> "Here's what your project has now:"

```
BEFORE THIS EXERCISE          AFTER THIS EXERCISE
┌────────────────────┐        ┌────────────────────┐
│ Make a change      │        │ Make a change       │
│      ↓             │        │      ↓              │
│ Hope nothing broke │        │ Linter catches      │
│      ↓             │        │ formatting issues   │
│ Ship it            │        │      ↓              │
│      ↓             │        │ Tests verify        │
│ Find out from users│        │ nothing broke       │
│ if something broke │        │      ↓              │
└────────────────────┘        │ AI reviewer flags   │
                              │ anything suspicious │
                              │      ↓              │
                              │ Ship with confidence│
                              └────────────────────┘
```

> "Three layers of protection: linter, tests, and code review. Each one catches problems the others miss."

**What would you like to do next?**
- **A)** Move on to the next exercise: set up the full automated pipeline (CI/CD)
- **B)** Write more tests for other parts of my project
- **C)** Tweak the linter rules or code review settings

**Share prompt:** "Explain the difference between a good test and a bad test using the vending machine analogy."

---

## Reference Material

**For Claude's use during this exercise:**

- **Linter setup by language:**
  - JavaScript/TypeScript: ESLint (`npm init @eslint/config`)
  - Python: Ruff (`pip install ruff`) or Flake8
  - HTML/CSS: HTMLHint, Stylelint
  - Choose the simplest config. Don't over-configure.

- **Test framework by language:**
  - JavaScript: Vitest or Jest
  - Python: pytest
  - Write tests that follow the vending machine rule: call a function, check the output. No tests that just assert a file exists or a variable has a type.

- **Good test patterns:**
  - Test the most important user-facing behavior first
  - Test edge cases: empty inputs, missing data, unexpected values
  - Each test should fail for a real reason, not because implementation details changed

- **Bad test patterns to avoid:**
  - Testing that CSS classes exist
  - Mocking so much that the test can't actually fail
  - Testing implementation details instead of outcomes
  - "Snapshot tests" that just assert nothing changed (for a PM audience, these create noise)

- **Code review setup:**
  - Claude Code: `claude review --pr <number>` or set up as GitHub Action

- **Stably.ai**: Integration/QA testing tool. Creates browser-based tests that click through the app. Useful for end-to-end flows (signup, purchase, etc.). Optional for this exercise.
