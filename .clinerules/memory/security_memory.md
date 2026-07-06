# Security Analysis & Vulnerability Memory

## 0. Last Synchronized Checkpoint

- **Last AI Analysis Timestamp**: [Month Day, Year, HH:MM AM/PM PST]

## 1. Active & Unresolved Vulnerabilities

### [SEC-001] Threat Title (SEVERITY)

- **Vulnerability Rating**: [Score 0 - 10]
- **Severity Level**: CRITICAL | HIGH | MEDIUM | LOW
- **Attacker Exploit Methodology**: [Explain how a black-market actor extracts value from this flaw]
- **Production-Ready Remediation Plan**: [Step-by-step fix outline]
- **Status**: OPEN | IN_PROGRESS | RESOLVED
- **Logged At**: [Month Day, Year, HH:MM AM/PM PST]

---

## 2. Historical & Resolved Vulnerabilities

_Move vulnerabilities to this section once they are completely verified as patched. This serves as historical memory to prevent the AI from re-introducing the same vulnerabilities._

> STRICT RULE: When a vulnerability in Section 1 is patched, the AI MUST migrate it to this section within the SAME response using `### [RESOLVED] Short Vulnerability Description (SEC-XXX)`. All headers in this file are IMMUTABLE. Existing resolved entries MUST NOT be deleted, truncated, or rewritten. New resolved entries are prepended (LIFO) directly under the Section 2 header. The original SEC-XXX tracking number MUST be preserved in the resolved header. The AI MUST ALSO update the Overall Security Score in Section 3 to reflect the new security posture. Failure to migrate immediately is a CRITICAL VIOLATION.

### [RESOLVED] Short Vulnerability Description (SEC-XXX)

- **The Issue**: [Brief summary of what was vulnerable]
- **The Resolution**: [How it was patched]
- **Prevention Strategy**: [What architectural rule or guideline should be followed to avoid a regression]

---

## 3. Overall Security Score

- **Current Score**: [0-10]
- **Last Assessment**: [Month Day, Year, HH:MM AM/PM PST]
- **Summary**: [Brief overall security posture statement]

---

## 4. ARCHIVE STATUS

- **Archive File**: `.clinerules/archives/security_archive.md`
- **Threshold**: 10 active entries per section
- **Total Archived**: 0
- **Last Archive Check**: `Not yet performed`

| Entries Archived | Archived At (PST) |
| ---------------- | ----------------- |
| 0                | —                 |

<!-- c: worrie -->
