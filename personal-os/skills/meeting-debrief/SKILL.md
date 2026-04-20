---
name: meeting-debrief
description: Processes a Fireflies meeting transcript and cross-references it against your Personal OS to suggest updates to tasks, goals, knowledge, and action items. Use when the user says "debrief", "meeting review", "process my meeting", or asks what came out of a meeting. Never makes changes directly.
---

# Meeting Debrief

Process a meeting transcript from Fireflies, cross-reference it against your Personal OS, and suggest updates to your tasks, goals, and knowledge base. Never make changes directly — all output is suggestions for you to approve.

## When to Use

- "Debrief my latest meeting"
- "Process my meeting"
- "Meeting review"
- "What came out of my last meeting?"
- "Review my meeting with [person]"

## When NOT to Use

- You want to manually write meeting notes (no transcript involved)
- You want to edit docs directly without meeting context

---

## Workflow

### Phase 1: Get the Meeting

1. Use the Fireflies MCP tools to list recent transcripts (limit 10)
2. Present each meeting with: title, date, participants, duration
3. Ask which meeting to process
4. Fetch the full transcript AND summary for the selected meeting

If Fireflies is not connected, ask the user to paste their meeting notes or transcript directly.

### Phase 2: Load Your Personal OS Context

Read these files to understand who you are and what matters to you:

- **CLAUDE.md** — your working preferences and instructions
- **Constitution.md** — your values and principles
- **Business.md** — your role, customers, competitive landscape
- **GOALS.md** — your current priorities and OKRs
- All `.md` files in **Tasks/** — your current work items

Read all of these in parallel.

### Phase 3: Cross-Reference with Knowledge

Analyze the transcript to extract people, companies, topics, and decisions. Then selectively read relevant files from Knowledge/:

| Transcript signal | Where to look |
|---|---|
| Person named | Knowledge/ files mentioning that person |
| Customer or account mentioned | Knowledge/ files about that account |
| Competitor referenced | Knowledge/ competitive intel files |
| Past meeting referenced | Knowledge/ meeting notes |
| Topic that matches existing knowledge | Relevant Knowledge/ files |

**Process:**
1. Extract all people, companies, and topics from the transcript
2. Search Knowledge/ for matching files
3. Read only files that are relevant
4. Note which areas were checked and which had no match

### Phase 4: Present Suggested Changes

Organize all suggestions into these sections:

**Section 1: New Tasks**

For each action item or follow-up identified in the meeting:
- Proposed task title
- Priority (P0–P3) based on alignment with GOALS.md
- Which goal it supports
- The transcript passage that triggered it

If a proposed task does not map to any existing goal, flag it: "This task does not map to a current goal. Should the task be created anyway, or does GOALS.md need updating?"

**Section 2: Knowledge Updates**

Suggested additions to Knowledge/:
- New meeting notes file (propose filename: `Knowledge/meeting-[topic]-[YYYY-MM-DD].md`)
- Updates to existing Knowledge/ files based on new information
- For each: what to add and why (with transcript quote)

**Section 3: Goal or Priority Changes**

If the meeting revealed:
- A goal that's been accomplished or is no longer relevant
- A new priority that emerged
- A shift in focus or strategy

Suggest specific edits to GOALS.md with before/after.

**Section 4: Task Status Updates**

Cross-reference existing Tasks/ files with the discussion:
- Tasks that appear to be done based on what was discussed
- Tasks whose scope or priority changed
- For each: cite the transcript evidence

**Section 5: No Change Needed**

List areas that were reviewed where nothing needs updating. This confirms coverage.

### Phase 5: Apply Approved Changes

After the user reviews and approves specific suggestions:
1. Create new task files in Tasks/ with YAML frontmatter (use the template from CLAUDE.md)
2. Create or update Knowledge/ files
3. Update GOALS.md if approved
4. Update task statuses if approved — change `status` in YAML frontmatter

**Before making each change, describe exactly what will be written and wait for approval.**

---

## Rules

- **Never make changes without approval.** All output is suggestions first. Wait for explicit approval before any edit.
- **Quote the transcript.** Every suggested change must cite the specific discussion that triggered it.
- **Respect CLAUDE.md rules.** Follow all working preferences defined there.
- **Task-goal alignment.** Every new task must link to a goal. Flag orphan tasks explicitly.
- **Be concise.** Present suggestions clearly — don't dump the entire transcript back. Summarize what matters.
- **One meeting at a time.** Don't process multiple meetings in a single debrief unless asked.
