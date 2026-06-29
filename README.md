# Workspace Rules & Skills Template

Make your AI agent smarter, faster, and highly token-efficient! It stops the AI from guessing your code structure or forgetting past progress. Saves time when moving to other AI agents without re-explaining everything so that it understands current context.

---

## Quick Links

[Folder Structure](#folder-structure-on-roo-template) | [Prompt Triggers](#prompt-triggers-manual-commands) | [Installation Guide](#installation-guide) | [FAQ](#faq) | [Own Usages](#own-usages-of-roo-code)

---

## Recent Updates:

- Restructured memory system: separated specialized logs into dedicated `.roottemplate/memory/` folder with individual files for errors, security, reviews, tests, implementation flows, and codebase mapping.
- Added **Reviewer persona** (`-r`) for structured code quality reviews with severity-classified findings and architectural compliance checks.
- Added **Tester persona** (`-t`) for test strategy design, test case generation, and coverage gap analysis.
- Implemented **Memory Archive Protocol**: when any tracked section exceeds 10 entries, oldest logs are automatically archived to `.roottemplate/archives/` to prevent context bloat while preserving history.
- Added **Workspace Initialization Protocol** with `workspace.json` that identifies which project is using the template and prevents re-initialization conflicts.
- Optimized all four templates (Cline, Roo, Kilo, OpenCode) to use consistent folder structures and path references within their respective root directories.

---

## You can use this template for:

- Cline [cline.bot] (use .clinerules folder)
- Roo Code [roocode.com] (use .roo folder)
- Zoo Code [Zoo Code Organization] (use .roo folder here since it's a community forked roo after its shutdown in vscode extension migrating to Roomote)
- Kilo Code [kilocode.ai] (use .kilo folder)
- OpenCode CLI (use .opencode folder)

_(or in any ai agent you're currently working with across platforms as long as you'll able to make the ai read these files.)_

---

## What is this Template For?

By default, AI coding assistants can quickly fill up your context window by reading too many files or repeating large blocks of code. They can also forget what they did in a previous chat session.

This template builds an **AI Memory Layer** inside your local project. It forces the AI to follow strict project rules, adopt specialized roles (like Coder or Debugger), and track its own progress in small, lightweight markdown files.

**Why Workspace instead of Global Directory?:** Global enforce a single memory layout across all projects. This causes critical context contamination, as memory files from prior projects leak into new ones upon initialization. Workspace rules isolate project documentation strictly within the local directory, ensuring that the AI’s contextual understanding remains perfectly aligned with the current workspace.

---

## Folder Structure (on .opencode template)

Here is a visual map of how every file works together to manage your AI assistant:

```text
Your-Project-Root/
└── .opencode/                      # The dedicated root configuration directory for OpenCode.
    ├── rules/                      # Core behavioral rules and task tracking.
    │   ├── .clinerules             # Primary recovery ground truth during context loss.
    │   ├── system_instructions.md  # System operational limitations, token management, and flag behaviors.
    │   └── project_memory.md       # Master task tracker for active milestones, completed work, and pending items.
    ├── memory/                     # Specialized memory logs separated by concern.
    │   ├── error_memory.md         # LIFO-sorted tracking ledger for active and historically resolved bug traces.
    │   ├── codebase_map.md         # Tracked files directory index, tech stack logs, and logic pathways.
    │   ├── implementation_memory.md # Architectural design maps, feature flows, and execution roadmaps.
    │   ├── security_memory.md      # Vulnerability tracking, threat modeling, and remediation plans.
    │   ├── review_memory.md        # Code review findings, quality assessments, and severity classifications.
    │   └── test_memory.md          # Test strategies, coverage analysis, and test case documentation.
    ├── skills/                     # Modular, on-demand task capabilities loaded dynamically via intent or flags.
    │   ├── ask/
    │   │   └── SKILL.md            # Read-only persona for architecture reviews and conceptual walkthroughs.
    │   ├── coder/
    │   │   └── SKILL.md            # Engineering persona for feature implementation without logic truncation.
    │   ├── debugger/
    │   │   └── SKILL.md            # Forensic diagnostic persona for systematic problem tracing and log analysis.
    │   ├── orchestrator/
    │   │   └── SKILL.md            # High-level task manager for step deconstruction and multi-agent coordination.
    │   ├── planner/
    │   │   └── SKILL.md            # Architectural blueprint leader tracking requirements before allowing code edits.
    │   ├── reviewer/
    │   │   └── SKILL.md            # Quality assurance persona for structured code reviews and best practices enforcement.
    │   ├── secure/
    │   │   └── SKILL.md            # Safety exploit evaluator mapping attack surfaces and vulnerability scores.
    │   └── tester/
    │       └── SKILL.md            # Test architect for strategy design, case generation, and coverage analysis.
    ├── archives/                   # Historical memory snapshots when sections exceed 10 entries.
    ├── workspace.json              # Workspace identity marker tracking project name and initialization state.
    ├── AGENTS.md                   # Skill execution mode registry and memory file location references.
    └── opencode.json               # OpenCode configuration pointing to instruction files.
```

_All four templates (.clinerules, .roo, .kilo, .opencode) share the same internal structure but use their respective root folder names for path references._

---

## Prompt Triggers (Manual Commands)

Type these prompts depending on these situations!

| Command / Flag | Type    | What it does / Purpose                                                                                                                                                         | Use Case                                                                                                                       |
| :------------- | :------ | :----------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :----------------------------------------------------------------------------------------------------------------------------- |
| `-o`           | Persona | **Orchestrator** - Managing massive, multi-step tasks and coordinating all personas simultaneously                                                                             | Prompting a general plan or massive implementation.                                                                            |
| `-p`           | Persona | **Planner** - Creates structured technical roadmaps and waits for approval before code changes                                                                                 | `-p [discuss your plan]`                                                                                                       |
| `-c`           | Persona | **Coder** - Writes clean, production-grade logic following codebase patterns                                                                                                   | Use this to act on agreed proposed plan from agent.                                                                            |
| `-d`           | Persona | **Debugger** - Deep root-cause error analysis and systematic tracing                                                                                                           | `-d [clearly state your error such as sending error logs]`                                                                     |
| `-a`           | Persona | **Ask** - Read-only code analysis and concept explanations                                                                                                                     | If you want to ask or clarify something without code modifications.                                                            |
| `-s`           | Persona | **Security Analyst** - Aggressive threat modeling, exploit evaluations, and code safety rating (0-10)                                                                          | Use to check for data leaks, credential risks, or black-market vulnerabilities without modifying core code.                    |
| `-r`           | Persona | **Reviewer** - Structured code quality reviews with severity classifications (CRITICAL/HIGH/MEDIUM/LOW) and architectural compliance checks                                    | Use after code implementation to validate quality, identify performance bottlenecks, or enforce best practices before merging. |
| `-t`           | Persona | **Tester** - Test strategy design, test case generation, and coverage gap analysis                                                                                             | Use before feature completion to plan unit/integration/E2E tests or analyze existing test coverage.                            |
| `-clean`       | Utility | **Clean Workspace** - Automated analysis and removal of unrelated junk files or redundant debugging traces                                                                     | Use to safely clean up diagnostic trash or non-functional file clutter while keeping active frontend/backend layers untouched. |
| `-setup`       | Utility | Dynamically inspects your whole workspace and updates all memory layers at once.                                                                                               | Use this on your very first prompt or whenever you start a brand new chat session!                                             |
| `-context`     | Memory  | Scans your current project structure and updates `project_memory.md` to record your active project workflow.                                                                   | Use when you update the context so the agent is aware of the current state. Also useful when migrating to other AI agents.     |
| `-error`       | Memory  | Analyzes active debugging traces and updates `error_memory.md` with current bugs, logs, and resolution steps. Records history of fixed errors to prevent hallucination.        | Every debugging session include `-error` in your prompt so it records resolved and current errors.                             |
| `-codebase`    | Memory  | Looks over your code layout and updates `codebase_map.md` with simple descriptions of your active application workflow. Records tech stack and explains purpose of every file. | Best practices: use this prompt when you're about to deploy or finished building your project.                                 |

---

## Why Manual Triggers Instead of Auto-Updates?

This template explicitly bans the AI from modifying its memory files in the background while it is generating code. You must type the flags manually to make it update its memory.

### Key Benefits of Manual Triggering:

- **Massive Token & Money Savings:** Automatic background updates force the AI to analyze, rewrite, and reread your entire repository structure on every single prompt. Manual syncing cuts out this massive token usage entirely since you will manage when to update the memory files.
- **Full Control of Personas:** You manually trigger personas on how you want the AI to act based on your prompt.
- **Prevents AI Hallucination:** If the AI rewrites its memory tracking layers during an active bug patch, it can get confused and mess up its instructions. Manual triggers give you total control over when the AI updates its project roadmap.
- **Clean Session Recovery:** If your context window resets or expires, simply type `-setup` in a fresh chat. The AI will read its lightweight memory logs and rebuild its mental map of your code instantly without needing you to re-explain anything.

---

## Installation Guide

### 1. Move to your downloads folder

```bash
cd Downloads
```

### 2. Clone the template repository

```bash
git clone https://github.com/worriee/clinerulestemplate.git
```

### Final Step:

Copy the [any template folder] from the cloned directory and paste it directly at the root of your current project workspace.

Start your very first prompt in AI agent using `-setup` and start your new workflow with this template 🔥.

### READ HERE IF YOU'RE USING KILO OR OPENCODE TEMPLATE

After you COPY the folder to your project ROOT DIRECTORY make sure you MOVE these files to the ROOT LEVEL also of your project. Make sure they aren't INSIDE the template folder or else this template WON'T WORK.

For OPENCODE:
<br>Move AGENTS.md & opencode.json to the root dir the same level as .opencode itself.

For KILO:
<br>Move kilo.json to the root the same level as .kilo template itself.

---

## FAQ

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
<br>Don't let the AI make random markdown files on your root directory. It is strictly instructed to log all architectural roadmaps, system flows, and complex feature plans inside `.opencode/memory/implementation_memory.md` using the standardized flow format.

**Q: Can I mix persona flags with memory flags in the same prompt?**
<br>Yes! If you want the AI to analyze a bug and update your logs simultaneously, you can type something like `-d here is the error trace, please fix it and run -error`. The AI will adopt the Debugger mindset and update your error memory file at the same time.

**Q: Do I need to copy the configuration folder into every single project workspace?**
<br>Yes. This configuration runs on a workspace level instead of global rules. This guarantees that your different projects don't leak context, history, or code descriptions into each other.

**Q: What should I do if the AI keeps hallucinating old errors that I already fixed?**
<br>Make sure to run the `-error` command regularly when debugging. The template forces the AI to look at historical resolved bugs inside `error_memory.md` so it remembers exactly how they were handled and won't try to reuse old broken logic.

**Q: Can I use this setup with VS Code or other platforms like Antigravity or Opencode CLI?**
<br>Yes it works even in different platforms as long as you can make the AI agent look or read to this specific folder. It won't have the same automated behavior if your AI agent doesn't have the ability to look for workspace-level rule files.

**Q: What is the difference between `project_memory.md` and the files in the `memory/` folder?**
<br>`project_memory.md` is your task tracker — it only holds active tasks, completed milestones, and pending items. All specialized logs (errors, security vulnerabilities, code reviews, test strategies, implementation flows, and codebase maps) live in separate files inside the `memory/` folder to keep concerns isolated and prevent any single file from becoming too large.

**Q: How do the Reviewer (`-r`) and Tester (`-t`) personas work with the memory system?**
<br>When you use `-r` or `-t`, the AI adopts the respective persona and performs its analysis. If you also include `-setup` or explicitly request logging, the findings are saved to `.opencode/memory/review_memory.md` or `.opencode/memory/test_memory.md` using the strict LIFO format with severity classifications and structured output templates.

**Q: What happens when a memory file has too many entries?**
<br>The archive protocol activates when any section exceeds 10 entries. The AI counts entries, extracts the oldest ones (bottom entries since LIFO places newest on top), creates an archive file in `.opencode/archives/` with a timestamped filename, and retains only the 10 most recent entries in the active section. This prevents context bloat while preserving complete history.

**Q: What is the `workspace.json` file for and do I need to configure it?**
<br>`workspace.json` is the workspace identity marker. On first use, the AI detects it says `"uninitialized"`, prompts you for a project name, and writes the initialized values. After that, it prevents re-initialization conflicts. You don't need to edit it manually — the AI handles it during `-setup`.

**Q: Can I use the Reviewer and Tester personas without saving logs to memory files?**
<br>Yes. The `-r` and `-t` personas work in read-only advisory mode by default. They only write to memory files when you explicitly include `-setup` in the prompt or directly request logging. This gives you full control over what gets persisted.

---

## Own Usages of Zoo Code

<p align="center">
    <img src="assets/usage1.png" width="200"/>
    <img src="assets/usage2.png" width="200"/>
    <img src="assets/usage3.png" width="200"/>
    <img src="assets/usage4.png" width="200"/>
    <img src="assets/usage5.png" width="200"/>
    <img src="assets/usage6.png" width="200"/>
    <img src="assets/usage7.png" width="200"/>
</p>
