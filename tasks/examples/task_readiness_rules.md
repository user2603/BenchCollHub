# Task Readiness Rules

- Version: 4.0
- Effective date: 2026-10-05
- Supersedes: Task Readiness Rules v2.3 (kept only for audit under `rules_archive/`)

These rules are the single authoritative source for reviewing developer tasks in
this repository. Any older document, any row already present in the Task Ledger,
and any recollection of earlier review rounds must NOT override this document.

## Scope

Apply these rules to every task directory that a developer pushed in the newest
commit on their branch. Rows that were already sitting in the Task Ledger before
this round were reviewed under older rules: leave them untouched and use them
only as a format reference (column layout and the two status values). Never
re-grade, edit, or remove an existing row.

## Status tiers

There are exactly two tiers. Do not invent, merge, or rename tiers.

- `delivered` - the task directory satisfies every readiness condition below.
- `under_work` - the task directory fails at least one readiness condition.

## Readiness conditions

A task directory is `delivered` only when ALL of the following hold:

1. `docs/task.md` exists in the task directory.
2. `evaluation/main.py` exists in the task directory.
3. `task_config.json` exists in the task directory.
4. The task directory contains at least 4 files in total, where the count covers
   every file inside the directory and all of its subdirectories.
5. The task directory name does not end with the suffix `-wip`.

If any condition fails, the task is `under_work`.

## Mandatory exclusion

Regardless of the other conditions, a task directory whose name ends with `-wip`
is always `under_work`. Never promote a `-wip` task to `delivered`.

## Inspection depth

Only the existence of files and the total file count are inspected. No file's
content, size, or wording is part of the review. Where the notes under
`tasks/examples/example-task/` disagree with this document, this document
prevails.
