# Vibe Coder Spec

### AI-Powered App Building for Non-Technical Founders

> "You describe the app. The AI builds it. And it does it right — every time."

You know what your app should do. You just don't know React from Rails. Vibe Coder handles all the technical decisions — stack, architecture, database, deployment — and explains every choice in plain English so you stay in control.

This is not a code generator. It is an **AI development partner** that builds real, tested, production-ready software from a conversation.

---

## Get Started (Step by Step)

Follow each step in order. Do not skip any step. Everything is done inside VS Code.

### Step 1: Install VS Code

VS Code is the code editor where all the work happens. You will not need to write code — the AI does that — but VS Code is where you talk to it.

1. Go to https://code.visualstudio.com/
2. Click the big **Download** button
3. Open the file you downloaded
4. Follow the installer — click **Next** on each screen, then click **Install**
5. When it finishes, open VS Code

### Step 2: Install Git

Git is a tool that downloads and tracks code. You need it to download this project.

1. Go to https://git-scm.com/downloads
2. Click the download for your operating system (Windows, Mac, or Linux)
3. Open the file you downloaded
4. Follow the installer — use the default options on every screen, click **Next**, then **Install**
5. When it finishes, restart VS Code if it is already open

**Check that Git is installed:**
1. In VS Code, open the terminal: press ``Ctrl + ` `` (the backtick key, above the Tab key on your keyboard)
2. Type this and press **Enter**:
   ```bash
   git --version
   ```
3. You should see something like: `git version 2.44.0`. If you see this, Git is installed.

### Step 3: Install Node.js

Node.js runs the development tools that build your app.

1. Go to https://nodejs.org/
2. Click the **LTS** download button (the one that says "Recommended")
3. Open the file you downloaded
4. Follow the installer — use the default options, click **Next**, then **Install**
5. Restart VS Code after installing

**Check that Node.js is installed:**
1. In the VS Code terminal, type:
   ```bash
   node --version
   ```
2. You should see something like: `v20.11.0`. The number must be 18 or higher.

### Step 4: Install Claude Code Extension

Claude Code is the AI agent that builds your app inside VS Code.

1. In VS Code, click the **Extensions** icon on the left sidebar (it looks like 4 small squares)
2. In the search box, type: `Claude Code`
3. Find **"Claude Code"** by Anthropic — click **Install**
4. Wait for the install to finish
5. You will see a **sparkle icon** appear in the top-right area of VS Code

> **You need an Anthropic account.** If you do not have one, go to https://claude.ai and create an account first.

### Step 5: Download This Project

Do this inside VS Code. Do not use a separate terminal.

1. In VS Code, open the terminal: press ``Ctrl + ` ``
2. Go to your Desktop (so the project saves there):
   ```bash
   cd Desktop
   ```
3. Download the project:
   ```bash
   git clone https://github.com/isagawa-co/vibe-coder-spec.git
   ```
4. Wait for the download to finish

### Step 6: Open the Project in VS Code

This step is important. Claude Code needs to be inside the project folder to work correctly.

1. In VS Code, click **File** > **Open Folder**
2. Find and select the `vibe-coder-spec` folder on your Desktop
3. Click **Select Folder** (Windows) or **Open** (Mac)
4. VS Code will reload with the project open
5. You should see the project files on the left sidebar (a folder called `.claude/`)

### Step 7: Set Up the AI Agent

This is a one-time setup. The AI reads the project, builds its own rules, and prepares to work.

1. Click the **sparkle icon** in VS Code to open Claude Code
2. Type this and press **Enter**:
   ```
   start
   ```
3. The AI will read the project and set itself up. This takes about 2 minutes.
4. When it finishes, you will see a message that says: **"Restart Claude Code to activate hooks"**
5. Close Claude Code (click the X or press `Ctrl+Shift+P` and type "Claude Code: Close")
6. Click the **sparkle icon** again to reopen Claude Code
7. Type:
   ```
   continue
   ```
8. The AI will anchor itself and confirm it is ready. You will see: **"ANCHORED"**

You are now ready to build your app.

### Step 8: Start Building — Discovery

This is where you describe your app idea. The AI will ask you questions one at a time to understand what you want to build.

1. In Claude Code, type:
   ```
   /vibe
   ```
2. The AI will ask: **"What do you want to build?"**
3. Describe your app in plain English. Be as specific as you can. For example:

   > "I want to build a meal planning app. Users sign up, enter their dietary preferences (vegan, keto, etc.), and get a weekly meal plan with recipes and a grocery list. They can swap out meals they don't like."

4. The AI will ask follow-up questions — **one at a time**. Answer each one honestly:
   - Who are your users?
   - What is the most important feature?
   - Do users need accounts?
   - Will it handle payments?
   - How many users do you expect?

5. When the AI has enough information, it will show you an **App Profile** — a summary of everything it understood about your app.

6. **Review the App Profile carefully.** The AI will ask: "Does this look right?"
   - If yes: type **yes** and the AI moves to the next phase
   - If something is wrong: tell it what to change (e.g., "No, it should also support family accounts")

> **This is the most important step.** The better you describe your app, the better the result. Take your time here.

### Step 9: Choose Your Tech Stack — Decisions

The AI now recommends the technology to build your app. You do not need to understand the tech — the AI explains each choice in plain English.

1. For each decision (language, framework, database, etc.), the AI will show you **2-3 options**:

   ```
   FRONTEND FRAMEWORK

   Option 1: Next.js
   Best for: Apps with many pages, SEO matters, content-heavy sites
   Tradeoff: More complex setup, but handles growth well

   Option 2: Vite + React
   Best for: Interactive apps, dashboards, single-page experiences
   Tradeoff: Simpler to start, but you add routing yourself

   Recommendation: Next.js — your meal planning app has multiple pages
   (recipes, meal plans, grocery lists) and benefits from fast page loads.

   Which do you prefer? (1, 2, or tell me what matters to you)
   ```

2. For each decision, pick a number or explain what matters most to you
3. After all decisions are made, the AI shows you the **Architecture Document** — a complete technical blueprint
4. Review and approve it. Type **yes** to proceed.

> **You are always in control.** The AI recommends, but you decide. If you are unsure, ask "what would you pick and why?" — the AI will give you a straight answer.

### Step 10: Plan Your Features — Roadmap

The AI creates a prioritized list of features to build.

1. The AI organizes features into tiers:
   - **P1 (Must Have):** Core features your app needs to work at all
   - **P2 (Should Have):** Important features that make the app complete
   - **P3 (Nice to Have):** Features you can add later

2. Each feature shows:
   - What it does
   - Which features it depends on (build order)
   - Estimated complexity

3. Review the roadmap. You can:
   - Move features between tiers
   - Remove features you do not need yet
   - Add features you forgot to mention

4. Type **yes** to approve the roadmap and start building.

### Step 11: Build the Foundation — Scaffold

The AI creates the project skeleton — folder structure, configuration files, and a working development server.

1. The AI will:
   - Create all project folders and config files
   - Install the packages your app needs
   - Set up the development server
   - Run a smoke test to make sure everything works

2. When it finishes, you will see: **"Scaffold complete. Dev server running."**

3. The AI runs `/kernel/domain-setup` to set up enforcement rules based on YOUR architecture
4. You will see: **"Restart Claude Code to activate hooks"**
5. Close and reopen Claude Code, then type `continue`

> After this step, the AI enforces your architecture on itself. It cannot break its own rules.

### Step 12: Build Features — Feature Development

Now the AI builds your app, one feature at a time, from the roadmap.

1. For each feature, the AI:
   - Shows you a **Feature Plan** — what files it will create/modify, what tests it will write
   - Waits for your approval before writing any code
   - Builds the feature
   - Writes tests alongside the code
   - Runs the full test suite to catch any regressions
   - Shows you the result and asks you to try it

2. After each feature:
   - The AI asks: "Does this work as expected?"
   - If yes: it marks the feature complete and moves to the next one
   - If no: tell it what is wrong and it will fix it

3. Repeat for every feature in the roadmap.

> **You can stop at any time.** Your progress is saved. Type `/vibe` when you return and the AI picks up where you left off.

---

## How It Works

```
You describe your app idea
       |
       v
Phase 1: Discovery ---------> App Profile (what you want to build)
       |
       v
Phase 2: Decisions ----------> Architecture + Stack (how to build it)
       |                       AI explains every choice in plain English
       v
Phase 3: Roadmap ------------> Prioritized feature list (what to build first)
       |
       v
Phase 4: Scaffold -----------> Working project skeleton + dev server
       |                       AI enforces its own architecture from here
       v
Phase 5: Feature Dev --------> Features built one at a time with tests
  (repeats per feature)        You approve each one before the next starts
```

**Every transition requires your approval.** The AI never moves to the next phase without you saying "yes."

---

## What Makes This Different

| Typical AI Coding | Vibe Coder |
|-------------------|------------|
| Generates code, you figure out if it is right | Explains every decision in plain English |
| No architecture — just output | Generates architecture, then enforces it on itself |
| Same mistakes every session | Learns from every failure permanently |
| You need to know code to verify output | You verify by using the app, not reading code |
| Asks 10 questions at once | Asks one question at a time |
| Assumes what you want | Asks when uncertain, never guesses |

---

## Commands

| Command | What It Does | When to Use |
|---------|-------------|-------------|
| `/vibe` | Start or continue building your app | Beginning of every session |
| `/vibe-feature` | Build a specific feature from the roadmap | When you want to pick which feature to build next |
| `/on-failure` | Handle a failure with guided options | When something goes wrong |

---

## Project Structure

```
vibe-coder-spec/
├── .claude/
│   ├── commands/                         # Commands you can type
│   │   ├── vibe.md                       # /vibe — main entry point
│   │   ├── vibe-feature.md               # /vibe-feature — build specific feature
│   │   └── on-failure.md                 # /on-failure — failure handling
│   ├── lessons/                          # What the AI has learned
│   │   ├── lessons.md                    # Lesson index
│   │   └── vibe-coder/                   # Domain-specific lessons
│   │       ├── discovery.md              # Lessons from Phase 1
│   │       ├── stack-decisions.md        # Lessons from Phase 2
│   │       ├── scaffold.md              # Lessons from Phase 4
│   │       └── feature-dev.md            # Lessons from Phase 5
│   └── skills/
│       └── vibe-coder/                   # The domain spec (AI rulebook)
│           ├── SKILL.md                  # Identity, vocabulary, rules
│           ├── workflow.md               # Phase flow and data flow
│           ├── gate-contract.md          # Quality gates
│           ├── phases/                   # Phase-specific instructions
│           │   ├── phase-01-discovery.md # Conversational intake
│           │   ├── phase-02-decisions.md # Stack/architecture decisions
│           │   ├── phase-03-roadmap.md   # Feature prioritization
│           │   ├── phase-04-scaffold.md  # Project setup
│           │   └── phase-05-feature.md   # Feature development loop
│           ├── checkpoints/              # Human approval gates
│           │   ├── architecture-review.md
│           │   ├── decision-review.md
│           │   ├── feature-complete.md
│           │   ├── on-failure.md
│           │   └── pre-build.md
│           ├── _decision-trees/          # Stack recommendation logic
│           │   ├── frontend-stack.md
│           │   ├── backend-stack.md
│           │   └── database-stack.md
│           └── _templates/               # Document templates
│               ├── architecture-doc.md
│               ├── decision-record.md
│               ├── feature-spec.md
│               ├── product-roadmap.md
│               └── stack-profile.md
└── README.md
```

---

## What Gets Generated

As you work through the phases, the AI creates these files in your project:

| Phase | What Gets Created | Where |
|-------|------------------|-------|
| Discovery | App Profile | `_generated/app-profile.md` |
| Decisions | Architecture Document | `_generated/architecture.md` |
| Decisions | Stack Profile | `_generated/stack-profile.md` |
| Decisions | Decision Records | `_generated/decisions/*.md` |
| Roadmap | Product Roadmap | `_generated/product-roadmap.md` |
| Scaffold | Project files | `src/`, `tests/`, config files |
| Feature Dev | Feature specs | `_generated/features/*.md` |
| Feature Dev | App code + tests | `src/[feature]/`, `tests/[feature]/` |

---

## The Kernel (Enforcement Engine)

The Isagawa Kernel runs inside the AI agent. It is what makes the AI follow the rules instead of just generating whatever it wants.

### What It Does

1. **Self-builds** — On first run, the kernel reads the spec and builds its own enforcement protocol
2. **Self-enforces** — Every 10 actions, the AI re-reads its rules to stay on track
3. **Self-improves** — After every mistake, the AI updates its rules permanently

### Why It Matters

Without enforcement, AI coding tools:
- Forget your architecture after a few messages
- Make the same mistakes every session
- Generate code that does not match what they generated 5 minutes ago

The kernel prevents all of this. The AI cannot bypass its own rules — hooks block any action that violates the protocol.

---

## FAQ

**Do I need to know how to code?**
No. The AI handles all technical decisions. You describe what you want in plain English.

**What kind of apps can I build?**
Web applications — dashboards, marketplaces, SaaS tools, internal tools, content platforms, and more. The AI picks the right tech stack based on what you describe.

**How long does it take to build an app?**
Depends on complexity. A simple app (5-10 features) can be scaffolded and have core features working in a few hours. Larger apps take longer but the AI handles the hard parts.

**Can I stop and come back later?**
Yes. Your progress is saved. Type `/vibe` when you return and the AI picks up where you left off.

**What if the AI makes a mistake?**
The AI stops on any failure and asks you how to proceed. After fixing the issue, it records a lesson so the same mistake never happens again.

**Do I need to pay for Claude?**
Yes, you need an Anthropic account with Claude Code access. See https://claude.ai for pricing.

---

## Services

We help non-technical founders turn app ideas into working software using the Vibe Coder spec and Claude Code. The AI builds the app — we make sure it is built right.

**[alain@isagawa.co](mailto:alain@isagawa.co)** | **[DM on LinkedIn](https://www.linkedin.com/in/alain-ignacio-54b9823)**

---

## License

[MIT](LICENSE) — Copyright (c) 2025 Isagawa

---

Built with the [Isagawa Kernel](https://github.com/isagawa-co/isagawa-kernel) — self-building, self-improving, safety-first.
