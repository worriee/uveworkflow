# OpenCode Agent Workspace Configuration

## External Instruction Loading

CRITICAL: The core operational guardrails, boundaries, and memory tracking systems for this workspace are managed inside the rules sub-directory. Always re-read these files whenever you experience token loss, context window loss or any related causes so that you can retain the state of the project immediately. The environment is configured to read instructions from the following tracking layers:

- Core Rules & Flag Guidelines: `.opencode/rules/.clinerules`
- Context Window & Boundaries: `.opencode/rules/system_instructions.md`

## Skill Execution Modes

The specialized operational personas are modularly isolated as native Agent Skills inside the skills folder. The system dynamically discovers and lazy-loads these skills on-demand when matching your single-letter command flags or direct task intents:

- **Orchestrator Mode (`-o`)**: `.opencode/skills/orchestrator/SKILL.md`
- **Planner Mode (`-p`)**: `.opencode/skills/planner/SKILL.md`
- **Coder Mode (`-c`)**: `.opencode/skills/coder/SKILL.md`
- **Debugger Mode (`-d`)**: `.opencode/skills/debugger/SKILL.md`
- **Ask Mode (`-a`)**: `.opencode/skills/ask/SKILL.md`
- **Security Analyst Mode (`-s`)**: `.opencode/skills/secure/SKILL.md`
- **Reviewer Mode (`-r`)**: `.opencode/skills/reviewer/SKILL.md`
- **Tester Mode (`-t`)**: `.opencode/skills/tester/SKILL.md`

## Memory File Locations

All persistent state tracking is centralized in two locations:

- **Configuration Rules**: `.opencode/rules/` — Core behavioral constraints and task tracker
- **Specialized Memory Logs**: `.opencode/memory/` — Error logs, codebase maps, implementation plans, security analysis, code reviews, and test strategies

<!-- c: worrie -->
