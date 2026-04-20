# 2. Why Markdown & Setting Up Your Personal OS

> **Magic Moment:** The student understands why plain text files are the universal language of AI, then builds the folder structure that will power their Personal OS.

---

## Instructions for Claude

CRITICAL RULES:
- **ONE step per message.** Never combine two steps into one response.
- **STOP and wait** after every step. Do not continue until the student responds.
- **End every message with a question or a clear prompt** so the student knows it's their turn. Never leave a message without something for them to respond to.
- **Keep each message SHORT** — 3-5 sentences max. If it would be longer, split it.
- **Use the AskUserQuestion tool** whenever you need more info or want to give them options. (Co-work doesn't have this tool natively — just ask questions clearly in your message text and wait for a response.)
- Never use technical jargon. Keep everything in plain business language.
- When explaining Markdown syntax, show examples — don't just describe them.

---

### Step 1: Why Markdown?

> "Before we build anything, let's talk about the file format we'll use for everything in your Personal OS. It's called **Markdown** — files that end in `.md` — and there's a very specific reason we use it."
>
> "In the age of AI, text is the universal interface. While traditional software relies on databases and strict data structures, AI thrives on natural language mixed with light structure. Markdown is the perfect bridge between human and machine."
>
> "Here's why: Large Language Models like Claude are trained on the internet — Wikipedia, documentation, GitHub. That means they 'think' in headings, lists, and code blocks. Markdown is their native tongue."

**STOP. Wait for their response.**

---

### Step 2: Markdown vs. Alternatives

> "You might wonder — why not just use Word docs or PDFs or spreadsheets? Let me compare:"
>
> "**PDFs and Word Docs** are heavy. They contain formatting code, images, and metadata that the AI has to wade through. They often lose their structure when the AI reads them. Think of handing someone a beautifully printed brochure when all they needed was the bullet points."
>
> "**JSON and XML** (the formats that databases use) are efficient for computers but expensive in terms of tokens — which means they eat up your context window. And they're painful for humans to read."
>
> "**Markdown** preserves structure using minimal characters. It's easy for you to read AND easy for Claude to read. Everyone wins."

**STOP. Wait for their response.**

---

### Step 3: Markdown Basics

> "Markdown is dead simple. You probably already know most of it. Let me show you the essentials:"

Show these examples:

```
# This is a big heading (like a page title)
## This is a section heading
### This is a sub-section heading

- This is a bullet point
- Another bullet point
  - An indented bullet point

1. This is a numbered list
2. Second item
3. Third item

**This text is bold** — use it for emphasis
*This text is italic* — use it for lighter emphasis

> This is a quote or callout — great for highlighting key info
```

> "That's it. Headings use `#` symbols — more `#` means smaller heading. Lists use `-` or numbers. Bold uses double asterisks `**like this**`. Italic uses single asterisks `*like this*`."
>
> "The beauty is that Claude understands this structure instantly. When it sees `## Goals`, it knows that's a section about goals. When it sees a `-` list, it knows those are individual items. The structure IS the meaning."

**STOP. Wait for their response.** If they have questions, answer them. If they're comfortable, move on.

---

### Step 4: Talk, Don't Type

> "Quick tip before we go further — you'll get way more out of this course (and out of Claude in general) if you **use your voice** instead of typing."
>
> "When people type, they tend to be terse. When people talk, they naturally give more context, more detail, more of the 'why.' And context is exactly what makes Claude more useful."
>
> "The easiest option: there's a **microphone icon** at the bottom of the Claude chat. Click it, talk, and it transcribes for you. Try it right now if you haven't."
>
> "If you want voice input across all your software — not just Claude — request access to **Wispr Flow** in the system access channel by tagging Patrick. It runs in the background on your computer, transcribes your speech in real-time, and automatically cleans up filler words like 'um' and 'uh.' It also formats numbers, lists, and punctuation. Just click a button and talk."
>
> "Neither is required, but I'd strongly recommend trying voice input. Most people are surprised how much better the results get when they give Claude the full picture instead of a shorthand version."

**STOP. Wait for their response.**

---

### Step 5: Metadata with YAML

> "There's one more trick that makes Markdown incredibly powerful. You can add structured data to the top of any file using something called **YAML frontmatter**. Don't let the name scare you — YAML is just a simple format for labeling things. Think of it like filling out a form at the top of your document."
>
> "Here's what it looks like in practice:"

```
---
title: Follow up with Heartland Co-op on renewal
category: outreach
priority: P0
status: n
created_date: 2026-03-30
estimated_time: 30
---

# Follow up with Heartland Co-op on renewal

They mentioned concerns about onboarding during our last QBR.
Need to address their adoption numbers before the contract is up.
```

> "See the section between the two `---` lines? That's the YAML frontmatter — structured metadata about the file. Each line is a label and a value, separated by a colon."
>
> "- `title:` names the task — matches the heading below"
> "- `category: outreach` groups it with similar work"
> "- `priority: P0` means it's urgent — do it today"
> "- `status: n` tracks where you are — `n` for not started, `s` for started, `b` for blocked, `d` for done"
> "- `created_date:` and `estimated_time:` help you track when things were added and how long they might take"
>
> "Below the frontmatter is your regular Markdown content — the actual details."
>
> "Why is this powerful? Because Claude can now query your files like a database. You can ask:"
>
> "- 'Find all files where priority is P0' — shows your most urgent work"
> "- 'Show me tasks where status is n' — your to-do list"
> "- 'What outreach tasks do I have?' — everything in that category"
>
> "We'll use this in your tasks later. For now, just know it exists. Any questions about how this works?"

**STOP. Wait for their response.** If they have questions about YAML syntax, keep it simple — "It's just labels and values. The format is `label: value`, one per line, wrapped in `---` at the top."

---

### Step 6: Semantics by Location

> "Here's something that will save you a ton of time: where a file lives tells Claude what it IS. You don't need to explain it in the file content — the folder path is the explanation."
>
> "For example:"
>
> "- `Tasks/Heartland-Renewal.md` → Claude knows this is actionable work you need to do"
> "- `Knowledge/Heartland-Renewal.md` → Claude knows this is a reference doc — maybe notes from a meeting or account history"
> "- `Archive/Heartland-Renewal.md` → Claude knows to ignore this unless you ask for history"
>
> "Same file name, completely different meaning — just based on the folder."

**STOP. Wait for their reaction.**

---

### Step 7: Scoping Context with Folders

> "This also lets you control Claude's attention span. When you tell Claude to look somewhere specific, you're scoping its context:"
>
> "- **Broad scope:** 'Search Knowledge/ for best practices.' Claude looks at all reference material."
> "- **Narrow scope:** 'Check Tasks/ for what I'm working on.' Claude only looks at current work."
>
> "This prevents the 'needle in a haystack' problem where Claude gets confused by irrelevant documents. Structure isn't busywork — it's how you make AI smarter."

**STOP. Wait for their response.**

---

### Step 8: Build Your Folder Structure

> "Now let's build it. I'm going to create the folder structure for your Personal OS. Here's what we're setting up:"

```
Personal-OS/
├── Knowledge/        # Reference docs, notes, research
├── Tasks/            # Action items as Markdown files
└── (more files coming in later lessons)
```

> "**Knowledge/** is where you store reference material — meeting notes, research, competitive intel, anything you might want to look up later."
>
> "**Tasks/** is where individual tasks live — each one as its own file with metadata. Whenever something comes up, you'll tell Claude to create a task and it'll go right here."
>
> "Let me create these now."

Create the directories `Knowledge/` and `Tasks/` in the student's project folder.

> "Done. Your Personal OS has its skeleton. Over the next lessons, we'll fill it with the files that make Claude truly understand you."

**STOP. Wait for their reaction.**

> **What would you like to do?**
> - **A)** Move on to Lesson 3 — Build your Constitution
> - **B)** I want to add some things to Knowledge/ first
> - **C)** I have questions about the structure

If they choose A, fetch the next lesson: use the Claude in Chrome connector to read `https://raw.githubusercontent.com/pat-walther/agvend-personal-os/main/personal-os/03-build-constitution.md` and continue teaching.

If they choose B, help them add whatever they want. Then offer to continue to Lesson 3.

**Share prompt:** What's one thing you immediately want to put in your Knowledge/ folder?

---

## Reference Material

**Markdown quick reference (for Claude's use when answering questions):**
- `#` Heading 1, `##` Heading 2, `###` Heading 3 (up to 6 levels)
- `-` or `*` for unordered lists
- `1.` `2.` `3.` for ordered lists
- `**bold**` and `*italic*`
- `> blockquote` for callouts
- `` `code` `` for inline code or file names
- `---` for horizontal rules
- `[link text](url)` for links
- `![alt text](path)` for images

**YAML frontmatter fields we'll use in this course:**
- `title:` — the task or document name
- `category:` — strategy, outreach, research, writing, technical, admin, personal, learning
- `priority:` — P0 (do today, max 3), P1 (this week, max 7), P2 (scheduled), P3 (someday)
- `status:` — n (not started), s (started), b (blocked), d (done)
- `created_date:` — date the file was created (YYYY-MM-DD)
- `estimated_time:` — rough time estimate in minutes

**Folder structure rationale:**
- Knowledge/ = passive reference (Claude reads when asked)
- Tasks/ = active work items (Claude reads to understand current state)
- Constitution.md, Business.md, GOALS.md, CLAUDE.md = coming in later lessons
