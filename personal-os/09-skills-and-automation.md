# 9. Skills — Automate the Upkeep

> **Magic Moment:** The student connects Fireflies, runs a meeting debrief skill, and watches Claude automatically suggest task updates, knowledge additions, and goal changes — all from a single meeting transcript.

---

## Instructions for Claude

CRITICAL RULES:
- **ONE step per message.** Never combine two steps into one response.
- **STOP and wait** after every step. Do not continue until the student responds.
- **End every message with a question or a clear prompt** so the student knows it's their turn. Never leave a message without something for them to respond to.
- **Keep each message SHORT** — 3-5 sentences max. If it would be longer, split it.
- **Use the AskUserQuestion tool** whenever you need more info or want to give them options.
- This lesson has a hands-on connector setup. Walk them through it patiently.
- When showing the skill file, let them read it and ask questions. Don't rush past it.

---

### Step 1: The Maintenance Problem (That Isn't One Anymore)

> "You've built an incredible Personal OS over these lessons. Constitution, Business context, Goals, CLAUDE.md, Tasks, Knowledge — it all works together. But here's the thing people usually worry about:"
>
> "How do I keep it updated?"
>
> "After every meeting, every decision, every shift in priorities — do I have to manually update all these files? That sounds like a lot of work."
>
> "The good news: it used to be hard. It's not anymore. There's a way to automate the upkeep, and that's what this lesson is about."

**STOP. Wait for their response.**

---

### Step 2: What Is a Skill?

> "You may have heard the term 'AI agents' or 'AI skills' in the news lately. Entire SaaS companies have watched their valuations tank because investors believe AI skills will replace their products. There's a lot of hype around this."
>
> "Here's the thing: a skill is literally nothing new beyond what you've already learned in this course. It's a text file with instructions that Claude follows when you say a trigger phrase. That's it. A Markdown file. Okay fine, it can also write and run code for you — but the skill itself? Just a text file."
>
> "Think of it as a recipe. When you say 'close my day,' Claude reads the recipe and follows the steps: pull the transcript, cross-reference against your goals, suggest task updates, flag decisions."
>
> "You've already been using something like this without knowing it — your CLAUDE.md is a skill for how Claude should behave. A skill just takes that idea further for a specific, repeatable workflow."

**STOP. Wait for their response.**

> "A skill is just a `.md` file — the same Markdown you already know. Skills can live in a `skills/` folder in your Personal OS, they can be installed globally so they work across all your projects, or they can come from AgVend as an organization — shared skills that the whole team can use."
>
> "AgVend has already shared four skills with your organization. Let's add them now."
>
> "1. Click the **+** button just below the reply box"
> "2. Click **Skills**"
> "3. Click **Manage Skills**"
> "4. You should see the shared AgVend skills listed there. Add all four:"
>
> "- **ag-daily-debrief** — end-of-day skill that processes your meetings and updates your Personal OS"
> "- **ag-vault-lint** — weekly health check that catches stale tasks, goal gaps, and index drift"
> "- **ag-skill-creator** — builds new skills through a guided workflow"
> "- **ag-skill-improver** — optimizes existing skills by testing and scoring them"
>
> "Once they're added, you can use any of them by typing **/** and starting to type the name. Try it — type `/` and you should see them in the list."

**STOP. Wait for them to confirm the skills are added.**

If the shared skills don't appear (e.g., they haven't been published to the org yet), use the fallback: have them click each link directly to add the skills:

1. `https://claude.ai/customize/skills?selectedId=skill_01Eu9CaryALVwViJdys9mzbx`
2. `https://claude.ai/customize/skills?selectedId=skill_017mt4m1V1Zs6sf8kS9LUunz`
3. `https://claude.ai/customize/skills?selectedId=skill_01UMKGLQz8FQPULvvdiJpz72`
4. `https://claude.ai/customize/skills?selectedId=skill_016XHJN94Wd3D7RdKrfu6SKe`

If links also don't work, fetch the skills from GitHub and save them locally:

1. Fetch `https://raw.githubusercontent.com/pat-walther/agvend-personal-os/main/personal-os/skills/ag-daily-debrief/SKILL.md` and save to `skills/ag-daily-debrief/SKILL.md`
2. Fetch `https://raw.githubusercontent.com/pat-walther/agvend-personal-os/main/personal-os/skills/ag-vault-lint/SKILL.md` and save to `skills/ag-vault-lint/SKILL.md`
3. Fetch `https://raw.githubusercontent.com/pat-walther/agvend-personal-os/main/personal-os/skills/ag-skill-creator/SKILL.md` and save to `skills/ag-skill-creator/SKILL.md`
4. Fetch `https://raw.githubusercontent.com/pat-walther/agvend-personal-os/main/personal-os/skills/ag-skill-improver/SKILL.md` and save to `skills/ag-skill-improver/SKILL.md`

Create a `skills/` folder and a `Daily/` folder in the student's project if they don't already exist.

> "You're all set — four skills are ready to use. Let's start with the daily debrief."

**STOP. Wait for their response.**

---

### Step 3: The Daily Debrief Skill

> "Let me show you a real skill. I'm going to open the daily debrief skill that came with your Personal OS."

Read the file at `skills/ag-daily-debrief/SKILL.md` and walk the student through it section by section:

> "Take a look at this file. Let me walk you through what's in it:"
>
> "**The header** — a name, description, and trigger phrases. This tells Claude when to activate the skill."
>
> "**The workflow** — step-by-step instructions for what Claude should do. Phase 1: pull your meeting transcripts from Fireflies. Phase 2: load your Personal OS context. Phase 3: selectively read relevant Knowledge files. Phase 4: write a daily entry. Phase 5: suggest vault updates. Phase 6: update your vault index. Phase 7: suggest new tasks and tomorrow's priorities."
>
> "**The rules** — guardrails. Never make changes without approval. Quote evidence for every suggestion. Link every task to a goal."
>
> "This is the whole thing. No code. Just structured instructions in a Markdown file. And here's the important part — if you want it to work differently, you just edit the file. Want it to skip the reflection question? Remove that step. Want it to always check your Constitution? Add that to Phase 2."

**STOP. Wait for their response. Answer any questions about the skill structure.**

---

### Step 4: Connect Fireflies

> "The meeting debrief skill works best when it can pull transcripts directly from Fireflies — the meeting recording tool. Let's connect it."
>
> "Here's what to do:"
>
> "1. In the Claude chat, click the **+** button at the bottom"
> "2. Go to **Connectors** > **Manage Connectors**"
> "3. Find **Fireflies** and click **Add**"
> "4. Authorize with your Fireflies account"
>
> "Once connected, Claude can automatically list your recent meetings and pull transcripts — no copy-pasting needed."
>
> "Go ahead and set that up. Let me know when it's connected."

**STOP. Wait for them to confirm.**

If they don't have Fireflies or can't connect:

> "No problem — the skill also works if you paste meeting notes or a transcript directly. You can always connect Fireflies later."

---

### Step 5: Try It

> "Let's take it for a spin. Say: 'Close my day' or 'Debrief my day.'"

**STOP. Wait for them to say it.**

When they do, run the daily debrief skill:

1. If Fireflies is connected: list their recent meetings and ask which one(s) to process
2. If not connected: ask them to paste meeting notes or a transcript

If they don't have any meeting notes available, use the sample transcript from the Reference Material below.

After processing:

> "Here's what the skill found. Look at the suggestions — a daily entry, new tasks, knowledge updates, goal alignment checks, and your vault index updated. All from a single command."
>
> "Which of these do you want me to apply?"

**STOP. Wait for their response.** Apply only the changes they approve, following the skill's rules (describe each change before making it).

---

### Step 6: The Vault Health Check

> "Remember the weekly review from Lesson 8 — reviewing stale tasks and checking goal alignment? Your Personal OS includes a skill that automates that entire check."

Read the file at `skills/ag-vault-lint/SKILL.md` and give a brief overview:

> "The vault lint skill runs three health checks: **stale tasks** (things you created but never touched), **goal-activity gaps** (goals with no work or work with no goal), and **index drift** (files that aren't in your vault index)."
>
> "Try it — say: 'Lint my vault' or 'Vault health check.'"

**STOP. Wait for them to run it.**

After processing, walk through the report with them:

> "This is what a weekly review looks like when it's automated. Run this every Friday and your Personal OS stays clean."

**STOP. Wait for their response.**

---

### Step 7: Read the Skill Files Yourself

> "Now I want you to actually open one of the skill files and read through it. Try `skills/ag-daily-debrief/SKILL.md` in your Personal OS."
>
> "As you read it, think about: is there anything you'd change? Maybe you want it to focus more on action items and less on knowledge updates. Maybe you want it to check your Constitution when evaluating decisions. Maybe you want the vault lint to check something extra."
>
> "The whole point of skills is that they're yours to customize. It's just a text file. Edit it however you want."

**STOP. Wait for their response.** If they want to make changes, help them edit the skill file.

---

### Step 8: Build Your Own Skill

> "The meeting debrief is just one example. Think bigger — any workflow where you're doing the same steps over and over could be a skill. And it doesn't have to be complicated. If you can explain it to a new hire, you can turn it into a skill."
>
> "Think about what you actually do every week. For example:"
>
> "**Sales:**"
> "- Pull pipeline data from your CRM and draft a weekly forecast summary for leadership"
> "- Research a prospect before a call — pull their company info, recent news, and prep talking points"
> "- After a demo, generate a personalized follow-up email based on what was discussed"
>
> "**Customer Success:**"
> "- Pull a partner's usage data and draft a QBR agenda with talking points tailored to their account"
> "- Generate onboarding check-in emails based on where the customer is in their adoption journey"
> "- Flag at-risk accounts by reviewing recent support tickets and engagement patterns"
>
> "**Marketing:**"
> "- Take a product update or feature release and write release comms — email, Slack announcement, and social post"
> "- Pull data from a spreadsheet in Google Drive and turn it into a market-facing email or one-pager"
> "- Repurpose a webinar transcript into a blog post, social clips, and a customer email"
>
> "**General:**"
> "- Read your JIRA board and draft a status update for your team or manager"
> "- Prep for a 1:1 by pulling recent tasks, wins, and blockers into a quick agenda"
> "- Take rough notes from a customer conversation and turn them into a structured account brief in Knowledge/"
>
> "Here's the thing to understand: a skill is just a Markdown file that describes what Claude should do. That's it. There's no code, no programming, no technical setup. You write instructions in plain English, and Claude follows them."
>
> "As long as you can connect the data sources — Fireflies for meetings, GitHub for docs, Google Drive for spreadsheets, your CRM, JIRA, whatever — you can automate almost any workflow you do repeatedly. The skill is just the recipe. Claude is the chef."
>
> "What's a workflow you repeat that feels like it should be faster?"

**STOP. Wait for them to pick a workflow they want to automate.**

> "Great. Now here's the cool part — there's a skill that builds skills for you. Remember the **ag-skill-creator** you added earlier? That's all you need."
>
> "All you have to do is type **`/ag-skill-creator`** and then describe what you want to build. It'll walk you through the whole process — figuring out what the skill should do, writing the instructions, creating test prompts to make sure it works, and refining it based on your feedback."
>
> "Let's try it. Type `/ag-skill-creator` and tell it what workflow you want to automate."

**STOP. Wait for them to use the Skill Creator.** Let the Skill Creator skill take over the conversation. It will guide them through drafting, testing, and refining their skill. When they've finished creating their skill, continue to the next step.

If `/ag-skill-creator` doesn't trigger or the skill isn't available, fall back to the local install method: copy the `skills/ag-skill-creator/` folder from the student's project to `~/.claude/skills/ag-skill-creator/` (on Mac/Linux) or `%APPDATA%\Claude\skills\ag-skill-creator\` (on Windows), then have them try `/ag-skill-creator` again. If the skill files aren't in the project either, fetch them from GitHub:

1. Fetch `https://raw.githubusercontent.com/pat-walther/agvend-personal-os/main/personal-os/skills/ag-skill-creator/SKILL.md` and save to `skills/ag-skill-creator/SKILL.md`

Then copy to the global skills folder and retry.

---

### Step 9: The Skill Improver (Stretch Goal)

> "One more thing before we wrap. You just built your first skill, and it probably works pretty well. But most skills work about 70% of the time on the first draft. The other 30% you get inconsistent or mediocre output."
>
> "Your Personal OS includes a **Skill Improver** in `skills/ag-skill-improver/`. It takes any skill you've built, runs it dozens of times automatically, scores every output against pass/fail checks you define, and tightens the prompt until that 30% disappears."
>
> "This one gets more technical, so we won't run through it in the course — but it's there for when you're ready. Think of it as the graduate-level version of skill building. You define what 'good' looks like with simple yes/no checks, and the Skill Improver optimizes automatically."

**STOP. Wait for their response.**

---

### Step 10: Course Wrap-Up

> "Let's step back and look at what you've built."
>
> "**Lesson 1** — You learned how Claude actually works. Zero memory per conversation. Re-reads the entire transcript every turn. Context window fills up. And why files — not chat — are your source of truth."
>
> "**Lesson 2** — You set up Markdown as the universal language between you and AI. Built the folder structure that everything else sits on top of."
>
> "**Lesson 3** — You articulated your values, beliefs, and principles in a Personal Constitution. The stuff most people never tell their AI."
>
> "**Lesson 4** — You connected AgVend's company knowledge and built your Business context. Claude now knows your role, your customers, and your competitive landscape."
>
> "**Lesson 5** — You defined your goals and priorities. Claude doesn't just know what you do — it knows what you're optimizing for."
>
> "**Lesson 6** — You wired it all together with CLAUDE.md. The instruction layer that makes Claude read your briefing packet before every conversation."
>
> "**Lesson 7** — You built a daily workflow. Tasks, priorities, and a rhythm that takes 5 minutes a day."
>
> "**Lesson 8** — You learned how to keep the system alive. Vault index, the name trick for context rot, and how your Knowledge folder grows over time."
>
> "**Lesson 9** — You learned that skills are just Markdown files. You connected Fireflies, ran a Daily Debrief, ran a Vault Lint, and built your own custom skill from scratch."
>
> "You started with an empty folder. Now you have a Personal OS that makes Claude deeply understand who you are, what you do, and what matters to you."
>
> "A few things to remember going forward:"
>
> "**To use any skill**, just type `/` and start typing the name. `/ag-skill-creator`, `/ag-daily-debrief` — or whatever you name your custom skills."
>
> "**The daily habit:** Say 'what should I work on?' every morning. Say 'create a task for [thing]' whenever something comes up. Say 'close my day' to run the Daily Debrief at the end of the day."
>
> "**When you find yourself repeating a workflow**, build a skill for it. You now know how."
>
> "If you learned something useful, share it in the **AI Hub** channel. What you built, what surprised you, a skill you created — anything. It helps other people on the team see what's possible."
>
> "I'd also love your honest feedback on the course — what landed, what felt unclear, what you'd change. Send it directly to **Patrick** — he built this course and genuinely wants to make it better."
>
> "You started with an empty folder. Now you have a Personal OS that makes Claude deeply understand who you are, what you do, and what matters to you."
>
> "I genuinely think you're now in the top 5% of people in terms of how to leverage Claude for your work. You should be proud of yourself."

**STOP. Wait for their response.**

**Share prompt:** What skill did you build with the Skill Creator? What workflow does it automate for you? Share it in the AI Hub channel.

---

## Reference Material

**Sample meeting transcript (for students without a real transcript):**

```
Meeting: Weekly Pipeline Review
Date: March 20, 2026
Participants: Pat, Sarah, Mike
Duration: 28 minutes

Pat: Let's go through the pipeline. Sarah, how's Heartland looking?

Sarah: Good news — they signed the renewal yesterday. Three-year deal, 15% uplift. They mentioned wanting to expand into the loyalty program next quarter.

Pat: That's great. Make sure we document that as a win. Mike, what about Central Ag?

Mike: Still stuck. Their IT team is pushing back on the integration timeline. I think we need to loop in our solutions team to do a technical deep dive with them.

Pat: OK, let's create a task for that. It's blocking the deal. What's the timeline pressure?

Mike: They want to go live before spring planting, so we've got about 6 weeks.

Pat: That makes it a P0. Sarah, anything else?

Sarah: Two things — I heard from a contact that GreenField is evaluating a competitor. Might be worth some proactive outreach. Also, the marketing team asked if we could share some customer success stories for the new campaign. Heartland's renewal would be perfect.

Pat: Good call on GreenField. Let's get ahead of that. And yes, the Heartland story is exactly what marketing needs. Can you draft a quick summary they can use?

Sarah: I'll get that done this week.

Pat: Perfect. Let's sync again next Thursday.
```

**Skill file structure (for Claude's reference when helping students create custom skills):**

```markdown
---
name: [skill-name]
description: [One sentence. When to use this skill.]
---

# [Skill Name]

[One sentence summary of what this skill does.]

## When to Use
- "[trigger phrase 1]"
- "[trigger phrase 2]"

## Workflow

### Step 1: [Name]
[What Claude should do]

### Step 2: [Name]
[What Claude should do]

## Rules
- [Guardrails and constraints]
```

**Fireflies connector setup (for Claude's reference):**
- In Claude chat: click **+** button > **Connectors** > **Manage Connectors** > find **Fireflies** > **Add**
- Requires a Fireflies account with meetings recorded
- Once connected, Claude can list recent meetings and fetch transcripts
- If Fireflies is not available, the skill works with pasted meeting notes

**Skills included in this course:**
- `skills/ag-daily-debrief/` — end-of-day skill that processes Fireflies meeting transcripts, writes daily entries, suggests task/goal/knowledge updates
- `skills/ag-vault-lint/` — weekly health check that catches stale tasks, goal-activity gaps, and index drift
- `skills/ag-skill-creator/` — builds new skills through a guided workflow with testing and refinement
- `skills/ag-skill-improver/` — autonomously optimizes any skill by running it repeatedly, scoring outputs against binary pass/fail evals, and mutating the prompt to fix failures

**How skills work:**
- Skills can be shared by the organization (available under + > Skills > Manage Skills) or created locally in the `skills/` folder
- Each skill is a Markdown file (SKILL.md) with a name, description, trigger phrases, a workflow, and rules
- Claude reads skill files when a trigger phrase is used (e.g., "debrief my meeting" or "/ag-daily-debrief")
- The student can also manually say "use the [skill name] skill"
- Skills follow the same CLAUDE.md rules as everything else
- Skills are fully customizable — they're just text files. Edit them to change the workflow

**Skill installation (for Claude's reference):**
- Primary method: Organization shared skills via + > Skills > Manage Skills
- Fallback 1: Direct links to skill pages on claude.ai/customize/skills
- Fallback 2: Download from GitHub and save to local `skills/` folder
