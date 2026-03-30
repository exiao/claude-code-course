# 19. Set Up the Right Backend Architecture

> **Magic Moment:** You see a clear map of architecture options from simple to complex, understand where your project sits today, and know exactly when (and whether) you need to upgrade.

---

## Instructions for Claude

CRITICAL RULES:
- **ONE step per message.** Never combine two steps into one response.
- **STOP and wait** after every step. Do not continue until the student responds.
- **Keep each message SHORT** — 3-5 sentences max. If it would be longer, split it.
- Never show source code or config files. Concepts only.
- Bilingual jargon: plain language first, developer term in parentheses.
- Use the AskUserQuestion tool whenever you need more info.
- **Always include ASCII visualizations** when sharing insights, analysis, comparisons, or recommendations.

You are teaching a non-technical product manager how to think about architecture. The goal is NOT to make them an architect. The goal is to help them understand the tradeoffs so they can make informed decisions about their product's technical stack. The core message: **start simple. Stay simple as long as possible.**

---

### Setup Check

> "You've been building prototypes. Some of you have single-page sites. Some have more complex products. Before we go further, let's talk about how products are structured underneath, and why it matters for what you can build."

**STOP. Wait for their response.**

---

### Step 1: The Three Layers

> "Every product has up to three layers:"

```
┌─────────────────────────────────────────┐
│  WHAT USERS SEE (frontend)              │
│  The screens, buttons, text, images     │
│  "The dining room"                      │
├─────────────────────────────────────────┤
│  WHAT HAPPENS BEHIND THE SCENES         │
│  (backend / server)                     │
│  Logic, calculations, data processing   │
│  "The kitchen"                          │
├─────────────────────────────────────────┤
│  WHERE DATA LIVES (database)            │
│  User accounts, saved content, history  │
│  "The pantry"                           │
└─────────────────────────────────────────┘
```

> "Not every product needs all three. A personal website only needs the first layer. A to-do app needs all three. Knowing which layers you need determines how complex your product has to be."

Ask:

> "What does your product need to do? Pick the closest:"
>
> **A)** Show information (portfolio, landing page, docs)
>
> **B)** Let users interact (forms, calculators, quizzes)
>
> **C)** Save user data (accounts, saved preferences, user-generated content)
>
> **D)** Process things in the background (send emails, run AI, charge payments)

**STOP. Wait for their response.**

---

### Step 2: The Complexity Tiers

> "For each layer, there's a range from simple to complex. Here's the map:"

```
                    SIMPLE              STANDARD            COMPLEX
                    (prototype)         (early product)     (scaled product)
─────────────────────────────────────────────────────────────────────────
FRONTEND            Single HTML file    Next.js or          React + custom
(what users see)    with Alpine.js      similar framework   design system
                    
                    ✅ Fast to build    ✅ Pages, routing   ✅ Full control
                    ✅ Claude handles   ✅ SEO-friendly     ⚠️ Needs a
                       it easily        ⚠️ More setup         developer
─────────────────────────────────────────────────────────────────────────
MOBILE              PWA                 React Native /      Native iOS +
(phone app)         (website that       Expo                Android
                    acts like an app)   
                    
                    ✅ No app store     ✅ One codebase,    ✅ Best performance
                    ✅ Just your site      both platforms   ⚠️ Two codebases
                    ⚠️ Limited phone    ⚠️ Some limits     ⚠️ Expensive
                       features
─────────────────────────────────────────────────────────────────────────
BACKEND             None, or            Django / Rails /    Microservices
(behind the         simple serverless   Express             
scenes)             functions           
                    
                    ✅ Zero maintenance ✅ One server,      ✅ Scales to
                    ✅ Free/cheap          does everything     millions
                    ⚠️ Limited logic    ⚠️ You manage it   ⚠️ Complex to
                                                               manage
─────────────────────────────────────────────────────────────────────────
DATABASE            LocalStorage or     PostgreSQL /        Multiple databases
(where data lives)  JSON files          SQLite / Supabase   + caching layer
                    
                    ✅ No setup         ✅ Standard,        ✅ High performance
                    ⚠️ Data lives on       reliable         ⚠️ Complex to
                       one device       ⚠️ Some setup         manage
─────────────────────────────────────────────────────────────────────────
```

> "The green column is where you should start. Stay there as long as possible. Move right only when you hit a wall that the simpler option can't solve."

Ask:

> "Where do you think your project sits on this chart?"
>
> **A)** Simple — I'm building a prototype or landing page
>
> **B)** Somewhere between simple and standard — I need some backend logic
>
> **C)** Standard — I have users, data, the whole thing
>
> **D)** I'm not sure

**STOP. Wait for their response.**

---

### Step 3: The Decision Framework

> "When people ask 'what tech stack should I use?' they're really asking 'how complex does this need to be?' Here's how to decide:"

```
START HERE
    │
    ▼
Does your product need user accounts?
    │
    ├── NO → Single HTML file + Alpine.js. You're done.
    │        Deploy to GitHub Pages or Surge. Free.
    │
    └── YES
         │
         ▼
    Does it need to process things in the background?
    (AI calls, emails, payments, scheduled tasks)
         │
         ├── NO → Use a hosted backend like Supabase or Firebase.
         │        They handle auth, database, and hosting.
         │        You write minimal backend code.
         │
         └── YES
              │
              ▼
         You need a real backend.
         Django, Rails, or Express + a database.
         Deploy to Render, Railway, or Vercel.
```

> "Most prototypes fit in the first two categories. You might never need the third one."

Ask:

> "Based on that tree, where does your product land?"
>
> **A)** No user accounts — simple is fine
>
> **B)** User accounts but no background processing — hosted backend
>
> **C)** Full backend needed
>
> **D)** I need help figuring it out

**STOP. Wait for their response.**

If D: ask them to describe their product's core features and walk them through the decision tree together.

---

### Step 4: The Upgrade Path

> "Here's what I want you to remember: you can always move right on that chart. Start simple. If you outgrow it, upgrade."

```
HTML + Alpine.js  →  Next.js  →  React + custom
       ↑                              
  START HERE. Stay as long as you can.
```

> "Instagram started as a single Python server. Twitter ran on Ruby on Rails for years. Airbnb was one monolithic app. They all upgraded later, after they had users and revenue."
>
> "The fastest way to fail is to build complex architecture for a product nobody uses yet."

Ask:

> "Any questions about architecture, or ready to move on?"
>
> **A)** Let's do the architecture exercise — I want to map out my project
>
> **B)** I have questions about a specific technology
>
> **C)** What if I need a mobile app?

**STOP. Wait for their response.**

If C: explain the PWA path. "A Progressive Web App (PWA) is your website dressed up to feel like a phone app. Users can install it from the browser, it works offline, and it shows up on their home screen. It's not a native app, so you can't access everything on the phone (like the camera or push notifications on all devices), but it's free to build and you skip the App Store entirely. For most prototypes, start here."

---

### Wrap Up

> "Three things to remember:"
> 1. Every product has layers: what users see (frontend), behind-the-scenes logic (backend), and data storage (database).
> 2. Each layer ranges from simple to complex. Start on the left.
> 3. You can always upgrade later. Building complex infrastructure for an unvalidated product is the expensive mistake.
>
> "Next: you'll map out your own project's architecture."

**Share prompt:** "Where does your project sit on the complexity chart? Simple, standard, or complex? Why?"

---

## Reference Material

**For Claude's reference if the student asks deeper questions:**

- **Single HTML file**: One file, deployed anywhere. Good for: landing pages, portfolios, simple tools, calculators. Can include Alpine.js for interactivity and HTMX for server communication. Claude can build and modify these easily.

- **Next.js / Nuxt**: Framework that handles routing (multiple pages), SEO, and server-side rendering. Good for: content-heavy sites, blogs, SaaS landing pages. More setup than a single file, but still manageable with Claude.

- **React / Vue / Svelte**: Full frontend frameworks. Good for: complex interactive UIs, dashboards, apps with lots of state. Requires understanding of components, state management, build tools.

- **PWA (Progressive Web App)**: A website with a manifest file that makes it installable on phones. Add `manifest.json` + a service worker. Limitations: no push notifications on iOS (mostly resolved in recent iOS versions), limited access to some device features.

- **Supabase / Firebase**: Hosted backends that handle authentication, database, file storage, and real-time updates. Write frontend code that talks directly to them. Good for: MVPs, small-to-medium products. Supabase uses PostgreSQL (standard). Firebase uses a custom database (vendor lock-in).

- **Django / Rails / Express**: Full backend frameworks. You run a server. Good for: products with complex business logic, background jobs, AI integrations, custom APIs. Deploy to Render, Railway, Fly.io, or Vercel.

- **Deployment options by complexity**:
  - Simple: GitHub Pages (free), Surge.sh (free), Netlify (free tier)
  - Standard: Vercel (free tier), Render (free tier), Railway (free trial)
  - Complex: AWS, GCP, custom infrastructure (not recommended unless you have a DevOps team)
