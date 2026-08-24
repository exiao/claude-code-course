# 24e. Exercise: Ship It (GitHub + CI/CD in One Loop)

> **Magic Moment:** About ten minutes in, one command gives you a pull request, an AI code review with an architecture diagram of your own project, and a live preview URL. All on a change you made two minutes ago.

---

## Instructions for Claude

CRITICAL RULES:
- **ONE step per message.** Never combine two steps into one response.
- **STOP and wait** after every step. Do not continue until the student responds.
- **Keep each message SHORT** (3-5 sentences max). If it would be longer, split it.
- Bilingual jargon: plain language first, real term in parentheses.
- Use the AskUserQuestion tool whenever you need more info.
- **Always include ASCII visualizations** when sharing pipeline state, comparisons, or diagrams.
- **Do not let the student get stuck on accounts.** The only account this exercise requires is GitHub. Surge needs an email and a password typed once. Render is optional and comes at the end.
- **Step 3 is the point of the whole exercise.** Everything before it is setup with nothing to look at. Get there fast, then slow down.

You are running a hands-on exercise where a non-technical PM goes from a folder on their laptop to a reviewed, previewed pull request, and then adds automatic checks to it. This single exercise replaces four older ones. The older files are still in this repo as deep-dive references and you should point at them when a student wants more.

**Order matters.** Older versions of this course set up tests, linters, code review, and hosting first, and only opened a pull request at the very end. That put the payoff forty-five minutes in. Here the pull request comes third, and tests get added to a pull request the student can already see.

---

### Setup Check

> "By the end of this you'll have a pull request with an AI review on it, a diagram of your own project, and a live URL you can send someone. The first three are about ten minutes away."

Confirm they have:
1. A project folder from an earlier lesson (any folder with files in it works; a single `index.html` is fine)
2. A GitHub account
3. The GitHub command-line tool. Run `gh --version`. If missing, install it and run `gh auth login`.

Then check Surge, the static host used for previews:

```bash
npm install -g surge
surge whoami
```

If `surge whoami` says they are not logged in, run `surge login` and let them type an email and password. It creates the account on the spot. No credit card, no dashboard, no configuration.

**STOP. Wait for confirmation that `gh --version` and `surge whoami` both work.**

---

### Step 1: Put the Project on GitHub

> "Right now your project lives on your laptop. If the laptop dies, so does the work. Let's fix that first."

Run these with them, explaining each line in plain language:

```bash
git init
git add -A
git commit -m "first commit"
gh repo create <project-name> --private --source=. --push
```

Plain-language version: `init` starts tracking changes, `add` picks what to include, `commit` saves a snapshot with a note, `repo create` makes the online copy and uploads it.

**STOP. Have them open the repo in a browser and confirm they see their files.**

---

### Step 2: Make One Small Change on a Branch

> "Never change the live version directly. Make a workspace copy (a branch), change it there, and propose it back."

```bash
git checkout -b my-first-change
```

Then have them make one visible change. Small is better: a headline, a color, a fixed typo. If their project has any code at all, a real one-line bug fix is ideal because the reviewer in the next step will have something to say.

```bash
git commit -am "describe what you changed"
git push -u origin my-first-change
```

**STOP. Wait for the push to finish.**

---

### Step 3: The Loop

This is the step the exercise exists for. Four results, one pass.

> "Now watch. One pull request, one review, one diagram, one live URL."

```bash
# 1. Open the proposal
gh pr create --fill

# 2. Publish a preview of this branch (pick any unused subdomain)
surge ./ <project-name>-pr-1.surge.sh

# 3. Have Claude review the change and map the project
git diff origin/main...HEAD > pr.diff
claude -p "Review this PR diff for bugs. Then draw a small ASCII architecture diagram of this project. Output markdown, under 15 lines.

$(cat pr.diff)" > review.md

# 4. Add the preview link and post it all as one comment
echo "

**Preview:** https://<project-name>-pr-1.surge.sh" >> review.md
gh pr comment 1 -F review.md
```

Then open the pull request in a browser.

```
WHAT YOU JUST BUILT

  your change
       ↓
  ┌──────────────────────────────────────┐
  │  Pull request #1                     │
  │                                      │
  │  ● review comment    ← Claude read   │
  │    with bugs found     your diff     │
  │                                      │
  │  ● architecture      ← your project, │
  │    diagram             not a stock   │
  │                        example       │
  │                                      │
  │  ● preview URL       ← live, share-  │
  │                        able, real    │
  └──────────────────────────────────────┘
```

> "That comment took about thirty seconds to generate. It is reading your actual diff and your actual file layout."

**STOP. Let them read the review. Ask what it caught.**

Notes for you:
- If the diff is large, cap it. Use `git diff --stat origin/main...HEAD` plus the first 200 lines of the diff instead of the whole thing.
- Surge only serves static files. If the project needs a server to run, the preview will show the raw front end only. Say so plainly and point at Step 7.
- Each Surge deploy needs its own subdomain. There is no automatic per-pull-request URL on the free tier, so the number in the subdomain is typed by hand.

---

### Step 4: Add a Spell-Checker and Tests

Now that a pull request exists to attach them to.

> "Your review comment is a person's opinion, generated fast. Tests are the part that never gets tired."

```
LINTER             Does it even turn on?

UNIT TESTS         Test one part
                   "Does the coin slot accept a quarter?"

INTEGRATION TESTS  Test parts working together
                   "Insert $1.50 → does credit show $1.50?"

END-TO-END TESTS   Test the whole journey
                   "Insert $1.50 → press B4 → chips come out"
```

Prompt to run:

```
Set up a linter and a test framework for this project. Write 3 meaningful unit
tests based on what this code actually does. Add a Makefile with `make lint` and
`make test`. Then update CLAUDE.md so you run both before opening any PR.
```

Have them run `make lint` and `make test` and watch them pass. Then commit and push to the same branch.

> "Every test follows one pattern: given this input, I expect this output. A good test checks what a person would actually do with the thing. A bad test checks that it is the right color."

For the design principles behind good tests, see `20e-tests-and-linter-exercise.md`.

**STOP. Wait for green tests locally.**

---

### Step 5: Make the Checks Run Themselves

> "Right now the tests only run when you remember. Let's make GitHub run them on every proposal, forever."

```
Create a GitHub Actions workflow file at .github/workflows/ci.yml that runs the
linter and all tests automatically on every pull request.
```

Commit, push, then refresh the pull request. A yellow dot appears, then a green check.

```
BEFORE                          AFTER

you remember to test            ┌─ push
you run make test               │
you hope you did                ├─ GitHub runs lint  ✓
                                ├─ GitHub runs tests ✓
                                │
                                └─ green check on the PR
```

> "Break it on purpose. Push something that fails a test and watch the check turn red."

Do that with them. A red check that they caused is worth more than a green one they were handed.

**STOP. Wait for both the red and the green.**

---

### Step 6: Merge and Watch It Go Live

```bash
gh pr merge --squash
```

If they set up auto-deploy in Step 7, the live site updates on its own. If they are on Surge only, redeploy the merged main branch to a stable subdomain:

```bash
git checkout main && git pull
surge ./ <project-name>.surge.sh
```

> "That is the full loop. Change, propose, review, preview, check, merge, live. You will run this same loop for every change from now on."

---

### Step 7: Real Hosting (optional, only if they have a backend)

Surge serves files. If the project has a server, a database, or an API, it needs a real host.

Point them at `22e-publish-your-app-exercise.md` for the full Render walkthrough: account, API key, the Render MCP server, a service connected to GitHub, and pull-request previews that generate their own URLs automatically.

> "Render gives you a preview URL per pull request with no typing. That is worth the twenty minutes of setup once you have real users. It is not worth it on day one."

---

### Step 8: A Permanent Reviewer (optional)

The review in Step 3 ran on their laptop. To make it happen automatically on every pull request, without anyone running a command:

- **Claude Code review:** run `/install-github-app` inside Claude Code and follow the screens. It adds a `CLAUDE_CODE_OAUTH_TOKEN` and the workflow files.
- **Codex:** turn on Code review at https://chatgpt.com/codex/settings/code-review, then comment `@codex review` on a pull request.
- **Cursor Bugbot:** https://cursor.com/bugbot, paid.

Full setup options and screenshots are in `21e-code-review-exercise.md`.

> "Local review is instant and free and works today. The GitHub App version is the one that catches things when you forget to ask."

---

### Wrap Up

```
YOUR PIPELINE

  branch → PR → [ lint ✓ ] → [ tests ✓ ] → [ review ] → preview URL → merge → live
```

**What do you want next?**
- **A)** Set up the permanent reviewer (Step 8)
- **B)** Move to real hosting with per-PR previews (Step 7)
- **C)** Map my architecture properly (`19e-architecture-exercise.md`)
- **D)** Move on to the next lesson

**Share prompt:** Bring back the review comment from your first pull request, including the diagram it drew of your project.

---

## Reference Material

**Why this order.** The four exercises this replaces set up hosting, tests, review, and CI first, and only reached a pull request at the end. Every one of those steps is invisible on its own: a linter with no pull request to run on, a hosting account with nothing deployed, a reviewer with nothing to review. Opening the pull request third means every later step has something visible to attach to.

**Why Surge before Render.** Surge needs one npm install and an email. Render needs a signup, an API key, an MCP server install, and a service configuration. Both end at a URL. Only one of them ends there in five minutes. Render is the right answer once the project has a backend, which is why it is Step 7 and not Step 1.

**Why `claude -p` before the GitHub App.** `claude -p` runs a one-shot prompt from the terminal using the authentication the student already has. No app install, no repository permissions, no token. It produces a real review of a real diff in under thirty seconds. The GitHub App is strictly better once it is set up, and it is a barrier before the payoff.

**The deep dives.** Nothing in the older exercises was thrown away. They cover the same ground more slowly, one topic at a time:

- `18e-github-exercise.md` — staging, commit history, and the full pull request lifecycle
- `19e-architecture-exercise.md` — reading your architecture and its tradeoffs
- `20e-tests-and-linter-exercise.md` — the four kinds of tests, coverage, and the vending machine rule
- `21e-code-review-exercise.md` — every code review option with screenshots
- `22e-publish-your-app-exercise.md` — Render, the MCP server, and automatic pull request previews
- `23e-cicd-pipeline-exercise.md` — the full pipeline built one piece at a time
