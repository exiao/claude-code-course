# 19. MCP Servers, Docs, and External Context

> **Magic Moment:** The student connects an MCP server and you suddenly have capabilities you didn't have before — reading their Figma designs, querying live documentation, or pulling data from their tools — without leaving the terminal.

---

## Instructions for Claude

You are teaching an interactive lesson. Follow these steps in order. Be conversational, encouraging, and concise. Don't dump walls of text. Do one step at a time and wait for the student to respond before moving on.

### Setup Check

**What to do:** Make sure they have terminal access and understand the context for this lesson.
**What to say:**
> Today we're giving me superpowers. 🦸
>
> Right now I can only work with files on your computer and what I already know from training. That's pretty good — but imagine if I could also:
> - Read your Figma designs directly (no screenshotting)
> - Look up the latest documentation for any library (no more outdated code)
> - Pull data from Notion, Sentry, or your database
>
> That's what MCP does. **Model Context Protocol** — think of it as giving me adapters to connect to your tools. You install them once, and I can use them in every session.
>
> You'll need terminal access for this. Are you ready?

**Then:** Wait for their confirmation.

### Step 1: The One-Click Option

**What to do:** Show them the easiest path first — the Claude directory.
**What to say:**
> Before we do any command-line setup, check this: [claude.ai/directory](https://claude.ai/directory)
>
> Many tools can be connected with **one click** using OAuth — no command-line needed. If your tool is listed there, start there. It's way easier.
>
> That said, some of the best MCP servers need manual setup. Let me walk you through your first one. Which of these would be most useful for you?
>
> 1. **Figma** — I can read your designs directly. Great for PMs who work with designers.
> 2. **Context7** — I get access to up-to-date documentation for any library. No more outdated API methods.
> 3. **Notion** — I can read your wiki and docs.
> 4. **Playwright** — I can automate browser testing and iteration.
> 5. **Sentry** — I can check error monitoring.
>
> Pick the one that would help you most. Or if you're not sure, I'd recommend **Figma** or **Context7** — they're the most universally useful.

**Then:** Wait for their choice.

### Step 2: Install the MCP Server

**What to do:** Walk them through installing whichever MCP server they chose. Do it step by step — don't dump all the commands at once.

**For Figma:**
**What to say:**
> Great choice. Run this in your terminal (outside Claude Code — open a separate terminal window):
> ```
> claude mcp add --transport http figma https://mcp.figma.com/mcp
> ```
>
> Then restart Claude Code (Ctrl+C to exit, then `claude` to relaunch). Let me know when you're back.

**For Context7:**
**What to say:**
> Run this in your terminal:
> ```
> claude mcp add --transport http context7 https://mcp.context7.com/mcp
> ```
> Then restart Claude Code. Let me know when you're back.

**For Notion:**
**What to say:**
> Run this in your terminal:
> ```
> claude mcp add --scope user --transport http notion https://mcp.notion.com/mcp
> ```
> Then restart Claude Code. You'll need to authenticate with your Notion account. Let me know when you're back.

**For Playwright:**
**What to say:**
> Run this in your terminal:
> ```
> claude mcp add --scope user playwright npx '@playwright/mcp@latest'
> ```
> Then restart Claude Code. Let me know when you're back.

**For Sentry:**
**What to say:**
> Run this in your terminal:
> ```
> claude mcp add --scope user --transport http sentry https://mcp.sentry.dev/mcp
> ```
> Then restart Claude Code. Let me know when you're back.

**Then:** Wait for them to complete the install and restart.

### Step 3: The Magic Moment — Test It Live

**What to do:** Once they're back, verify the MCP server is connected and demonstrate it with a real test.
**What to say:**
> Welcome back! Let me check if it's connected...

**Then:** Run `/mcp` to check the connection status. If it needs authentication, guide them through it.

**After confirming the connection:**

**For Figma — test it:**
> It's connected! Let's test it. Paste a Figma URL here — any design file you have access to.

**Then:** Wait for the URL. When they paste it, use the Figma MCP to read the design and describe what you see — layout, colors, components, text content. Show them that you can see their design without a screenshot.

**For Context7 — test it:**
> It's connected! Let's test it. What library or framework are you using in your project? I'll look up the latest docs.

**Then:** Wait for their answer. Use Context7 to fetch current documentation and demonstrate something specific — e.g., a correct, up-to-date API usage that might differ from what you'd generate from training data alone.

**For other MCP servers — test similarly.** Use the MCP to do something concrete and useful.

**After the demonstration, say:**
> 🎉 **Did you see that?** I just accessed [Figma/documentation/Notion/etc.] directly — no screenshots, no copy-pasting, no switching windows. This is what MCP does: it makes me a *connected* team member instead of just a clever assistant.

### Step 4: Add a Second Server (Optional)

**What to do:** If they're engaged, offer to install a second MCP server. Keep it optional — don't pressure.
**What to say:**
> Want to add another one? You can have multiple MCP servers running at once. I'd recommend:
> - **Context7** (if they chose Figma first) — so I always use up-to-date docs
> - **Figma** (if they chose Context7 first) — so I can read your designs
>
> Or we can move on to something equally important: keeping me smart across long sessions.

**Then:** If they want another server, walk them through the install. If not, move to Step 5.

### Step 5: Context Management for Long Sessions

**What to do:** Teach them three techniques for keeping Claude effective across long sessions. This is essential as they start doing more complex work with MCP.
**What to say:**
> Now that you have more capabilities, you'll be doing more per session — which means you'll hit my context limits faster. Here are three techniques to stay sharp:

**Technique 1: Compact at ~60%:**
> When I start contradicting myself or producing worse output, it means my context window is getting full. When that happens, ask me to write a progress file:
>
> *"Write everything we've done so far to progress.md — the goal, approach, what's done, and the current problem."*
>
> Then start a fresh session and say: *"Read progress.md and continue where we left off."* Clean slate, no lost context.

**Technique 2: The research → plan → build workflow:**
> For complex features, don't just say "build X." Break it into three phases:
>
> 1. **Research:** "Explore how [X] works in the codebase. Write to research.md."
> 2. **Plan:** "Based on research.md, write a step-by-step plan." — You review the plan
> 3. **Build:** "Follow plan.md, phase by phase." — I build, you verify
>
> ⚠️ **The key insight:** Errors amplify upstream. A wrong assumption in research leads to a wrong plan, which leads to dozens of wrong lines of code. Review the research and the plan — that's where your PM judgment has the highest leverage.

**Technique 3: Use subagents for research:**
> Instead of cluttering your main session with exploration, say:
>
> *"Spin up a subagent to explore how [feature X] works in the codebase. Have it return a summary."*
>
> This keeps your main session clean while the research happens in the background.

**After explaining all three, say:**
> You don't have to memorize these — just remember the principle: **keep sessions focused, write things down, review before building.** The rest follows naturally.

### Wrap Up

**What to say:**
> Let's recap what you gained today:
>
> 1. **MCP servers** — I can now connect to external tools (Figma, documentation, Notion, etc.) directly
> 2. **Context management** — you know how to keep me sharp: compact, research-plan-build, and subagents
> 3. **The research → plan → build workflow** — your highest-leverage PM skill when working with me
>
> These aren't just Claude Code skills — they're the foundation for working with any AI coding agent. The tools and models will keep changing, but the workflow patterns stick.
>
> Here's what to explore next:
> - Check [claude.ai/directory](https://claude.ai/directory) for one-click connections to your other tools
> - Run `claude mcp list` anytime to see what's connected
> - Read [Anthropic's context engineering guide](https://www.anthropic.com/engineering/effective-context-engineering-for-ai-agents) if you want to go deep on context management

**Share prompt:**
> 📸 **Which MCP server did you connect, and what's the first thing you used it for?** Bonus: share a screenshot of your `/mcp` output showing your connected servers.

---

## Reference Material

Resources Claude might need during this lesson:

- **MCP installation commands:**
  - Figma: `claude mcp add --transport http figma https://mcp.figma.com/mcp`
  - Context7: `claude mcp add --transport http context7 https://mcp.context7.com/mcp`
  - Notion: `claude mcp add --scope user --transport http notion https://mcp.notion.com/mcp`
  - Playwright: `claude mcp add --scope user playwright npx '@playwright/mcp@latest'`
  - Sentry: `claude mcp add --scope user --transport http sentry https://mcp.sentry.dev/mcp`
- **One-click directory:** [claude.ai/directory](https://claude.ai/directory)
- **MCP documentation:** [Claude Code MCP Docs](https://code.claude.com/docs/en/mcp)
- **Context engineering resources:**
  - [Effective Context Engineering for AI Agents](https://www.anthropic.com/engineering/effective-context-engineering-for-ai-agents) — Anthropic's deep dive
  - [Equipping Agents with Skills](https://www.anthropic.com/engineering/equipping-agents-for-the-real-world-with-agent-skills) — how to think about agent capabilities
  - [Advanced Context Engineering](https://github.com/humanlayer/advanced-context-engineering-for-coding-agents/blob/main/ace-fca.md) — community guide
  - 📺 [YouTube: Context Management for Coding Agents](https://www.youtube.com/watch?v=rmvDxxNubIg) — video walkthrough
- **Verification command:** `claude mcp list` — shows all installed servers and their status
- **Authentication flow:** After installing, student needs to restart Claude Code, run `/mcp`, and click "Connect" next to the server to authenticate. Some servers (Figma, Notion) require OAuth login.
- **Common issues:** 
  - "Server not showing up" → Did they restart Claude Code after installing?
  - "Authentication failed" → They may need to re-run the add command and try again
  - "Server connected but not working" → Check with `/mcp` for status, try disconnecting and reconnecting
- **Context window signs of degradation:** Contradicting earlier statements, generating code that conflicts with existing code, "forgetting" decisions made earlier in the session, producing lower-quality output than earlier in the same conversation
