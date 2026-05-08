# Bootstrap Flow

Use this file when the user starts a new Timechamber topic or when the active
`chamber-*` directory does not yet define a completed learning contract.

The goal is to ask enough to tailor the chamber without turning onboarding into
a long form.

## Opening Prompt

Ask:

> What do you want to learn in this Timechamber?
>
> You can answer freely, or include details like your goal, current level,
> preferred project type, and how intense you want the practice to be.

If the answer is broad, ask 2-4 follow-up questions from the sections below.
Do not ask every question.

## Root Flow

When the user is in the Timechamber root and wants to start a topic:

1. Ask the opening prompt.
2. Choose a chamber directory name from the topic.
3. Create `chamber-<learning-name>/`.
4. Copy/adapt `templates/chamber/` into that directory.
5. Continue onboarding inside the new chamber.
6. Fill `CHAMBER.md`, `LEARNING.md`, and `LESSONS.md`.

Do not keep topic-specific progress files in the root.

Use a background bookkeeping subagent by default for updates to chamber
progress files such as `LESSONS.md`, `REVIEWS.md`, and
`CHECKPOINT_NOTES.md`. Confirm required updates before continuing past a
review, lesson status change, or checkpoint note. If subagents are unavailable,
make the smallest necessary direct edit and note that fallback.
When the Codex runtime supports model or reasoning overrides, spawn this
bookkeeping subagent with the fastest suitable model or low reasoning mode.

## Universal Questions

Use these for any subject:

- What is the concrete thing you want to be able to do?
- What is your current level?
- Do you want theory-first, practice-first, or a mix?
- How much time do you want each session to take?
- Do you want checkpoint exercises, quizzes, projects, or all three?
- Do you prefer strict correction or gentle hints first?
- Is there anything you do not want to spend time on?

## Programming Questions

Use these when the subject is programming:

- Which language or stack do you want to use?
- What kind of project do you want to build?
- Do you want to write everything from scratch or use libraries where normal?
- Should checkpoints be small command-line programs, tests, web apps, games, or
  something else?
- What tooling should be assumed?
- Do you want the agent to write boilerplate and tests while you implement the
  core logic?

## Math / Theory Questions

Use these when the subject is conceptual or mathematical:

- Do you want proofs, intuition, worked examples, or applications?
- Should exercises be calculation-heavy, explanation-heavy, or mixed?
- Do you want the agent to grade answers strictly?
- Should formulas be introduced slowly or all at once?

## Creative Skill Questions

Use these for writing, design, music, art, or similar:

- What style or reference point are you aiming for?
- Do you want critique, imitation exercises, or original projects?
- Should the agent prioritize taste, technique, speed, or consistency?
- What kind of artifact should each checkpoint produce?

## After Onboarding

If a chamber directory does not already exist, create one:

```text
chamber-<learning-name>
```

Then create or update `CHAMBER.md` inside that directory with:

- subject;
- target outcome;
- current level;
- preferred learning style;
- checkpoint style;
- review style;
- constraints;
- first lesson;
- first checkpoint.

Then initialize or update:

- `LEARNING.md`;
- `LESSONS.md`;
- `REVIEWS.md`;
- `CHECKPOINT_NOTES.md`.

These files belong inside the `chamber-*` directory, not in the root.

Use the background bookkeeping subagent for ongoing updates to the progress
files after onboarding, with direct edits only as a fallback. Prefer the
fastest suitable model or low reasoning mode for that subagent.
