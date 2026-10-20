# Ultimate Vibe Experience (UVE Coding Strat)

<p align="center">
  <img src="https://badgen.net/badge/Template%20Version/V7.0/blue" height="30" alt="Template V7.0"/>
  <img src="https://badgen.net/badge/AI%20Personas/8/red" height="30" alt="AI Personas 8"/>
  <img src="https://badgen.net/badge/Memory%20Layers/7/purple" height="30" alt ="Memory Layers 7"/>
</p>

<p align="center">
  <strong>Want this kind of </strong> <del>vibing</del> <strong>coding experience? (Y/n):</strong>
</p>

---

## Quick Links

[What's this for?](#whats-this-for) | [How to Use?](#how-to-use-persona-triggers) | [Problem We Solve](#the-problem-we-solve) | [Memory Layers](#memory-layers) | [Folder Structure](#folder-structure-on-opencode-template) | [Installation](#installation-guide) | [FAQ](#faq) | [Usages](#own-usages) | [Template Compression](#template-compression-v50-baseline)

---

## Recent Updates

<details>
<summary>Show updates</summary>

1. **v7.0 — one rules file, smarter backups:** `.clinerules` and `system_instructions.md` merged into a single `instructions.md` per template. Same rules, one place, no contradictions. `-obsidian` now asks for your vault paths once, stores them in `project_memory.md`, copies only changed files, and writes a graph hub note named after your project. Tone matching added.

---

2. **Claude Code template (6.0):** Added a native `.claude/` template so the workflow runs on Claude Code too. Same 8 personas, same flags, same memory system — nothing dropped.

---

3. **Obsidian sync:** `-obsidian` turns your project logs into a graph-ready backup. The first run asks for two paths — your vault root and your backup root — and saves both in `project_memory.md`, editable by hand any time. Every run after that compares each file and copies only what changed, reports what it skipped, and asks before deleting anything. A hub note named after your project links every backup, so the project sits at the center of the graph.

---

4. **Updating from an older version:** Versions 6.0 and below ship two rule files instead of `instructions.md`. If your template already has the `-update` flag, just run it — it overwrites the rules, deletes the obsolete files, and keeps your memory logs and `workspace.json` identity.

```
-update
```

Still on 4.0 or below with no `-update` section? Copy the `-update` row from the [how to use](#how-to-use-persona-triggers) table, paste it to your agent, then include `-update` in your prompt. Once only.

</details>

---

## Template Compression (v5.0 baseline)

>From v5.0 to current

_File names below are the ones measured at v5.0. `.clinerules` and `system_instructions.md` were merged into a single `instructions.md` in 7.0._

> 7.0: 16.7KB → 15.0KB in one file, 17 duplicate rules removed, 3 contradictions fixed.

### Rules & Skills

| File                     | Before     | After      | Saved   |
| ------------------------ | ---------- | ---------- | ------- |
| `.clinerules`            | 26.9KB     | 9.1KB      | 66%     |
| `system_instructions.md` | 24.3KB     | 6.0KB      | 75%     |
| `orchestrator/SKILL.md`  | 10.6KB     | 3.2KB      | 69%     |
| `tester/SKILL.md`        | 7.3KB      | 2.9KB      | 60%     |
| 6 other skills           | 21.4KB     | 6.7KB      | 69%     |
| **Subtotal**             | **84.5KB** | **27.9KB** | **66%** |

### Memory & Archives

| File                       | Before     | After      | Saved   |
| -------------------------- | ---------- | ---------- | ------- |
| `codebase_map.md`          | 8.9KB      | 5.2KB      | 42%     |
| `project_memory.md`        | 3.8KB      | 1.5KB      | 61%     |
| `test_memory.md`           | 2.8KB      | 1.2KB      | 57%     |
| `security_memory.md`       | 2.2KB      | 1.1KB      | 50%     |
| `review_memory.md`         | 2.1KB      | 1.0KB      | 52%     |
| `error_memory.md`          | 1.9KB      | 0.9KB      | 53%     |
| `implementation_memory.md` | 1.4KB      | 0.7KB      | 50%     |
| 5 archive files            | 1.0KB      | 0.5KB      | 50%     |
| **Subtotal**               | **24.2KB** | **11.3KB** | **53%** |

### Total Impact (per template)

| Category          | Before      | After      | Saved   | Tokens Saved |
| ----------------- | ----------- | ---------- | ------- | ------------ |
| Rules + Skills    | 84.5KB      | 27.9KB     | 66%     | ~14,100      |
| Memory + Archives | 24.2KB      | 11.3KB     | 53%     | ~3,200       |
| **Grand Total**   | **108.7KB** | **39.2KB** | **64%** | **~17,300**  |

> Every context reload, every flag trigger, every `-setup` run reads these files. **64% less tokens burned per read.**

### What Changed

- Notation legend (MUST/BAN/CRIT/CMD/SAME) replaces verbose phrases
- Two rule files merged into one `instructions.md`, duplicates removed
- Resolution mandates consolidated (4 blocks → 1)
- SKILL.md personas trimmed to role + rules only
- Memory file preambles shortened, duplicate rules removed
- Archive status blocks compressed
- Timestamp fallback (PowerShell/Bash/Node.js)
- Tool discovery with web search for test frameworks

### What Stayed

- All rules, flows, and behavioral constraints unchanged
- Section header names preserved (fixed system labels)
- Entry formats preserved (`### [ERR-001]`, `### [RESOLVED]`, etc.)
- LIFO sorting rules intact
- Archive threshold (10 entries) unchanged

---

## What's this for?

AI coding tools forget your project fast. They read too many files, fill up context, and lose track of what they built last session.

This template adds a **memory layer** to your project. It gives the AI strict rules, specialized roles, and lightweight markdown files to track its own progress.

**Why workspace-level, not global?** Global rules mix all your projects together. Old project data leaks into new ones. Workspace rules keep each project isolated and clean.

---

## The Problem We Solve

### Key Differences

| Aspect                | Without Template            | With UVE Coding Strat      |
| :-------------------- | :-------------------------- | :------------------------- |
| **Memory**            | Lost after context reset    | Saved in markdown files    |
| **Token Usage**       | Reads entire repo each time | Only reads relevant memory |
| **AI Behavior**       | Generic, no specialization  | 8 specialized personas     |
| **Session Recovery**  | Re-explain everything       | Type `-setup` to restore   |
| **Project Isolation** | Global rules cause leaks    | Workspace-level isolation  |

---

## Memory Layers

Your project stores memory in simple markdown files. The AI reads them when needed.

| File                       | Purpose                               |
| :------------------------- | :------------------------------------ |
| `project_memory.md`        | Task tracker (permanent)              |
| `error_memory.md`          | Bug traces and fix history            |
| `codebase_map.md`          | File index and tech stack (permanent) |
| `implementation_memory.md` | Architecture and feature flows        |
| `security_memory.md`       | Vulnerability tracking                |
| `review_memory.md`         | Code review findings                  |
| `test_memory.md`           | Test strategies and coverage          |

When any section passes 10 entries, the oldest are moved to `archives/`.

---

## Folder Structure (on .opencode template)

```text
Your-Project-Root/
└── .opencode/                          Root configuration directory for OpenCode.
    ├── rules/                          Core behavioral rules and task tracking.
    │   ├── instructions.md             All rules: boundaries, flags, personas, gates, skills.
    │   └── project_memory.md           Task tracker: objective, recent git changes, completed/blocked/next move.
    ├── memory/                         Specialized memory logs separated by concern.
    │   ├── error_memory.md             LIFO-sorted tracking for active and resolved bugs.
    │   ├── codebase_map.md             File directory index, tech stack, and logic paths.
    │   ├── implementation_memory.md    Architectural design maps and feature flows.
    │   ├── security_memory.md          Vulnerability tracking and threat modeling.
    │   ├── review_memory.md            Code review findings and severity classifications.
    │   └── test_memory.md              Test strategies, coverage analysis, and case docs.
    ├── archives/                       Pre-created archive files for overflow entries.
    │   ├── error_archive.md            Receives archived entries from error_memory.md
    │   ├── implementation_archive.md   Receives archived entries from implementation_memory.md
    │   ├── security_archive.md         Receives archived entries from security_memory.md
    │   ├── review_archive.md           Receives archived entries from review_memory.md
    │   └── test_archive.md             Receives archived entries from test_memory.md
    ├── skills/                         Modular on-demand task capabilities.
    │   ├── ask/
    │   │   └── SKILL.md                Read-only persona for architecture reviews.
    │   ├── coder/
    │   │   └── SKILL.md                Engineering persona for feature implementation.
    │   ├── debugger/
    │   │   └── SKILL.md                Forensic diagnostic persona for problem tracing.
    │   ├── orchestrator/
    │   │   └── SKILL.md                High-level task manager for multi-agent coordination.
    │   ├── planner/
    │   │   └── SKILL.md                Architectural blueprint leader for requirements.
    │   ├── reviewer/
    │   │   └── SKILL.md                Quality assurance persona for code reviews.
    │   ├── secure/
    │   │   └── SKILL.md                Safety exploit evaluator for vulnerability scores.
    │   └── tester/
    │       └── SKILL.md                Test architect for strategy and case generation.
    ├── workspace.json                  Workspace identity marker and initialization state.
    ├── AGENTS.md                       Skill execution mode registry and memory references.
    └── opencode.json                   OpenCode configuration pointing to instruction files.
```

_All templates share the same internal structure. Only the root folder name differs._

---

## How to Use? (Persona Triggers)

Use these triggers depending on the situations:

| Command / Flag | Type            | What it does                                                                                                      | Use Case                                                                                                                                 |
| :------------- | :-------------- | :---------------------------------------------------------------------------------------------------------------- | :--------------------------------------------------------------------------------------------------------------------------------------- |
| `-setup`       | Utility         | Updates all memory files at once.                                                                                 | First prompt or new chat session.                                                                                                        |
| `-o`           | Persona/Utility | Orchestrator - manages complex tasks.                                                                             | Multi-step plans or implementations. Use when you prompt big tasks. Click [here](#orchestrator-workflow--o) to see orchestrator workflow |
| `-p`           | Persona         | Planner - creates roadmaps, waits for approval.                                                                   | `-p describe your plan`                                                                                                                  |
| `-c`           | Persona         | Coder - writes production code.                                                                                   | After agreeing on a plan.                                                                                                                |
| `-d`           | Persona         | Debugger - traces errors.                                                                                         | `-d describe the error`                                                                                                                  |
| `-a`           | Persona         | Ask - read-only analysis.                                                                                         | Questions without code changes.                                                                                                          |
| `-s`           | Persona/Memory  | Security - threat modeling, safety rating (0-10).                                                                 | Check for data leaks or credential risks.                                                                                                |
| `-r`           | Persona/Memory  | Reviewer - code quality reviews (CRITICAL/HIGH/MEDIUM/LOW).                                                       | After code changes to check quality.                                                                                                     |
| `-t`           | Persona/Memory  | Tester - test strategies and coverage analysis.                                                                   | Before feature completion.                                                                                                               |
| `-clean`       | Utility         | Removes junk files and debug traces.                                                                              | Do clean up after debugging or testing.                                                                                                  |
| `-context`     | Memory          | Scans git (status/diff/unpushed) → fills Section 1. Updates `project_memory.md`.                                  | When project context changes.                                                                                                            |
| `-error`       | Memory          | Updates `error_memory.md` with bugs and fixes.                                                                    | Every debugging session.                                                                                                                 |
| `-codebase`    | Memory          | Updates `codebase_map.md` with file descriptions.                                                                 | Before deployment.                                                                                                                       |
| `-init`        | Utility         | Initializes `workspace.json`.                                                                                     | First-time setup.                                                                                                                        |
| `-archive`     | Utility         | Appends the oldest entries to `archives/*.md` once a section passes 10.                                            | When memory files get too large.                                                                                                         |
| `-obsidian`    | Utility         | Incremental vault backup. Asks for your vault path once, stores it in `project_memory.md`, then copies only changed files.           | Sync workflow logs to Obsidian.                                                                                                          |
| `-update`      | Utility         | Fetches this current repository for newest updates of the templates while preserving logs and workspace identity. | Keep your workflow templates current with the upstream repo.                                                                             |

### Why Manual Triggers Instead of Auto-Updates?

The AI cannot update memory files on its own. You must type the flags manually.

- **Saves tokens and money.** Auto-updates read your entire repo on every message.
- **You control personas.** You decide when the AI switches roles.
- **Prevents hallucination.** The AI won't rewrite memory mid-task and get confused.
- **Easy session recovery.** Type `-setup` in a new chat to restore context.

---

## Orchestrator Workflow (-o)

| Step | Stage        | What Happens                                            |
| :--: | :----------- | :------------------------------------------------------ |
|  1   | **PLAN**     | Suggests modern tools, explains WHY, asks your approval |
|  2   | **CODE**     | Implements after you approve each tool choice           |
|  3   | **TEST**     | Runs typecheck, lint, Vitest, Playwright, coverage      |
|  4   | **DEBUG**    | Fixes failures, explains bugs in simple terms           |
|  5   | **SECURE**   | Checks OWASP Top 10, suggests security tools            |
|  6   | **DEBUG**    | Second pass for hidden or newly introduced issues       |
|  7   | **TEST**     | Second pass to verify all fixes are clean               |
|  8   | **CLEAN**    | Removes debug artifacts, suggests ESLint/Prettier       |
|  9   | **REVIEW**   | Quality check with severity ratings                     |
|  10  | **DOCUMENT** | Writes summary for your project docs or thesis          |
|  11  | **ASK**      | "Fix findings? New task? Questions?"                    |

Loops back if tests fail or security issues are found. The AI never moves to the next step without your **approval**.

---

## Installation Guide

### Step 1: Download

```bash
git clone https://github.com/worriee/uveworkflow.git
```

### Step 2: Pick Your Folder

| AI Tool             | Folder        |
| :------------------ | :------------ |
| Cline               | `.clinerules` |
| Roo Code / Zoo Code | `.roo`        |
| Kilo Code           | `.kilo`       |
| OpenCode            | `.opencode`   |
| Pi                  | `.pi`         |
| Claude Code         | `.claude`     |

_\*this will work in any platforms if you can make the agent read these folders_

### Step 3: Paste Into Your Project

Copy the folder into your project root (same level as `src/` or `app/`).

```
your-project/
├── src/
├── package.json
├── .opencode/    <-- paste here
```

### Step 4: Move Root Files

| Tool       | Files to Move                   |
| :--------- | :------------------------------ |
| OpenCode   | `AGENTS.md` and `opencode.json` |
| Kilo       | `AGENTS.md` and `kilo.json`     |
| Pi         | `AGENTS.md`                     |
| Claude Code| `CLAUDE.md`                     |

```
your-project/
├── src/
├── package.json
├── .opencode/
├── AGENTS.md     <-- move here
├── opencode.json <-- move here
```

These files must be in your project root, not inside the template folder.

### Step 5: Start

Type `-setup` in your AI Agent. It will read the template and learn your project.

> incase `-setup` won't work prompt this instead:\
> @AGENTS.md read your rules and follow them strictly.

---

## FAQ

<details>
<summary>Show Questions</summary>

**Q: What happens if I forget to type a memory flag manually?**
<br>The AI will still write code normally, but it won't update its internal progress tracking logs. If your chat session expires or resets, the AI won't know where you left off. Just type the correct flag (`-context`, `-error`, etc.) on your next prompt to sync it up.

**Q: Why can't the AI just update the memory files on its own every time?**
<br>Because reading and rewriting the whole memory layout on every single message uses a massive amount of tokens, which costs you more money. It also slows down the AI and makes it prone to messing up active code instructions when it gets confused during bug fixes.

**Q: Will the AI create extra folders or clutter my project?**
<br>No. A strict rule stops the AI from creating any new folders inside the template directory. It is only allowed to read and edit the existing memory files within the designated `memory/` folder.

**Q: I am starting a completely new chat session. What do I type first?**
<br>Type `-setup`. This tells the AI to read the local memory logs immediately so it gets the exact context of your project without you having to re-explain everything.

**Q: I use OpenRouter free models and the AI keeps forgetting things mid-chat. Is this normal?**
<br>Yes, free or smaller API models often have smaller context limits or weaker memory retention. If the AI starts acting lost or forgets instructions, just run `-setup` again in a fresh prompt to force-reload its brain with your project context.

**Q: What if I have a huge project plan or database design map? Where should the AI save it?**
<br>Don't let the AI make random markdown files on your root directory. It is strictly instructed to log all architectural roadmaps, system flows, and complex feature plans inside the template's `memory/implementation_memory.md` using the standardized flow format.

**Q: Can I mix persona flags with memory flags in the same prompt?**
<br>Yes! If you want the AI to analyze a bug and update your logs simultaneously, you can type something like `-d here is the error trace, please fix it and run -error`. The AI will adopt the Debugger mindset and update your error memory file at the same time.

**Q: Do I need to copy the configuration folder into every single project workspace?**
<br>Yes. This configuration runs on a workspace level instead of global rules. This guarantees that your different projects don't leak context, history, or code descriptions into each other.

**Q: What should I do if the AI keeps hallucinating old errors that I already fixed?**
<br>Make sure to run the `-error` command regularly when debugging. The template forces the AI to look at historical resolved bugs inside `error_memory.md` so it remembers exactly how they were handled and won't try to reuse old broken logic.

**Q: Can I use this setup with VS Code or other platforms like Antigravity or Opencode CLI?**
<br>Yes it works even in different platforms as long as you can make the AI agent look or read to this specific folder. It won't have the same automated behavior if your AI agent doesn't have the ability to look for workspace-level rule files.

**Q: What is the difference between `project_memory.md` and the files in the `memory/` folder?**
<br>`project_memory.md` holds objective, recent git changes (diffs, new files, unpushed commits), completed work, blockers, next move, and relevant files. All specialized logs (errors, security vulnerabilities, code reviews, test strategies, implementation flows, and codebase maps) live in separate files inside the `memory/` folder to keep concerns isolated.

**Q: How do the Reviewer (`-r`) and Tester (`-t`) personas work with the memory system?**
<br>When you use `-d`, `-r`, `-t`, or `-s`, the AI scans the repo, writes its findings to the matching memory file first, shows you the list, then stops. It does not fix anything until you approve. `-a` and `-p` never write to memory.

**Q: What happens when a memory file has too many entries?**
<br>When any section passes 10 entries, the oldest are appended to the matching file in `archives/`. The 10 newest stay in the active file. No new files are created. This prevents context bloat while preserving complete history.

**Q: What is the `workspace.json` file for and do I need to configure it?**
<br>`workspace.json` is the workspace identity marker. On first use, the AI detects it says `"uninitialized"`, prompts you for a project name, and writes the initialized values. After that, it prevents re-initialization conflicts. You don't need to edit it manually — the AI handles it during `-setup`.

**Q: Where does `-obsidian` write my files?**
<br>Wherever you told it once. The first time you run `-obsidian` it asks two questions: your vault root (the folder that contains `.obsidian/`) and your backup root (defaults to `<vault>/Memory`). Both are saved in `project_memory.md` under Important Details. You can edit those two lines by hand any time, and the AI will use the new paths next run. Later runs compare each file and copy only what changed, so nothing is duplicated.

**Q: Why is there one rules file now instead of two?**
<br>`.clinerules` and `system_instructions.md` said many of the same things in slightly different words, and they had already started disagreeing with each other. They are now merged into `instructions.md`, with each rule appearing once. Fewer files, fewer tokens, no contradictions.

</details>

---

## Own Usages

<details>
<summary>Show usage</summary>

<p align="center">
    <p><img src="assets/usage1.png" width="200"/></p>
    <p><img src="assets/usage2.png" width="200"/></p>
    <p><img src="assets/usage3.png" width="200"/></p>
    <p><img src="assets/usage4.png" width="200"/></p>
    <p><img src="assets/usage5.png" width="200"/></p>
</p>

</details>
