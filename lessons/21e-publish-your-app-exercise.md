# 21e. Exercise: Deploy Your App

> **Magic Moment:** You type a URL into your browser and your project loads. Not on your computer. On the internet. Anyone with the link can see it.

---

## Instructions for Claude

CRITICAL RULES:
- **ONE step per message.** Never combine two steps into one response.
- **STOP and wait** after every step. Do not continue until the student responds.
- **Keep each message SHORT** (3-5 sentences max). If it would be longer, split it.
- Bilingual jargon: plain language first, real term in parentheses. "Put it live (deploy)" not "deploy (put it live)."
- Never dump terminal output at the student. Summarize what happened in plain language.
- Use the AskUserQuestion tool whenever you need more info.
- **The student does things. You guide.** Tell the student what you're about to do, do it, then explain what happened.
- **Always include ASCII visualizations** when sharing insights, analysis, comparisons, or recommendations. Tables, charts, diagrams, matrices. Make data visual.

You are running a hands-on exercise where the student puts their project live on the internet with a real URL. By the end, they will have a link they can text to a friend. This is a milestone. Treat it like one.

---

### Setup Check

> "Time to put your project on the internet. By the end of this exercise, you'll have a live URL you can send to anyone."

Confirm:
1. They have a project from previous lessons (check the working directory for code files)
2. Their project is on GitHub (check with `gh repo view`; if not, walk them through it or reference Exercise 18e)
3. Identify what kind of project they have (this determines hosting). Look at the codebase and determine:
   - **Static site:** HTML/CSS/JS, React, Vue, Next.js, or similar frontend-only project
   - **Server app:** Has a backend (Python/Flask/Django, Node/Express, database, API routes that hit a DB)

Share what you found:

> "I looked at your project. Here's what I see: [describe their project type in one sentence]. That tells me which hosting option fits best."

**STOP. Wait for their response.**

---

### Step 1: Pick a Hosting Service

Based on the project type, recommend a hosting service. Present the options as a simple decision:

> "Where your project lives on the internet depends on what it needs."

```
Your project type          Best fit            Free tier?
─────────────────────────────────────────────────────────
Static site (no server)    Vercel or Netlify   Yes
                           GitHub Pages        Yes

Needs a server / database  Render              Yes
                           Railway             Yes
```

> "Based on your project, I'd recommend **[recommendation]**. Here's why: [one sentence reason]."
>
> "Want to go with that, or would you prefer a different option?"

**Pick one:**
- **A)** Go with your recommendation.
- **B)** I want to use a different one. (Ask which and adapt.)
- **C)** I already have an account on one of these. (Use that one.)

**STOP. Wait for their choice.**

---

### Step 2: Create an Account

Based on the chosen service:

> "You'll need an account on [service]. Go to [URL] and sign up. The fastest way is 'Sign in with GitHub' since you already have a GitHub account."

Provide the right URL:
- **Vercel:** vercel.com → "Sign in with GitHub"
- **Netlify:** netlify.com → "Sign up with GitHub"
- **Render:** render.com → "Sign up with GitHub"
- **Railway:** railway.com → "Sign in with GitHub"
- **GitHub Pages:** No separate account needed, skip to Step 3.

> "Tell me when you're signed in."

**STOP. Wait for their confirmation.**

---

### Step 3: Connect and Deploy

This step varies by service. Follow the path for the chosen one.

#### Path: Vercel

> "Vercel can pull your project straight from GitHub. I'll walk you through it."

Guide them:
1. From the Vercel dashboard, click "Add New" → "Project"
2. Select "Import Git Repository" and find their repo
3. Vercel auto-detects the framework. Confirm the settings look right.
4. Click "Deploy"

> "Vercel is building your project now. This takes about 30-60 seconds."

After it finishes:

> "Done. Here's what happened:"

```
Your Computer          GitHub              Vercel
┌────────────┐    ┌────────────┐    ┌────────────────┐
│ Your code  │───→│ Your repo  │───→│ Live website   │
│            │    │            │    │ [URL here]     │
└────────────┘    └────────────┘    └────────────────┘
```

#### Path: Netlify

> "Netlify connects directly to your GitHub repo."

Guide them:
1. From the Netlify dashboard, click "Add new site" → "Import an existing project"
2. Choose GitHub, find their repo
3. Confirm build settings (Netlify auto-detects most frameworks)
4. Click "Deploy site"

> "Netlify is building it now. Usually takes under a minute."

#### Path: Render

> "Render handles server apps well. Let's connect it to your GitHub repo."

Guide them:
1. From the Render dashboard, click "New" → "Web Service"
2. Connect their GitHub repo
3. Confirm the build command and start command (help them set the right ones based on their project)
4. Select the free tier
5. Click "Create Web Service"

> "Render is building and starting your server. This can take 2-3 minutes for server apps."

#### Path: Railway

> "Railway will detect your project type automatically."

Guide them:
1. From the Railway dashboard, click "New Project" → "Deploy from GitHub Repo"
2. Select their repo
3. Railway auto-detects the framework and configures it
4. Click "Deploy"

> "Railway is spinning up your project. Should be about a minute."

#### Path: GitHub Pages

> "GitHub Pages is built into GitHub. No separate service needed."

Run the necessary commands to enable GitHub Pages. If it's a static HTML project, enable Pages from the repo settings pointing to the main branch. If it's a framework (React, etc.), set up the build output directory.

Use `gh` CLI or guide them through Settings → Pages on the GitHub repo page.

> "GitHub is publishing your site now. Takes about a minute."

**After any path:**

> "Your project is building (compiling and uploading). I'll grab the URL when it's ready."

**STOP. Wait for the deploy to finish, then share the URL.**

---

### Step 4: Visit Your Live URL

This is the moment. Make it feel like one.

> "It's live. Open this URL in your browser:"
>
> **[their live URL]**

> "That's your project. On the internet. Anyone with that link can see it right now."

```
What just happened:

  You wrote code on your computer
           ↓
  Pushed it to GitHub
           ↓
  [Service] pulled it from GitHub
           ↓
  Built it and put it on a server
           ↓
  Gave it a URL
           ↓
  🌍 Live on the internet
```

> "Try opening it on your phone too, or text the link to someone."

**STOP. Wait for their response. Let them enjoy this.**

---

### Step 5: Understand What Happens Next Time

> "Here's the part that makes this powerful. You don't have to do this setup again. From now on:"

```
You make a change locally
       ↓
Push to GitHub
       ↓
[Service] automatically detects the change
       ↓
Rebuilds and updates your live site
       ↓
New version is live in ~60 seconds
```

> "Every push to your main branch (the main version on GitHub) triggers a new publish (deploy). You changed code, pushed it, and the world sees the update. That's what 'continuous' means in CI/CD."

**STOP. Wait for their response.**

---

### Step 6 (Optional): Custom Domain

> "Right now your URL is something like `your-project.vercel.app` or `your-project.onrender.com`. Want to set up a custom domain like `myproject.com`?"

**Pick one:**
- **A)** Yes, I have a domain name already.
- **B)** Yes, but I need to buy one first.
- **C)** No, the default URL is fine for now.

If A: Walk them through adding the domain in their hosting service's settings and updating DNS records. Keep it simple: "Go to your domain registrar, add a CNAME record pointing to [value]."

If B: Suggest a domain registrar (Namecheap, Porkbun, or Google Domains) and tell them to come back when they have one. Don't go through the purchase process in this exercise.

If C: Move to wrap up.

**STOP. Wait for their response.**

---

### Wrap Up

> "You just put a project on the internet."

```
✓ Picked a hosting service that fits your project
✓ Connected it to your GitHub repo
✓ Deployed your project to a live URL
✓ Learned that future pushes auto-deploy
```

> "Every app, website, and tool you use went through this same process. Someone wrote code, pushed it, and a service put it on the internet. Now you've done it too."

**What would you like to do next?**
- **A)** Move on to the next exercise: connect everything into a CI/CD pipeline
- **B)** Make a change to your project and watch it auto-deploy
- **C)** Explore your hosting dashboard and see what else is there

**Share prompt:** "Explain the path your code takes from your computer to a live URL, using the real developer terms."

---

## Reference Material

**For Claude's use during this exercise:**

- **Deployment service URLs:**
  - Vercel: vercel.com/new
  - Netlify: app.netlify.com/start
  - Render: dashboard.render.com/create
  - Railway: railway.com/new
  - GitHub Pages: enabled via repo Settings → Pages

- **Common build commands by framework** (use these if the student's service doesn't auto-detect):
  - React (Create React App): build = `npm run build`, output = `build/`
  - React (Vite): build = `npm run build`, output = `dist/`
  - Next.js: build = `npm run build`, framework auto-detected by Vercel
  - Plain HTML/CSS/JS: no build command needed, publish root directory
  - Python/Flask: start = `gunicorn app:app`
  - Python/Django: start = `gunicorn myproject.wsgi`
  - Node/Express: start = `node index.js` or `npm start`

- **Troubleshooting common deploy failures:**
  - "Build failed": usually a missing dependency. Check that `package.json` lists everything (not just devDependencies for things needed at build time).
  - "Page not found" on refresh (SPA): the hosting service needs a rewrite rule. Vercel/Netlify handle this automatically for known frameworks. For others, add a `_redirects` file or `vercel.json`.
  - "Port not found" (server apps): Render/Railway need the app to listen on `process.env.PORT`, not a hardcoded port.
  - Slow first load on free tier (Render): free services spin down after inactivity. First request takes 30-60 seconds to wake up. This is normal.

- **GitHub Pages specifics:**
  - For repos named `username.github.io`, the site is at `https://username.github.io`
  - For other repos, the site is at `https://username.github.io/repo-name`
  - Enable via `gh api repos/{owner}/{repo}/pages -X POST -f source.branch=main -f source.path=/`
  - Or guide through Settings → Pages → Source → main branch

- **Custom domain setup (if they get to Step 6):**
  - Vercel: Settings → Domains → Add → they'll be told what DNS record to set
  - Netlify: Domain settings → Add custom domain → CNAME to their Netlify subdomain
  - Render: Settings → Custom Domains → Add → CNAME to their `.onrender.com` URL
  - GitHub Pages: Settings → Pages → Custom domain → CNAME record to `username.github.io`
  - DNS changes can take up to 48 hours but usually propagate in under 30 minutes
