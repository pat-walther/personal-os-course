---
name: agv-daily-debrief
description: End-of-day skill that reconstructs the day from Fireflies meeting transcripts, writes a daily entry, cross-references goals and tasks, and suggests updates. Use when the user says "debrief", "close my day", "daily close", "daily debrief", or "what happened today?"
---

# Daily Debrief

Reconstruct the day from Fireflies meeting transcripts and user-provided context. Write a daily entry to `Daily/YYYY-MM-DD.md`. Cross-reference against goals, tasks, and knowledge. Suggest updates with evidence. Never make vault changes directly outside the daily entry.

## When to Use

- "Close my day", "daily close", "debrief", "daily debrief"
- "What happened today?"
- "End of day"

## When NOT to Use

- You want to manually write meeting notes (no debrief needed)
- You want to edit docs directly without end-of-day context
- You want just the raw transcript text without analysis

---

## Workflow

### Phase 0: Date and Mode

1. Determine the target date. Default is today.
2. Check if `Daily/YYYY-MM-DD.md` already exists. If it does, warn the user and ask whether to overwrite or skip. Do not overwrite silently.

### Phase 1: Gather Meeting Data

1. Query Fireflies transcripts using `fireflies_get_transcripts` with `fromDate` set to the target date and `toDate` set to the day after the target date. Set `limit` to 50 to ensure all meetings are captured.
2. For each qualifying meeting, fetch the full transcript AND summary using `fireflies_get_transcript` and `fireflies_get_summary`.
3. If multiple meetings qualify, process all of them.

**Graceful degradation:**

| Fireflies | Behavior |
|-----------|----------|
| Available with meetings | Full workflow — all phases |
| Available but no meetings | Ask user to describe their day or paste meeting notes |
| Unavailable (MCP not connected) | Ask user to paste meeting notes manually |
| No data and no pasted notes | Ask the user to describe their day manually, then proceed with what they provide |

### Phase 2: Load Foundation Context

Always read these files regardless of what happened during the day. Read all in parallel.

- `CLAUDE.md`
- `Constitution.md`
- `Business.md`
- `GOALS.md`
- `Knowledge/vault-index.md` (read the index FIRST to understand what exists)
- All `.md` files in `Tasks/`

### Phase 3: Selective Knowledge Reading

Analyze the meetings (and any user-provided context) to extract people, companies, topics, and decisions. Use `Knowledge/vault-index.md` as the navigation tool — scan it for relevant entries BEFORE opening individual files.

| Signal | Where to look |
|---|---|
| Person named | Knowledge/ files mentioning that person |
| Customer or account mentioned | Knowledge/ files about that account |
| Competitor referenced | Knowledge/ competitive intel files |
| Product or feature discussed | Knowledge/ product files |
| Past meeting referenced | Knowledge/ meeting notes |
| Topic matching existing knowledge | Relevant Knowledge/ files |

**Process:**
1. Read `Knowledge/vault-index.md` and scan for entries matching extracted entities
2. Read only the files the index identifies as relevant
3. Track which areas were checked and which were skipped

Do not read everything — only what is relevant to today's meetings.

### Phase 4: Write Daily Entry

Compose a daily entry for `Daily/YYYY-MM-DD.md`. Present the full entry for approval before writing.

**Entry format:**

```markdown
# YYYY-MM-DD

## What happened
[Narrative of the day based on meetings and any context the user provides. Be specific — names, topics, outcomes. Not "worked on various things."]

## Meetings
### Meeting Title (HH:MM, participants)
- Key points
- Decisions made
- Action items
- Notable quotes

[Repeat for each meeting that day]

## Decisions made
[From meetings. Note which meeting each decision came from.]

## Learnings
[New information encountered — insights from meetings, things learned, perspectives shifted]

## Open threads
[Unresolved items: things started but not finished, questions asked but not answered, threads that need follow-up]

## Tasks touched
[Tasks worked on, completed, or modified during the day]

## Reflection
[One question. Make it specific to the day. Not generic. Something that prompts genuine thought.]
```

**Guidelines for the daily entry:**
- "What happened" should read as a coherent narrative, not a bullet dump
- Be specific. Names, topics, outcomes.
- The entry should stand alone as a complete record of the day
- Meetings get woven into "What happened" chronologically AND get their own detailed section

### Phase 5: Vault Change Suggestions

Present all suggested changes organized into these sections. Every suggestion must cite specific evidence (transcript quote or user-provided context).

**Section 1: Foundation Doc Changes**

Suggested edits to `CLAUDE.md`, `Constitution.md`, `Business.md`, or `GOALS.md`. For each:
- File path
- What to change (add, edit, or remove)
- Why (quote the specific transcript passage or context that triggered it)

**Section 2: Knowledge Base Updates**

Suggested additions or edits to Knowledge/ files. For each:
- File path (propose filename for new files: `Knowledge/meeting-[topic]-[YYYY-MM-DD].md`)
- What to change or add
- Why (with evidence)

**Section 3: No Change Needed**

List areas that were reviewed where nothing needs updating. This confirms coverage and builds trust.

### Phase 6: Vault Index Update

After writing the daily entry and any approved vault changes, update `Knowledge/vault-index.md`:

1. Add or update the entry for the new daily entry
2. Update entries for any Knowledge/ files that were modified
3. Add entries for any new files created
4. Keep entries in the same format as the existing index

Present the index updates for approval.

### Phase 7: Wrap-up

**New task suggestions:**

For each action item or follow-up identified:
- Proposed task title and filename
- Priority (P0-P3) based on urgency and goal alignment
- Which goal from GOALS.md it supports
- The transcript passage that triggered it

Every new task must link to a goal in `GOALS.md`. If a task does not map to any existing goal, flag it: "This task does not map to a current goal. Should it be added, or does GOALS.md need updating?"

**Completed task suggestions:**

Cross-reference existing `Tasks/` files with the day's activity. If a meeting indicates a task is done or no longer relevant, propose marking it complete. Cite the evidence.

**Top 3 priorities for tomorrow:**

Based on open threads, existing tasks, upcoming deadlines, and goal alignment, suggest the top 3 things to focus on tomorrow.

**Reflection question:**

Ask one reflection question. Make it specific to the day, not generic.

---

## Rules

- **Never make vault changes directly.** All vault suggestions are presented for approval. The daily entry IS written (after approval), but vault edits are suggestions only.
- **Quote evidence.** Every suggested vault change must cite the specific transcript passage or user context that triggered it.
- **Task-goal alignment.** Every new task must link to a goal. Flag orphan tasks explicitly.
- **Always update the vault index.** Every file touched or created during the debrief must have its vault-index.md entry updated.
- **Be concise.** Summarize what matters. Don't dump the entire transcript back.
- **Present daily entry for approval before writing.** Show the full entry, get a thumbs up, then write the file.
- **If no data, ask.** If Fireflies has no meetings and the user hasn't provided context, ask them to describe their day before proceeding.
