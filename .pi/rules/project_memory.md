# Project Memory & Context Tracker

## 0. Last Synchronized Checkpoint

- **Last AI Analysis Timestamp**: [Month Day, Year, HH:MM AM/PM PST]

## 1. Project Overview

### Project Identity

- **Project Name**: _[Name of this project]_
- **Primary Goal**: _One-sentence purpose of this application_
- **Target Users / Audience**: _Who uses this software_
- **Current Phase**: _Prototype / Alpha / Beta / Production / Maintenance_
- **Active Branch**: _main / dev / feature-xxx_

### Key Constraints

_List budget, timeline, platform restrictions, team size, or technical limitations currently in effect._

---

## 2. Active Milestones & Roadmap

_Track high-level releases, versions, or major feature milestones the project is working toward._

### [MS-001] Milestone Title

- **Target Version/Release**: _v1.0, v2.0, etc._
- **Due Date**: _[Target completion date]_
- **Key Deliverables**: _What must be finished for this milestone_
- **Dependencies**: _What prerequisites must be done first_
- **Status**: IN_PROGRESS | COMPLETED | BLOCKED
- **Notes**: _Any additional context_

_Log new milestones here in LIFO format (newest on top)._

---

## 3. Current Sprint & Active Tasks

- [Describe the active task here]
- [Describe the active task here]

---

## 4. Completed Milestones

- [Describe the completed milestone here]
- [Describe the completed milestone here]

---

## 5. Pending Tasks & Backlog

- [Describe the pending task here]
- [Describe the pending task here]

---

## 6. Architectural Decisions & Constraints

_Keep a running history of critical architectural choices, patterns to follow, or constraints to prevent AI hallucination or regression._

### [DEC-001] Decision Title

- **Context**: _Why this decision was needed (problem, requirement, constraint)_
- **Choice Made**: _What was chosen and implemented_
- **Alternatives Considered**: _What was rejected and why_
- **Impact**: _What files, modules, or layers this decision affects_
- **Date Logged**: _[Month Day, Year, HH:MM AM/PM PST]_

_Log new decisions here in LIFO format (newest on top)._

---

## 7. MEMORY FILE REGISTRY

All specialized memory logs are stored in `.pi/memory/` directory:

- **Error Memory**: `.pi/memory/error_memory.md` — Active bugs, stack traces, resolution history
- **Codebase Map**: `.pi/memory/codebase_map.md` — Directory structure, file purposes, dependency mapping
- **Implementation Memory**: `.pi/memory/implementation_memory.md` — Architectural design maps, feature flows, execution roadmaps
- **Security Memory**: `.pi/memory/security_memory.md` — Vulnerability tracking, threat modeling, remediation plans
- **Review Memory**: `.pi/memory/review_memory.md` — Code review findings, quality assessments
- **Test Memory**: `.pi/memory/test_memory.md` — Test strategies, coverage analysis, test case documentation

**Archive Files** (pre-created, receive overflow from memory files):

- **Error Archive**: `.pi/archives/error_archive.md`
- **Implementation Archive**: `.pi/archives/implementation_archive.md`
- **Security Archive**: `.pi/archives/security_archive.md`
- **Review Archive**: `.pi/archives/review_archive.md`
- **Test Archive**: `.pi/archives/test_archive.md`

_Note: `codebase_map.md` and `project_memory.md` are excluded from archival._

---

## 8. ARCHIVE STATUS

- **Archive Location**: `.pi/archives/`
- **Threshold**: 10 active entries per section (LIFO ordering)
- **Archives Created**: 0
- **Last Archive Check**: `Not yet performed`

| Archive File        | Source Memory | Entries Archived | Archived At (PST) |
| ------------------- | ------------- | ---------------- | ----------------- |
| _(No archives yet)_ |               |                  |                   |

<!-- c: worrie -->
