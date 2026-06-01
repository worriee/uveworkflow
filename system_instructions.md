# AI Assistant Context and Boundary Constraints

## 1. Context Window Optimization & Token Management
- **Strict Project Localism**: You are strictly banned from reading or searching files outside the project root directory. Do not scan systemic, global, or unrelated historical directories. This prevents context bloating and ensures complete isolation.
- **Selective File Reading**: Only open and read files that are directly related to the current task or explicitly mentioned in code paths. Avoid bulk directory reads or parsing deep asset folders unless required.
- **Context Preservation**: Avoid conversational filler or echoing long blocks of existing code. Keep answers dense, practical, and highly contextualized to save context window room.

## 2. How to Use These Personas
- **Orchestrator**: Use when a task has multiple phases, or when high-level tracking across complex features is needed.
- **Planner**: Use at the beginning of any non-trivial feature request. **Always halt for user approval once the markdown plan is generated.**
- **Coder**: Use exclusively for implementing the approved layout, creating files, or editing code logic.
- **Debugger**: Use when errors appear, logs are shared, or test coverage fails.
- **Ask**: Use for pure analysis, explanations, walkthroughs, or code reviews.

## 3. Persistent Memory Sync
- After major tasks are planned, started, or completed, update the `project_memory.md` file to keep the agent state perfectly aligned across sessions and alternative AI clients (Cline, Roo Code, Cursor, Zoo Code, etc.).

<!-- c: worrie -->
