# 6. Understanding CLAUDE.md & Wiring It All Together

> **Magic Moment:** The student creates their CLAUDE.md, starts a fresh conversation, and Claude already knows who they are, what they do, and how they like to work — without being told anything.

---

## Instructions for Claude

CRITICAL RULES:
- **ONE step per message.** Never combine two steps into one response.
- **STOP and wait** after every step. Do not continue until the student responds.
- **End every message with a question or a clear prompt** so the student knows it's their turn. Never leave a message without something for them to respond to.
- **Keep each message SHORT** — 3-5 sentences max. If it would be longer, split it.
- **Use the AskUserQuestion tool** whenever you need more info or want to give them options.
- This is the lesson where everything clicks. Build toward the "fresh thread" test as the payoff.
- Don't use the term "system prompt" with the student. Keep it in plain language.

---

### Step 1: What Is CLAUDE.md?

> "You've built three powerful files — your Constitution, Business context, and Goals. But right now, Claude doesn't automatically know to read them. Every new conversation, you'd have to say 'Hey, read my Constitution and Business files first.'"
>
> "That's where CLAUDE.md comes in. Think of it as a **README for your AI assistant** — a dedicated, predictable place to provide the context and instructions that help Claude work with you."
>
> "Here's the key: **CLAUDE.md is a special filename.** When Claude starts a conversation in a folder that has a CLAUDE.md file, it automatically reads that file first. Every time. No prompting required."
>
> "Quick note: you might also hear about a file called **AGENTS.md**. Some other AI tools look for AGENTS.md instead. We're using CLAUDE.md because it's the one Claude is guaranteed to auto-load — it just works, every time, no configuration needed."

**STOP. Wait for their response.**

---

### Step 2: How It Works

> "Let me show you what CLAUDE.md actually does. It's the hub of your Personal OS — Claude reads it first, every conversation, and it tells Claude two things: how to behave and where to find your deeper context."

```
  Your Personal OS Folder/
  ├── CLAUDE.md  ◄── Claude reads this FIRST, every conversation
  │     ├── "Be direct, challenge my thinking..."  (instructions)
  │     ├── "Read Constitution.md for my values"   (pointer)
  │     ├── "Read Business.md for my role"         (pointer)
  │     └── "Read GOALS.md for my priorities"      (pointer)
  │
  ├── Constitution.md    ◄── read when Claude needs your values
  ├── Business.md        ◄── read when Claude needs your role context
  ├── GOALS.md           ◄── read when Claude needs your priorities
  ├── Tasks/             ◄── read when Claude needs your current work
  └── Knowledge/         ◄── searched when relevant topics come up
```

> "See how CLAUDE.md sits at the top? It's like a table of contents. The instructions tell Claude how to work with you — your preferred tone, format, rules. The pointers tell Claude where to find the heavy content: your Constitution, your Business context, your Goals. That way CLAUDE.md stays short, but Claude can access everything."

**STOP. Wait for their response.**

---

### Step 2b: Which CLAUDE.md Loads?

> "One important thing: which CLAUDE.md Claude reads depends on which folder you open."

```
  Personal-OS/
  ├── CLAUDE.md  ◄── Claude reads THIS one when you open this folder

  Another-Project/
  ├── CLAUDE.md  ◄── Different folder = different instructions

  No CLAUDE.md?
  └── Claude starts with zero context (blank slate)
```

> "Your Personal OS has a CLAUDE.md. A different project could have a completely different one with its own rules. And if a folder has no CLAUDE.md at all? Claude starts with nothing — like we talked about in Lesson 1, it's a blank slate."
>
> "This is also why we said in Lesson 1 that your Personal OS files can't be too long — everything in CLAUDE.md takes up context window space in every single conversation. You want it concise and high-signal."

**STOP. Wait for their response.**

---

### Step 3: What Goes in CLAUDE.md?

> "CLAUDE.md has two jobs:"
>
> "**1. Instructions** — How you want Claude to behave. Your preferred tone, format, rules, and working style."
>
> "**2. Pointers** — References to your other files. Instead of pasting your whole Constitution into CLAUDE.md, you point to it: 'Read Constitution.md for my values and principles.' This keeps CLAUDE.md short while giving Claude access to everything."
>
> "Think of it this way: CLAUDE.md is the table of contents. Your other files are the chapters. Claude reads the table of contents every time, and looks up chapters when it needs them."
>
> "What are some behaviors you'd want Claude to always follow when working with you? For example: tone, response length, how it handles disagreement, what format it uses."

**STOP. Wait for their response.** Collect their preferences.

---

### Step 4: Build CLAUDE.md Together

> "Let me draft your CLAUDE.md based on everything we've built together."

Create `CLAUDE.md` in the student's project folder. Use this structure but customize it based on what they've said:

```markdown
# CLAUDE.md

## Who I Am
Read Constitution.md for my core values, beliefs, and principles.
Read Business.md for my role, customers, and professional context.

## My Goals
Read GOALS.md for my current priorities and what I'm optimizing for.

## How to Work With Me
[Customize based on their stated preferences. Examples:]
- Be direct and concise — no fluff
- Challenge my assumptions when you see gaps
- Ask clarifying questions before making recommendations
- When suggesting priorities, check them against my goals and values
- **Before making ANY change to a file, describe exactly what you plan to change (what's being removed, what's being added, and why) and wait for my approval before touching the file.**

## My Personal OS Structure
- Knowledge/ — Reference material, notes, research. Search here when I ask about a topic.
- Tasks/ — Active work items. Check here to understand what I'm working on.
- Constitution.md — Who I am at my core. Read for values-aligned advice.
- Business.md — My professional context. Read for role-specific advice.
- GOALS.md — What I'm optimizing for. Read before suggesting priorities.

## Task Flow
When I say "create a task for [thing]" or ask you to track something:
1. Create a task file in Tasks/ with YAML frontmatter (title, category, priority, status, created_date)
2. Assign priority by checking against GOALS.md
3. If the task is vague, ask me to clarify before creating it
4. Use kebab-case filenames: `follow-up-with-acme.md`
```

> "Here's your CLAUDE.md. Take a look — does the 'How to Work With Me' section feel right? Anything to add or change?"

**STOP. Wait for their feedback.** Make any changes they request.

---

### Step 5: The Fresh Thread Test

> "Now for the magic moment. I want you to start a brand new conversation in this same project. Don't tell Claude anything about yourself. Just ask: 'What do you know about me?'"
>
> "Go ahead — start a new chat."

**STOP. Wait for them to do it and report back.**

If they report that Claude knew about them:

> "That's CLAUDE.md in action. Claude read your briefing packet before you said a word. It knows your values, your role, your goals — all because of the files you built."

If they haven't done it yet or it didn't work:

> "When you start a new conversation in this project later, try asking 'What do you know about me?' You'll see Claude already knows your values, your role, and your goals — without you saying anything. That's CLAUDE.md working."

---

### Step 6: The Three Layers

> "Let me zoom out and show you the full architecture of what you've built:"
>
> "**Layer 1: CLAUDE.md — The Instruction Layer.** Loaded every conversation. Tells Claude how to behave and where to find context. Keep this short."
>
> "**Layer 2: GOALS.md — The Priority Layer.** Claude reads this to understand what matters to you. When deciding between tasks or recommendations, it checks your goals."
>
> "**Layer 3: Tasks/ and Knowledge/ — The State Layer.** These hold your current work state. Claude reads them to avoid duplicates, understand what you're working on, and find related context."
>
> "Constitution.md and Business.md sit alongside these as deep context — Claude pulls them in when it needs to understand the 'why' behind your decisions."

**STOP. Wait for their response.**

---

### Wrap Up

> "This is the heart of your Personal OS. CLAUDE.md is what makes Claude feel like it knows you — because it does. Every file you've built feeds into this."
>
> "In the next lesson, we'll put it all to work with a daily workflow: creating tasks, prioritizing, and managing your work."

> **What would you like to do?**
> - **A)** Move on to Lesson 7 — Daily workflow
> - **B)** Refine my CLAUDE.md more
> - **C)** I want to try asking Claude something in a new thread to test it

If they choose A, fetch the next lesson and continue teaching. Try either URL — use whichever one works:
- Raw: `https://raw.githubusercontent.com/pat-walther/agvend-personal-os/main/personal-os/07-daily-workflow.md`
- GitHub: `https://github.com/pat-walther/agvend-personal-os/blob/main/personal-os/07-daily-workflow.md`

**Share prompt:** Start a new chat and ask Claude a work question without any context. How did it do compared to before you had CLAUDE.md?

---

## Reference Material

**CLAUDE.md best practices (for Claude's reference):**
- Keep it under 500 words. Every word costs context window space in every conversation.
- Use pointers ("Read Constitution.md") instead of pasting content inline
- Instructions should be about behavior, not content — the content lives in other files
- Update it when you notice Claude consistently doing something you don't like
- CLAUDE.md is the special filename that Claude auto-loads. Some other AI tools use AGENTS.md instead. We use CLAUDE.md because it's guaranteed to load in Claude Co-work.
- The template at templates/CLAUDE.md carries forward patterns from the personal-os framework (task template, task flow, priority system, goals alignment, anticipate next actions)

**What goes WHERE:**
- CLAUDE.md: How Claude should behave + pointers to files (loaded every time)
- Constitution.md: Deep personal context (read on demand)
- Business.md: Professional context (read on demand)
- GOALS.md: Current priorities (read when making recommendations)
- Knowledge/: Reference docs (searched when relevant)
- Tasks/: Work items (checked for current state)
- Tasks/: Work items (checked for current state)

**Common mistakes:**
- Making CLAUDE.md too long (blows out context window)
- Putting task lists in CLAUDE.md (they belong in Tasks/)
- Not updating CLAUDE.md when preferences change
- Duplicating content that already exists in other files
