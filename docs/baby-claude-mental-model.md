# Course Mental Model — Capability Progression

For a user coming from ChatGPT only. Each layer builds on the previous mental shift.
Applies to: course structure, Baby Claude game, and lesson sequencing.

---

## Capability Layers

### Layer 0: "I already know this"
- Q&A response — type question, get answer
- *This is ChatGPT. No new mental model needed.*

### Layer 1: "Wait, it actually DID something"
- Creates files, edits code, runs terminal commands
- *Shift: it's not just talking — it acts on your real computer*
- Students have no project on Day 1, so this comes first. Claude builds something from scratch — the first wow is real files appearing on your computer.

### Layer 2: "Oh, it can see my stuff"
- Claude reads your files, knows your project
- *Shift: it's not a blank chat — it has context*
- Now the student has a project (from Layer 1). Claude reads and understands what it just built. They also learn the agent loop mental model here.

### Layer 3: "It remembers things across conversations"
- CLAUDE.md, project memory, design docs, style guides
- *Shift: it's not stateless — it accumulates knowledge*

### Layer 4: "It has workflows, not just answers"
- Skills, plan mode, structured approaches
- *Shift: it's not reactive — it has processes*

### Layer 5: "It connects to the outside world"
- MCP servers, external APIs, docs
- *Shift: it's not sandboxed — it reaches out*

### Layer 6: "It can run multiple workers"
- Subagents, parallel tasks
- *Shift: it's not one thread — it's a team*

---

## Layer Groupings

- **Layers 1-2 (Build & Context):** It does things → It understands things
- **Layers 3-4 (Memory & Workflows):** It remembers → It has processes
- **Layers 5-6 (Scale):** It reaches out → It parallelizes

---

## PM Use Cases Mapped to Layers

Each PM activity draws on specific capability layers:

| PM Activity | Layers Used | Why |
|---|---|---|
| **ASCII for design** | 0 (Q&A) → 1 (creates output) | Lowest barrier to "it made something" — instant visual feedback in terminal, no browser needed |
| **Building prototypes** | 2 (reads context) + 1 (creates/edits/runs) | Core build loop: read context → create files → open browser |
| **Brainstorming & design thinking** | 0 (Q&A) + 2 (sees codebase) + 3 (remembers past decisions) | Mostly conversational, but project context and memory make it specific, not generic |
| **Crafting designs that match your app** | 3 (remembers style guide) + 2 (reads existing designs) + 1 (edits files) | Memory is what makes it *your* brand, not generic output |
| **PM workflows** (feedback, competitive, release notes, backlog) | 2 (reads data) + 1 (creates artifacts) + 4 (follows structured process) | Repeatable workflows — perfect for skills |

---

## Course Skeleton

### Module 1: "It builds things" (Layer 1) — Day 1
- Student has no project yet — Claude creates one from scratch
- ASCII mockups (fastest feedback, stays in terminal)
- HTML prototypes (open in browser)
- **PM payoff:** From zero to clickable prototype without filing a ticket

### Module 2: "It knows your world" (Layer 2) — Day 1
- Now they have a project — Claude reads and understands it
- Explore the codebase, ask questions, brainstorm with context
- **PM payoff:** Context-aware ideation, not generic ChatGPT answers

### Module 3: "It remembers" (Layer 3) — Day 2
- CLAUDE.md, design docs, style guides, product context
- Start a new conversation — Claude still knows everything
- **PM payoff:** Every conversation builds on the last. Your brand, your decisions, your voice.

### Module 4: "It builds more" (Layers 1+3) — Day 2
- Now with context + memory, building gets more powerful
- Screenshot to code, multiple prototypes
- **PM payoff:** Recreate any design, explore multiple directions at once

### Module 5: "It has workflows" (Layer 4) — Day 3
- Learn skills BEFORE PM workflows — so you can build as you go
- Install a skill, then build your own
- **PM payoff:** Encode any repeating process into a one-command automation

### Module 6: "It does your PM job" (Layers 1+4) — Days 3-4
- Now they can turn each workflow into a skill as they learn it
- Brainstorm, feedback analysis, data, competitive, backlog, comms
- **PM payoff:** Your entire PM toolkit, automated

### Module 7: "It scales" (Layers 5-6) — Day 5
- MCP servers, external APIs
- Subagents, parallel work, deploy
- **PM payoff:** It works while you sleep

---

## Design Notes

- **ASCII for design** is a strong early "wow" moment: it's Layer 1 (action) with zero setup friction — no browser, no HTML, feedback is right there in terminal. Good bridge between "it talks" and "it builds."
- The Baby Claude game should cover Layers 0-2 (the foundational mental shift). Layers 3-6 are better served by lessons.
- Every lesson should anchor to: "you already know Layer X, now here's Layer X+1."
- **Act first, understand second.** The student's first experience is watching Claude do something real, not reading about how context works.

---

## Decisions Made

- **Action comes first.** Students don't have a codebase on Day 1, so Layer 1 (building) comes before Layer 2 (reading context). Claude builds something, then the student discovers context for free.
- **One ordering.** No separate "conceptual" vs "teaching" order. The layers are numbered in the order we teach them.
