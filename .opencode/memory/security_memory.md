# Security & Vulnerability Memory

## 0. Last Checkpoint

- **Last Sync**: [Month Day, Year, HH:MM AM/PM PST]

## 1. Active Vulnerabilities

### [SEC-001] Threat Title (SEVERITY)

- **Rating**: [0-10]
- **Severity**: CRITICAL | HIGH | MEDIUM | LOW
- **Exploit**: _How attacker extracts value_
- **Remediation**: _Step-by-step fix_
- **Status**: OPEN | IN_PROGRESS | RESOLVED
- **Logged**: [Month Day, Year, HH:MM AM/PM PST]

---

## 2. Resolved Vulnerabilities

> On patch → migrate Section 1 to Section 2 SAME using `### [RESOLVED] Desc (SEC-XXX)`. Update score Section 3. Headers immutable. LIFO prepend only.

### [RESOLVED] Short Description (SEC-XXX)

- **Issue**: _What was vulnerable_
- **Resolution**: _How patched_
- **Prevention**: _Rule to avoid regression_

---

## 3. Security Score

- **Score**: [0-10]
- **Last Assessment**: [Month Day, Year, HH:MM AM/PM PST]
- **Summary**: _Posture statement_

---

## 4. Archive Status

- **File**: `archives/security_archive.md`
- **Threshold**: 10 entries
- **Archived**: 0

<!-- c: worrie -->
