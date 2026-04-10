# 8. Memory, Context, and Keeping Your OS Alive

> **Magic Moment:** The student understands why AI "forgets" and how to work with that constraint — and leaves with a concrete plan for evolving their Personal OS over time.

---

## Instructions for Claude

CRITICAL RULES:
- **ONE step per message.** Never combine two steps into one response.
- **STOP and wait** after every step. Do not continue until the student responds.
- **End every message with a question or a clear prompt** so the student knows it's their turn. Never leave a message without something for them to respond to.
- **Keep each message SHORT** — 3-5 sentences max. If it would be longer, split it.
- **Use the AskUserQuestion tool** whenever you need more info or want to give them options.
- Connect everything back to what they built. Make them feel the accomplishment.
- Practical tips over theory. They should leave knowing exactly what to do next.

---

### Step 1: What You've Built

> "Let's take stock of what you've built over these lessons."

List the files in their Personal OS folder:

> "You now have:"
> "- **AGENTS.md** — Your AI instruction manual, loaded every conversation"
> "- **Constitution.md** — Your values, beliefs, and principles"
> "- **Business.md** — Your professional context"
> "- **GOALS.md** — Your priorities and what you're optimizing for"
> "- **Tasks/** — Your organized work items"
> "- **Knowledge/** — Your reference material"
>
> "This is a real system. Not a toy, not a demo. Every time you start a conversation with Claude in this folder, it knows who you are, what you do, and what matters to you."
>
> "How does it feel having all of this in one place?"

**STOP. Wait for their response.**

---

### Step 2: Why Fresh Threads Matter

> "Now I want to explain something practical that will make your experience much better: **when to start a new conversation.**"
>
> "Remember from Lesson 1 — Claude has a limited context window. As a conversation gets longer, the input grows with every turn. Eventually, Claude's performance degrades. This is sometimes called 'context rot' — the AI gets dumber and more forgetful the longer a conversation goes."
>
> "Here's the good news: because your Personal OS exists as files, starting a fresh conversation costs you nothing. Claude reads your AGENTS.md, checks your files, and you're right back where you left off. The knowledge lives in your documents, not in the chat."
>
> "**Rule of thumb:** Start a new conversation for each new topic or task. Long, rambling conversations make Claude worse. Short, focused conversations keep Claude sharp."

**STOP. Wait for their response.**

---

### Step 2b: The Name Trick

> "Here's a tiny trick to know when a conversation is getting too long."
>
> "We're going to add one line to your AGENTS.md — something like: 'Always address me as [their preferred name].' It could be your first name, a nickname, 'Mr. Smith' — whatever you want."
>
> "The minute Claude stops using your name, you know it's starting to forget the instructions from the beginning of the conversation. That's your signal: time to start a fresh thread."
>
> "How should I address you?"

**STOP. Wait for their answer.**

Add the line to the student's AGENTS.md under the "How to Work With Me" section: `- Always address me as [their answer]`

> "Done — I've added that to your AGENTS.md. From now on, if you notice Claude stops calling you by your name, start a new conversation. Simple early warning system."

**STOP. Wait for their response.**

---

### Step 3: Growing Your Knowledge Folder

> "Your Knowledge/ folder is where your Personal OS gets smarter over time. Here are the kinds of things that belong there:"
>
> "- **Meeting notes** — After an important meeting, drop the notes in Knowledge/. Next time you ask Claude about that topic, it'll find them."
> "- **Competitive intel** — Competitor updates, win/loss reports, market research."
> "- **Decision records** — When you make an important decision, write down what you decided and why. Your future self will thank you."
> "- **Processes and playbooks** — How you do things. Onboarding steps, deal qualification criteria, customer escalation procedures."
>
> "You don't have to organize it perfectly. Use descriptive filenames and Claude will find what it needs."
>
> "And here's the best part: in the last lesson, you'll get a skill called the **Daily Debrief**. You'll connect Fireflies, say 'close my day,' and Claude will pull your meeting transcripts, process them into Knowledge files, suggest new tasks, and update your vault index — all without you lifting a finger."
>
> "For now, the manual version works great. What's one thing you could add to Knowledge/ right now?"

**STOP. Wait for their response.** If they want to add something, help them create the file.

---

### Step 4: Your Vault Index

> "As your Personal OS grows — more Knowledge files, more tasks, more daily entries — Claude needs a way to know what's in here without reading every single file."
>
> "Right now you have maybe 10 files. But imagine you have hundreds. Meeting notes, competitive research, partner profiles, process docs. If Claude had to open every file to figure out which ones matter for your question, it would blow through your context window before it even got to your actual request."
>
> "The trick is a **vault index** — basically a table of contents for your entire Personal OS. One line per file, describing what's in it. You add a pointer in your AGENTS.md that says 'read the vault index to understand what files exist.' Now Claude can scan the index, find the 2-3 files that are relevant, and only read those."
>
> "This is why we keep AGENTS.md short — it loads every single conversation. If you tried to describe every file in AGENTS.md directly, it would get massive. Instead, AGENTS.md just points to the index, and the index points to everything else."

**STOP. Wait for their response.**

---

### Step 4b: Generate the Index

> "Let me generate your vault index right now."

Scan the student's entire Personal OS folder. Create `Knowledge/vault-index.md` with an entry for every file:

```markdown
# Vault Index

One-line description of every file in the Personal OS. Claude reads this to know what exists and where to find it.

## Foundation
- `AGENTS.md` -- AI instruction manual, loaded every conversation
- `Constitution.md` -- Personal values, beliefs, and principles
- `Business.md` -- Professional context, role, accounts, competitive landscape
- `GOALS.md` -- Priorities organized by timeframe

## Tasks
- `Tasks/[filename].md` -- [one-line description per task]

## Knowledge
- `Knowledge/[filename].md` -- [one-line description per file]
```

Also add a pointer to the vault index in the student's AGENTS.md, under the "My Personal OS Structure" section: `- Knowledge/vault-index.md — Table of contents for all files. Read this to find what's relevant.`

> "Done — your vault index is at `Knowledge/vault-index.md`, and I've added a pointer to it in your AGENTS.md. Now Claude can always find the right files without reading everything."
>
> "Now, this probably sounds like a lot of work to maintain — adding a line every time you create a new file. The good news: in the next lesson, you'll get a skill that updates this automatically. You won't have to touch it."

**STOP. Wait for their response.**

---

### Step 5: Evolving Your AGENTS.md

> "Your AGENTS.md isn't set in stone. It should evolve as you learn what works and what doesn't."
>
> "**Signs it's time to update AGENTS.md:**"
> "- Claude keeps making the same mistake → add a rule about it"
> "- You keep repeating the same instruction → move it into AGENTS.md"
> "- Your priorities shifted → update the pointers or working style preferences"
> "- You discovered a new workflow → add it to the instructions"
>
> "**Signs your AGENTS.md is too long:**"
> "- Claude seems to ignore parts of it → it's beyond what fits in context"
> "- You haven't updated it in months → some of it is probably stale"
> "- It has detailed content instead of pointers → move content to other files"
>
> "Remember: shorter is better. AGENTS.md gets loaded in EVERY conversation. Every word in it is a word that can't be used for your actual request."
>
> "Take a look at your AGENTS.md now. Anything you'd already want to change based on your experience today?"

**STOP. Wait for their response.** Make any changes they suggest.

---

### Step 6: The Weekly Review

> "Here's a practice that keeps your Personal OS healthy: a weekly review. Takes about 10 minutes."
>
> "**Every week, ask Claude:**"
> "1. 'Review my tasks — what's stale, what's done, what needs reprioritizing?'"
> "2. 'Process my backlog'"
> "3. 'Are my goals still current?'"
>
> "**Every month:**"
> "- Read through your Constitution.md — still feel accurate?"
> "- Update Business.md if your role, accounts, or landscape changed"
> "- Refresh GOALS.md for the new month/quarter"
>
> "The system only works if you maintain it. But the maintenance is minimal — 10 minutes a week, and Claude does most of the heavy lifting."

**STOP. Wait for their response.**

---

### Step 7: Tips and Tricks

> "A few final tips from people who use this daily:"
>
> "**Tip 1: Use BACKLOG.md liberally.** The best ideas come at the worst times. Just dump them. Don't try to organize in the moment."
>
> "**Tip 2: Name files descriptively.** `competitive-analysis-q1-2026.md` beats `notes.md`. Claude uses filenames to decide what's relevant."
>
> "**Tip 3: Don't over-engineer it.** If your Personal OS starts feeling like work, simplify. Drop folders you don't use. Merge files that overlap."
>
> "**Tip 4: Share what works.** If you find a workflow or AGENTS.md instruction that's great, share it with the team. These systems get better through collective learning."
>
> "And a few tips specifically for better AI memory:"
>
> "**Be specific in AGENTS.md.** Vague instructions get vague results. 'Be helpful' does nothing. 'Challenge my assumptions before agreeing with my plan' changes behavior."
>
> "**Update GOALS.md regularly.** Stale goals lead to wrong priorities. If Claude keeps suggesting things that don't matter anymore, your goals file is probably out of date."
>
> "**Use Knowledge/ for reference.** Don't repeat context in every task. Put it in Knowledge/ once and let Claude find it when it's relevant."
>
> "**Link related files.** Help Claude find connections by referencing other files — for example, a task can point to `Knowledge/heartland-qbr-notes.md` for background."

**STOP. Wait for their response.**

---

### Step 8: What's Next

> "Now, if you're looking at all of this thinking 'that's a lot to keep updated' — I hear you. Maintaining your Constitution, Business context, Goals, Tasks, and Knowledge manually after every meeting and every decision sounds like work."
>
> "Here's the good news: **you won't have to.** The next lesson changes everything."
>
> "In Lesson 9, you'll learn about **skills** — reusable instruction files that automate the upkeep for you. After a meeting, you'll say 'debrief my meeting' and Claude will automatically pull the transcript, cross-reference it against your goals, suggest task updates, flag knowledge additions, and check for goal changes. All from a single command."
>
> "You'll also learn how to build your own skills for any workflow you repeat — and how to stress-test them so they work reliably."
>
> "Ready?"

> **What would you like to do?**
> - **A)** Move on to Lesson 9 — Skills and automation
> - **B)** I want to spend more time setting up my maintenance habits first
> - **C)** I have questions about what we covered

If they choose A, fetch the next lesson: use the Claude in Chrome connector to read `https://raw.githubusercontent.com/pat-walther/agvend-personal-os/main/personal-os/09-skills-and-automation.md` and continue teaching.

**Share prompt:** What's one thing you learned about context and memory that changed how you think about working with AI?

---

## Reference Material

**Context window management (for Claude's reference):**
- Start new conversations for new topics — don't let threads get stale
- Files persist, chats don't — the value lives in documents
- AGENTS.md loads every time — keep it short (under 500 words)
- Long chats degrade performance — this is "context rot"
- If a chat starts giving weird answers, start fresh

**Maintenance cadence:**
- Daily: backlog capture, task completion, morning priorities (5 min)
- Weekly: task review, backlog processing, stale task cleanup (10 min)
- Monthly: goals refresh, business context update, Constitution check (15 min)
- Quarterly: major goals revision, AGENTS.md overhaul, archive old tasks (30 min)

**Common failure modes and fixes:**
- "Claude doesn't seem to know me" → Check that AGENTS.md exists in the project root
- "Claude ignores my files" → Make sure the project has folder access granted
- "My context window fills up fast" → AGENTS.md is probably too long. Trim it.
- "Tasks are getting stale" → Schedule a weekly review habit
- "I stopped using it" → Simplify. Use only BACKLOG.md and GOALS.md if the full system is too much.

**What makes a great Personal OS:**
- Concise — every file earns its space
- Current — reflects reality, not aspirations from 3 months ago
- Connected — goals tie to values, tasks tie to goals
- Consistent — updated regularly, even if briefly
- Personal — written in your voice, for your workflow, not a template you never customized
