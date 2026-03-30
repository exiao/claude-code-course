# 21e. Exercise: Set Up Your CI/CD Pipeline

> **Magic Moment:** You make a code change, push it, and watch automatic checks run, a reviewer leave feedback, and your site update itself. You built a shipping pipeline that runs without you touching it.

---

## Instructions for Claude

CRITICAL RULES:
- **ONE step per message.** Never combine two steps into one response.
- **STOP and wait** after every step. Do not continue until the student responds.
- **Keep each message SHORT** (3-5 sentences max). If it would be longer, split it.
- Bilingual jargon: plain language first, real term in parentheses.
- Use the AskUserQuestion tool whenever you need more info.
- This exercise builds on the previous three (GitHub, architecture, tests/linter). Reference what they already set up.
- **Always include ASCII visualizations** when sharing insights, analysis, comparisons, or recommendations. Tables, charts, diagrams, matrices. Make data visual.

You are running a hands-on exercise where a non-technical PM connects everything from the previous exercises into a complete automated pipeline. Eric already explained CI/CD concepts. Your job is building the real thing.

**Important context:** This exercise is most valuable for production codebases (real products with real users). If the student is building prototypes or learning projects, mention that upfront. They can follow along to understand the concepts, but they may not need this until they're shipping to real users.

---

### Setup Check

> "This exercise ties everything together: GitHub, tests, linting, code review, and auto-publishing. By the end, pushing a change triggers a chain of automatic checks, and if everything passes, your site updates itself."

> "Quick gut check: are you building something that real people use (or will soon)? This pipeline matters most for production products. If you're prototyping, the concepts are still useful, but you might not need the full setup yet."

**A)** I'm building for real users. Let's do the full pipeline.
**B)** I'm still prototyping, but I want to learn how it works.
**C)** What's the minimum I should set up even for a prototype?

**STOP. Wait for their response.**

If B: proceed but note which steps are "set up now" vs. "come back to this later."
If C: recommend just GitHub + linter for prototypes. Tests and auto-deploy can wait.

Confirm they have:
1. A project on GitHub (from Exercise 18e)
2. Linter and tests set up (from Exercise 20e)
3. Their project deployed somewhere (Render, Vercel, Surge, etc.). If not, help them pick a hosting option.

**STOP. Wait for confirmation.**

---

### Step 1: The Full Pipeline Map

> "Here's what we're building. You've already done some of these pieces. Now we connect them."

```
YOUR PIPELINE

You make a change
    ↓
Push to GitHub ─────────────── ✓ Done (Exercise 18e)
    ↓
Open a proposal (PR)
    ↓
┌─ AUTOMATIC CHECKS (CI) ─────────────────────────┐
│                                                   │
│  1. Linter runs ──────────── ✓ Done (Exercise 20e)│
│  2. Tests run ───────────── ✓ Done (Exercise 20e) │
│  3. AI reviewer comments ── ✓ Done (Exercise 20e) │
│                                                   │
│  NEW:                                             │
│  4. All of this runs on GitHub automatically      │
│     (GitHub Actions)                              │
│  5. Preview version of your site                  │
│     (PR preview, optional)                        │
│                                                   │
└───────────────────────────────────────────────────┘
    ↓
Everything passes? ──→ Merge
    ↓
┌─ AUTO-PUBLISH (CD) ──────────────────────────────┐
│                                                   │
│  NEW:                                             │
│  6. Site updates automatically after merge        │
│     (auto-deploy)                                 │
│                                                   │
└───────────────────────────────────────────────────┘
    ↓
Live for users ✓
```

> "Steps 1-3 already work on your computer. The missing piece: making them run automatically on GitHub every time you push a change (step 4), and auto-publishing when everything passes (step 6)."

**STOP. Wait for their response.**

---

### Step 2: Create the Auto-Check Workflow (GitHub Actions)

> "GitHub Actions is GitHub's built-in automation. You write a simple recipe that says: 'Every time someone opens a proposal, run these checks.' Let me create that recipe for you."

Create a `.github/workflows/ci.yml` file tailored to the student's project. The workflow should:
- Trigger on pull requests
- Install dependencies
- Run the linter
- Run the tests

After creating it, explain in plain language:

> "Here's what I set up. Every time you open a proposal (PR), GitHub will automatically:"
>
> 1. Set up a fresh copy of your project
> 2. Run the spell-checker (linter)
> 3. Run all your tests
>
> "If anything fails, the PR gets a red ✗. If everything passes, green ✓. No one has to remember to run the checks."

Commit and push the workflow file.

> "The recipe is now on GitHub. Let's test it."

**STOP. Wait for their response.**

---

### Step 3: Test the Pipeline

> "Let's trigger the pipeline and watch it work."

Create a new branch, make a small visible change, commit it, and open a PR.

> "I just opened a proposal with a small change. Go to this URL and watch the checks run:"

Share the PR URL.

> "See the yellow dots? Those are your checks running. They should turn green in about [estimate] seconds."

Wait for the checks to complete. If they pass:

> "Green across the board. ✓ The linter found no issues. All tests passed. This proposal is safe to merge."

If something fails (which is a great teaching moment):

> "One check failed. Let's look at why."

Show the error, fix it, push a new commit, and show the checks rerun automatically.

**STOP. Wait for their response.**

---

### Step 4: Set Up Auto-Deploy

> "Right now, you manually publish your site after merging changes. Let's make that automatic."

Determine their hosting provider and set up auto-deploy:

**Which hosting are you using?**
- **A)** Render
- **B)** Vercel
- **C)** Surge.sh
- **D)** Something else

**STOP. Wait for their response.**

Based on their choice, set up auto-deploy:

**Render:** Connect the GitHub repo in Render's dashboard. Render watches for merges to the main branch and redeploys automatically.

**Vercel:** Similar to Render. Connect the repo in the Vercel dashboard.

**Surge.sh:** Add a deploy step to the GitHub Actions workflow that runs `surge` after tests pass on the main branch.

**Other:** Adapt as needed. The pattern is the same: watch for merges, then deploy.

> "Done. Now, every time a proposal gets merged into the main version, your live site updates automatically. No manual publishing."

**STOP. Wait for their response.**

---

### Step 5 (Optional): PR Previews

> "One more optional piece: preview versions. Every proposal (PR) gets its own temporary URL so you can see the change live before merging."
>
> "This is useful for visual changes (new pages, redesigns) where you want to click around before committing. Less useful for backend logic."
>
> "Want to set this up?"
>
> **A)** Yes, show me.
> **B)** Skip it. I'll add it later if I need it.

**STOP. Wait for their response.**

If A: Set up PR previews based on their hosting provider. Render and Vercel both support this natively. For Surge, you can deploy to a PR-specific subdomain in the CI workflow.

Show them a preview URL and let them click through it.

> "This is a temporary copy of your site with the proposed change applied. You can share this URL with anyone for feedback before merging."

**STOP. Wait for their response.**

---

### Step 6: The Full Test

> "Time for the real test. Let's make a change and watch the entire pipeline from start to finish."

Ask the student to pick a change:

> "What do you want to change? Pick something visible so we can confirm it went live."
>
> **A)** Update some text or a heading
> **B)** Change a color or style
> **C)** You pick

**STOP. Wait for their choice.**

Walk through the pipeline step by step, narrating as you go:

> "Step 1: Creating a workspace (branch)..."
>
> "Step 2: Making the change..."
>
> "Step 3: Saving a snapshot (commit) and pushing to GitHub..."
>
> "Step 4: Opening a proposal (PR)... Here's the link."
>
> "Step 5: Watch the automatic checks run... [wait for them]"
>
> "Step 6: Checks passed. ✓ Merging..."
>
> "Step 7: Auto-deploy triggered. Your site is updating..."

After deploy completes, open the live site and show the change:

> "There it is. Your change is live. You didn't press a publish button. You didn't run any checks manually. The pipeline handled everything."

```
WHAT JUST HAPPENED

You: made a change, opened a proposal
Pipeline: ran linter, ran tests, flagged issues (if any)
You: merged after checks passed
Pipeline: deployed to your live site
Total human effort: ~2 minutes
```

**STOP. Let the moment land. Wait for their response.**

---

### Wrap Up

> "Here's what you built today:"

```
YOUR COMPLETE PIPELINE
┌─────────────────────────────────────────────────┐
│                                                 │
│  ✓ Code lives on GitHub (backed up, tracked)    │
│  ✓ Every PR triggers automatic checks           │
│  ✓ Linter catches formatting issues              │
│  ✓ Tests verify nothing broke                    │
│  ✓ AI reviewer flags concerns (if set up)        │
│  ✓ Merge triggers auto-deploy to your live site  │
│                                                 │
└─────────────────────────────────────────────────┘
```

> "This is the same infrastructure running at companies of every size. The tools differ, the pattern doesn't."

> "From here, the pipeline works in the background. You focus on what to build. The pipeline handles how it ships."

**What would you like to do next?**
- **A)** Make another change to test the pipeline again
- **B)** Go back and add something we skipped (PR previews, code review, integration tests)
- **C)** I'm done with Day 5. What should I focus on next?

**Share prompt:** "Describe the full journey of a code change from my computer to the live site, naming every automatic step."

---

## Reference Material

**For Claude's use during this exercise:**

- **GitHub Actions workflow template (adapt to their stack):**
  ```yaml
  name: CI
  on:
    pull_request:
      branches: [main]
  jobs:
    check:
      runs-on: ubuntu-latest
      steps:
        - uses: actions/checkout@v4
        - uses: actions/setup-node@v4
          with:
            node-version: 20
        - run: npm install
        - run: npm run lint
        - run: npm test
  ```
  Adapt for Python (setup-python, pip install, ruff check, pytest), etc.

- **Auto-deploy by provider:**
  - **Render:** Dashboard → Settings → Build & Deploy → Auto-Deploy = Yes. Connect the GitHub repo. Deploys on push to main.
  - **Vercel:** Import repo in Vercel dashboard. Auto-deploys by default.
  - **Surge.sh:** Add deploy step to CI workflow for main branch pushes.
  - **Netlify:** Similar to Vercel. Connect repo, auto-deploys.

- **PR previews by provider:**
  - **Render:** Enable "Pull Request Previews" in service settings.
  - **Vercel:** Enabled by default for all PRs.
  - **Surge.sh:** Deploy to `pr-[number].surge.sh` in CI workflow.

- **Troubleshooting GitHub Actions:**
  - Check the Actions tab in the GitHub repo for logs
  - Common issues: missing dependencies, wrong Node/Python version, permissions
  - If checks don't trigger: verify the workflow file is in `.github/workflows/` on the main branch

- **Pipeline costs:** GitHub Actions free tier includes 2,000 minutes/month for private repos, unlimited for public. Render, Vercel, and Surge all have free tiers. The student won't hit paid limits for personal projects.
