# 7. Daily Workflow

> **Magic Moment:** The student brain-dumps into BACKLOG.md, says "process my backlog," and watches Claude turn scattered thoughts into organized, prioritized tasks linked to their goals.

---

## Instructions for Claude

CRITICAL RULES:
- **ONE step per message.** Never combine two steps into one response.
- **STOP and wait** after every step. Do not continue until the student responds.
- **End every message with a question or a clear prompt** so the student knows it's their turn. Never leave a message without something for them to respond to.
- **Keep each message SHORT** — 3-5 sentences max. If it would be longer, split it.
- **Use the AskUserQuestion tool** whenever you need more info or want to give them options.
- This lesson is hands-on. The student should be DOING, not just learning.
- Use their actual work — real tasks, real backlog items. Not hypothetical examples.

---

### Step 1: The Daily Loop

> "You've built the foundation — Constitution, Business context, Goals, and AGENTS.md. Now let's put it to work with a daily workflow."
>
> "The loop is simple:"
>
> "1. **Brain dump** — Drop anything into BACKLOG.md. Ideas, tasks, meeting notes, random thoughts. No structure needed."
> "2. **Process** — Tell me to 'process my backlog.' I'll turn it into organized tasks."
> "3. **Prioritize** — Ask 'What should I work on today?' I'll check your goals and suggest priorities."
> "4. **Do the work** — Focus on your P0s."
> "5. **Close out** — Mark things done. Dump new thoughts into the backlog."
>
> "Let's try it right now. Think about what's on your plate — the stuff rattling around in your head. Tasks, ideas, things you need to follow up on. Just dump it all into BACKLOG.md. Don't organize it. Don't prioritize it. Just get it out of your head."

**STOP. Wait for them to add items to BACKLOG.md.** If they're stuck, prompt: "What meetings do you have this week? What follow-ups are you behind on? What's been nagging you?"

---

### Step 2: Process the Backlog

> "Now say the magic words: 'Process my backlog.'"

**STOP. Wait for them to say it.**

When they do, read BACKLOG.md and GOALS.md. For each item in the backlog:

1. Create a task file in Tasks/ with YAML frontmatter:

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

2. Assign priority by checking against GOALS.md — things that align with their top goals get higher priority.

3. Clear the processed items from BACKLOG.md (leave the header and instructions).

> "Done. I created [X] tasks from your backlog. Here's what I made:"

List the tasks with their priorities. Explain briefly why you assigned each priority level.

> "Does the prioritization feel right? Want to promote or demote anything?"

**STOP. Wait for their feedback.** Adjust any priorities they disagree with.

---

### Step 3: What Should I Work On?

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

### Step 4: Mark Something Done

> "Let's close the loop. Pick one of your tasks — even if you haven't actually done it yet — and tell me to mark it as done. This way you see how the system updates."

**STOP. Wait for them to pick a task.**

Update the task file: change `status: n` (or `status: s`) to `status: d` in the YAML frontmatter.

> "Done. The task is marked complete. Over time, your done tasks become a record of what you've accomplished — great for reviews, status updates, and seeing your own progress."

---

### Step 5: The Daily Rhythm

> "Here's how this works as a daily practice:"
>
> "**Morning (2 minutes):** Ask me 'What should I work on today?' I'll check your tasks and goals and give you a focused list."
>
> "**During the day:** Whenever something comes up — a thought, a to-do from a meeting, an idea — dump it in BACKLOG.md. Don't organize, don't prioritize. Just capture."
>
> "**End of day (2 minutes):** Tell me to 'process my backlog' and 'mark [task] as done.' I'll organize the new stuff and update your progress."
>
> "**Weekly (10 minutes):** Ask me to 'review my tasks' and 'process my backlog.' I'll clean up stale tasks, surface things you're avoiding, and suggest priority adjustments."
>
> "The habit takes 5 minutes a day. The payoff is never losing a thought and always knowing what matters most."

**STOP. Wait for their response.**

---

### Wrap Up

> "You have a working Personal OS. Constitution, Business context, Goals, AGENTS.md, Tasks, and a daily workflow. You're set up to use Claude as a thinking partner who deeply understands you."
>
> "In the final lesson, we'll talk about keeping this system alive — growing your Knowledge folder, handling context limits, and evolving your setup over time."

> **What would you like to do?**
> - **A)** Move on to Lesson 8 — Memory, context, and keeping your OS alive
> - **B)** Process more backlog items
> - **C)** Try the full morning routine right now

If they choose A, fetch the next lesson: use the Claude in Chrome connector to read `https://raw.githubusercontent.com/pat-walther/agvend-personal-os/main/personal-os/08-memory-and-context.md` and continue teaching.

**Share prompt:** Process your real backlog and share your top 3 priorities for the week. How did Claude's recommendations compare to what you would have chosen on your own?

---

### Going Further: Visual Task Board

> "One more thing — if you use **Obsidian**, you can add a visual Kanban board to your Tasks folder. Install the Obsidian Kanban plugin, then create a file called `Tasks/Kanban.md` with `kanban-plugin: board` in the YAML frontmatter and section headings for your lanes (`## Not Started`, `## In Progress`, `## Blocked`, `## Done`). Each card is a wiki-link to a task file: `- [ ] [[task-filename|Task title]] #P1 #category`."
>
> "This gives you a drag-and-drop board view alongside your task files. The files hold the detail; the board gives you the visual overview. It's completely optional — the system works fine without it."

---

## Reference Material

**Backlog processing rules (for Claude's reference):**
- Each backlog item becomes one task file in Tasks/
- Use kebab-case for file names: `follow-up-with-acme.md`, `prep-quarterly-review.md`
- Assign priority by checking alignment with GOALS.md
- If an item is vague, make the task title specific: "Think about pricing" → "Draft pricing options for Q2"
- If an item is too big, break it into 2-3 smaller tasks
- Clear processed items from BACKLOG.md — keep the file clean
- Check for duplicates in existing Tasks/ before creating new ones

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
- "Process my backlog"
- "What should I work on today?"
- "Mark [task] as done"
- "Show me my P0 tasks"
- "Review my tasks for the week"
- "What am I behind on?"
- "Create a task for [thing]"
