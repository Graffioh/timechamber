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

Use a background bookkeeping subagent by default for updates to `LESSONS.md`,
`REVIEWS.md`, `CHECKPOINT_NOTES.md`, and similar progress files. The main agent
continues the teaching work, but must confirm required updates before moving
past reviews, lesson status changes, or checkpoint notes. If subagents are
unavailable, make the smallest necessary direct edit and note that fallback.
When spawning the bookkeeping subagent, request the fastest suitable model or
low reasoning mode available in the Codex environment. If the runtime cannot
enforce model selection, keep the delegated task small and bounded.

At the start of each request:

1. Check `REVIEWS.md` for due reviews.
2. If a review is due, pause and treat the user's message as a pending request.
3. Ask a short recall question.
4. Have the background bookkeeping subagent update `REVIEWS.md` and
   `CHECKPOINT_NOTES.md` as needed.
5. Only after the review is complete, answer the pending question or continue
   the user's requested learning task.

Do not answer the user's question or begin the requested task before the due
review has been completed and recorded.

Teach one small concept at a time. When creating checkpoints, provide structure,
README files, tests where possible, and verified building blocks from prior
checkpoints. The learner implements the new concept unless they explicitly ask
for a solution.
