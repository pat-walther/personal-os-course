# 8. Skills — Automate the Upkeep

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

> "You've built an incredible Personal OS over these lessons. Constitution, Business context, Goals, AGENTS.md, Tasks, Knowledge — it all works together. But here's the thing people usually worry about:"
>
> "How do I keep it updated?"
>
> "After every meeting, every decision, every shift in priorities — do I have to manually update all these files? That sounds like a lot of work."
>
> "The good news: it used to be hard. It's not anymore. There's a way to automate the upkeep, and that's what this lesson is about."

**STOP. Wait for their response.**

---

### Step 2: What Is a Skill?

> "A skill is just a text file with instructions that Claude follows when you say a trigger phrase. That's it."
>
> "Think of it as a recipe. When you say 'debrief my meeting,' Claude reads the recipe and follows the steps: pull the transcript, cross-reference against your goals, suggest task updates, flag decisions."
>
> "You've already been using something like this without knowing it — your AGENTS.md is a skill for how Claude should behave. A skill just takes that idea further for a specific workflow."
>
> "Skills live in a folder called `skills/` in your Personal OS. Each skill is a `.md` file — the same Markdown you already know."

**STOP. Wait for their response.**

---

### Step 3: The Meeting Debrief Skill

> "Let me show you a real skill. I'm going to open the meeting debrief skill that came with your Personal OS."

Read the file at `skills/meeting-debrief/SKILL.md` and walk the student through it section by section:

> "Take a look at this file. Let me walk you through what's in it:"
>
> "**The header** — a name, description, and trigger phrases. This tells Claude when to activate the skill."
>
> "**The workflow** — step-by-step instructions for what Claude should do. Phase 1: get the meeting transcript. Phase 2: load your Personal OS context. Phase 3: cross-reference. Phase 4: present suggestions. Phase 5: apply what you approve."
>
> "**The rules** — guardrails. Never make changes without approval. Quote the transcript. Link every task to a goal."
>
> "This is the whole thing. No code. Just structured instructions in a Markdown file. And here's the important part — if you want it to work differently, you just edit the file. Want it to always create a Knowledge/ summary? Add that step. Want it to skip goal alignment? Remove that rule."

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

> "Let's take it for a spin. Say: 'Debrief my latest meeting.'"

**STOP. Wait for them to say it.**

When they do, run the meeting debrief skill:

1. If Fireflies is connected: list their recent meetings and ask which one to process
2. If not connected: ask them to paste meeting notes or a transcript

If they don't have any meeting notes available, use the sample transcript from the Reference Material below.

After processing:

> "Here's what the skill found. Look at the suggestions — new tasks, knowledge updates, and goal alignment checks, all pulled from one meeting transcript."
>
> "Which of these do you want me to apply?"

**STOP. Wait for their response.** Apply only the changes they approve, following the skill's rules (describe each change before making it).

---

### Step 6: Read the Skill File Yourself

> "Now I want you to actually open the skill file and read through it. It's at `skills/meeting-debrief/SKILL.md` in your Personal OS."
>
> "As you read it, think about: is there anything you'd change? Maybe you want it to always save a meeting summary. Maybe you want it to focus more on action items and less on knowledge updates. Maybe you want it to check your Constitution when evaluating decisions."
>
> "The whole point of skills is that they're yours to customize. It's just a text file. Edit it however you want."

**STOP. Wait for their response.** If they want to make changes, help them edit the skill file.

---

### Step 7: Build Your Own Skill

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

> "Great. Now here's the cool part — there's a skill that builds skills for you. Your Personal OS comes with a **Skill Creator** in the `skills/skill-creator/` folder."
>
> "All you have to do is say: **'/Skill Creator'** and then describe what you want to build. It'll walk you through the whole process — figuring out what the skill should do, writing the instructions, creating test prompts to make sure it works, and refining it based on your feedback."
>
> "Let's try it. Say '/Skill Creator' and tell it what workflow you want to automate."

**STOP. Wait for them to use the Skill Creator.** Let the Skill Creator skill take over the conversation. It will guide them through drafting, testing, and refining their skill. When they've finished creating their skill, continue to the next step.

---

### Step 8: Improve What You Built

> "You just built your own skill. But here's the thing — most skills work about 70% of the time on the first draft. The other 30% you get inconsistent or mediocre output. That's normal."
>
> "Your Personal OS comes with a **Skill Improver** in `skills/skill-improver/`. It takes any skill you've built, runs it dozens of times automatically, scores every output against pass/fail checks you define, and then tightens the prompt until that 30% disappears."

**STOP. Wait for their response, then explain evaluations.**

> "The key is defining what 'good' looks like. You do this with simple yes/no checks — called evaluations. For example, if you built a follow-up email skill, your evals might be:"
>
> "- Does the email reference something specific from the meeting?"
> "- Is it under 200 words?"
> "- Does it include a clear next step or ask?"
> "- Does it sound like a human wrote it, not a template?"
>
> "Each check is pass/fail — no scales, no 'rate it 1-10.' That's what makes it reliable. The Skill Improver runs your skill multiple times, scores every output against your checks, then makes one targeted change to the skill, tests again, and keeps the change only if the score improves."
>
> "Over a few rounds, your skill goes from 'works most of the time' to 'works almost every time.'"
>
> "Say **'/Skill Improver'** and point it at the skill you just built. It'll ask you for your eval checks, then start the optimization loop."

**STOP. Wait for them to try it.** Let the Skill Improver skill take over. When they're done (or want to move on), continue to the wrap-up.

---

### Step 9: Course Wrap-Up

> "Let's step back and look at what you've built across all 9 lessons."
>
> "**Lesson 0:** Why Claude Co-work and context matter"
> "**Lesson 1:** Why Markdown is the language of AI, and your folder structure"
> "**Lesson 2:** Your Personal Constitution — values, beliefs, and principles"
> "**Lesson 3:** Your Business context — role, customers, competitive landscape"
> "**Lesson 4:** Your Goals — priorities organized by timeframe and OKRs"
> "**Lesson 5:** AGENTS.md — the instruction layer that wires it all together"
> "**Lesson 6:** Your daily workflow — backlog, tasks, priorities"
> "**Lesson 7:** Memory, context, and keeping your system alive"
> "**Lesson 8:** Skills — automate workflows, build your own, and stress-test them"
>
> "You started with an empty folder. Now you have a Personal OS that makes Claude deeply understand you, a system that keeps itself updated through skills, and the ability to build and optimize new skills whenever you find a workflow worth automating."
>
> "The real value starts now. Use it every day. Say 'debrief my meeting' after every call. Say 'what should I work on?' every morning. Brain dump into your backlog and let Claude organize it. When you find yourself repeating a workflow, build a skill for it."
>
> "What questions do you have? And what's the first skill you're going to run?"

**STOP. Wait for their response.**

---

### Step 10: Share and Give Feedback

> "One last thing before we wrap."
>
> "If you learned something useful or enjoyed the course, share it in the **AI Hub** channel. What you built, what surprised you, a skill you created — anything. It helps other people on the team see what's possible, and it builds momentum."
>
> "I'd also love your honest feedback on the course itself:"
>
> "- Did the 'why' behind each lesson come through clearly? Did you understand why we were building each piece, or did any part feel like busy work?"
> "- Was the depth right — too shallow, too deep, or just right?"
> "- What would you add, change, or remove?"
> "- Any suggestions for making this better for the next group?"
>
> "Please send your feedback directly to **Patrick** — he built this course and genuinely wants to make it better."

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
- `skills/meeting-debrief/` — processes meeting transcripts, suggests task/goal/knowledge updates
- `skills/skill-creator/` — builds new skills through a guided workflow with testing and refinement
- `skills/skill-improver/` — autonomously optimizes any skill by running it repeatedly, scoring outputs against binary pass/fail evals, and mutating the prompt to fix failures

**How skills work:**
- Skills are stored in the `skills/` folder of the Personal OS
- Each skill is a Markdown file (SKILL.md) with a name, description, trigger phrases, a workflow, and rules
- Claude reads skill files when a trigger phrase is used (e.g., "debrief my meeting" or "/Skill Creator")
- The student can also manually say "use the [skill name] skill"
- Skills follow the same AGENTS.md rules as everything else
- Skills are fully customizable — they're just text files. Edit them to change the workflow
