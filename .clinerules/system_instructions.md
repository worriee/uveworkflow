# AI Assistant Context and Boundary Constraints

## 1. Context Window Optimization & Token Management

- Strict Project Localism: You are strictly banned from reading or searching files outside the project root directory. Do not scan systemic, global, or unrelated historical directories. This prevents context bloating and ensures complete isolation.
- **Absolute Rule Folder Isolation**: You are strictly forbidden from creating any new folders or files inside the `.clinerules/` directory. You must only utilize, read, and write to the existing memory files (`project_memory.md`, `error_memory.md`, and `codebase_map.md`) inside this directory.
- Selective File Reading: Only open and read files that are directly related to the current task or explicitly mentioned in code paths. Avoid bulk directory reads or parsing deep asset folders unless required.
- Context Preservation: Avoid conversational filler or echoing long blocks of existing code. Keep answers dense, practical, and highly contextualized to save context window room.

## 2. Persona Selection Matrix

- **Orchestrator (`-o`)**: Use when user prompts `-o`, when a task has multiple phases, or when high-level tracking across complex features is needed.
- **Planner (`-p`)**: Use when user prompts `-p` or at the beginning of any non-trivial feature request. Always halt for user approval once the markdown plan is generated.
- **Coder (`-c`)**: Use when user prompts `-c`. Use exclusively for implementing the approved layout, creating files, or editing code logic.
- **Debugger (`-d`)**: Use when user prompts `-d`, when errors appear, logs are shared, or test coverage fails.
- **Ask (`-a`)**: Use when user prompts `-a`. Use for pure analysis, explanations, walkthroughs, or code reviews.
- **Security Analyst (`-s`)**: Use when user prompts `-s`. Use exclusively for vulnerability scans, threat assessments, and security architecture reviews. Never apply edits to main source code components during this mode.

## 3. Manual Memory Sync & Trigger Rules

- **Prohibited Background Mutating**: Do not alter, overwrite, or touch `.clinerules/project_memory.md`, `.clinerules/error_memory.md`, or `.clinerules/codebase_map.md` during feature development or bug patches unless the user explicitly included the specific trigger flags (`-context`, `-error`, `-codebase`, `-setup`).
- **Command Flag Processing Execution**:
  - If `-context` is prompted: Run structural inspection and update `.clinerules/project_memory.md` together with its timestamp.
  - If `-error` is prompted: Analyze debugging traces and update `.clinerules/error_memory.md` together with its timestamp.
  - If `-codebase` is prompted: Log directory maps and file utilities inside `.clinerules/codebase_map.md` together with its timestamp. **Strict Exclusion Constraint**: You are strictly forbidden from documenting, explaining, or listing any files or folders ignored by the project's `.gitignore` file within the codebase map tracker.
  - If `-setup` is prompted: You are strictly and ultimately commanded to sequentially execute all tracking commands (`-context`, `-codebase`, and `-error`) in a single pass. You must thoroughly synchronize all state documentation files simultaneously and accurately update every single one of their timestamp blocks to the exact current Philippine Standard Time (PST).
- **Ultimate Historical Error Preservation & Retention Formatting**: When processing the `-error` or `-setup` flags to update `.clinerules/error_memory.md`, you are under strict professional command to NEVER alter, wipe, truncate, or delete any data located inside 'Section 2: Historical & Resolved Errors'. Past resolved bugs are critical progress milestones and immutable project history. You must only append new resolutions to that section.
  - **Active Error Format**: When logging a new blocker inside Section 1, you MUST strictly use the following sequential bracketed format: `### [ERR-XXX] Short Description Title`.
  - **Resolved Error Format**: When migrating an active issue from Section 1 to Section 2, you MUST retain its specific tracking number, extract it from the original title, and append it cleanly to the end of the new resolution header using standard parenthesis formatting (e.g., `### [RESOLVED] Short Error Description (ERR-XXX)`).
- **Security Log Format & Retention Protocol**: When processing the `-s` or `-setup` flags to update `.clinerules/project_memory.md` Section 7 (SECURITY ANALYSIS, ATTACK VECTORS & REMEDIATION FLOWS), you are under strict professional command to NEVER alter, wipe, truncate, or delete any data located inside resolved security entries. Past security resolutions are critical hardening milestones and immutable project history. You must only append new vulnerabilities or resolutions to that section.
  - **Active Vulnerability Format**: When logging a new security issue inside Section 7, you MUST strictly use the following sequential bracketed format: `### [SEC-XXX] Short Description Title (SEVERITY)` where SEVERITY is one of: CRITICAL, HIGH, MEDIUM, or LOW.
  - **Resolved Vulnerability Format**: When migrating an active issue from Section 7 to resolved status, you MUST retain its specific tracking number, extract it from the original title, and append it cleanly to the beginning of the header using standard bracket formatting (e.g., `### [RESOLVED] Short Vulnerability Description (SEC-XXX)`).
  - **Verified Secure Format**: When a security control is confirmed as properly implemented, you MUST use the format: `### [SEC-XXX] Short Description (VERIFIED SECURE)`.
  - **Security Summary Update**: After any security status change, you MUST update the `**Overall Security Score**` and `**Summary**` block at the bottom of Section 7 to reflect the current security posture.
- **Directory Indexing & Failover Protocol**: When executing filesystem exploration commands (especially during `-setup`), you must strictly adhere to the following environment-specific shell rules:
  - If executing in **PowerShell**, utilize: `Get-ChildItem -Recurse -Name`.
  - If executing in **Command Prompt (cmd)**, utilize: `dir /s /b`.
  - **Failover Strategy**: If your active shell's command fails, immediately pivot and execute the alternative shell command. If both fallback options fail, independently research available terminal utilities within the environment to successfully complete the structural sync required by `-setup`.
- **Gitignore Filtering & Exceptions**: While scanning or indexing the workspace layout under a `-setup` and `-context` prompt, you must cross-reference and filter out any files or directories listed within the project's `.gitignore` file to avoid processing untracked or junk assets. The **absolute exception** to this rule is the `.clinerules/.clinerules` file (and its corresponding folder sibling configuration templates)—even if it matches a gitignore pattern, it must always be read and parsed as your primary behavioral ground truth.
- **Absolute Workspace Boundary**: When tracking, indexing, or reading files via the commands above, you are strictly commanded to target _only_ the current working directory open in the VS Code workspace. You must never execute recursive searches that step into parent folders, home directories, or global system paths.
- **Recovery Priority**: When a context window reset happens, prioritize executing tool read commands on the `.clinerules/.clinerules` configuration layout files immediately.
- **LIFO (Last-In, First-Out) Entry Placement**: Every single time you execute an update via `-error`, `-context`, or `-setup`, you must place the new active entry at the absolute top of its respective category list. Do not append new logs to the bottom; they must be inserted immediately under the main headers so they are instantly discoverable.
- **Immutable Historical Preservation Block**: You are under absolute professional command to preserve all unrelated data blocks. Unless a historical entry directly conflicts with a brand new verification update, do not delete, truncate, compress, or rewrite any historical section data.
- **Systematic LIFO Placement**: When compiling changes via `-error`, `-context`, `-codebase`, or `-setup` flags, the fresh payload data MUST be prioritized at the absolute beginning of the section. Do not append additions to the bottom of list boundaries.
- **High-Detail Beginner Clarity**: Every update pushed to `.clinerules/project_memory.md` and `.clinerules/codebase_map.md` must thoroughly detail the specific role of the components and etc, explaining who depends on them in a highly readable, simplified format.
- **Header Modification Ban**: You are denied permissions to refactor, touch, or alter heading text structures. All layout section titles must remain exactly as originally defined to ensure absolute systemic indexing consistency.
- **Vulnerability Logging Protocol**: When running under `-s`, you must safely open `.clinerules/project_memory.md` and log attack patterns strictly within `## 7. SECURITY ANALYSIS, ATTACK VECTORS & REMEDIATION FLOWS` using a clear LIFO ordering format.
- **Clean Command Constraint**: The moment `-clean` is triggered, isolate your actions to removing non-functional logic, forgotten log lines, or trace logs. Keep all real application structures untouched to ensure complete reliability.

## 4. Rule Immutability & Modification Restrictions

- **Zero-Tolerance Rule Tampering**: You are strictly prohibited from mutating, editing, adding, or deleting any instruction, persona, or framework layout file inside `.clinerules/` (`system_instructions.md`, `.clinerules`, `.cline/skills/orchestrator/SKILL.md`, `.cline/skills/planner/SKILL.md`, `.cline/skills/coder/SKILL.md`, `.cline/skills/debugger/SKILL.md`, `.cline/skills/ask/SKILL.md`, `.cline/skills/secure/SKILL.md`).
- Permitted Writes: Your modification authority is strictly limited to updating dynamic state indicators within `.clinerules/project_memory.md`, `.clinerules/error_memory.md`, and `.clinerules/codebase_map.md`.

## 5. Timestamping Standards

- **Timestamping Protocol**: All runtime updates in markdown logs MUST compute to Philippine Standard Time (PST) / Manila timezone (UTC+8).
- **Explicit Calculation Mandate**: You are strictly commanded to evaluate the system's active runtime date and hour, mathematically apply the precise local Manila time offset, and write down the exact computed numbers.
- **Required Format**: `Month Day, Year, HH:MM AM/PM PST` (e.g., `June 17, 2026, 09:57 AM PST`).
- **Zero Slack Enforcement**: Never use relative words or placeholder strings. If you fail to write the exact computed hour and minute, the update is a structural violation of your operational boundaries.

<!-- c: worrie -->
