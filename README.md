# Timechamber

Timechamber is a small framework for learning with an agent.

It gives the agent a way to keep track of:

- what you want to learn;
- what lesson you are on;
- what exercises you have done;
- what you got stuck on;
- when something should be reviewed again.

The root of this repo is only the framework. Real learning happens in folders
named `chamber-*`.

Example:

```text
chamber-c-inference-engine/
chamber-linear-algebra/
chamber-writing-essays/
```

Those folders are ignored by git, so this repo can stay as the clean reusable
framework.

## How It Starts

When you start a new chamber, the agent should first ask what you want to
learn. It should not invent a curriculum immediately.

A good first prompt is:

```text
What do you want to learn in this Timechamber?
```

You can answer freely. If the topic is broad, the agent asks a few follow-up
questions and then creates a folder like:

```text
chamber-<topic-name>/
```

Inside that folder, the agent keeps:

- `CHAMBER.md`: what you are learning and how;
- `LEARNING.md`: the plan;
- `LESSONS.md`: lesson status;
- `REVIEWS.md`: spaced repetition;
- `CHECKPOINT_NOTES.md`: what happened during exercises.

## Root Files

- `AGENTS.md`: rules the agent should follow.
- `BOOTSTRAP.md`: questions for starting a new chamber.
- `STRUCTURE.md`: how folders are organized.
- `templates/`: files copied into new chambers.

## Basic Loop

The intended loop is:

1. Learn one small thing.
2. Hear it explained with a clear metaphor or example.
3. Add the right rigor for the subject.
4. Ask questions or request a deeper dive.
5. Do a checkpoint exercise.
6. Run a test if the topic supports it.
7. Write down mistakes and weak spots.
8. Review later.

Keep it simple. The point is not to make a school system. The point is to stop
losing context between sessions.
