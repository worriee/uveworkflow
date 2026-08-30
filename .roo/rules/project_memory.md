# Project Memory & Context Tracker

## 0. Last Checkpoint

- **Last Sync**: [Month Day, Year, HH:MM AM/PM PST]

## 1. Recent Changes (Git)

- **Vault Path**: [set after first `-obsidian`]
- **Last Scan**: [Month Day, Year, HH:MM AM/PM PST]

> `-context` scan: `git status` + `git diff` + `git log @{u}..HEAD`. LIFO, newest on top.

| File | Status | Δ Lines | What Changed |
|---|---|---|---|
| `src/foo.js` | M | +12/−4 | fixed validation bug |

_Diff visual (git-style):_
```diff
src/foo.js
+ const validate = ...
+ return result
- return raw
```

_New files visual:_
```
src/
└── new-feature/
    ├── module.js   (new)
    └── test.js     (new)
```

- **Unpushed**: N commits | **Staged**: N | **Unstaged**: N | **Untracked**: N
- **Total Δ**: +N / −N lines

---

## 2. Objective

- **Purpose**: _one-liner_
- **Goal**: _what done looks like_
- **Users**: _who benefits_

---

## 3. Important Details

- _constraints, gotchas, key decisions_

---

## 4. Completed

### [DONE] Short Desc — Date

- What finished

---

## 5. Blocked

### [BLOCKED] Short Desc

- Blocker — what unblocks

---

## 6. Next Move

1. next action
2. after that

---

## 7. Relevant Files

| Path | Why Relevant |
|---|---|
| `src/...` | short reason |

<!-- c: worrie -->
