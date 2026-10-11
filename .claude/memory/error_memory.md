# Error Log

## 0. Last Checkpoint

- **Last Check**: [Month Day, Year, HH:MM AM/PM PST]

## 1. Active Errors

### [ERR-001] Short Description

- **Symptom**: _What fails? Error logs, stack traces._
- **Trigger**: _What command/file/action caused this?_
- **Root Cause**: _Initial assessment._

---

## 2. Resolved Errors

### [RESOLVED] Short Description (ERR-001)

- **Issue**: _What went wrong_
- **Resolution**: _How it was fixed_
- **Prevention**: _Rule to avoid regression_

---

## 3. Debug Rules

- Lookback: Cross-reference this file before fixing. Check for similar past failures.
- Document: Log new errors in Section 1 before writing fixes.
- Transition: On fix → update status, document solution, move to Section 2.

---

## 4. Archive Status

- **File**: `archives/error_archive.md`
- **Threshold**: 10 entries
- **Archived**: 0

<!-- c: worrie -->
