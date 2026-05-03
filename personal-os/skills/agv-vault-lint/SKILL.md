---
name: agv-vault-lint
description: Weekly health check on your Personal OS. Checks for stale tasks, goal-activity gaps, and index drift. Use when you say "lint my vault", "vault health check", "clean up", or as part of your weekly review.
---

# Vault Lint

Run 3 health checks against the Personal OS vault and present a structured report. Never make changes without explicit approval.

---

## Step 1: Load Context

Read all of the following in parallel:

- `CLAUDE.md`
- `GOALS.md`
- `Knowledge/vault-index.md`
- Every `.md` file in `Tasks/`
- Every daily entry from the last 14 days in `Daily/`

If any file is missing, note it in the report and continue with what exists.

---

## Step 2: Run Health Checks

### Check 1 — Stale Tasks

Read every task file in `Tasks/`.

A task is **stale** when all of these are true:
- Its frontmatter `status` is `n` (not started)
- Its `created_date` is more than 30 days ago
- No daily entry from the last 14 days mentions it (search by filename and by task title)

For each stale task, propose one of:
- **Kill** — remove the task file entirely
- **Keep** — set a new target date (suggest one)
- **Merge** — combine with another related task (name the candidate)

### Check 2 — Goal-Activity Contradictions

Cross-reference `GOALS.md` against `Daily/` entries from the last 14 days.

Flag two categories:

1. **Goals with no activity** — a goal listed in `GOALS.md` that is not mentioned in any daily entry from the last 14 days. Cite the goal name and confirm zero mentions.
2. **Activity without a goal** — work appearing in daily entries that does not map to any goal in `GOALS.md`. Cite the specific daily entry and the activity described.

### Check 3 — Index Drift

Compare `Knowledge/vault-index.md` against actual files on disk.

Flag three categories:

1. **Missing from index** — files that exist in the vault but have no entry in `vault-index.md`.
2. **Removed files** — entries in `vault-index.md` that point to files that no longer exist on disk.
3. **Stale descriptions** — spot-check 5 random files listed in the index. Read each file and compare its current content against the index description. Flag any where the description no longer matches.

---

## Step 3: Present Report

Output the report in this exact format:

```
## Vault Lint Report — YYYY-MM-DD

### Stale Tasks (X found)
- `task-filename.md` — Created YYYY-MM-DD, last mentioned: never/YYYY-MM-DD. Recommend: kill/keep/merge.

### Goal-Activity Gaps
- Goal with no activity: [goal name] — no mentions in last 14 days
- Activity without goal: [activity] — not mapped to GOALS.md

### Index Drift (X issues)
- Missing from index: `filename.md`
- Stale description: `filename.md` — index says X, file now says Y
- Removed: `filename.md` — in index but file no longer exists

### No Issues Found
[List every area checked where everything is current]
```

If a check finds zero issues, move it to the "No Issues Found" section and confirm what was checked (e.g., "Stale Tasks: checked 12 task files, all are active or recently mentioned").

---

## Step 4: Execute Approved Changes

Wait for the user to review the report. Then:

- Execute only what the user explicitly approves (task kills, index updates, date changes, etc.)
- After all approved changes are made, update `Knowledge/vault-index.md` with a `Last lint: YYYY-MM-DD` line at the top of the file

---

## Rules

- **Never make changes without approval.** The lint report is a proposal only.
- **Quote evidence for every finding.** Cite specific files, dates, or content.
- **Be specific.** Name each stale task, each gap, each drift issue by filename and detail.
- **Track what was checked.** List areas with no issues so the user knows coverage was thorough.
