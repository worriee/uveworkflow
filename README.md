## Recent Updates: 07/06/2026

- New Rule Added: Rule Folder Isolation - You are strictly forbidden from creating any new folders or files inside the `.roo/` directory. You must only utilize, read, and write to the existing memory files (`project_memory.md`, `error_memory.md`, and `codebase_map.md`).
- Context Memory Update: Added a new section in project_memory.md. 
<br>Section 6: DOCUMENTED IMPLEMENTATION PLANS & FEATURE FLOWS
<br>You are strictly commanded to use this section to log full architectural design maps, planned execution outlines, or documented system feature flows when requested. You must maximize this section to prevent creating cluttering outside files.

---

# Workspace Rules Template

Make your VS Code AI agent smarter, faster, and highly token-efficient! It stops the AI from guessing your code structure or forgetting past progress. Saves time when moving to other ai agents without re-explaining everything so that it understands current context.

---

## You can use this template if you use these vscode extensions:

- Cline [cline.bot]
- Roo Code [roocode.com]
- Zoo Code [Zoo Code Organization] (community forked roo after its shutdown in vscode extension migrating to Roomote)
- Kilo Code [kilocode.ai] (do check the exclusive guide for this in installation guide below)

---

## What is this Template For?

By default, AI coding assistants can quickly fill up your context window by reading too many files or repeating large blocks of code. They can also forget what they did in a previous chat session.

This template builds an **AI Memory Layer** inside your local project. It forces the AI to follow strict project rules, adopt specialized roles (like Coder or Debugger), and track its own progress in small, lightweight markdown files.

<b>Why Workspace instead of Global Rules?:</b> Global rules enforce a single memory layout across all projects. This causes critical context contamination, as memory files from prior projects leak into new ones upon initialization. Workspace rules isolate project documentation strictly within the local directory, ensuring that the AI’s contextual understanding remains perfectly aligned with the current workspace.

---

## Folder Structure & How It Works

Here is a visual map (based on updated roo code global rules directory) of how every file works together to manage your AI assistant:

```text
Your-Project-Root/
│
└── .roo/                                # Core configurations directory
    ├── rules/                           # Main instruction and memory files
    │   ├── .clinerules                  # Main configuration layout and boundaries
    │   ├── system_instructions.md       # Optimization rules and timezone settings
    │   ├── codebase_map.md              # [Memory] Tracks your app's workflow and code paths
    │   ├── error_memory.md              # [Memory] Tracks active and fixed error logs
    │   └── project_memory.md            # [Memory] Tracks active context and project overview
    │
    ├── rules-ask/
    │   └── ask.md                       # Persona for reading code and explaining concepts
    ├── rules-code/
    │   └── coder.md                     # Persona for writing clean, production-grade logic
    ├── rules-debug/
    │   └── debugger.md                  # Persona for deep root-cause error analysis
    ├── rules-orchestrator/
    │   └── orchestrator.md              # Persona for managing massive, multi-step task, and acting all personas at once
    └── rules-plan/
        └── planner.md                   # Persona for creating technical roadmaps first
```

# Quick File Breakdown:

- rules/.clinerules & rules/system_instructions.md: These files act as the AI's permanent "brain constraints." They define safety zones, timezone standards, and force the AI to respect your local project boundaries.

- The Dynamic Memory Files (project_memory.md, error_memory.md, codebase_map.md): These are the only tracking files the AI is allowed to write into. They act as short cheat sheets so the AI always knows what it did in your last chat session.

- The Sub-folders (rules-ask/, rules-code/, etc.): Whenever you choose a different mode in your extension, the AI automatically reads the matching .md file inside these folders to change its mindset instantly.

# ⚡ Prompt Triggers (Manual Commands)

Type these prompts depending on these situations!

<br>[Newly Added: Manual Triggers on Persona's]

-o, -p, -c, -d, -a (Orchestrator, Planner, Coder, Debug, Ask)

<b>What it does:</b> Type -p in your prompt so the ai acts as planner that plans your expected ideas.
<br>Example to prompt: "-p I want to build a comprehensive fitness and nutrition app that seamlessly integrates calorie tracking with gym progress logging".

---

-setup

<b>What it does:</b> Dynamically inspects your whole workspace and updates all three memory layers at once. Use this on your very first prompt or whenever you start a brand new chat session!

---

-context

<b>What it does:</b> Scans your current project structure and updates project_memory.md to record your active project workflow.

---

-error

<b>What it does:</b> Analyzes active debugging traces and updates error_memory.md with current bugs, logs, and resolution steps. It also records history fixed errors to prevent hallucinating and bringing up old fixed bugs. Every debugging session include -error on your prompt

---

-codebase

<b>What it does:</b> Looks over your code layout and updates codebase_map.md with simple descriptions of your active application workflow. This is useful if you're vibe learning xd, It records your app's techstack and even explain to you the purpose of every file so you can keep track of ai changes and your current app state. Best practices to use this prompt is when you're about to deploy or finished building your project.
<br>
<br>

# Why Manual Triggers Instead of Auto-Updates?

This template explicitly bans the AI from modifying its memory files in the background while it is generating code. You must type the flags manually to make it update its memory.

# Key Benefits of Manual Triggering:

<b>Massive Token & Money Savings:</b> Automatic background updates force the AI to analyze, rewrite, and reread your entire repository structure on every single prompt. Manual syncing cuts out this massive token usage entirely since you will manage when to update the memory files.

<b>Full Control of Personas:</b> You manually trigger personas on how you want the ai to act based on your prompt.

# Prevents AI Hallucination:

If the AI rewrites its memory tracking layers during an active bug patch, it can get confused and mess up its instructions. Manual triggers give you total control over when the AI updates its project roadmap.

# Clean Session Recovery:

If your context window resets or expires, simply type -setup in a fresh chat. The AI will read its lightweight memory logs and rebuild its mental map of your code instantly without needing you to re-explain anything.

---

# Installation Guide

## 1. Move to your downloads folder

cd Downloads

## 2. Clone the template repository

git clone https://github.com/worriee/clinerulestemplate.git

## Final Step:

Copy the .roo folder (or .clinerules folder depending on your extension you're working with) from the cloned template directory and paste it directly at the root of your current project workspace.

Start your very first prompt in ai agent using -setup and start cooking 🔥.

## Kilo Code Guide (you can use neither of .roo and .clinerules together with their existing memory logs.)

**First Chat Session**
<br><br>You: "Read the rules and active parameters stored within the [template folder u want to retain] directory layout. Apply the system constraints instantly."
<br><br>AI: I have read your...
<br><br>You: "-setup" OR "read existing memory files so you'll have the current context of the project"

---

Feedback is a must, tbh the .clinerules template of mine isn't working properly in cline extension. It often overlaps to the context window and forgets frequently. Maybe because I'm using free api ai model from openrouter lol. But this maybe works for you, so give it a try :>.

---
<br>

# Own Usages

<p align="center">
    <img src="assets/usage1.png" width="200"/>
    <img src="assets/usage2.png" width="200"/>
    <img src="assets/usage3.png" width="200"/>
    <img src="assets/usage4.png" width="200"/>
    <img src="assets/usage5.png" width="200"/>
    <img src="assets/usage6.png" width="200"/>
    <img src="assets/usage7.png" width="200"/>
</p>