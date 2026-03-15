# Course Restructure Plan: Layer-Based Progression

## 1. Current Lessons Mapped to Capability Layers

| # | Lesson | Primary Layer | Secondary Layer | Notes |
|---|--------|--------------|-----------------|-------|
| 01 | Install & First Magic Moment | 3 (Action) | 0 (Q&A) | Setup + builds an HTML file. Currently placed as intro but demonstrates Layer 3 immediately. |
| 02 | How Agents Actually Work | 1 (Sees stuff) | 0 (Q&A) | Mental model lesson. Teaches the agent loop + context engineering concept. |
| 03 | Install & Trigger First Skill | 4 (Workflows) | -- | Jumps straight to skills on Day 1. Too early per the mental model. |
| 04 | Introduce Your Product | 1 (Sees stuff) | -- | Core Layer 1: Claude reads and understands a real codebase. |
| 05 | Brainstorm Features | 1 (Sees stuff) | 4 (Workflows) | Uses codebase context for ideation. Framework-heavy (SCAMPER, ICE). |
| 06 | Project Memory (CLAUDE.md) | 2 (Remembers) | -- | Core Layer 2. Creates CLAUDE.md for persistent context. |
| 07 | First Prototype | 3 (Action) | -- | Core Layer 3. ASCII wireframes then full HTML build. |
| 08 | Design Context (design.md) | 2 (Remembers) | 3 (Action) | Creates design.md for visual memory. Rebuilds prototype with it. |
| 09 | Screenshot Feedback Loop | 3 (Action) | -- | Iteration workflow: screenshot, describe, fix, repeat. |
| 10 | Architecture | 1 (Sees stuff) | 3 (Action) | Reads codebase, diagrams architecture, evaluates features. |
| 11 | Multiple Prototypes | 3 (Action) | -- | Build 3 versions, compare, combine. Parallel exploration. |
| 12 | Screenshot to Code | 3 (Action) | -- | Recreate designs from screenshots. |
| 13 | Design Systems & Tokens | 2 (Remembers) | 3 (Action) | DESIGN.md with tokens. Heavy overlap with Lesson 08. |
| 14 | MCP & External Context | 5 (External) | -- | Core Layer 5. Figma, Context7, Notion, Playwright, Sentry. |
| 15 | Customer Feedback Analysis | 3 (Action) | 4 (Workflows) | Analyzes reviews, produces strategy brief. PM workflow. |
| 16 | Data Analysis Without SQL | 3 (Action) | 4 (Workflows) | CSV analysis with ASCII charts. PM workflow. |
| 17 | Competitive Analysis | 3 (Action) | 4 (Workflows) | Web research, positioning matrix, competitive brief. |
| 18 | Release Notes from Git | 3 (Action) | 1 (Sees stuff) | Reads git log, produces release notes. Lightweight automation. |
| 19 | Weekly Stakeholder Updates | 3 (Action) | 4 (Workflows) | Multi-audience update generation. |
| 20 | Backlog Prioritization | 3 (Action) | 4 (Workflows) | RICE/ICE scoring, devil's advocate. |
| 21 | Personal OS | 2 (Remembers) | -- | USER.md, SOUL.md, AGENTS.md. Advanced memory/persona. |
| 22 | Build Custom Skills | 4 (Workflows) | -- | Core Layer 4. Build and test a custom SKILL.md. |
| 23 | OpenClaw (Always-On AI) | 6 (Multi-worker) | 5 (External) | 24/7 persistent agent, scheduled tasks, chat control. |
| 24 | Deploy & Ship | 3 (Action) | 4 (Workflows) | Tests, CI/CD, live deployment. Capstone. |

---

## 2. Proposed New Lesson Order (Layer Progression)

### Module 1: "It Builds Things" (Layer 3 first)

**Students have no project on Day 1.** So we start with action: Claude creates something from scratch. The first wow is real files appearing on their computer.

| Order | Current # | Lesson | Rationale |
|-------|-----------|--------|-----------|
| 1 | 01 | Install & First Magic Moment | Setup + Claude builds something. Student's first "wait, it actually DID that" moment. |
| 2 | 07 | First Prototype | ASCII wireframes + full HTML build. Now they have a real project to work with. |
| 3 | 09 | Screenshot Feedback Loop | Iterate on what they just built. Tightens the action loop. |

### Module 2: "It Knows Your World" (Layers 0-1)

Now the student has a project. Claude reads and understands it. They also learn the mental model behind what just happened.

| Order | Current # | Lesson | Rationale |
|-------|-----------|--------|-----------|
| 4 | 02 | How Agents Work | Now they've *experienced* the agent loop — this lesson explains what happened. |
| 5 | 04 | Introduce Your Product | If they have a real product, Claude reads that codebase. If not, Claude explores what it just built. |
| 6 | 10 | Architecture (rename: "See Your Product's Blueprint") | Natural follow-up: read it, then map it. |

### Module 3: "It Remembers" (Layer 2)

The student makes Claude's knowledge persistent.

| Order | Current # | Lesson | Rationale |
|-------|-----------|--------|-----------|
| 7 | 06 | Project Memory (CLAUDE.md) | Core Layer 2 lesson. |
| 8 | 08+13 | **MERGE: Design Context & Design Systems** | These two overlap significantly. Merge into one lesson: create design.md/DESIGN.md, wire to CLAUDE.md, rebuild prototype with it. |

### Module 4: "It Builds More" (Layer 3, advanced)

Now with context + memory, building gets more powerful.

| Order | Current # | Lesson | Rationale |
|-------|-----------|--------|-----------|
| 9 | 12 | Screenshot to Code | Recreate existing designs. Benefits from having design context (Module 3). |
| 10 | 11 | Multiple Prototypes | Build 3, compare, combine. Requires comfort with the build loop. |

### Module 5: "It Has Workflows" (Layer 4)

Learn skills BEFORE PM workflows — so students can build skills as they go through Module 6.

| Order | Current # | Lesson | Rationale |
|-------|-----------|--------|-----------|
| 11 | 03 | Install & Trigger First Skill | Students have built prototypes, explored codebases, set up memory. Now they learn to encode processes. |
| 12 | 22 | Build Custom Skills | Build a skill from scratch. Sets them up to create skills for PM workflows in Module 6. |

### Module 6: "It Does Your PM Job" (Layers 1+4, PM Workflows)

Applied PM workflows. Each lesson produces a real deliverable. Students can now turn each workflow into a skill as they learn it.

| Order | Current # | Lesson | Rationale |
|-------|-----------|--------|-----------|
| 13 | 05 | Brainstorm Features | Requires codebase context + memory. Fits better as a workflow lesson than as an early "context" lesson. |
| 14 | 15 | Customer Feedback Analysis | PM workflow: raw data in, strategy out. |
| 15 | 16 | Data Analysis Without SQL | PM workflow: CSV analysis. |
| 16 | 17 | Competitive Analysis | PM workflow: research + brief. |
| 17 | 20 | Backlog Prioritization | PM workflow: scoring + recommendation. |
| 18 | 18+19 | **MERGE: Release Notes & Stakeholder Updates** | Both are "transform raw info into polished comms." Merge into one lesson with two exercises: git log to release notes, then raw notes to multi-audience updates. |

### Module 7: "It Scales" (Layers 5-6)

External connections, persistent operation, and shipping.

| Order | Current # | Lesson | Rationale |
|-------|-----------|--------|-----------|
| 19 | 14 | MCP & External Context | Core Layer 5. |
| 20 | 21 | Personal OS | USER.md/SOUL.md/AGENTS.md. Advanced memory + persona. |
| 21 | 23 | OpenClaw (Always-On AI) | Aspirational Layer 6. Everything compounds. |
| 22 | 24 | Deploy & Ship | Capstone. Tests, CI/CD, live URL. |

---

## Visual Overview

```
COURSE MAP — 22 LESSONS ACROSS 7 MODULES


DAY 1
├─ MODULE 1: "It builds things" ──────────────────────────────┐
│                                                              │
│  ① Install          ② First Prototype    ③ Iterate          │
│  "Hello world"      ASCII → HTML → open  Screenshot loop    │
│                     in browser                               │
├──────────────────────────────────────────────────────────────┘
│
├─ MODULE 2: "It knows your world" ───────────────────────────┐
│                                                              │
│  ④ How Agents Work  ⑤ Your Product       ⑥ Architecture     │
│  The loop explained  Claude reads your    Map the blueprint  │
│                      codebase                                │
├──────────────────────────────────────────────────────────────┘

DAY 2
├─ MODULE 3: "It remembers" ──────────────────────────────────┐
│                                                              │
│  ⑦ CLAUDE.md         ⑧ Design System                        │
│  Project memory      Brand + tokens       (08+13 merged)    │
│                                                              │
├──────────────────────────────────────────────────────────────┘
│
├─ MODULE 4: "It builds more" ────────────────────────────────┐
│  (now with context + memory)                                 │
│                                                              │
│  ⑨ Screenshot→Code   ⑩ Multiple Prototypes                  │
│  Recreate designs    Build 3, compare, pick best             │
│                                                              │
├──────────────────────────────────────────────────────────────┘

DAY 3
├─ MODULE 5: "It has workflows" ──────────────────────────────┐
│  (learn skills BEFORE PM workflows → build as you go)        │
│                                                              │
│  ⑪ First Skill       ⑫ Build Custom Skills                  │
│  Install + trigger   Create your own reusable workflow       │
│                                                              │
├──────────────────────────────────────────────────────────────┘
│
├─ MODULE 6: "It does your PM job" ───────────────────────────┐
│  (now they can turn each workflow into a skill)              │
│                                                              │
│  ⑬ Brainstorm    ⑭ Feedback     ⑮ Data Analysis             │
│  Features        Analysis       Without SQL                  │
│                                                              │
│  ⑯ Competitive   ⑰ Backlog      ⑱ Comms                     │
│  Analysis        Prioritization  Release notes +             │
│                                  stakeholder updates         │
│                                  (18+19 merged)              │
├──────────────────────────────────────────────────────────────┘

DAY 5
├─ MODULE 7: "It scales" ────────────────────────────────────┐
│                                                              │
│  ⑲ MCP Servers       ⑳ Personal OS                          │
│  External APIs       USER.md + SOUL.md                       │
│                                                              │
│  ㉑ OpenClaw          ㉒ Deploy & Ship                        │
│  Always-on AI        Tests → CI/CD → live URL (capstone)     │
│                                                              │
└──────────────────────────────────────────────────────────────┘
```

---

## 3. Gaps and Redundancies

### Redundancies (lessons that overlap too much)

| Issue | Lessons | Recommendation |
|-------|---------|----------------|
| Design context created twice | 08 (design.md) + 13 (DESIGN.md) | **Merge.** Lesson 08 creates design.md, Lesson 13 creates DESIGN.md with more detail. Same concept, same payoff (before/after rebuild). Combine into one lesson that goes from brand questions to full design token file. |
| Communication generation | 18 (Release Notes) + 19 (Stakeholder Updates) | **Merge.** Both follow the pattern: gather raw info, produce polished multi-format output. Combine into "Comms That Write Themselves" with two exercises. |
| Brainstorming frameworks | 05 (SCAMPER/ICE/Personas) + 20 (RICE/ICE) | **Minor overlap.** Both use ICE scoring. Differentiate by removing ICE from Lesson 05 (keep it as pure ideation) and reserving scoring frameworks for Lesson 20 only. |

### Gaps (layers with insufficient coverage)

| Gap | Layer | Recommendation |
|-----|-------|----------------|
| Layer 5 has only one lesson | 5 (External) | **Acceptable for now.** MCP is covered well in Lesson 14, and several other lessons mention MCP integrations (Figma in 13, analytics in 16, Jira/Linear in 20). Consider splitting Lesson 14 into "MCP Basics" and "Advanced Integrations" if students struggle. |
| Layer 6 is aspirational only | 6 (Multi-worker) | **Gap.** Lesson 23 (OpenClaw) is a demo/vision lesson -- students don't actually run subagents. Lesson 11 mentions parallel terminals but doesn't teach it. Add a hands-on exercise where the student runs 2-3 Claude Code sessions in parallel on the same project. Could fold into Lesson 11 or create a standalone lesson. |
| No lesson on prompt engineering specifically | 0-1 | **Minor gap.** Lesson 02 covers context engineering conceptually, but there's no dedicated lesson on writing effective prompts (specificity, constraints, examples). The course philosophy is "context > prompts," which is valid, but a short section on prompt craft would help. Consider adding to Lesson 02 or the first Module 4 lesson. |
| No lesson on error recovery / debugging | 3 | **Gap.** When Claude builds something wrong, students need a mental model for how to recover: revert, start fresh, use git, narrow the scope. This is implied in Lesson 09 ("when to start fresh") but deserves more attention. Consider adding a section to the Architecture lesson or the iteration lesson. |

---

## 4. Lessons to Merge, Split, or Rewrite

### Merge

| Action | Lessons | New Title | Rationale |
|--------|---------|-----------|-----------|
| Merge | 08 + 13 | "Give Claude Your Design System" | Eliminates the design.md vs DESIGN.md confusion. One lesson that goes from brand personality to design tokens to before/after rebuild. |
| Merge | 18 + 19 | "Comms That Write Themselves" | Both are "raw info to polished output." Exercise 1: git log to release notes. Exercise 2: notes to stakeholder updates. Saves a lesson slot. |

### Rewrite

| Action | Lesson | Change | Rationale |
|--------|--------|--------|-----------|
| Rewrite | 03 | Move later + reframe as "why skills matter" | Currently placed before students know what workflows they'd want to automate. After Module 4, they've done 5+ manual workflows and the motivation is obvious. |
| Rewrite | 05 | Remove scoring, pure ideation | Currently does ideation AND ICE scoring. Split the scoring to Lesson 20. Keep 05 focused on the "compressed design sprint" concept. |
| Rewrite | 10 | Tighten scope, rename | "Architecture" sounds scary for PMs. Rename to "See Your Product's Blueprint" and focus on the PM-relevant parts: what's easy to build, what's hard, where the free wins are. |
| Rewrite | 23 | Add hands-on component | Currently aspirational/demo only. Add a concrete exercise: even if they don't install OpenClaw, have them run two parallel Claude sessions or set up a cron-based automation. |

### Split (none recommended)

No lessons are trying to do too much on their own. The merges above reduce the total count from 24 to 22, which is a better fit for a 5-day course (roughly 4-5 lessons per day).

---

## 5. Proposed Module Groupings

| Module | Theme | Mental Model Shift | Lessons | Est. Time |
|--------|-------|-------------------|---------|-----------|
| **1: It Builds Things** | Action first | "It actually DID something" | 3 lessons (Install, First Prototype, Iteration Loop) | Half day |
| **2: It Knows Your World** | Context & comprehension | "It can see my stuff" | 3 lessons (Agent Loop, Introduce Product, Architecture) | Half day |
| **3: It Remembers** | Persistent memory | "It's not stateless" | 2 lessons (CLAUDE.md, Design System) | 2-3 hours |
| **4: It Builds More** | Advanced prototyping | Context + memory make building better | 2 lessons (Screenshot to Code, Multiple Prototypes) | 2-3 hours |
| **5: It Has Workflows** | Skills & automation | "It has processes" | 2 lessons (Install Skill, Build Skill) | 2-3 hours |
| **6: It Does Your Job** | PM workflows | Applied capability + skills | 6 lessons (Brainstorm, Feedback, Data, Competitive, Backlog, Comms) | Full day+ |
| **7: It Scales** | External + persistent + shipping | "It's a team" | 4 lessons (MCP, Personal OS, OpenClaw, Deploy) | Full day |

**Total: 22 lessons across 7 modules.**

### Mapping to a 5-Day Cohort Schedule

| Day | Modules | Arc |
|-----|---------|-----|
| Day 1 | Module 1 + Module 2 | "Build first, understand second" — make something, then learn how it works |
| Day 2 | Module 3 + Module 4 | "Make it yours" — memory, design system, advanced builds |
| Day 3 | Module 5 + Module 6 (first half) | "Automate your job" — learn skills, then apply to PM workflows |
| Day 4 | Module 6 (second half) | "Automate your job" continued — more PM workflows, each one a potential skill |
| Day 5 | Module 7 | "Scale it" — external tools, personal OS, ship it |

---

## Summary of Key Recommendations

1. **Move Lesson 03 (Skills) from Day 1 to after PM workflows.** Students need to feel the pain of repeating workflows before the automation payoff lands.
2. **Merge Lessons 08+13 (design context).** They teach the same concept at different depths. One lesson is enough.
3. **Merge Lessons 18+19 (comms generation).** Same pattern, different outputs. Combine into one lesson with two exercises.
4. **Move Lesson 10 (Architecture) earlier.** It's a natural follow-up to "Introduce Your Product" and gives PMs the vocabulary to evaluate features.
5. **Move Lesson 05 (Brainstorm) to Module 4.** It's a PM workflow that benefits from memory and design context being set up first.
6. **Add a hands-on parallel work exercise** to fill the Layer 6 gap. Students should actually experience running multiple agents, even briefly.
7. **Reframe lesson titles for PM audience.** "Architecture" becomes "See Your Product's Blueprint." Reduce jargon in titles.
