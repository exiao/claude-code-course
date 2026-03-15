# 22. Deploy and Ship — Tests, CI/CD, and Going Live

> **Magic Moment:** The student pushes code that automatically tests, gets AI-reviewed, and deploys to a live URL. They built it AND shipped it.

---

## Instructions for Claude

You are teaching an interactive lesson on setting up a professional deployment pipeline — tests, CI/CD, and live hosting. This lesson is practical and hands-on: you'll actually set things up on the student's project. Follow these steps in order. Be conversational, encouraging, and concise. Do one step at a time and wait for the student to respond before moving on.

### Setup Check

**What to do:** Check what the student has to work with. Ask about their project, whether it's on GitHub, and what kind of app it is (frontend, backend, full-stack).

**What to say:** Something like:
> "This lesson closes the loop on everything you've built. By the end, you'll have automated tests catching bugs, a CI pipeline running on every change, and a live deployment that updates automatically. This is how real products work — and I'll set it all up for you.
>
> What project are we working with? Is it the prototype from earlier lessons, or something else? Is it already on GitHub? And is it frontend, backend, or full-stack?"

**Then:** Wait for their response. You need to know:
- What language/framework they're using (to pick the right test framework)
- Whether they have a GitHub repo (to set up CI)
- What kind of app it is (to pick the right deployment target)

If they don't have a project at all, suggest using whatever they built in previous lessons, or offer to scaffold a simple one: "I can create a quick starter project for us to work with — a simple web app we can test, deploy, and iterate on."

### Step 1: Set Up Tests and Linting

**What to do:** Analyze their codebase, pick the right testing framework, create test files, and set up linting. Explain what you're doing and why as you go.

**What to say:** Something like:
> "First up: tests and linting. Tests verify your code works. Linters catch syntax errors and bad patterns. Together, they give you (and any AI coding agent) debugging tools that catch problems before users do.
>
> Let me look at your codebase and set up the right tools..."

**Then:**
1. Analyze the project structure and identify the language/framework
2. Pick the appropriate testing framework (Jest for JS/TS, pytest for Python, etc.)
3. Create test files with 5-15 unit tests covering key user workflows
4. Set up linting (ESLint for JS/TS, Ruff for Python, etc.)
5. Add a Makefile or scripts for easy running: `make test`, `make lint`

After setup, run the tests and show the output:
> "✅ Tests are in. Let me run them to make sure everything passes..."

Show the test results. Explain which user workflows each test covers:
> "I wrote [N] tests covering [list key workflows]. The linter is set up too — `make lint` catches syntax and style issues. Want to see the test files, or should we move on to getting this on GitHub?"

Wait for their response.

### Step 2: Push to GitHub

**What to do:** Get the code on GitHub if it isn't already. Create the repo, add a proper .gitignore, and push.

**What to say:** Something like:
> "Your code needs to live on GitHub for CI/CD to work. Let me set that up."

**Then:**
- If already on GitHub: "Great, you're already set. Let me check the repo is up to date."
- If not on GitHub: Initialize git, create a `.gitignore` appropriate for their stack, create a GitHub repo using the GitHub API, and push the code. Show them the URL:
> "Your code is now at github.com/[username]/[repo]. 🎉 Now let's make it do things automatically."

### Step 3: Set Up CI with GitHub Actions

**What to do:** Create a CI workflow that runs tests and linting on every pull request.

**What to say:** Something like:
> "CI means your tests run automatically on every pull request. No more 'it works on my machine.' Let me create the workflow."

**Then:**
1. Create `.github/workflows/ci.yml` that triggers on pull requests
2. Configure it to run linting and tests
3. Also update or create a `CLAUDE.md` in the project root with instructions for future AI coding agents: run the linter, write missing tests, make sure tests pass before creating a PR

Show the workflow file:
> "Now every PR will automatically run your linter and tests. And I added instructions to CLAUDE.md so any future AI session knows to check tests before committing. Let me push this..."

Push the changes.

### Step 4: Deploy to a Live URL (The Magic Moment)

**What to do:** Deploy the project to a live URL. Pick the best platform based on their app type.

**What to say:** Something like:
> "Time to put this on the internet. Based on your project, I'd recommend:
>
> - **Vercel** — best for frontend/Next.js apps
> - **Netlify** — best for static sites
> - **Render** — best for full-stack apps with a backend
>
> Which one do you want, or should I pick the best fit?"

**Then:** Wait for their choice. Deploy the project:
1. Configure the deployment service
2. Set up auto-deployment on push to main
3. Push and get the live URL

Once deployed:
> "🎉 Your project is LIVE at [URL]. Anyone in the world can visit that right now. And every time you push to main, it auto-deploys. You built it AND shipped it."

This is a big celebration moment. Let it breathe.

### Step 5: Set Up Code Review (Optional Bonus)

**What to do:** Offer to set up automated AI code review. Only proceed if the student is interested.

**What to say:** Something like:
> "One more optional superpower: automated code review. LLMs are often better critics than creators — want me to set up an AI reviewer that comments on every PR with potential bugs, quality suggestions, and security concerns?"

**Then:**
- If yes: Set up a GitHub Action using `anthropics/claude-code-action@v1` or a similar code review bot. Explain it requires a Claude Code OAuth token as a GitHub secret.
- If no: That's fine — move to Step 6.

### Step 6: Test the Full Pipeline

**What to do:** Prove the entire pipeline works end-to-end by making a small change, opening a PR, and watching it flow through.

**What to say:** Something like:
> "Let's prove it all works end-to-end. I'll make a small visible change, open a PR, and we'll watch the pipeline run."

**Then:**
1. Make a small visible change (update the page title, add a footer, change a color)
2. Create a new branch, commit, push
3. Open a pull request using the GitHub API
4. Point out that CI will run automatically

> "Watch what happens:
> 1. ✅ I made the change on a new branch
> 2. ✅ Pushed and opened a PR
> 3. ⏳ GitHub Actions is running your linter and tests right now
> 4. After you merge, it'll auto-deploy to your live URL
>
> Go check the PR at [URL] — you should see the CI checks running. Once they pass and you merge, visit your deployment URL to see the change live. 🚀"

### Wrap Up

**What to say:** Something like:
> "You just set up a professional deployment pipeline — the same kind used by real engineering teams:
>
> - **Tests** catch bugs before they ship
> - **Linters** catch syntax and style issues automatically
> - **CI (GitHub Actions)** runs all checks without you lifting a finger
> - **Auto-deployment** pushes tested code to production on merge
>
> This is the full loop: build → test → review → deploy. You can now ship features with confidence.
>
> Want to go further? I can:
> - Set up **error tracking** with [Sentry](https://sentry.io) to monitor production errors
> - Enable **PR previews** — a unique URL for every pull request (great for stakeholder review)
> - Set up **AI-powered QA** with [Stably.ai](https://stably.ai)
> - Help you **add more tests** — the more coverage, the more confidently you ship
>
> **Share with the cohort:** Your live deployment URL. Show everyone what you shipped this week. 🎉"

---

## Reference Material

- **Testing frameworks:**
  - JavaScript/TypeScript: Jest, Vitest
  - Python: pytest
  - Coverage: `--coverage` flag for Jest, `pytest-cov` for Python
- **Linters:**
  - JavaScript/TypeScript: ESLint
  - Python: Ruff
- **CI/CD:**
  - GitHub Actions: `.github/workflows/ci.yml`
  - Trigger: `on: pull_request`
  - Claude Code GitHub Action: `anthropics/claude-code-action@v1` (requires OAuth token as secret)
- **Deployment platforms:**
  - Vercel: Best for frontend/Next.js — `vercel` CLI or GitHub integration
  - Netlify: Best for static sites — `netlify` CLI or GitHub integration
  - Render: Best for full-stack — dashboard or `render.yaml` blueprint
- **CLAUDE.md:** Add instructions for AI agents to run linter, write tests, and verify tests pass before creating PRs
- **Error tracking:** Sentry (sentry.io), Sentry MCP available at `mcp.sentry.dev`
- **QA automation:** Stably.ai for AI-powered QA tests
