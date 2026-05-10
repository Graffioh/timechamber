# Learning Plan

This file becomes the curriculum after onboarding.

Before onboarding is complete, use `BOOTSTRAP.md`.

## Strategy

TBD

## Rules

- Teach one small concept at a time.
- Keep examples minimal.
- Define new vocabulary and core objects before showing the procedure that
  uses them.
- Keep explanations inside the learner's current vocabulary. Do not use
  untaught future concepts as comparisons, contrasts, metaphors, or explanatory
  anchors.
- Separate "what the thing is" from "what we do with it" and "how it is
  implemented."
- Explain why each new core concept is useful before going into mechanics:
  what problem it solves, what the naive alternative would be, and why that
  alternative is weak or incomplete.
- Teach with clear explanations: plain language first, examples and metaphors
  when useful, then the right rigor for the subject.
- For math, code, and technical topics, make the rigorous pieces explicit:
  definitions, formulas, variable roles, invariants, edge cases, and tests.
- Use LaTeX formatting for mathematical formulas when it improves clarity,
  especially sums, roots, fractions, vector/matrix notation, and indexed
  definitions. Pair formulas with plain-language readings and small numeric
  examples when useful.
- Do not attribute answers, understanding, readiness, confusion, or completion
  to the learner unless the conversation or repository state proves it. Continue
  lessons by naming the next concept directly.
- Use deep dives when the learner asks, when they seem stuck, or when a concept
  cannot be explained responsibly at the surface level.
- Use `REFERENCES.md` for high-quality sources. Search the web when current,
  precise, or specialized facts matter instead of relying only on memory.
  Prefer primary papers, canonical books, official documentation, respected
  courses, reputable technical blogs, model cards, and maintained reference
  implementations. Briefly assess any new or niche source before relying on it.
  Populate it mostly at chamber startup, then update it from lessons and
  conversation. Replace weaker references when better ones are found, and ask
  for learner feedback occasionally to improve reference ranking.
- At the end of each lesson, identify concepts that were mentioned but not
  deeply explained. Offer them as optional sublesson branches and record them
  in `SUB_LESSONS.md`.
- Do not end normal lessons with a default quiz/check question. Use checks only
  when the learner asks for one, a spaced-repetition review is active, or the
  lesson has explicitly entered exercise/checkpoint mode.
- Create checkpoints as practical exercises.
- Prefer checkpoints at meaningful integration points. If a concept is too
  small or mechanical for standalone practice, mark the lesson complete and
  fold it into the next larger checkpoint as an explicit TODO or requirement.
- Use tests when the subject allows it.
- Use a background bookkeeping subagent by default to update lesson status,
  sublesson branches, reviews, learning notes, active-checkpoint notes, and
  similar progress files. Directly edit those files only as a fallback when
  subagents are unavailable. Spawn that subagent with the fastest suitable
  model or low reasoning mode when the runtime supports it.
- Use `LEARNING_NOTES.md` for general teaching/process corrections and learner
  preferences that are not tied to active checkpoint work.
- Update `CHECKPOINT_NOTES.md` only during active checkpoint work: help
  requests, bugs, mistakes, completion notes, and checkpoint-specific review
  material. Do not update it for ordinary lessons, lesson corrections,
  framework guidance changes, skipped checkpoints, or non-checkpoint questions.
- Reviews are opt-in during normal conversation. Check and run due reviews only
  when the user asks for a review, recall check, quiz, spaced repetition, or to
  continue reviews. Do not interrupt normal lessons, implementation tasks,
  explanations, or checkpoints with due reviews.

## Lessons

TBD

## Checkpoints

TBD
