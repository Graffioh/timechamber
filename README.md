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

## How To Use

1. Open this repo with your coding agent.
2. Start from the Timechamber root.
3. Ask to start a new chamber, or say what you want to learn.
4. Answer the short onboarding questions.
5. Let the agent create a `chamber-*` folder from the templates.
6. Continue future sessions from inside that chamber folder.

Example:

```text
I want to start a Timechamber for learning linear algebra.
```

Once a chamber exists, you can ask for the next lesson, a checkpoint exercise,
a review, a deeper explanation, or an optional side branch.

## Learning Loop

The normal loop is:

1. Learn one small concept at a time.
2. Start with the idea itself, then the procedure that uses it.
3. Understand why the concept matters before jumping into mechanics.
4. Ground it with a tiny example, metaphor, formula, or code snippet.
5. Pause for questions, corrections, or a deeper branch.
6. Practice with a checkpoint when the concept is worth standalone work.
7. Record useful mistakes, weak spots, and follow-up topics.
8. Review important ideas later with short recall checks.

Small mechanical concepts can be folded into a later combined checkpoint
instead of becoming busywork.

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

## Starting A Chamber

A chamber starts with a topic and a short learning contract: what you want to
learn, where you are starting from, how you like to practice, and what a useful
checkpoint should look like.

The agent uses that conversation to create a `chamber-*` folder from the
templates. After that, the chamber becomes the home for the curriculum, lesson
status, exercises, notes, references, and reviews for that topic.

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
