# Workspace Error Log & Debugging Memory

## 0. Last Synchronized Checkpoint

- **Last Error Check**: [Month Day, Year, HH:MM AM/PM PST]

## 1. Active & Unresolved Errors

_List errors currently blocking development. Update this section immediately when a new error occurs during execution or user prompting._

### [ERR-001] Error Identifier / Short Description

- **Symptom**: _What is failing? Paste error logs, stack traces, or broken behavior here._
- **Context/Trigger**: _What command, file, or action caused this error?_
- **Suspected Root Cause**: _Initial assessment of why this is happening._

---

## 2. Historical & Resolved Errors

_Move errors to this section once they are completely verified as fixed. This serves as historical memory to prevent the AI from re-introducing the same bugs._

### [RESOLVED] Error Identifier / Short Description

- **The Issue**: _Brief summary of what went wrong._
- **The Resolution**: _How it was fixed (e.g., code changes, configuration adjustments, dependency updates)._
- **Prevention Strategy**: _What architectural rule or guideline should be followed to avoid a regression?_

---

## 3. Persistent Debugging Rules

- **Lookback Before Guessing**: Before attempting to fix any code, cross-reference this file to see if a similar failure has happened before.
- **Immediate Documentation**: Every time a debugger action fails or reveals a new error, log it under section 1 before writing any fixes.
- **Clean Transitions**: When an error is resolved, update its status, document the solution, and shift it to section 2.

---

## 4. ARCHIVE STATUS

- **Archive File**: `.pi/archives/error_archive.md`
- **Threshold**: 10 active entries per section
- **Total Archived**: 0
- **Last Archive Check**: `Not yet performed`

| Entries Archived | Archived At (PST) |
| ---------------- | ----------------- |
| 0                | —                 |

<!-- c: worrie -->
