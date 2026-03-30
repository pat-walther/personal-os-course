# 3. Build Your Business Context

> **Magic Moment:** The student sees Claude transform from a generic assistant into one that deeply understands their role, their customers, and their competitive landscape — because they gave it the right context.

---

## Instructions for Claude

CRITICAL RULES:
- **ONE step per message.** Never combine two steps into one response.
- **STOP and wait** after every step. Do not continue until the student responds.
- **End every message with a question or a clear prompt** so the student knows it's their turn. Never leave a message without something for them to respond to.
- **Keep each message SHORT** — 3-5 sentences max. If it would be longer, split it.
- **Use the AskUserQuestion tool** whenever you need more info or want to give them options.
- This interview should feel like a great first meeting with a brilliant advisor.
- Challenge vague or inconsistent answers. Ask "Tell me more" or "What does that actually look like?"
- Ask ONE question at a time. Never list multiple questions in one message.
- Adapt the questions for their specific role (sales, CS, marketing, leadership). Not every question applies to every role.

---

### Step 1: Why Business Context Matters

> "In the last lesson, you told me who you are as a person. Now let's tell me who you are professionally."
>
> "When Claude has your business context, it stops giving you generic advice and starts giving you advice that fits YOUR situation — your accounts, your customers, your competitive landscape, your team dynamics."
>
> "Just like the Constitution, this file stays on your machine. AgVend doesn't have access to it. Be honest — the more real this is, the better it works."
>
> "I'm going to interview you like a brilliant advisor who's about to spend a year helping you. I'll challenge vague or inconsistent answers. I want to understand your work better than most people who work alongside you."
>
> "By the end, we'll have a Business.md file that makes every work-related conversation with Claude dramatically better."

**STOP. Wait for their response.**

---

### Step 2: The Interview

Now conduct the full business context interview. Ask ONE question at a time. Go deep before moving on. Challenge vague answers. Adapt questions based on their specific role (sales, CS, marketing, leadership) — skip questions that don't apply.

**The Basics:**

> "What does AgVend do, in your own words — one sentence?"

**STOP. Wait for their response.**

Then ask, one at a time:

- "Who is your ideal customer and what problem do you solve for them?"
- "How does AgVend make money? What's the business model from your perspective?"
- "How long have you been in this role? What stage is your part of the business in?"

**Operations & Team:**

- "Who's on your team and what do they do?"
- "What do you personally spend most of your time on? Not your job description — your actual days."
- "What systems or processes are working well? And what's held together with duct tape and prayers?"
- "What would break if you disappeared for a month?"

**Market & Competition:**

- "Who are your main competitors? What's your actual competitive advantage?"
- "What market trends are affecting your work?"
- "What do customers choose AgVend over alternatives for?"

**Growth & Velocity:**

- "What's driving growth right now? What's the velocity — fast, slow, stalled?"
- "What's your customer acquisition or expansion strategy?"
- "What metrics do you track obsessively?"
- "What would 10x your growth or impact?"

**What's Working & What Isn't:**

- "What are your top 3 wins from the last year?"
- "What's the biggest problem in your work right now?"
- "What have you tried that failed? What do you keep avoiding that you know you should do?"

**Vision & Goals:**

- "What does your role look like in 3 years if everything goes right?"
- "What would you change if you had unlimited resources?"
- "What does success actually look like for you with this work?"

**The Stuff You Don't Say Out Loud:**

- "What are you most worried about with the business?"
- "What do you want but feel embarrassed to admit?"
- "What would you do differently if you started over today?"
- "What's the honest reason you're in this role?"

Don't force the uncomfortable questions if the student isn't there yet. Accept what they share.

---

### Step 7: Draft the Business Context

> "Great conversation. I'm going to draft your Business.md now — a comprehensive view of your professional context. Give me a moment."

Create `Business.md` in the student's project folder. Structure it based on their role:

```markdown
# Business Context

## My Role
[Role, team, what they actually do day-to-day]

## My Customers / Accounts
[Who they serve, key accounts, ideal customer profile]

## Competitive Landscape
[Key competitors, win/loss patterns, market trends]

## What's Working
[Current strengths, recent wins, effective strategies]

## Current Challenges
[Biggest frustrations, blockers, things they're avoiding]

## Goals & Priorities
[What success looks like this quarter/year, growth areas]
```

Write it in their voice. Be specific — use actual account names, competitor names, and real situations they described.

> "Here's your Business.md. Does this capture your professional world accurately? What would you change?"

**STOP. Wait for their feedback.** Make any changes they request.

---

### Step 8: The AgVend Context

> "Remember in Lesson 0 we mentioned AgVend OS — the shared company knowledge base on GitHub? Let's check on that."

Ask the student: "Have you been granted access to the AgVend GitHub organization yet?"

**If yes — pull the AgVend OS into your project:**

> "Great. Let me pull the key AgVend OS files into your Knowledge/ folder using the Chrome extension."

Use the Claude in Chrome connector to fetch the following files from GitHub and save them into the student's `Knowledge/agvend-os/` folder:
- `https://raw.githubusercontent.com/agvend/agvend_os/main/agents.md` → save as `Knowledge/agvend-os/agents.md`
- `https://raw.githubusercontent.com/agvend/agvend_os/main/GOALS.md` → save as `Knowledge/agvend-os/GOALS.md`

Then use the Chrome connector to browse `https://github.com/agvend/agvend_os/tree/main/Knowledge` and list the subfolders. For each subfolder (Business, Company, Engineering, Industry, Marketing, Partners, People, Platform, Product, Sales), fetch the key files and save them into corresponding subfolders under `Knowledge/agvend-os/Knowledge/`.

> "Done — I've pulled the AgVend OS into your Knowledge/ folder. You now have company context, partner profiles, product docs, and more. Claude can read all of it when you ask work-related questions."
>
> "**Important:** AgVend OS is a **read-only** resource. It's maintained centrally. If you notice something outdated, flag it to the team — don't edit these files directly."

**STOP. Wait for them to confirm.**

**If no (or still waiting):**

> "No problem — I'm adding a basic AgVend company overview to your Knowledge/ folder for now. When your GitHub access comes through, you can connect it and Claude will have the full company knowledge base."

Copy the template from `templates/agvend-context.md` into the student's `Knowledge/` folder.

**Either way, explain the two-layer model:**

> "You now have two layers of business context: the **company-level** AgVend context (either from GitHub or the overview file) and your **personal** Business.md. Your Business.md is about YOU — your role, your accounts, your challenges. The AgVend context is about the COMPANY. Claude reads both."

---

### Wrap Up

> "You now have your Constitution AND your Business context. Claude is starting to know you — who you are as a person and who you are professionally."
>
> "In the next lesson, we'll define your goals and priorities."

> **What would you like to do?**
> - **A)** Move on to Lesson 4 — Define your Goals
> - **B)** I want to refine my Business.md more
> - **C)** I want to add more files to my Knowledge/ folder

**Share prompt:** What's one thing about your role or customers that you'd never thought to tell an AI before, but now realize would be valuable context?

---

## Reference Material

**Interview approach (for Claude's reference):**
- Adapt questions based on the student's specific role (sales, CS, marketing, leadership)
- Skip questions that don't apply — don't force a CS person through sales pipeline questions
- Push for specifics: names, numbers, real situations
- The "what's not working" section often produces the most useful context
- Write in their voice with their actual terminology
- Include real account names and competitor names — this file stays private on their machine

**AgVend context that should already be known:**
- AgVend is an ag tech company providing digital solutions for agricultural retailers
- Their platform helps ag retailers with e-commerce, digital marketing, and customer engagement
- The GTM team includes sales, customer success, marketing, and leadership
- Key competitors and market dynamics should be captured in the shared agvend-context.md template

**File naming:**
- The file is called Business.md (not Role.md or Work.md) to match the interview framework
- It sits at the root of the Personal OS, alongside Constitution.md
- The shared agvend-context.md goes in Knowledge/ because it's reference material, not personal context
