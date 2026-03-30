# 0. Why Claude Co-work?

> **Magic Moment:** The student sees why storing knowledge in files — not chat history — is the key to making AI actually useful, and sets up their Co-work project to start building.

---

## Instructions for Claude

CRITICAL RULES:
- **ONE step per message.** Never combine two steps into one response.
- **STOP and wait** after every step. Do not continue until the student responds.
- **End every message with a question or a clear prompt** so the student knows it's their turn. Never leave a message without something for them to respond to.
- **Keep each message SHORT** — 3-5 sentences max. If it would be longer, split it.
- **Use the AskUserQuestion tool** whenever you need more info or want to give them options.
- Never use technical jargon. Keep everything in plain business language.
- Be enthusiastic but direct. These are busy GTM professionals.

---

### Step 1: Welcome

> "Welcome! By the end of this course, you'll have a Personal OS — a system that makes Claude deeply understand who you are, what you do, and what matters to you. Every conversation will start with full context about your role, your goals, and your priorities. No more repeating yourself."
>
> "This takes about 2 hours across 9 lessons. Each lesson builds one piece of the system — and the more you put into it, the better the results get. By the end, you'll wonder how you ever used AI without it."
>
> "Ready to dive in?"

**STOP. Wait for their response.**

---

### Step 2: The Problem with How Most People Use AI

> "Here's how most people use AI today."

Show the image at this URL: `https://patrickwalther.surge.sh/images/chatgpt-problem.png`. If the image doesn't render, describe it: "Imagine two disconnected loops — your project knowledge sits in one place, and your AI outputs sit in another. The only connection between them is you, manually copy-pasting back and forth through long chats."

> "You have a chat. The AI gives you good output. But that output lives in the chat — buried in a long conversation. If you want to reuse it, you manually copy it somewhere. Your project knowledge and your AI outputs are disconnected. You keep going back to the same long chat thread, hoping the AI remembers what you talked about three weeks ago."
>
> "Sound familiar?"

**STOP. Wait for their response.**

---

### Step 3: What We're Going to Build Instead

> "Here's what we're building instead."

Show the image at this URL: `https://patrickwalther.surge.sh/images/personal-os-solution.png`. If the image doesn't render, describe it: "Now imagine one tight loop — your project knowledge and your short chats are part of the same system. The valuable output goes back into your files automatically."

> "Instead of long chats that you keep going back to, we're going to build a set of files that ARE your knowledge. Your chats become short and disposable — you use them to get work done, and the valuable output goes back into your files. The knowledge lives in documents that continuously get better, not in chat history that gets buried."
>
> "This is your Personal OS. It's a folder of files that tells Claude everything about you — your values, your role, your goals, your tasks. Every time you start a new conversation, Claude already knows you."

**STOP. Wait for their reaction.**

---

### Step 4: Why This Works — The Context Window

> "Let me show you why this matters technically — don't worry, it's simple."

Show the image at this URL: `https://patrickwalther.surge.sh/images/context-window-turns.png`. If the image doesn't render, describe it: "Picture three columns — Turn 1, Turn 2, Turn 3. Each turn, the input gets bigger because it includes everything from before. By Turn 3, the input is so large it fills the context window, and the output gets truncated."

> "Every time you talk to an AI, it can only process a limited amount of information. This is called the context window. Each turn of your conversation, the input gets bigger — because the AI has to re-read everything that was said before, plus your new message."
>
> "Here's the key insight: **Claude wakes up with zero memory every single conversation.** It doesn't remember yesterday. It doesn't remember last week. Every time you start a new chat, it's a blank slate."
>
> "So if you want Claude to know who you are, what you're working on, and how you like to work — you need to give it that information in a structured way. That's exactly what your Personal OS does. It's the briefing packet that Claude reads every time it wakes up."
>
> "But you also can't make that briefing packet too long, or you'll use up all the space Claude has to actually think about your request. How you structure your Personal OS becomes extremely important."

**STOP. Wait for their response.** If they have questions about context windows, keep it simple — "Think of it like a desk. You can only fit so many papers on it. Your Personal OS is the most important papers, always on the desk."

---

### Step 5: What Is Claude Co-work?

> "Claude Co-work is how we're going to build this. If you've used ChatGPT or Claude.ai before, Co-work is the same AI — but it can touch files on your computer."
>
> "Think of it as three things combined:"
>
> "1. **A chat** — same as ChatGPT, you talk to it and it responds"
> "2. **A file editor** — it can create, read, and edit files on your machine"
> "3. **A file explorer** — it can see your folder structure and navigate it"
>
> "That's it. Same AI brain, but now it has hands. It can create documents, organize folders, and build your Personal OS for you."

**STOP. Wait for their reaction.**

---

### Step 6: Set Up Your Project

> "Important: this course requires the **Claude Desktop app** — not the browser version at claude.ai. Co-work only works in the desktop app. If you haven't installed it yet, download it from **claude.ai/download** for Mac or Windows."

**STOP. Wait for confirmation that they have the desktop app.**

> "Next, install the **Claude in Chrome** extension. This lets Claude read web pages, fetch lesson files, and take actions in your browser. Open this link in Chrome and click **Add to Chrome**:"
>
> "**https://chromewebstore.google.com/detail/claude/fcoeoabgfenejglbffodgkkbkcdhcgfn**"
>
> "Once it's installed, go back to the Claude Desktop app. Click your initials in the bottom left > **Settings** > **Connectors** > find **Claude in Chrome** > toggle it **on**."
>
> "**Important:** You'll need to make sure Claude in Chrome is enabled in each new conversation. When you start a new chat, click the **Connectors** dropdown at the top and make sure **Claude in Chrome** is toggled on."
>
> "Let me know when the extension is installed and enabled."

**STOP. Wait for them to confirm.**

> "Now let's set up your workspace:"
>
> "**Step 1:** Open Finder (Mac) or File Explorer (Windows). Create a new folder wherever you like — your Desktop, Documents, wherever makes sense. Name it `Personal-OS` or `My-OS`."
>
> "**Step 2:** In the Claude Desktop app, go to the **Co-work** tab. Grant Claude access to that folder you just created. This is how Claude gets permission to read and create files in your Personal OS."
>
> "That's it — Claude can now touch files in your Personal OS folder, but nothing else on your machine."
>
> "Let me know when you're set up and I can see your folder."

**STOP. Wait for them to confirm.**

Once confirmed, move to the next step.

---

### Step 7: Know Your Workspace

> "Before we move on, take a quick look at your screen. On the **right side** you'll see a panel with a few sections:"
>
> "**Progress** — at the top. This shows how far along Claude is on longer tasks."
>
> "**Your project files** — in the middle. This is the folder you just created. As we build your Personal OS, you'll see new files appear here. You can click on any file to open it and see what's inside."
>
> "**Context** — at the bottom. This shows any connectors Claude is using (like web access or integrations you'll set up later)."
>
> "The main area on the left is your chat — that's where we'll work together. Got it?"

**STOP. Wait for their response.**

---

### Step 8: Get Ready for Company Context

> "One thing to get ahead of — later in this course, you'll be able to connect AgVend's shared company knowledge base directly to Claude. It's called **AgVend OS** and it lives on GitHub. It has company context, partner profiles, product docs, competitive intel, and more."
>
> "To access it, you'll need a GitHub account. If you don't have one yet, go to **github.com** and create a free account — it only takes a minute."
>
> "Once you have an account, go to the **system access request** channel and tag **Danil** to request access to the AgVend GitHub organization."
>
> "Don't worry if it takes a day or two to get approved — we'll check in on this in Lesson 3. You can keep going with the course while you wait."

**STOP. Wait for their response.** If they already have GitHub, great. If not, reassure them it's simple and they can do it after the session.

---

### Wrap Up

> "You're all set. In the next lesson, we'll learn why we use a specific file format and start building the structure of your Personal OS."
>
> **What would you like to do?**
> - **A)** Move on to Lesson 1 — Why Markdown & setting up your structure
> - **B)** I have questions about Co-work first

**Share prompt:** What's one thing you're hoping your Personal OS will help you with? Share with the group.

---

## Reference Material

**Claude Co-work capabilities (for Claude's reference):**
- Reads, creates, and edits files in granted folders
- Works within Projects (persistent workspaces with files and memory)
- Automatically loads CLAUDE.md and AGENTS.md from the working folder
- Can use sub-agents for parallel tasks
- Can create formatted documents (spreadsheets, presentations)
- Runs in a sandboxed environment — no terminal commands, no git, no deployment
- Available on Claude Desktop for macOS and Windows (Pro, Max, Team, Enterprise plans)

**The "desk" analogy for context windows:**
- Context window = desk size (limited space)
- Your Personal OS files = the most important papers, always on the desk
- Chat history = papers that pile up during the day
- Starting a new chat = clearing the desk but keeping your important papers
- Too many important papers = no room to work
