---
name: agv-skill-improver
description: "Optimize any skill by running it repeatedly, scoring outputs against binary evals, mutating the prompt, and keeping improvements. Based on Karpathy's autoresearch methodology. Adapted for Claude Co-work (no terminal, no subagents). Use when: optimize this skill, improve this skill, run autoresearch on, make this skill better, self-improve skill, benchmark skill, eval my skill, run evals on. Outputs: an improved SKILL.md, a results log, and a changelog of every mutation tried."
---

# Autoresearch for Skills

Most skills work about 70% of the time. The other 30% you get garbage. The fix isn't to rewrite the skill from scratch. It's to let Claude run it multiple times, score every output, and tighten the prompt until that 30% disappears.

This skill adapts Andrej Karpathy's autoresearch methodology (autonomous experimentation loops) to skill optimization. Instead of optimizing ML training code, we optimize skill prompts.

**This version is built for Claude Co-work** — no terminal, no subagents, no Python scripts. Everything happens in the conversation and in your project files.

---

## the core job

Take any existing skill, define what "good output" looks like as binary yes/no checks, then run a loop that:

1. Generates outputs from the skill using test inputs
2. Scores every output against the eval criteria
3. Mutates the skill prompt to fix failures
4. Keeps mutations that improve the score, discards the rest
5. Repeats until the score ceiling is hit or the user stops it

**Output:** An improved SKILL.md + `changelog.md` of every mutation attempted + a live HTML dashboard you can watch in your browser.

---

## before starting: gather context

**STOP. Do not run any experiments until all fields below are confirmed with the user. Ask for any missing fields before proceeding.**

1. **Target skill** — Which skill do you want to optimize? (need the file path or the user can open it)
2. **Test inputs** — What 3-5 different prompts/scenarios should we test the skill with? (variety matters — pick inputs that cover different use cases so we don't overfit to one scenario)
3. **Eval criteria** — What 3-6 binary yes/no checks define a good output? (these are your "test questions" — see the Eval Guide section below for how to write good evals)
4. **Runs per experiment** — How many times should we run the skill per mutation? Default: 3. (more runs = more reliable scores, but slower. 3 is the sweet spot for Co-work since we run sequentially.)
5. **Budget cap** — Optional. Max number of experiment cycles before stopping. Default: 5 cycles. (Co-work runs are interactive, so smaller budgets keep things manageable.)

---

## step 1: read the skill

Before changing anything, read and understand the target skill completely.

1. Read the full SKILL.md file
2. Read any referenced files the skill links to
3. Identify the skill's core job, process steps, and output format
4. Note any existing quality checks or anti-patterns already in the skill

Do NOT skip this. You need to understand what the skill does before you can improve it.

---

## step 2: build the eval suite

Convert the user's eval criteria into a structured test. Every check must be binary — pass or fail, no scales.

**Format each eval as:**

```
EVAL [number]: [Short name]
Question: [Yes/no question about the output]
Pass condition: [What "yes" looks like — be specific]
Fail condition: [What triggers a "no"]
```

**Rules for good evals:**
- Binary only. Yes or no. No "rate 1-7" scales. Scales compound variability and give unreliable results.
- Specific enough to be consistent. "Is the text readable?" is too vague. "Are all words spelled correctly with no truncated sentences?" is testable.
- Not so narrow that the skill games the eval. "Contains fewer than 200 words" will make the skill optimize for brevity at the expense of everything else.
- 3-6 evals is the sweet spot. More than that and the skill starts parroting eval criteria back instead of actually improving.

**Max score calculation:**
```
max_score = [number of evals] × [runs per experiment]
```

Example: 4 evals × 3 runs = max score of 12.

---

## step 3: set up tracking

Create a working directory in the user's project: `autoresearch-[skill-name]/`

Create these files:

**`autoresearch-[skill-name]/SKILL.md.baseline`** — exact copy of the original skill. This is your revert target. NEVER edit this file.

**`autoresearch-[skill-name]/[user-chosen-name].md`** — the working copy you will mutate. Ask the user what to name it (e.g., "daily-debrief-v2", "vault-lint-optimized").

**`autoresearch-[skill-name]/results.json`** — score tracking data that powers the dashboard:

```json
{
  "skill_name": "[name]",
  "status": "running",
  "current_experiment": 0,
  "baseline_score": 0,
  "best_score": 0,
  "experiments": [],
  "eval_breakdown": []
}
```

**`autoresearch-[skill-name]/changelog.md`** — mutation log (starts empty, you'll append after each experiment).

**`autoresearch-[skill-name]/dashboard.html`** — a live HTML dashboard the user can open in their browser. Generate it as a single self-contained HTML file with inline CSS and JavaScript. Use Chart.js loaded from CDN for the line chart. The JS should fetch `results.json` and re-render on a 10-second auto-refresh interval.

The dashboard must show:
- A score progression line chart (experiment number on X axis, pass rate % on Y axis)
- A colored bar for each experiment: green = keep, red = discard, blue = baseline
- A table of all experiments with: experiment #, score, pass rate, status, description
- Per-eval breakdown: which evals pass most/least across all runs
- Current status: "Running experiment [N]..." or "Complete"
- Clean styling with soft colors (white background, pastel accents, clean sans-serif font)

After creating the dashboard, tell the user where it is so they can open it in their browser. Update `results.json` after every experiment so the dashboard stays current. When the run finishes, update `status` to `"complete"`.

---

## step 4: establish baseline

Run the skill AS-IS before changing anything. This is experiment #0.

1. For each test input, read the working copy skill and follow its instructions to complete the task
2. After each run, score the output against every eval — pass or fail
3. Record the results in `results.json` and update the dashboard
4. Present the baseline score to the user

**How to "run" the skill in Co-work:**
Since Co-work doesn't have subagents, you run the skill yourself. For each test input:
- Read the skill's instructions
- Execute the task as if you were a fresh Claude following those instructions
- Produce the output
- Then switch hats: score that output against the evals as objectively as you can

This is less rigorous than independent subagents (you wrote the skill and you're also running it), but the human review step compensates. Be honest in your scoring — the point is to find failures, not to prove the skill works.

**IMPORTANT:** After establishing baseline, confirm the score with the user before proceeding. If baseline is already 90%+, the skill may not need optimization — ask the user if they want to continue.

---

## step 5: run the experiment loop

This is the core autoresearch loop.

**LOOP:**

1. **Analyze failures.** Look at which evals are failing most. Read the actual outputs that failed. Identify the pattern — is it a formatting issue? A missing instruction? An ambiguous directive?

2. **Form a hypothesis.** Pick ONE thing to change. Don't change 5 things at once — you won't know what helped.

   Good mutations:
   - Add a specific instruction that addresses the most common failure
   - Reword an ambiguous instruction to be more explicit
   - Add an anti-pattern ("Do NOT do X") for a recurring mistake
   - Move a buried instruction higher in the skill (priority = position)
   - Add or improve an example that shows the correct behavior
   - Remove an instruction that's causing the skill to over-optimize for one thing at the expense of others

   Bad mutations:
   - Rewriting the entire skill from scratch
   - Adding 10 new rules at once
   - Making the skill longer without a specific reason
   - Adding vague instructions like "make it better" or "be more creative"

3. **Make the change.** Edit `[user-chosen-name].md` with ONE targeted mutation. NEVER touch the original SKILL.md or the baseline.

4. **Run the experiment.** Execute the skill [N] times with the same test inputs. Score each output.

5. **Decide: keep or discard.**
   - Score improved → **KEEP.** Log it. This is the new version of `[user-chosen-name].md`.
   - Score stayed the same → **DISCARD.** Revert `[user-chosen-name].md` to previous version. The change added complexity without improvement.
   - Score got worse → **DISCARD.** Revert `[user-chosen-name].md` to previous version.

6. **Log the result** — update `results.json` (so the dashboard refreshes) and append to `changelog.md`.

7. **Show the user** a brief update: what you changed, whether it helped, current score.

8. **Repeat.** Go back to step 1 of the loop.

**Stop when:**
- The user says to stop
- You hit the budget cap
- You hit 95%+ pass rate for 2 consecutive experiments (diminishing returns)
- You've tried 3 mutations in a row with no improvement (you're stuck — present what you have)

**If you run out of ideas:** Re-read the failing outputs. Try combining two previous near-miss mutations. Try a completely different approach to the same problem. Try removing things instead of adding them. Simplification that maintains the score is a win.

---

## step 6: write the changelog

After each experiment (whether kept or discarded), append to `changelog.md`:

```markdown
## Experiment [N] — [keep/discard]

**Score:** [X]/[max] ([percent]%)
**Change:** [One sentence describing what was changed]
**Reasoning:** [Why this change was expected to help]
**Result:** [What actually happened — which evals improved/declined]
**Failing outputs:** [Brief description of what still fails, if anything]
```

This changelog is the most valuable artifact. It's a research log that any future session can pick up and continue from.

---

## step 7: deliver results

When the loop stops, present:

1. **Score summary:** Baseline score → Final score (percent improvement)
2. **Total experiments run:** How many mutations were tried
3. **Keep rate:** How many mutations were kept vs discarded
4. **Top 3 changes that helped most** (from the changelog)
5. **Remaining failure patterns** (what the skill still gets wrong, if anything)
6. **The improved `[user-chosen-name].md`** (in the working directory — the original SKILL.md is untouched)
7. **Location of `dashboard.html`, `results.json`, and `changelog.md`** for reference

---

## output format

The skill produces five files in `autoresearch-[skill-name]/`:

```
autoresearch-[skill-name]/
├── dashboard.html         # live browser dashboard (auto-refreshes from results.json)
├── results.json           # score data powering the dashboard
├── changelog.md           # detailed mutation log
├── [user-chosen-name].md  # the improved skill
└── SKILL.md.baseline      # original skill before optimization
```

**The original SKILL.md is NEVER modified.** The improved version lives in `[user-chosen-name].md`. The user can review and manually apply changes if they choose. Do NOT offer to overwrite the original.

---

## example: optimizing a diagram-generator skill

**Context gathered:**
- Target skill: `skills/diagram-generator/SKILL.md`
- Test inputs: "OAuth flow diagram", "CI/CD pipeline", "microservices architecture"
- Evals: (1) All text legible and spelled correctly? (2) Uses only pastel/soft colors? (3) Linear layout — left-to-right or top-to-bottom? (4) Free of numbers, ordinals, and ordering?
- Runs per experiment: 3
- Max score: 12

**Baseline run (experiment 0):**
Generated 3 outputs. Scored each against 4 evals. Result: 8/12 (67%).
Common failures: 2 outputs had numbered steps, 1 had bright red elements.

**Experiment 1 — KEEP (10/12, 83%):**
Change: Added "NEVER include step numbers, ordinal numbers (1st, 2nd), or any numerical ordering in diagrams" to the anti-patterns section.
Result: Numbering failures dropped from 2 to 0. Other evals held steady.

**Experiment 2 — DISCARD (9/12, 75%):**
Change: Added "All text must be minimum 14px font size."
Result: Legibility improved by 1, but color compliance dropped by 2. Reverted.

**Experiment 3 — KEEP (11/12, 92%):**
Change: Replaced vague "pastel colors" instruction with specific hex codes: `#A8D8EA, #AA96DA, #FCBAD3, #FFFFD2, #B5EAD7`.
Result: Color eval went from 2/3 to 3/3. Other evals held.

**Final delivery:**
- Baseline: 8/12 (67%) → Final: 11/12 (92%)
- 3 experiments, 2 kept, 1 discarded
- Top changes: specific hex codes for colors, explicit anti-numbering rule

---

## the test

A good autoresearch run:

1. **Started with a baseline** — never changed anything before measuring the starting point
2. **Used binary evals only** — no scales, no vibes, no "rate this 1-10"
3. **Changed one thing at a time** — so you know exactly what helped
4. **Kept a complete log** — every experiment recorded, kept or discarded
5. **Improved the score** — measurable improvement from baseline to final
6. **Didn't overfit** — the skill got better at the actual job, not just at passing the specific test inputs

If the skill "passes" all evals but the actual output quality hasn't improved — the evals are bad, not the skill. Go back to step 2 and write better evals.

---

## Eval Guide

How to write eval criteria that actually improve your skills instead of giving you false confidence.

### the golden rule

Every eval must be a yes/no question. Not a scale. Not a vibe check. Binary.

Why: Scales compound variability. If you have 4 evals scored 1-7, your total score has massive variance across runs. Binary evals give you a reliable signal.

### good evals vs bad evals

**Text/copy skills (newsletters, emails, posts):**

Bad evals:
- "Is the writing good?" (too vague)
- "Rate the engagement potential 1-10" (scale = unreliable)

Good evals:
- "Does the output contain zero phrases from this banned list: [game-changer, here's the kicker, level up]?" (binary, specific)
- "Does the opening sentence reference a specific time, place, or sensory detail?" (binary, checkable)
- "Is the output between 150-400 words?" (binary, measurable)

**Document skills (proposals, reports, decks):**

Bad evals:
- "Is it comprehensive?" (compared to what?)

Good evals:
- "Does the document contain all required sections: [list them]?" (binary, structural)
- "Is every claim backed by a specific number, date, or source?" (binary, checkable)
- "Does the executive summary fit in 3 sentences or fewer?" (binary, countable)

### the 3-question test

Before finalizing an eval, ask:

1. **Could two different people score the same output and agree?** If not, the eval is too subjective.
2. **Could a skill game this eval without actually improving?** If yes, the eval is too narrow.
3. **Does this eval test something the user actually cares about?** If not, drop it.

### template

```
EVAL [N]: [Short name]
Question: [Yes/no question]
Pass: [What "yes" looks like — one sentence, specific]
Fail: [What triggers "no" — one sentence, specific]
```
