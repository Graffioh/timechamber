# Spaced Repetition Reviews

Current recall levels:

- `1`: repeat it; the idea is weak or fuzzy.
- `2`: quiz me; ask targeted questions about specific hard parts.
- `3`: remembered; no extra work needed right now.

Review schedule:

| Stage | Next interval after recall level `3` |
| --- | --- |
| `new` | 30 minutes |
| `30m` | 1 day |
| `1d` | 3 days |
| `3d` | 7 days |
| `7d` | 14 days |
| `14d` | 30 days |
| `30d` | 60 days |

If recall level is `1`, briefly repeat the topic and schedule another review
for 30 minutes later.

If recall level is `2`, ask targeted questions using `CHECKPOINT_NOTES.md`, then
schedule another review for 30 minutes later unless the user reaches level `3`.

## Scheduling Rules

- Recall `1`: do not advance `Stage`; set `Next Due` to 30 minutes from now.
- Recall `2`: do not advance `Stage`; ask targeted questions; set `Next Due` to
  30 minutes from now unless the user reaches recall `3`.
- Recall `3`: advance `Stage`; set `Next Due` using the next interval in the
  schedule.

## Review Rule

At the start of each chat request, check this file. If any review is due, pause
the current task and treat the user's message as a pending request. Do not
answer the user's question or begin the requested task until the review is
complete and this file has been updated. Have the background bookkeeping
subagent update this file, preferably with the fastest suitable model or low
reasoning mode. After the review is recorded, return to the pending request.

Stage progression:

```text
new -> 30m -> 1d -> 3d -> 7d -> 14d -> 30d -> 60d
```

## Cards

| Item | Topic | Source | Completed At | Last Review | Stage | Next Due | Last Recall | Weak Spots |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
