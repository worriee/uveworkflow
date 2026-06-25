# OpenCode Agent Workspace Configuration

## External Instruction Loading

CRITICAL: The core operational guardrails, boundaries, and memory tracking systems for this workspace are managed inside the rules sub-directory. The environment is configured to read instructions from the following tracking layers:

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
<!-- c: worrie -->
