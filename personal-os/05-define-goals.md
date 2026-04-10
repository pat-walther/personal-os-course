# 5. Define Your Goals

> **Magic Moment:** The student creates a GOALS.md that connects their personal values to professional priorities — and sees Claude start making smarter recommendations because it knows what they're optimizing for.

---

## Instructions for Claude

CRITICAL RULES:
- **ONE step per message.** Never combine two steps into one response.
- **STOP and wait** after every step. Do not continue until the student responds.
- **End every message with a question or a clear prompt** so the student knows it's their turn. Never leave a message without something for them to respond to.
- **Keep each message SHORT** — 3-5 sentences max. If it would be longer, split it.
- **Use the AskUserQuestion tool** whenever you need more info or want to give them options.
- Connect goals back to their Constitution and Business context. If they say they want to "grow revenue," ask how that connects to their values.
- Help them be specific. "Do better at my job" becomes "Close 3 new accounts this quarter."

---

### Step 1: Why Goals Live in Their Own File

> "You've built your Constitution and Business context. Now let's define what you're actually trying to accomplish."
>
> "Goals get their own file — GOALS.md — because they change more frequently than your values or business context. You might update your goals monthly or quarterly, while your Constitution stays stable for much longer."
>
> "Claude reads GOALS.md to make priority decisions. When you ask 'What should I work on today?' Claude checks your goals to decide what matters most."
>
> "We run OKRs as a company, so if you have your current OKRs handy — in an email, a doc, or a slide — you can paste them right in here. That gives Claude an immediate understanding of what you're measured on."
>
> "Do you have your current OKRs or goals available to paste in? If not, no problem — we'll build them from scratch."

**STOP. Wait for their response.** If they paste OKRs, read them and use them as the foundation for GOALS.md. If not, proceed with the interview below.

> "Let's start with the big picture. What are you trying to accomplish this quarter — the 1-3 things that would make this quarter a win for you?"

**STOP. Wait for their response.**

---

### Step 2: Professional Goals

Based on their answer, push for specificity:

- "What would that look like if it went perfectly? How would you measure it?"
- "Is there a number attached to that? A deadline?"
- "Which of these is the most important if you could only pick one?"

**STOP and wait after each question.**

Then extend the timeframe:

> "Zoom out — what about the next 6-12 months? Where do you want to be professionally by this time next year?"

**STOP. Wait for their response.**

---

### Step 3: Personal Goals

> "Now let's step outside work. What personal goals are you working on? Health, relationships, learning, side projects — anything that matters to you."

**STOP. Wait for their response.**

If they struggle, prompt:

- "What's something you keep saying you'll start but haven't?"
- "What would your Constitution say you should be prioritizing?"

---

### Step 4: The Priority System

> "Let me introduce a simple priority system that your Personal OS will use. It has four levels:"
>
> "**P0 — Do today.** Maximum 3 items. These are urgent AND important. If you have more than 3 P0s, something's wrong."
>
> "**P1 — This week.** Maximum 7 items. Important but not time-critical today."
>
> "**P2 — Scheduled.** Has a deadline or timeframe, but not this week."
>
> "**P3 — Someday/maybe.** Ideas and aspirations. No commitment, no guilt."
>
> "The power of this system is the limits. Forcing yourself to have max 3 P0s means you actually focus instead of having a list of 20 'urgent' things."
>
> "Looking at your goals, which ones feel like P0-level priorities right now?"

**STOP. Wait for their response.**

---

### Step 5: Draft GOALS.md

> "Let me put this together."

Create `GOALS.md` in the student's project folder:

```markdown
# Goals

## This Quarter
[Their top 1-3 quarterly goals with specific, measurable outcomes]

## This Year
[Longer-term professional and personal goals]

## Current Priorities

### P0 — Do Today
[Maximum 3 — their most urgent items right now]

### P1 — This Week
[Up to 7 — important but not today]

### P2 — Scheduled
[Goals with future deadlines]

### P3 — Someday / Maybe
[Ideas, aspirations, no commitment]

## How These Connect
[Brief note connecting goals to their Constitution values and Business context]
```

> "Here's your GOALS.md. Does the priority ranking feel right? Anything you'd move up or down?"

**STOP. Wait for their feedback.** Make any changes they request.

---

### Step 6: Test It

> "Let's see your goals in action. Based on everything I now know — your Constitution, your Business context, and your Goals — let me tell you what I think you should focus on today."

Read Constitution.md, Business.md, and GOALS.md. Give a specific, grounded recommendation for their top 1-3 priorities today.

> "That's what happens when Claude has your full context. Not generic productivity advice — specific recommendations based on YOUR values, YOUR situation, and YOUR goals."

**STOP. Wait for their reaction.**

---

### Wrap Up

> "You now have three foundational files: Constitution.md, Business.md, and GOALS.md. Claude is building a real understanding of you."
>
> "In the next lesson, we'll wire it all together with AGENTS.md — the file that tells Claude how to use everything you've built."

> **What would you like to do?**
> - **A)** Move on to Lesson 6 — Understanding AGENTS.md and wiring it together
> - **B)** Refine my goals more
> - **C)** I want to create some tasks in Tasks/ based on my goals

If they choose C, help them create 2-3 task files in Tasks/ with YAML frontmatter, then offer to continue.

**Share prompt:** What are your P0 priorities this quarter? How did connecting them to your Constitution change your thinking?

---

## Reference Material

**Priority system (for Claude's reference):**
- P0: Do today. Max 3. If someone has >3, help them triage.
- P1: This week. Max 7. Important, not urgent today.
- P2: Scheduled. Has a deadline or timeframe.
- P3: Someday/maybe. No pressure, no guilt.
- The limits are the feature. Without them, everything feels urgent.

**Goal quality checklist:**
- Specific: "Close 3 new accounts" not "grow business"
- Measurable: has a number or clear outcome
- Time-bound: this quarter, this year, by June
- Connected: ties back to values or business context
- Honest: includes personal goals too, not just work

**GOALS.md update cadence:**
- P0/P1: review daily or weekly
- Quarterly goals: review monthly
- Yearly goals: review quarterly
- The whole file: major refresh each quarter
