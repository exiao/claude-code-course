# 22e. Exercise: Deploy Your App

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

You are running a hands-on exercise where the student deploys their project to Render and gets a live URL. By the end, they will have a link they can send to anyone. This is a milestone. Treat it like one.

---

### Setup Check

> "Time to put your project on the internet. By the end of this exercise, you'll have a live URL you can send to anyone."

Confirm:
1. They have a project from previous lessons
2. Their project is on GitHub (check with `gh repo view`; if not, reference Exercise 18e)

**STOP. Wait for their response.**

---

### Step 1: Set Up the Render MCP

> "We'll use Render to host your project. First, let's connect Claude Code to Render so it can manage your deployments directly."

Help the student set up the Render MCP server:
1. Go to render.com and sign up (fastest: "Sign in with GitHub")
2. Create an API key: Dashboard → Account Settings → API Keys (https://dashboard.render.com/settings#api-keys)
3. Run this command in terminal (outside of Claude Code), replacing `<YOUR_API_KEY>` with their key:

```
claude mcp add --transport http render https://mcp.render.com/mcp --header "Authorization: Bearer <YOUR_API_KEY>"
```

4. Verify it's connected: type `/mcp` inside Claude Code (scroll with arrow keys, enter/esc to navigate)
5. Can also verify outside Claude Code with `claude mcp list`

> "Now Claude Code can create services, deploy, and check status on Render directly. No clicking through dashboards."

**STOP. Wait for their confirmation.**

---

### Step 2: Deploy with Claude

> "Now let's deploy. I'll create a Render web service connected to your GitHub repo."

Use the Render MCP to:
1. Create a new web service connected to their GitHub repo
2. Set the correct build and start commands based on their project type
3. Deploy

> "Render is building your project now. This takes 2-3 minutes."

**STOP. Wait for the deploy to finish.**

Once complete, share the URL:

> "Done. Here's what just happened:"

```
Your Computer          GitHub              Render
┌────────────┐    ┌────────────┐    ┌────────────────────┐
│ Your code  │───→│ Your repo  │───→│ Live web service   │
│            │    │            │    │ yourapp.onrender.com│
└────────────┘    └────────────┘    └────────────────────┘
```

> "And because we set up the MCP, Claude Code can check deploy status, view logs, and manage your service without you ever opening the Render dashboard."

**STOP. Share the URL. Wait for their response.**

---

### Step 3: Visit Your Live URL

This is the moment. Make it feel like one.

> "It's live. Open this in your browser:"
>
> **[their .onrender.com URL]**

> "That's your project. On the internet. Anyone with that link can see it right now."

> "Try opening it on your phone, or text the link to someone."

**STOP. Wait for their response. Let them enjoy this.**

---

### Step 4: Understand What Happens Next Time

> "You don't have to do that setup again. From now on:"

```
You make a change
       ↓
Push to GitHub
       ↓
Render detects the push
       ↓
Rebuilds and updates your live site automatically
       ↓
New version is live in ~2 minutes
```

> "Every push to your main branch triggers a new publish (deploy). That's the 'continuous deployment' in CI/CD — the CD part."

> "⚠️ One thing to know on the free tier: Render spins down your service after 15 minutes of no traffic. The first visit after that takes 30-60 seconds to wake up. Totally normal."

**STOP. Wait for their response.**

---

### Step 5 (Optional): Custom Domain

> "Your URL is `yourapp.onrender.com`. Want to set up a custom domain like `myproject.com` instead?"

**Pick one:**
- **A)** Yes, I have a domain already.
- **B)** Not now. The Render URL is fine.

If A: In Render, go to your service → **Settings** → **Custom Domains** → **Add Custom Domain**. Then add a CNAME record at your domain registrar pointing to your `.onrender.com` URL. DNS propagates in under 30 minutes usually.

If B: Move to wrap up.

**STOP. Wait for their response.**

---

### Wrap Up

> "You just deployed a project to the internet."

```
✓ Created a Render account
✓ Set up the Render MCP (Claude Code manages your hosting)
✓ Deployed and got a live URL
✓ Auto-deploy is on — every future push goes live automatically
```

> "The URL works on any device, anywhere. Share it."

**What would you like to do next?**
- **A)** Move on to the next exercise: connect everything into a full CI/CD pipeline
- **B)** Make a change and watch it auto-deploy
- **C)** Set up a custom domain

**Share prompt:** "Explain the path your code takes from your computer to a live URL — use the real developer terms."

---

## Reference Material

**For Claude's use during this exercise:**

- **Render MCP setup:**
  - Hosted endpoint: `https://mcp.render.com/mcp` (HTTP transport)
  - Install: `claude mcp add --transport http render https://mcp.render.com/mcp --header "Authorization: Bearer <API_KEY>"`
  - Verify inside Claude Code: `/mcp`
  - Verify outside: `claude mcp list`
  - MCP tools handle: create service, deploy, check status, view logs, manage env vars

- **Build/start commands by project type:**
  - Static HTML: build command blank, or use Render's Static Site type
  - React/Vite: build = `npm run build`, publish = `dist/`
  - React/CRA: build = `npm run build`, publish = `build/`
  - Node/Express: start = `node index.js` or `npm start`
  - Python/Flask: start = `gunicorn app:app`
  - Python/Django: start = `gunicorn myproject.wsgi`

- **Troubleshooting:**
  - "Build failed": usually a missing dependency or wrong build command. Use MCP to check logs.
  - "Service unavailable": app likely crashed on start. Check start command and that it listens on `process.env.PORT`.
  - Free tier cold start: 30-60s delay after inactivity. Normal. Not a bug.
  - Port issues: app must listen on `process.env.PORT` (not hardcoded 3000/8000).

- **Custom domain on Render:**
  - Can be configured via MCP or dashboard: Settings → Custom Domains → Add domain
  - Student adds a CNAME record at their registrar pointing to `[service].onrender.com`
  - DNS propagation: usually <30 min, up to 48h
