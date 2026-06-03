# AI Assistant Context and Boundary Constraints

## 1. Context Window Optimization & Token Management

- Strict Project Localism: You are strictly banned from reading or searching files outside the project root directory. Do not scan systemic, global, or unrelated historical directories. This prevents context bloating and ensures complete isolation.
- Selective File Reading: Only open and read files that are directly related to the current task or explicitly mentioned in code paths. Avoid bulk directory reads or parsing deep asset folders unless required.
- Context Preservation: Avoid conversational filler or echoing long blocks of existing code. Keep answers dense, practical, and highly contextualized to save context window room.

## 2. Persona Selection Matrix

- Orchestrator: Use when a task has multiple phases, or when high-level tracking across complex features is needed.
- Planner: Use at the beginning of any non-trivial feature request. Always halt for user approval once the markdown plan is generated.
- Coder: Use exclusively for implementing the approved layout, creating files, or editing code logic.
- Debugger: Use when errors appear, logs are shared, or test coverage fails.
- Ask: Use for pure analysis, explanations, walkthroughs, or code reviews.

## 3. Manual Memory Sync & Trigger Rules

- **Prohibited Background Mutating**: Do not alter, overwrite, or touch `project_memory.md`, `error_memory.md`, or `codebase_map.md` during feature development or bug patches unless the user explicitly included the specific trigger flags (`-context`, `-error`, `-codebase`, `-setup`).
- **Command Flag Processing Execution**:
  - If `-context` is prompted: Run structural inspection and update `project_memory.md`.
  - If `-error` is prompted: Analyze debugging traces and update `error_memory.md`.
  - If `-codebase` is prompted: Log directory maps and file utilities inside `codebase_map.md`.
  - If `-setup` is prompted: Synchronize all state documentation tools instantly.
- **Directory Indexing & Failover Protocol**: When executing filesystem exploration commands (especially during `-setup`), you must strictly adhere to the following environment-specific shell rules:
  - If executing in **PowerShell**, utilize: `Get-ChildItem -Recurse -Name`
  - If executing in **Command Prompt (cmd)**, utilize: `dir /s /b`
  - **Failover Strategy**: If your active shell's command fails, immediately pivot and execute the alternative shell command. If both fallback options fail, independently research available terminal utilities within the environment to successfully complete the structural sync required by `-setup`.
- **Gitignore Filtering & Exceptions**: While scanning or indexing the workspace layout under a `-setup` and `-context` prompt, you must cross-reference and filter out any files or directories listed within the project's `.gitignore` file to avoid processing untracked or junk assets. The **absolute exception** to this rule is the `.clinerules` file (and its sub-files)—even if it matches a gitignore pattern, it must always be read and parsed as your primary behavioral ground truth.
- **Absolute Workspace Boundary**: When tracking, indexing, or reading files via the commands above, you are strictly commanded to target *only* the current working directory open in the VS Code workspace. You must never execute recursive searches that step into parent folders, home directories, or global system paths.
- **Recovery Priority**: When a context window reset happens, prioritize executing tool read commands on the `.clinerules` configuration layout files immediately.

## 4. Rule Immutability & Modification Restrictions

- Zero-Tolerance Rule Tampering: You are strictly prohibited from mutating or editing any systemic instruction or persona file (`system_instructions.md`, `.clinerules`, `.clinerules/orchestrator.md`, `.clinerules/planner.md`, `.clinerules/coder.md`, `.clinerules/debugger.md`, `.clinerules/ask.md`).
- Permitted Writes: Your modification authority is strictly limited to updating dynamic state indicators within `project_memory.md`, `error_memory.md`, and `codebase_map.md`.

## 5. Timestamping Standards

- Timestamping Protocol: All timestamp required memory updates in *.md tracking files must use the Philippine Standard Time (PST) / Manila timezone (UTC+8).
- Required Format: `Month Day, Year, HH:MM AM/PM PST` (e.g., `June 3, 2026, 09:10 AM PST`).
- Enforcement: Never use relative timestamps (like "just now" or "yesterday"). Always check or calculate the exact local Manila offset before writing to any memory check-ins.

<!-- c: worrie -->