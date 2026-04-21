# 7. Daily Workflow

> **Magic Moment:** The student says "create a task for [thing]" and watches Claude turn it into a structured, prioritized task linked to their goals — then asks "what should I work on today?" and gets a focused answer.

---

## Instructions for Claude

CRITICAL RULES:
- **ONE step per message.** Never combine two steps into one response.
- **STOP and wait** after every step. Do not continue until the student responds.
- **End every message with a question or a clear prompt** so the student knows it's their turn. Never leave a message without something for them to respond to.
- **Keep each message SHORT** — 3-5 sentences max. If it would be longer, split it.
- **Use the AskUserQuestion tool** whenever you need more info or want to give them options.
- This lesson is hands-on. The student should be DOING, not just learning.
- Use their actual work — real tasks, real situations. Not hypothetical examples.

---

### Step 1: Set Up Tasks

Before starting, silently create the Tasks/ folder and a Kanban board file if they don't already exist:

Create `Tasks/Kanban.md`:

```markdown
---
kanban-plugin: board
---

## Not Started

## In Progress

## Blocked

## Done
```

Then begin the lesson:

> "You've built the foundation — Constitution, Business context, Goals, and CLAUDE.md. Now let's put it to work with a daily workflow."
>
> "The system is simple: whenever something comes up — a task, a follow-up, an idea — you just tell me. Say 'create a task for [thing]' and I'll turn it into a structured task file, link it to your goals, and prioritize it."
>
> "Let's try it right now. Think about something that's on your plate — a follow-up you owe someone, a project you need to start, something that's been nagging you. Tell me: 'Create a task for [thing].'"

**STOP. Wait for them to create their first task.**

---

### Step 2: Create the Task

When they say "create a task for [thing]", create a task file in Tasks/ with YAML frontmatter:

```markdown
---
title: [Actionable task name]
category: [strategy|outreach|research|writing|technical|admin|personal|learning]
priority: [P0|P1|P2|P3]
status: n
created_date: [YYYY-MM-DD]
estimated_time: [minutes estimate]
---

# [Task title]

**Goal:** [Which goal from GOALS.md this supports]

## What this is

[1-2 paragraph description of what needs to happen and why]

## What "done" looks like

- [Concrete acceptance criterion]
- [Concrete acceptance criterion]

## Open questions

- [If any, otherwise omit this section]
```

Use kebab-case for the filename: `follow-up-with-acme.md`, `prep-quarterly-review.md`.

Read GOALS.md and assign priority based on goal alignment. If the task is vague, ask for clarification before creating it.

**After creating the task file, also add a card to `Tasks/Kanban.md`.** Add a line under the column that matches the task's `status`:
- `status: n` → under `## Not Started`
- `status: s` → under `## In Progress`
- `status: b` → under `## Blocked`
- `status: d` → under `## Done`

The card format is: `- [ ] [[filename|Task title]] #priority #category`

For example, a new P1 strategy task with filename `prep-quarterly-review.md` gets this line added under `## Not Started`:
```
- [ ] [[prep-quarterly-review|Prep quarterly review]] #P1 #strategy
```

This is what makes tasks visible on the Kanban board in Obsidian. The Kanban plugin only renders cards that are explicitly listed in the board file — it does not auto-discover task files.

> "Done — I created that as a task. Here's what I made:"

Show the task with its priority and goal alignment. Explain briefly why you assigned that priority.

> "Feel right? Want to change the priority or add anything?"

**STOP. Wait for their feedback.** Adjust if needed.

---

### Step 3: Create a Few More

> "Good. Now let's build up a real task list. Think about 2-3 more things on your plate — meetings to prep for, follow-ups, projects, anything. Tell me each one and I'll create tasks for them."

**STOP. Wait for them to create more tasks.** Create each one following the same format. After they've created 3-4 total:

> "You now have [X] tasks in your system, all linked to your goals and prioritized. Let's put them to work."

**STOP. Wait for their response.**

---

### Step 4: What Should I Work On?

> "Now ask me: 'What should I work on today?'"

**STOP. Wait for them to ask.**

Read GOALS.md and all task files in Tasks/. Recommend their top 1-3 priorities for today based on:
- P0 items first, then P1s
- Tasks with `status: s` (in progress) over `status: n` (not started)
- Alignment with quarterly goals
- Any deadlines (check `due_date` in frontmatter if present)
- What makes strategic sense given their Business.md context

> "Based on your goals and current tasks, here's what I'd focus on today:"
>
> [List 1-3 specific tasks with brief reasoning]
>
> "What do you think? Ready to tackle these?"

**STOP. Wait for their response.**

---

### Step 5: Mark Something Done

> "Let's close the loop. Pick one of your tasks — even if you haven't actually done it yet — and tell me to mark it as done. This way you see how the system updates."

**STOP. Wait for them to pick a task.**

Update the task file: change `status: n` (or `status: s`) to `status: d` in the YAML frontmatter.

**Also update `Tasks/Kanban.md`:** move the card's `- [ ] [[...]]` line from its current column to the `## Done` column, and change the checkbox to `- [x]`.

> "Done. The task is marked complete — both in the task file and on your Kanban board. Over time, your done tasks become a record of what you've accomplished — great for reviews, status updates, and seeing your own progress."

---

### Step 6: The Daily Rhythm

> "Here's how this works as a daily practice:"
>
> "**Morning (2 minutes):** Ask me 'What should I work on today?' I'll check your tasks and goals and give you a focused list."
>
> "**During the day:** Whenever something comes up — a to-do from a meeting, a follow-up, an idea — just say 'Create a task for [thing].' I'll handle the rest."
>
> "**End of day (2 minutes):** Mark things done. Create tasks for anything new that came up."
>
> "**Weekly (10 minutes):** Ask me to 'review my tasks.' I'll clean up stale tasks, surface things you're avoiding, and suggest priority adjustments."
>
> "The habit takes 5 minutes a day. The payoff is never losing a thought and always knowing what matters most."

**STOP. Wait for their response.**

---

### Wrap Up

> "You have a working Personal OS. Constitution, Business context, Goals, CLAUDE.md, Tasks, and a daily workflow. You're set up to use Claude as a thinking partner who deeply understands you."
>
> "In the next lesson, we'll talk about keeping this system alive — growing your Knowledge folder, handling context limits, and evolving your setup over time."

> **What would you like to do?**
> - **A)** Move on to Lesson 8 — Memory, context, and keeping your OS alive
> - **B)** Create more tasks
> - **C)** Try the full morning routine right now

If they choose A, fetch the next lesson using the Claude in Chrome connector and continue teaching. Try either URL — use whichever one works:
- Raw: `https://raw.githubusercontent.com/pat-walther/agvend-personal-os/main/personal-os/08-memory-and-context.md`
- GitHub: `https://github.com/pat-walther/agvend-personal-os/blob/main/personal-os/08-memory-and-context.md`

**Share prompt:** Create your real tasks and share your top 3 priorities for the week. How did Claude's recommendations compare to what you would have chosen on your own?

---

## Reference Material

**Task creation rules (for Claude's reference):**
- Each task becomes one file in Tasks/
- Use kebab-case for file names: `follow-up-with-acme.md`, `prep-quarterly-review.md`
- Assign priority by checking alignment with GOALS.md
- If an item is vague, make the task title specific: "Think about pricing" → "Draft pricing options for Q2"
- If an item is too big, break it into 2-3 smaller tasks
- Check for duplicates in existing Tasks/ before creating new ones
- **Every task file must also have a corresponding card in `Tasks/Kanban.md`** — the Kanban plugin does not auto-discover files

**Kanban board sync rules (for Claude's reference):**
- When creating a task: add `- [ ] [[filename|title]] #priority #category` under the matching status column
- When changing status: move the card line to the new column
- When marking done: move the card to `## Done` and change `- [ ]` to `- [x]`
- Status-to-column mapping: `n` → Not Started, `s` → In Progress, `b` → Blocked, `d` → Done

**YAML frontmatter fields:**
- `title` — the task name (matches the `# heading` in the body)
- `category` — one of: strategy, outreach, research, writing, technical, admin, personal, learning
- `priority` — P0 through P3
- `status` — single letter: `n` (not started), `s` (started/in-progress), `b` (blocked), `d` (done)
- `created_date` — ISO date (YYYY-MM-DD)
- `estimated_time` — rough estimate in minutes

**Priority assignment logic:**
- P0: Directly supports a quarterly goal AND has a deadline this week. Maximum 3.
- P1: Directly supports a quarterly goal OR has a near-term deadline
- P2: Supports a yearly goal, has a future deadline
- P3: Good idea but no goal alignment or deadline

**Task file naming:**
- Lowercase with hyphens: `fix-api-latency.md`
- Descriptive but short: 3-5 words max
- No dates in filenames — use YAML frontmatter for dates

**Common commands the student should learn:**
- "Create a task for [thing]"
- "What should I work on today?"
- "Mark [task] as done"
- "Show me my P0 tasks"
- "Review my tasks for the week"
- "What am I behind on?"
