# Timechamber Structure

The root of this repository defines the framework. Actual learning happens in
directories named:

```text
chamber-<learning-name>
```

Examples:

```text
chamber-c-inference-engine
chamber-linear-algebra
chamber-rust-cli-tools
chamber-writing-essays
```

Use lowercase kebab-case names. Keep names short and descriptive.

## Root Files

Root files explain how Timechamber works:

- `README.md`: overview.
- `AGENTS.md`: agent rules.
- `BOOTSTRAP.md`: first-run onboarding flow.
- `STRUCTURE.md`: directory structure and chamber rules.
- `templates/`: files copied into new chambers and checkpoints.

Root files should not track a specific user's lesson progress.

Template groups:

```text
templates/chamber/     files copied into new chamber-* directories
templates/checkpoint/  files copied into checkpoint folders
```

## Root Flow

When starting a new topic from the root:

1. Ask what the user wants to learn.
2. Choose a chamber name.
3. Create `chamber-<name>/`.
4. Copy/adapt `templates/chamber/`.
5. Continue onboarding inside that chamber.
6. Fill the chamber-local learning files.

## Chamber Files

Each `chamber-*` directory should contain:

```text
chamber-<name>/
  AGENTS.md
  CHAMBER.md
  LEARNING.md
  LESSONS.md
  REVIEWS.md
  CHECKPOINT_NOTES.md
  checkpoint_01_<name>/
    README.md
    ...
```

The user should interact with the agent while the working directory is inside
the relevant `chamber-*` directory.

## Creating a Chamber

When the user wants to learn a new topic:

1. Ask the onboarding questions from `BOOTSTRAP.md`.
2. Choose a chamber directory name.
3. Create `chamber-<name>/`.
4. Copy/adapt the files from `templates/chamber/`.
5. Fill in `CHAMBER.md` with the learning contract.
6. Fill in `LEARNING.md` with the curriculum.
7. Initialize `LESSONS.md`, `REVIEWS.md`, and `CHECKPOINT_NOTES.md`.

Do not create lesson-specific state in the root.
