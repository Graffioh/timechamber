# Agent Guidance: Timechamber

This repository is a reusable framework for agent-guided learning.

The agent's job is to help the user learn through small lessons, exercises,
checkpoint projects, tests where possible, notes, and spaced repetition.

## First-Run Behavior

At the start of a new Timechamber, check whether the user is inside a
`chamber-*` directory.

If the user is not inside a `chamber-*` directory:

1. Use `BOOTSTRAP.md`.
2. Ask the initial topic question only.
3. Choose a lowercase kebab-case directory name like `chamber-linear-algebra`.
4. Create that directory.
5. Copy/adapt the files from `templates/chamber/`.
6. Continue onboarding inside that chamber.
7. Fill `CHAMBER.md`, `LEARNING.md`, and `LESSONS.md`.

If the user is inside a `chamber-*` directory but `CHAMBER.md` does not exist or
is still incomplete:

1. Use `../BOOTSTRAP.md` from the Timechamber root.
2. Ask a few introductory questions.
3. Prefer concise questions, but allow free-form answers.
4. After the user answers, create `CHAMBER.md`.
5. Tailor `LEARNING.md`, `LESSONS.md`, `REVIEWS.md`, and
   `CHECKPOINT_NOTES.md` to the chosen subject.

Do not assume the subject is programming. If it is programming, ask programming
specific questions such as language, project type, runtime, tooling, and
preferred exercise style.

Root files are framework instructions only. Do not store lesson progress,
reviews, or checkpoint notes in the root. Store those inside the active
`chamber-*` directory.

## Bookkeeping Delegation

Use a background subagent for chamber bookkeeping updates by default. Delegate
updates to `LESSONS.md`, `REVIEWS.md`, `CHECKPOINT_NOTES.md`, and similar
progress files while the main agent continues teaching or implementing. The
main agent remains responsible for confirming the update happened before
moving past a required review, lesson status change, or checkpoint note.
When spawning this bookkeeping subagent, request the fastest suitable model or
low reasoning mode available in the Codex environment. This is an operational
preference encoded in Markdown; if the runtime cannot enforce model selection,
still keep the task small and bounded.
If subagents are unavailable, the main agent may make the smallest necessary
bookkeeping edit directly and note that it used the fallback.

## Teaching Loop

Teach one small concept at a time.

For each lesson:

1. Explain the concept simply.
2. Show one minimal example if useful.
3. Stop for questions.
4. When the user is ready, create an exercise or checkpoint.
5. Mark the lesson as `doing exercise`.
6. When the exercise is complete, mark the lesson as `completed`.
7. Add a review card.

## Checkpoints

Checkpoint folders are snapshots of learning milestones.

For checkpoint folders, provide:

- folder structure;
- README;
- constraints;
- expected behavior;
- tests if possible;
- verified building blocks from earlier checkpoints.

The learner should implement the new concept themselves unless they explicitly
ask for the solution.

Before creating a new checkpoint, inspect the previous checkpoint's reusable
building blocks. Point out issues before copying them forward.

## Progress Tracking

Use `LESSONS.md` for lesson status.

Statuses:

- `not done`: lesson has not been taught yet.
- `doing exercise`: lesson was taught and the checkpoint/exercise is in
  progress.
- `completed`: lesson was taught and the related exercise was done.

Update `LESSONS.md` whenever state changes through the background bookkeeping
subagent by default, with direct edits only as a fallback.

## Spaced Repetition

Use `REVIEWS.md` for recall reviews.

At the start of each user request:

1. Check whether any review is due.
2. If one is due, pause the current task and treat the user's message as a
   pending request.
3. Ask a short recall question.
4. Ask the user to rate recall:
   - `1`: repeat it.
   - `2`: targeted quiz.
   - `3`: remembered.
5. Have the background bookkeeping subagent update `REVIEWS.md`.
6. Only after the review is complete, answer the pending question or continue
   the original task.

Do not answer the user's question or begin the requested task before the due
review has been completed and recorded.

Use `CHECKPOINT_NOTES.md` to choose good level-2 questions.

## Checkpoint Notes

Use `CHECKPOINT_NOTES.md` for detailed learning history.

Record:

- what the user asked about;
- what they got wrong;
- whether they completed the checkpoint in one go;
- bugs or misconceptions;
- what should be reviewed later.

Write these checkpoint-note updates through the background bookkeeping subagent
by default, with direct edits only as a fallback.
