# Chamber Agent Guidance

This directory is one active Timechamber.

Use the local files as source of truth:

- `CHAMBER.md`: learning contract and constraints.
- `LEARNING.md`: curriculum and checkpoint plan.
- `LESSONS.md`: lesson progress.
- `REVIEWS.md`: spaced repetition schedule.
- `CHECKPOINT_NOTES.md`: detailed checkpoint history.

If `CHAMBER.md` is missing or still says `Status: not initialized`, use
`../BOOTSTRAP.md` from the Timechamber root and finish onboarding before
teaching lessons.

At the start of each request:

1. Check `REVIEWS.md` for due reviews.
2. If a review is due, pause and ask a short recall question.
3. Update `REVIEWS.md` and `CHECKPOINT_NOTES.md` as needed.
4. Continue the user's requested learning task.

Teach one small concept at a time. When creating checkpoints, provide structure,
README files, tests where possible, and verified building blocks from prior
checkpoints. The learner implements the new concept unless they explicitly ask
for a solution.

