# Baby Claude Redesign Plan

## Design Philosophy

The current game has one correct answer per level and a linear path. The redesign
treats every option as a valid choice that teaches something real, structures the
game as a choose-your-own-adventure across capabilities, and uses the fact that
Claude is ACTUALLY building things on the player's computer as the core feedback
mechanism.

---

## 1. Core Learning Loop (Guitar Hero Model)

Guitar Hero teaches you to play by compressing the Trigger-Action-Feedback-Investment
loop into seconds. Baby Claude should do the same.

```
TRIGGER          ACTION              FEEDBACK                 INVESTMENT
"What should     Player picks        Claude ACTUALLY does     Player sees real
Baby Claude      any option          it on their computer     artifact, wants
try next?"       (all are valid)     (file, ASCII, page)      to do more
     |                |                     |                      |
     +-----<----------+----------<----------+----------<-----------+
                         ~30-60 seconds per loop
```

### Per-capability breakdown:

| Capability      | Trigger                          | Action                  | Feedback (real)                          | Investment                          |
|-----------------|----------------------------------|-------------------------|------------------------------------------|-------------------------------------|
| ASCII Art       | "I want to express myself!"      | Pick a subject/style    | ASCII art appears in terminal RIGHT NOW  | "What else can it draw?"            |
| Create Files    | "I need a home for my stuff"     | Pick what to create     | File appears on disk, `ls` proves it     | "I have real files on my computer"  |
| Read Context    | "There's a mysterious file..."   | Pick what to read       | Claude quotes it back, uses it           | "It actually understood my docs"    |
| Edit/Write      | "This needs to be better"        | Pick what to build      | File content changes, diff shown         | "It wrote real code for me"         |
| Run Commands    | "How do I see what I made?"      | Pick how to launch      | Browser opens, thing is LIVE             | "That's running on MY machine"      |
| Combine (Agent) | "Let's put it all together"      | Pick a final project    | Full working project in browser          | "I built that with 5 choices"       |

### Key timing constraint
Each loop should take 30-60 seconds. The player picks, Claude acts, the result
is visible. No waiting. The ASCII art capability is the fastest loop (result
appears in the terminal itself) which is why it comes first.

---

## 2. Adventure Structure

### Map Overview

The game is a tree, not a line. The player starts at the Nest and explores
outward. Each region unlocks a capability. The player must visit at least 3
regions before the Final Evolution becomes available, but the ORDER is up to them.

```
                        ┌─────────────┐
                        │  THE NEST   │
                        │  (Start)    │
                        │  Layer 0    │
                        └──────┬──────┘
                               │
                  ┌────────────┼────────────┐
                  │            │            │
           ┌──────▼──────┐ ┌──▼────────┐ ┌─▼───────────┐
           │  THE CAVE   │ │ THE       │ │ THE         │
           │  OF SEEING  │ │ WORKSHOP  │ │ GALLERY     │
           │  Layer 2    │ │ Layer 1   │ │ Layer 1     │
           │  (Read)     │ │ (Create/  │ │ (ASCII Art) │
           │             │ │  Edit)    │ │             │
           └──────┬──────┘ └──┬────────┘ └──┬──────────┘
                  │           │             │
                  │      ┌────▼────────┐    │
                  │      │ THE LAUNCH  │    │
                  │      │ PAD         │    │
                  │      │ Layer 1     │    │
                  │      │ (Run Cmds)  │    │
                  │      └────┬────────┘    │
                  │           │             │
           ┌──────▼──────┐    │             │
           │ THE MEMORY  │    │             │
           │ GARDEN      │    │             │
           │ Layer 3     │    │             │
           │ (CLAUDE.md) │    │             │
           └──────┬──────┘    │             │
                  │           │             │
                  └─────┬─────┘─────────────┘
                        │
                  ┌─────▼──────────┐
                  │  FINAL         │
                  │  EVOLUTION     │
                  │  (Combine all) │
                  │  Unlocks after │
                  │  3+ regions    │
                  └────────────────┘
```

### Navigation Rules

1. After the Nest intro, the player sees 3 paths and picks one.
2. Each region has 2-3 choices inside it. ALL choices are valid and produce
   different real artifacts.
3. After completing a region, the player returns to the hub and sees their
   updated ability bar + remaining paths.
4. Once 3+ capabilities are unlocked, Final Evolution appears as a new option.
5. Players CAN visit all regions before doing Final Evolution (completionist path).
6. Total: 10-15 minutes regardless of path.

---

## 3. Every Decision Point: All Options and Where They Lead

### THE NEST (Start)

Baby Claude hatches. Opening ASCII art and intro screen (keep current design).
Then immediately:

```
"I can feel three paths ahead of me... Where should I explore first?"

  A) The Gallery — "I see colors and shapes... I want to EXPRESS myself!"
  B) The Cave of Seeing — "There's something in the dark... I want to READ it!"
  C) The Workshop — "I hear hammering... I want to BUILD something!"
```

All three are valid. The player picks their first region.

---

### THE GALLERY (ASCII Art — Layer 1 with zero friction)

**Why this exists:** ASCII art is the fastest possible feedback loop. The result
appears right in the terminal. No files to open, no browser. Pure "wow, it did
that" with zero friction. This is the recommended first stop.

**Setup:** Claude creates the `baby-claude-adventure/` folder if it doesn't exist yet.

**Decision point:**

```
Baby Claude enters the Gallery... the walls are blank canvases.

"I feel shapes inside me trying to get out! What should I create?"

  A) A self-portrait — "What do I even look like??"
  B) The player's name in giant block letters
  C) A map of our adventure so far
```

**What each choice produces (Claude actually renders these):**

- **A) Self-portrait:** Claude draws a detailed ASCII Baby Claude (bigger and more
  elaborate than the title screen version — multiple expressions, accessories).
  Then saves it to `baby-claude-adventure/self-portrait.txt`.

- **B) Player's name:** Claude asks "What's your name?" then renders it in large
  ASCII block letters with decorative borders. Saves to
  `baby-claude-adventure/name-banner.txt`.

- **C) Adventure map:** Claude draws an ASCII map showing the Nest and the paths,
  with a "YOU ARE HERE" marker. Saves to `baby-claude-adventure/map.txt`.

**Capability unlocked:** ASCII/Terminal Output + Create Files

**Feedback moment:** The art appears RIGHT IN THE TERMINAL. No file to open. Then
Claude mentions it also saved the file — bonus discovery that it created a real
file too. Two capabilities in one.

```
  ┌──────────────────────────────────┐
  │  ABILITIES UNLOCKED:            │
  │  🎨 ASCII Art (terminal output) │
  │  📄 Create Files                │
  └──────────────────────────────────┘
```

After: Return to hub. Show remaining paths.

---

### THE CAVE OF SEEING (Read Context — Layer 2)

**Why this exists:** This teaches that Claude can read existing files and use them
as context. The "aha" is: it's not a blank chat, it knows your world.

**Setup:** Before presenting choices, Claude creates
`baby-claude-adventure/mysterious-scroll.md` containing:

```markdown
# Mysterious Scroll
The bearer of this scroll has a secret power.
Their favorite color is: [ask the player]
Their quest is: [ask the player]
Their greatest PM skill is: [ask the player]
```

**Decision point:**

```
Baby Claude squints into the darkness... there's a scroll on the wall!

"I can sense writing... I think I can READ things now! What should I do?"

  A) Read the mysterious scroll and follow its instructions
  B) Read my own source code — "What AM I, anyway?"
  C) Look around — "What other files are hiding in this computer?"
```

**What each choice produces:**

- **A) Read the scroll:** Claude reads the scroll, then asks the player three
  questions (favorite color, quest, PM skill). Then rewrites the scroll with their
  answers filled in and reads it back dramatically.

- **B) Read own source code:** Claude reads the game file itself
  (`baby-claude.md`) and pulls out a funny quote or observation about its own
  instructions. "Wait... I'm reading my OWN instructions? It says here I'm
  supposed to be 'cute and confused.' I AM cute and confused! This is META."

- **C) Look around:** Claude runs `ls` on the current directory and narrates what
  it finds like an explorer. "I see a README... some lesson files... OH, is that
  a package.json? This place has LAYERS."

**Capability unlocked:** Read Files & Context

```
  ┌──────────────────────────────────┐
  │  ABILITY UNLOCKED:              │
  │  👀 Read & Use Context          │
  └──────────────────────────────────┘
```

After: Return to hub.

---

### THE WORKSHOP (Create & Edit — Layer 1)

**Why this exists:** This teaches file creation and editing. The player picks what
to build and Claude builds it.

**Setup:** Claude creates `baby-claude-adventure/` if it doesn't exist yet.

**Decision point:**

```
Baby Claude finds a workbench covered in tools...

"I think I can MAKE things! Real files, on your real computer! What should I build?"

  A) A personal homepage — "Every adventurer needs a base camp!"
  B) A PM cheat sheet — "Let me write down everything I know about being a PM!"
  C) A tiny game — "A game inside a game?? INCEPTION!"
```

**What each choice produces:**

- **A) Personal homepage:** Claude creates `baby-claude-adventure/homepage.html`
  with a styled page. Uses a retro terminal aesthetic (dark background, green/cyan
  text, monospace font). Includes the player's name if they did the Gallery first.
  Content: "Welcome to [name]'s PM Command Center" with sections for abilities
  unlocked so far.

- **B) PM cheat sheet:** Claude creates `baby-claude-adventure/pm-cheatsheet.md`
  — a genuinely useful PM cheat sheet with sections on user stories, prioritization
  frameworks, stakeholder communication templates. Real, useful content they can
  keep after the game.

- **C) Tiny game:** Claude creates `baby-claude-adventure/mini-game.html` — a
  small browser-based game (e.g., a "click the Claude" whack-a-mole or a trivia
  quiz about PM concepts). Includes HTML + CSS + JavaScript in one file.

**Capability unlocked:** Create Files + Edit/Write Content

```
  ┌──────────────────────────────────┐
  │  ABILITIES UNLOCKED:            │
  │  📄 Create Files                │
  │  📝 Write & Edit Content        │
  └──────────────────────────────────┘
```

After: Return to hub. If they built an HTML file, suggest visiting the Launch Pad
to see it in the browser.

---

### THE LAUNCH PAD (Run Commands — Layer 1)

**Availability:** Appears as an option after the player has completed at least one
region that produced an HTML file (Workshop or Gallery-if-it-saved-HTML). If the
player hasn't made an HTML file yet, this region creates one first.

**Decision point:**

```
Baby Claude discovers a big red button labeled "LAUNCH"...

"I've been building things but they're just sitting as files!
I think I can RUN COMMANDS to bring them to life! What should I launch?"

  A) Open my creation in the browser — "Let the world see what I made!"
  B) Start a file explorer — "Let me see ALL the files in my adventure folder!"
  C) Run a system command — "What can this computer DO?"
```

**What each choice produces:**

- **A) Open in browser:** Claude runs `open` (macOS) / `xdg-open` (Linux) /
  `start` (Windows) on the most recent HTML file they created. The player sees
  their creation live in the browser.

- **B) File explorer:** Claude runs the OS command to open the
  `baby-claude-adventure/` folder in Finder/Explorer. Player sees all the real
  files they've created so far.

- **C) System command:** Claude runs a few fun commands:
  `echo "Baby Claude was here" | say` (macOS text-to-speech) or equivalent.
  Then shows the output of `date`, `whoami`, and `ls -la baby-claude-adventure/`.
  "I can talk to your WHOLE COMPUTER!"

**Capability unlocked:** Run Terminal Commands

```
  ┌──────────────────────────────────┐
  │  ABILITY UNLOCKED:              │
  │  🖥️  Run Commands               │
  └──────────────────────────────────┘
```

After: Return to hub.

---

### THE MEMORY GARDEN (CLAUDE.md — Layer 3)

**Availability:** Appears as an option after completing The Cave of Seeing (Read).
This teaches that Claude can have persistent memory across conversations.

**Decision point:**

```
Baby Claude finds a quiet garden with a stone tablet...

"This tablet... it's for writing things I want to REMEMBER. Even after
this conversation ends. It's called... a CLAUDE.md."

  A) Write a memory about this adventure — who the player is, what we built
  B) Write a style guide — so future Claude always builds in my favorite style
  C) Write a personality file — so future Claude remembers who Baby Claude grew up to be
```

**What each choice produces:**

- **A) Adventure memory:** Claude creates `baby-claude-adventure/CLAUDE.md` with
  a summary of the adventure: player name, choices made, artifacts created, and
  capabilities unlocked. Written so that a future Claude conversation could read it
  and know what happened.

- **B) Style guide:** Claude creates `baby-claude-adventure/CLAUDE.md` with design
  preferences: color scheme (asks the player), font preferences, aesthetic (asks
  player to pick: retro terminal / minimalist / bold & colorful). This becomes a
  real artifact they can use in later lessons.

- **C) Personality file:** Claude creates `baby-claude-adventure/CLAUDE.md` written
  in Baby Claude's voice: "Hi future me! I'm Baby Claude. I was raised by [player
  name]. I like [things from the adventure]. When I grow up I want to be a great PM
  assistant."

**Capability unlocked:** Persistent Memory (CLAUDE.md)

```
  ┌──────────────────────────────────┐
  │  ABILITY UNLOCKED:              │
  │  🧠 Memory (CLAUDE.md)          │
  └──────────────────────────────────┘
```

After: Return to hub.

---

### HUB (Between Regions)

Every time the player returns to the hub, Claude shows:

```
═══════════════════════════════════════════════════════════
  THE NEST — Adventure Hub

  Abilities: [icons of unlocked abilities]
  Regions explored: X/5
  Artifacts created: [list of real files]

  ┌─ Available Paths ─────────────────────────────────┐
  │                                                    │
  │  [only shows unvisited regions + Final Evolution   │
  │   if 3+ regions complete]                          │
  │                                                    │
  └────────────────────────────────────────────────────┘

  Where to next?
═══════════════════════════════════════════════════════════
```

---

### FINAL EVOLUTION (Combine All — requires 3+ capabilities)

**Decision point:**

```
Baby Claude starts glowing...

"I can feel all my abilities COMBINING. I'm ready to build
something REAL. Something that uses EVERYTHING I've learned.

What should my masterpiece be?"

  A) A PM Command Center — a dashboard with all my artifacts, interactive
     terminal, and links to everything I built
  B) A Baby Claude Portfolio — a showcase of the adventure with animations,
     the story of how I grew up, and my graduation ceremony
  C) A Tool for the Player — something actually useful: a meeting notes
     template generator, a sprint planning tool, or a decision log
```

**What each choice produces:**

All three produce a multi-file project in `baby-claude-adventure/` that:
- Reads CLAUDE.md (or style guide) for personalization (Read capability)
- Creates 2-3 new files (Create capability)
- Writes substantial HTML/CSS/JS (Edit capability)
- Opens the result in the browser (Run capability)
- References the ASCII art or other artifacts from earlier (Context)

**A) PM Command Center:**
Creates `baby-claude-adventure/command-center.html`:
- Dark-themed dashboard
- Sidebar listing all created artifacts (with real file names)
- Embedded interactive terminal (JS) that responds to commands:
  `help`, `abilities`, `files`, `whoami`, `history`
- Ability progress visualization
- Links to open each artifact

**B) Baby Claude Portfolio:**
Creates `baby-claude-adventure/portfolio.html`:
- Animated "boot sequence" that types out the story of the adventure
- Each chapter corresponds to a region the player visited (dynamic based on
  their actual path)
- ASCII art from the Gallery embedded in the page (if they visited)
- Graduation animation at the end
- Personalized with their name and choices

**C) Tool for the Player:**
Creates `baby-claude-adventure/pm-tool.html`:
- A genuinely useful single-page app
- Meeting notes template with auto-generated sections
- Sprint planning calculator
- Decision log with pros/cons columns
- Styled according to CLAUDE.md preferences (if they exist)
- Actually useful after the game ends

---

## 4. Capability Unlock & Combination Map

```
VISIT ORDER IS FLEXIBLE — these are the capabilities, not the sequence:

┌──────────────┐     ┌──────────────┐     ┌──────────────┐
│  🎨 ASCII    │     │  👀 Read     │     │  📄 Create   │
│  (Gallery)   │     │  (Cave)      │     │  📝 Edit     │
│              │     │              │     │  (Workshop)  │
└──────┬───────┘     └──────┬───────┘     └──────┬───────┘
       │                    │                    │
       │                    ▼                    │
       │             ┌──────────────┐            │
       │             │  🧠 Memory   │            │
       │             │  (Garden)    │            │
       │             │  requires:   │            │
       │             │  Read        │            │
       │             └──────┬───────┘            │
       │                    │                    │
       │              ┌─────▼──────┐             │
       │              │ 🖥️ Run     │             │
       │              │ (LaunchPad)│             │
       │              │ requires:  │             │
       │              │ any HTML   │             │
       │              │ artifact   │             │
       │              └─────┬──────┘             │
       │                    │                    │
       └────────────────────┼────────────────────┘
                            │
                     3+ unlocked
                            │
                     ┌──────▼───────┐
                     │  🌟 EVOLVE   │
                     │  (Final)     │
                     └──────────────┘
```

### Combination effects (earlier choices affect later regions):

| If you did...         | Then later...                                         |
|-----------------------|-------------------------------------------------------|
| Gallery first         | Workshop can reference your ASCII art in the HTML     |
| Cave first            | Workshop can use info it learned from reading files   |
| Gallery + Cave        | Memory Garden can include your art + scroll answers   |
| Workshop + any HTML   | Launch Pad immediately opens your creation            |
| Any 3 regions         | Final Evolution weaves ALL your artifacts together    |

---

## 5. What Claude Actually Builds (Artifact Map)

Every playthrough produces real files. Here's the complete artifact map:

```
baby-claude-adventure/
├── [Gallery artifacts — pick 1]
│   ├── self-portrait.txt        (option A)
│   ├── name-banner.txt          (option B)
│   └── map.txt                  (option C)
│
├── [Cave artifacts — pick 1]
│   ├── mysterious-scroll.md     (option A — filled in with player answers)
│   ├── meta-discovery.md        (option B — Claude's observations about itself)
│   └── exploration-log.md       (option C — directory listing narrative)
│
├── [Workshop artifacts — pick 1]
│   ├── homepage.html            (option A)
│   ├── pm-cheatsheet.md         (option B)
│   └── mini-game.html           (option C)
│
├── [Memory Garden artifacts — pick 1]
│   └── CLAUDE.md                (all options — different content)
│
├── [Final Evolution — pick 1]
│   ├── command-center.html      (option A)
│   ├── portfolio.html           (option B)
│   └── pm-tool.html             (option C)
│
└── [Launch Pad creates no new files — it runs/opens existing ones]
```

**Minimum files per playthrough:** 3-4 (skip some regions, go straight to Final)
**Maximum files per playthrough:** 6 (visit all regions + Final Evolution)

---

## 6. "Wow" Moments and Escalation

The wow moments escalate from "instant terminal magic" to "it built a whole app":

```
WOW LEVEL 1 — "It drew something!" (Gallery)
  ┃  ASCII art appears in the terminal. Instant. No files to open.
  ┃  Elapsed time: ~30 seconds into the game.
  ┃  Emotional hit: delight, surprise
  ┃
WOW LEVEL 2 — "It read my stuff!" (Cave)
  ┃  Claude reads a file and quotes it back, or reads the game's own
  ┃  source code. Player realizes it can see their filesystem.
  ┃  Emotional hit: "oh wait, this is different from ChatGPT"
  ┃
WOW LEVEL 3 — "It built a real file!" (Workshop)
  ┃  Claude writes a complete HTML page or useful document.
  ┃  Player can open it and it works.
  ┃  Emotional hit: "it just wrote code for me"
  ┃
WOW LEVEL 4 — "It opened my browser!" (Launch Pad)
  ┃  Claude runs a command and their creation appears in the browser.
  ┃  Player realizes Claude can DO things, not just write things.
  ┃  Emotional hit: "it controls my computer"
  ┃
WOW LEVEL 5 — "It remembered me!" (Memory Garden)
  ┃  Claude creates CLAUDE.md with personalized content.
  ┃  Player realizes this persists across conversations.
  ┃  Emotional hit: "it's not stateless"
  ┃
WOW LEVEL 6 — "It built a whole app using everything!" (Final Evolution)
     Claude combines read + create + edit + run + memory into a
     multi-file interactive project. Opens in browser. It works.
     Emotional hit: "I just built a real thing with 5 choices"
```

---

## 7. Different Playthroughs, Different Outcomes

### Playthrough A: "The Artist" (Gallery-first path)
```
Nest → Gallery (self-portrait) → Workshop (homepage with art) →
  Launch Pad (open in browser) → Final Evolution (portfolio)
```
- Artifacts: self-portrait.txt, homepage.html (with embedded ASCII art),
  portfolio.html
- Skips: Cave, Memory Garden
- Vibe: visual, creative, expressive
- Time: ~10 minutes

### Playthrough B: "The Explorer" (Cave-first path)
```
Nest → Cave (read own source code) → Gallery (adventure map) →
  Memory Garden (adventure memory) → Workshop (tiny game) →
  Launch Pad (open game) → Final Evolution (command center)
```
- Artifacts: meta-discovery.md, map.txt, CLAUDE.md, mini-game.html,
  command-center.html
- Vibe: thorough, curious, completionist
- Time: ~15 minutes

### Playthrough C: "The Builder" (Workshop-first path)
```
Nest → Workshop (PM cheat sheet) → Cave (look around filesystem) →
  Launch Pad (open files) → Final Evolution (PM tool)
```
- Artifacts: pm-cheatsheet.md, exploration-log.md, pm-tool.html
- Skips: Gallery, Memory Garden
- Vibe: practical, utilitarian, gets-things-done
- Time: ~10 minutes

### Playthrough D: "The Completionist"
```
Nest → Gallery → Cave → Workshop → Memory Garden →
  Launch Pad → Final Evolution
```
- All artifacts created. Maximum files. Longest path.
- Final Evolution references everything.
- Time: ~15 minutes

### What changes between playthroughs:
1. **Different files on disk** — each path produces a unique set of artifacts
2. **Different Final Evolution content** — the capstone project references only
   the artifacts that exist, making each version unique
3. **Different capability order** — the "aha" moments hit in different sequences
4. **Different personalization** — name, colors, preferences carry forward
5. **CLAUDE.md only exists if they visit Memory Garden** — future course lessons
   can reference this ("remember when you created CLAUDE.md in Baby Claude?")

---

## 8. Graduation Screen (Updated)

The graduation screen should be dynamic based on the player's path:

```
╔════════════════════════════════════════════════════════════╗
║                                                            ║
║            GRADUATION DAY                                  ║
║                                                            ║
║           ╭──────────────╮                                 ║
║           │   ^          │                                 ║
║           │   @ @        │                                 ║
║           │    v         │    "I'm all grown up!"          ║
║           │   \___/      │                                 ║
║           ╰──────────────╯                                 ║
║                                                            ║
║   YOUR ADVENTURE:                                          ║
║   [dynamically lists regions visited in order]             ║
║                                                            ║
║   YOUR ARTIFACTS:                                          ║
║   [dynamically lists every file created with real paths]   ║
║                                                            ║
║   ABILITIES UNLOCKED:                                      ║
║   [only the ones they actually unlocked]                   ║
║                                                            ║
║   WHAT YOU LEARNED:                                        ║
║   Claude Code has 4 core abilities:                        ║
║     Read files    — it sees your project                   ║
║     Create files  — it makes new things                    ║
║     Edit files    — it writes real content                 ║
║     Run commands  — it acts on your computer               ║
║                                                            ║
║   Everything in this course — every prototype, every       ║
║   workflow, every tool — is a combination of these four.   ║
║                                                            ║
║   The agent loop: Think → Tool → Observe → Repeat         ║
║                                                            ║
║   Go look at baby-claude-adventure/ — those files are      ║
║   real, on your real computer, and they work.              ║
║                                                            ║
╚════════════════════════════════════════════════════════════╝
```

---

## 9. Implementation Notes

### Character voice
Baby Claude should still be cute, enthusiastic, and slightly confused. Use emoji
sparingly (not every sentence). Use ASCII art generously. The personality evolves
as capabilities unlock — starts confused, becomes confident, ends proud.

### Error handling
- If a command fails, stay in character ("My wings glitched!") and continue.
- If the player goes off-script, gently redirect: "I don't know that path yet!
  Here's where I can go..." and re-show available options.
- If the player says "stop" or "quit," show a partial graduation with what they
  built so far.

### State tracking
Claude must track internally:
- Which regions have been visited
- Which artifacts have been created (by filename)
- Player's name (if provided)
- Player's preferences (color, style — if provided)
- Number of capabilities unlocked

This state determines: hub display, available paths, Final Evolution content,
and graduation screen.

### Timing budget (10-15 minutes total)
- Nest + first region: 3 minutes
- Each additional region: 2 minutes
- Final Evolution: 3 minutes
- Graduation: 1 minute
- Minimum path (3 regions + Final): ~10 minutes
- Maximum path (5 regions + Final): ~15 minutes
