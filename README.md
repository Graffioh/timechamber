# Timechamber

Timechamber is a small framework for learning with an agent without losing
context between sessions.

The root of this repo is the reusable framework. Actual learning happens in
folders named `chamber-*`.

Example:

```text
chamber-c-inference-engine/
chamber-linear-algebra/
chamber-writing-essays/
```

Each chamber keeps its own curriculum, lessons, exercises, notes, references,
and review cards. Chamber folders are ignored by git so the framework can stay
clean and reusable.

## What It Tracks

Timechamber gives the agent a simple place to remember:

- what you want to learn;
- the current lesson and checkpoint;
- optional side topics that came up;
- exercises you are working on;
- mistakes, weak spots, and teaching notes;
- useful references for the subject;
- what should be reviewed later.

It is not meant to become a heavy school system. The point is a calm learning
loop with enough memory to keep moving.

## How It Starts

From the repo root, the agent should first ask:

```text
What do you want to learn in this Timechamber?
```

After a short onboarding conversation, it creates a directory like:

```text
chamber-<topic-name>/
```

Then it copies and adapts the chamber template files, fills in the learning
contract, and continues inside that chamber.

If you are already inside a `chamber-*` folder, the agent should use that
chamber's files instead of storing progress in the root.

## Root Files

- `README.md`: this overview.
- `AGENTS.md`: the main rules the agent should follow.
- `BOOTSTRAP.md`: onboarding flow for starting or repairing a chamber.
- `STRUCTURE.md`: folder layout and chamber conventions.
- `templates/chamber/`: starter files for a new chamber.
- `templates/checkpoint/`: starter files for checkpoint exercises.

Root files are framework instructions only. Topic-specific learning progress
belongs inside a chamber.

## Chamber Files

A chamber usually contains:

- `AGENTS.md`: chamber-specific agent guidance.
- `CHAMBER.md`: the learning contract: subject, goal, style, constraints.
- `LEARNING.md`: the curriculum and interaction rules.
- `LESSONS.md`: lesson status and current focus.
- `SUB_LESSONS.md`: optional branches that came up during lessons.
- `REVIEWS.md`: spaced repetition cards and recall history.
- `REFERENCES.md`: source map for books, docs, papers, courses, and links.
- `LEARNING_NOTES.md`: chamber-level teaching observations and preferences.
- `CHECKPOINT_NOTES.md`: detailed notes only during active checkpoint work.
- `checkpoint_*`: exercise folders for meaningful milestones.

Checkpoint folders are snapshots. They should contain the prompt, constraints,
compile/run instructions, tests when useful, and any verified building blocks
from earlier checkpoints.

## Learning Loop

The normal loop is:

1. Learn one small concept.
2. Define the core object before teaching the operation around it.
3. Explain why the concept exists and what problem it solves.
4. Use a tiny example, metaphor, formula, or code snippet as needed.
5. Name optional side topics and record them in `SUB_LESSONS.md`.
6. Ask questions or take a deeper branch.
7. Start a checkpoint only when it is worth standalone practice.
8. Record checkpoint issues in `CHECKPOINT_NOTES.md`.
9. Add or update review cards in `REVIEWS.md`.

Small mechanical concepts can be folded into a later combined checkpoint
instead of becoming busywork.

## Reviews

Reviews are opt-in during normal conversation. The agent should check
`REVIEWS.md` when you ask for a review, quiz, recall check, or spaced
repetition.

The review flow is intentionally small:

1. Ask one due recall question.
2. Let you answer.
3. Ask for a recall rating: `1` repeat, `2` targeted quiz, or `3` remembered.
4. Update `REVIEWS.md`.
5. Return to the learning task.

## References

Each chamber has a `REFERENCES.md` file for sources that actually shape the
lessons: official docs, canonical books, papers, respected courses, maintained
implementations, and strong technical writeups.

The agent should prefer high-quality sources, avoid thin SEO-style links, and
update the file as better references appear.

## Bookkeeping

When lesson status, reviews, sublessons, learning notes, or checkpoint notes
need updates, the agent should usually delegate that small bookkeeping task to
a background subagent if the environment supports it. If not, it can make the
smallest direct edit.

This keeps the main conversation focused on learning while the chamber files
stay current.
