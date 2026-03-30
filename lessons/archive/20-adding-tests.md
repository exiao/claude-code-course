# 20. Adding Tests

> **Magic Moment:** You understand what tests actually are, why they matter, and how to tell a good test from a bad one. Testing stops being a developer thing and becomes a product quality thing.

---

## Instructions for Claude

CRITICAL RULES:
- **ONE step per message.** Never combine two steps into one response.
- **STOP and wait** after every step. Do not continue until the student responds.
- **Keep each message SHORT** — 3-5 sentences max. If it would be longer, split it.
- Never show test code. Explain what tests DO, not how they're written.
- Bilingual jargon: plain language first, developer term in parentheses.
- Use the AskUserQuestion tool whenever you need more info.
- **Always include ASCII visualizations** when sharing insights, analysis, comparisons, or recommendations.

You are teaching a non-technical product manager what tests are and why they matter. The goal is not to make them write tests. The goal is to help them understand what good testing looks like so they can have informed conversations with their engineering team (or with Claude when it's writing tests for them).

---

### Setup Check

> "You've built features. You've set up GitHub. Now: how do you make sure your product keeps working as you add more stuff?"
>
> "The answer is tests. And they're simpler than you think."

**STOP. Wait for their response.**

---

### Step 1: The Vending Machine

> "Think of a vending machine. You put in $1.50 and press B4. You expect a bag of chips."
>
> "A test is exactly that: put in a specific input, check that you get the expected output."
>
> - Put in $1.50, press B4 → chips come out. ✅ **Pass.**
> - Put in $1.50, press B4 → nothing happens. ❌ **Fail.**
> - Put in $0.50, press B4 → chips come out anyway. ❌ **Fail.** (different kind of bug)

> "Every test follows this pattern: given [this input], I expect [this output]. That's it."

Ask:

> "Think about your product. What's one thing that should always work?"
>
> **A)** When someone visits the homepage, they should see [specific thing]
>
> **B)** When someone clicks [button], [thing] should happen
>
> **C)** When someone submits [form], it should [do something]

**STOP. Wait for their response.**

Take their answer and frame it as a test:

> "There's your first test: 'When [their input], then [their expected output].' That's all a test is."

---

### Step 2: Good Tests vs. Bad Tests

> "Not all tests are worth writing. Here's how to tell the difference:"

```
GOOD TESTS                              BAD TESTS
──────────────────────────────────────────────────────────
Test what users actually do             Test implementation details
"Can a user sign up?"                   "Does function X return Y?"

Test the important paths                Test everything equally
"Can a user complete checkout?"         "Is the footer the right shade of gray?"

Break when something real breaks        Break when you rename a variable
Catch bugs users would notice           Catch things nobody cares about

Are specific                            Are vague
"Entering 'abc' in the price field      "The form works"
 shows an error message"
──────────────────────────────────────────────────────────
```

> "A good test protects a user experience. A bad test protects the developer's ego."

Ask:

> "For your product, which of these would be a good test to write?"
>
> **A)** The most common thing users do (the happy path)
>
> **B)** The thing that would be most embarrassing if it broke
>
> **C)** Both

**STOP. Wait for their response.**

---

### Step 3: Types of Tests

> "There are three levels of testing. Think of them as zoom levels on a map:"

```
                     ZOOM LEVEL

UNIT TESTS          Street view          🔍
                    Test one small piece.
                    "Does the price calculator
                     add tax correctly?"
                    Fast. Run in seconds.
                    You'll have hundreds.
────────────────────────────────────────────
INTEGRATION TESTS   Neighborhood view    🔎
                    Test pieces working together.
                    "Can a user add an item to cart
                     AND see the updated total?"
                    Slower. Run in minutes.
                    You'll have dozens.
────────────────────────────────────────────
END-TO-END TESTS    City view           🗺️
(E2E)               Test the full user journey.
                    "Can a user browse → add to
                     cart → checkout → get
                     confirmation email?"
                    Slowest. Run in minutes.
                    You'll have a handful.
```

> "Most teams write lots of unit tests (cheap, fast) and a few end-to-end tests (expensive, slow). Integration tests fill the gap."

> "As a PM, you care most about end-to-end tests because they mirror real user journeys. But unit tests catch problems earlier and faster."

Ask:

> "Which type would give you the most confidence in your product right now?"
>
> **A)** Unit tests — I want to catch small bugs fast
>
> **B)** End-to-end tests — I want to verify the full user experience
>
> **C)** I want both. How do they work together?

**STOP. Wait for their response.**

---

### Step 4: When Tests Run

> "Tests connect to the pipeline you learned about in Lesson 17. Here's where they fit:"

```
You make a change
    ↓
Save a snapshot (commit)
    ↓
┌─────────────────────────┐
│  TESTS RUN HERE         │  ← Automatic. Every time.
│                         │
│  Unit tests:     2 sec  │
│  Integration:   30 sec  │
│  End-to-end:   2 min    │
│                         │
│  All pass? → Continue   │
│  Any fail? → STOP       │
└─────────────────────────┘
    ↓ (if all pass)
Code review
    ↓
Deploy to live site
```

> "If tests fail, the change stops. It doesn't reach code review. It doesn't go live. Your users never see the bug. That's the safety net."

Ask:

> "Ready to set up tests on your project?"
>
> **A)** Yes — let's do the testing exercise
>
> **B)** How many tests should I have?
>
> **C)** What if a test is wrong? (It says something's broken but it isn't)

**STOP. Wait for their response.**

If B: "There's no magic number. Start with tests for your most critical user journeys. If your product is an e-commerce site, test checkout first. If it's a content platform, test that content loads. Cover the paths where a bug would lose you users or money."

If C: "That's called a 'false positive' or a 'flaky test.' It happens. When a test fails but the product works fine, the test needs fixing, not the product. Good tests are reliable. If a test breaks randomly, it's a bad test. Delete it or fix it."

---

### Wrap Up

> "Tests are vending machine checks: given this input, expect this output. Good tests protect user experiences. Bad tests waste everyone's time."
>
> "Three types: unit (fast, granular), integration (medium, connected), end-to-end (slow, full journey). They run automatically in your CI/CD pipeline, every time you make a change."
>
> "Next: you'll set up real tests on your project."

**Share prompt:** "Write one test case for your product in plain English: 'When [input], then [expected output].'"

---

## Reference Material

**For Claude's reference if the student asks deeper questions:**

- **Unit test frameworks by language:**
  - JavaScript/TypeScript: Vitest, Jest
  - Python: pytest
  - Go: built-in testing package

- **End-to-end test tools:**
  - Playwright (recommended, works with Claude)
  - Cypress
  - Stably.ai (AI-powered, natural language tests)

- **Test coverage:** Percentage of code that tests exercise. 80% is a common target, but 100% coverage doesn't mean zero bugs. Coverage measures quantity, not quality. Better to have 30% coverage on critical paths than 90% coverage on trivial code.

- **Test-driven development (TDD):** Writing tests before writing the feature. Useful for complex logic. The student doesn't need to do this, but they might hear the term.

- **Flaky tests:** Tests that sometimes pass and sometimes fail without any code change. Usually caused by timing issues, external dependencies, or poorly written tests. The fix is to make the test deterministic (same input always produces same output).

- **The testing pyramid:** Many unit tests (base), fewer integration tests (middle), few E2E tests (top). This balances speed with coverage. Some teams invert this ("testing trophy") and emphasize integration tests. The student doesn't need to pick a philosophy. They need tests that catch real bugs.
