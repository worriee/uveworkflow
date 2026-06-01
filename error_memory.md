# Workspace Error Log & Debugging Memory

## 1. Active & Unresolved Errors
*List errors currently blocking development. Update this section immediately when a new error occurs during execution or user prompting.*

### [ERR-001] Error Identifier / Short Description
- **Symptom**: *What is failing? Paste error logs, stack traces, or broken behavior here.*
- **Context/Trigger**: *What command, file, or action caused this error?*
- **Suspected Root Cause**: *Initial assessment of why this is happening.*

---

## 2. Historical & Resolved Errors
*Move errors to this section once they are completely verified as fixed. This serves as historical memory to prevent the AI from re-introducing the same bugs.*

### [RESOLVED] Error Identifier / Short Description
- **The Issue**: *Brief summary of what went wrong.*
- **The Resolution**: *How it was fixed (e.g., code changes, configuration adjustments, dependency updates).*
- **Prevention Strategy**: *What architectural rule or guideline should be followed to avoid a regression?*

---

## 3. Persistent Debugging Rules
- **Lookback Before Guessing**: Before attempting to fix any code, cross-reference this file to see if a similar failure has happened before.
- **Immediate Documentation**: Every time a debugger action fails or reveals a new error, log it under section 1 before writing any fixes.
- **Clean Transitions**: When an error is resolved, update its status, document the solution, and shift it to section 2.

<!-- c: worrie -->