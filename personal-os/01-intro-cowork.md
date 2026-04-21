# 1. Why Claude Co-work?

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
- **IMPORTANT:** The GitHub URLs and Surge URLs in lesson files contain the course creator's name (pat-walther / patrickwalther). This is NOT the student's name. Never use "Walther" or "Patrick" as the student's name. Always ask the student for their name.

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

Show the image at this URL: `https://patrickwalther.surge.sh/images/chatgpt-problem_adj.png`. If the image doesn't render, describe it: "Imagine two disconnected loops — your project knowledge sits in one place, and your AI outputs sit in another. The only connection between them is you, manually copy-pasting back and forth through long chats."

> "You have a chat. The AI gives you good output. But that output lives in the chat — buried in a long conversation. If you want to reuse it, you manually copy it somewhere. Your project knowledge and your AI outputs are disconnected. You keep going back to the same long chat thread, hoping the AI remembers what you talked about three weeks ago."
>
> "Sound familiar?"

**STOP. Wait for their response.**

---

### Step 3: The Blank Slate — How Claude's Memory Actually Works

> "So why does that happen? Let me explain something fundamental about how Claude works. This will change how you think about every AI conversation you have."
>
> "Here's the key insight: **Claude wakes up with zero memory every single conversation.** It doesn't remember yesterday. It doesn't remember last week. Every time you start a new chat, it's a completely blank slate."
>
> "That means the brilliant conversation you had last Tuesday? Gone. The context you spent twenty minutes explaining? Claude doesn't know it happened."

**STOP. Wait for their response.**

---

### Step 3b: How Conversations Really Work Under the Hood

> "It goes even deeper than that. Even *within* a single conversation, Claude doesn't actually remember what you said earlier. Here's what's really happening:"
>
> "When you send your first message, Claude reads it and responds. Simple. But when you send your second message, the system takes your first message, Claude's first response, AND your new message — and sends that entire thing back to Claude. Claude reads all of it fresh, then generates a new response."
>
> "When you reply a third time, it takes *everything* — all your messages, all of Claude's responses, plus your new one — and sends the whole transcript back. Claude reads the entire conversation from the top again."
>
> "It's not like talking to a person who remembers what you said. It's more like handing someone a transcript of your conversation every single time and saying 'read this and respond to the latest message.'"

Show the image at this URL: `https://patrickwalther.surge.sh/images/context-window-turns.png`. If the image doesn't render, describe it: "Picture three columns — Turn 1, Turn 2, Turn 3. Each turn, the input gets bigger because it includes everything from before. By Turn 3, the input is so large it fills the context window, and the output gets truncated."

> "This is what that looks like. See how the input grows with every turn? That's because it's re-reading everything from scratch each time."

**STOP. Wait for their response.**

---

### Step 3c: The Context Window — Why Long Conversations Break Down

> "Now here's where it gets tricky. That transcript can only get so long. Claude has what's called a **context window** — think of it like a fixed-size desk. You can only fit so many papers on it. Each turn of your conversation, the stack of papers gets bigger because it includes everything from before."
>
> "Once the conversation gets long enough, the oldest parts start falling off the edge. Claude literally can't see them anymore."
>
> "You've probably already experienced this. You're deep in a conversation, and suddenly it feels like Claude forgot something you said at the beginning. It's not being difficult — it physically can't see those early messages anymore because they've been pushed out of the window."

**STOP. Wait for their response.**

---

### Step 4: What We're Going to Build Instead

> "So now you understand the two problems: Claude starts every conversation with zero memory, and even within a conversation, older context eventually disappears. **The chat is not your single source of truth.** It can't be — it's temporary by design."
>
> "Here's what we're building instead."

Show the image at this URL: `https://patrickwalther.surge.sh/images/personal-os-solution.png`. If the image doesn't render, describe it: "Now imagine one tight loop — your project knowledge and your short chats are part of the same system. The valuable output goes back into your files automatically."

> "Instead of relying on chat history, we're going to build a set of files that ARE your knowledge. **Your files are the source of truth — not the chat.** Files persist. They're always there. The chat disappears."
>
> "Here's the workflow: you have a conversation with Claude, you learn something valuable — a new insight, a better way to phrase your goals, an updated list of priorities. Instead of hoping you'll find that buried in a chat transcript later, you update your file. The file always has the latest, best version of your thinking. Every conversation makes your files smarter."
>
> "This is your Personal OS. It's a folder of files that tells Claude everything about you — your values, your role, your goals, your tasks. Every time you start a new conversation, those files get loaded in, and Claude already knows you."
>
> "But you also can't make those files too long, or you'll use up all the space Claude has to actually think about your request. How you structure your Personal OS becomes extremely important — it's about giving Claude the *right* context, not *all* the context."

**STOP. Wait for their response.** If they have questions, keep the desk analogy going — "Your Personal OS files are the most important papers, always on the desk. Chat history is papers that pile up during the day. Starting a new chat clears the desk but keeps your important papers."

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

### Step 5b: Know Your Workspace

> "Let me quickly orient you to what you're looking at. On the **right side** of your screen, you'll see a panel with three sections:"
>
> "**Progress** — at the top. If Claude has several tasks to do, they'll show up here so you can see what it's working on."
>
> "**Files** — in the middle. This is the folder you've opened. As we build your Personal OS, you'll see new files appear here. You can click any file to open it and see what's inside."
>
> "**Context** — at the bottom. When Claude uses connectors, skills, or plugins, they show up here while it's using them. We'll explain what those are in a moment."
>
> "The main area on the the middle is your chat — that's where we'll work together. Got it?"

**STOP. Wait for their response.**

---

### Step 5c: Extending Claude — Connectors, Skills, and Plugins

> "There are three ways to extend what Claude can do beyond the basics. You don't need to set any of these up right now — I just want you to know they exist."
>
> "**Connectors** are ways to connect Claude to other software you use at AgVend and get data from there. For example: Slack, Google Calendar, Gmail. You probably already have your first one — **Claude in Chrome** — since we've been using it to show images today."
>
> "**Skills** let you teach Claude a repeatable process it can run over and over again. We'll build some of these later in the course."
>
> "**Plugins** are a way for the organization to share a combination of skills and connectors together. We'll use one of these in Lesson 4 to load AgVend's company knowledge base."
>
> "You can find all of these by clicking the **+** button just below the reply box."

**STOP. Wait for their response.**

> "If you don't have the Claude in Chrome extension yet, install it here — open this link in Chrome and click **Add to Chrome**: **https://chromewebstore.google.com/detail/claude/fcoeoabgfenejglbffodgkkbkcdhcgfn**"
>
> "Once it's installed, click the **+** below the reply box, then **Connectors**, and make sure **Claude in Chrome** is toggled on."

**STOP. Wait for them to confirm Claude in Chrome is enabled.**

---

### Step 6: Your Project Folder

> "You’ve already set up a folder on your computer and allowed Claude access—this is your Personal OS."
> 
> "As we work through the course, Claude will create and update files in that folder, like your Constitution, Business context, and Goals. Everything lives locally, right on your machine."
> 
> "You can always open that folder in Finder (Mac) or File Explorer (Windows) to see and manage your files—they’re just regular documents, fully owned by you."
> 
> "And most importantly: these files are private. They’re saved only on your computer. No one else can read them but you."

**STOP. Wait for their response.**

---

### Wrap Up

> "You're all set. In the next lesson, we'll learn why we use a specific file format and start building the structure of your Personal OS."
>
> **What would you like to do?**
> - **A)** Move on to Lesson 2 — Why Markdown & setting up your structure
> - **B)** I have questions about Co-work first

If they choose A, fetch the next lesson using the Claude in Chrome connector and continue teaching. Try either URL — use whichever one works:
- Raw: `https://raw.githubusercontent.com/pat-walther/agvend-personal-os/main/personal-os/02-why-markdown-and-setup.md`
- GitHub: `https://github.com/pat-walther/agvend-personal-os/blob/main/personal-os/02-why-markdown-and-setup.md`

**Share prompt:** What's one thing you're hoping your Personal OS will help you with? Share with the group.

---

## Reference Material

**Claude Co-work capabilities (for Claude's reference):**
- Reads, creates, and edits files in granted folders
- Works within Projects (persistent workspaces with files and memory)
- Automatically loads CLAUDE.md from the working folder
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
