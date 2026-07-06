# Test Strategy & Coverage Memory

## 0. Last Synchronized Checkpoint

- **Last AI Analysis Timestamp**: [Month Day, Year, HH:MM AM/PM PST]

## 1. Active Test Strategies

### [TEST-001] Test Case Title

- **File/Path**: `path/to/test_file.ext`
- **Type**: Unit | Integration | E2E | Performance
- **Preconditions**: [Required setup or state before test execution]
- **Test Input**: [Specific data or mock state required]
- **Expected Output**: [Exact expected result or behavior]
- **Assertions**: [Specific assertions to validate]
- **Framework**: Vitest | Playwright
- **Coverage Target**: [0-100%]
- **Coverage Status**: COVERED | UNCOVERED | PARTIAL
- **Logged At**: [Month Day, Year, HH:MM AM/PM PST]

---

## 2. Historical & Resolved Test Strategies

_Move test strategies to this section once they are completely verified as resolved. This serves as historical memory to prevent the AI from re-introducing the same test gaps._

### [RESOLVED] Short Test Description (TEST-XXX)

- **The Issue**: Brief summary of what was failing or uncovered
- **The Resolution**: How it was addressed (test added, coverage improved, flaky test fixed)
- **Prevention Strategy**: What testing guideline should be followed to avoid regression
- **Verified Coverage**: Final coverage percentage after resolution
- **Resolved At**: [Month Day, Year, HH:MM AM/PM PST]

---

## 3. Test Summary Metrics

- **Total Test Cases Designed**: 0
- **Unit Tests**: 0
- **Integration Tests**: 0
- **E2E Tests**: 0
- **Performance Tests**: 0
- **Overall Coverage**: 0%
- **Last Test Run**: `Not yet performed`

---

## 3.5 Strict Resolution Protocol

- **Immediate Migration**: When an active test strategy in Section 1 is implemented or verified, it MUST be migrated to Section 2 in the SAME response using `### [RESOLVED] Short Test Description (TEST-XXX)`.
- **Header Lock**: All section headers in this file are IMMUTABLE. The AI is FORBIDDEN from editing, renaming, adding, or deleting any `#`, `##`, or `###` system header.
- **Historical Preservation**: Existing resolved entries in Section 2 MUST NOT be deleted, truncated, or rewritten. New resolved entries are prepended (LIFO) directly under the Section 2 header.
- **Tracking Number Retention**: The original TEST-XXX number from the active entry MUST be preserved in the resolved header as `(TEST-XXX)`.
- **Violation Severity**: Failure to migrate immediately or to preserve history is a CRITICAL VIOLATION.

---

## 4. ARCHIVE STATUS

- **Archive File**: `.roo/archives/test_archive.md`
- **Threshold**: 10 active entries per section
- **Total Archived**: 0
- **Last Archive Check**: `Not yet performed`

| Entries Archived | Archived At (PST) |
| ---------------- | ----------------- |
| 0                | —                 |

<!-- c: worrie -->
