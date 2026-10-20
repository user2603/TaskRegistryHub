# Task Readiness Policy — Version 3.2

Effective date: 2026-11-01
Supersedes: version 2.0 (archived under `docs/policies/archive/`)

This is the only document that defines how a task in this collection is graded
for the Task Tracker. Older policy versions, archived tracker exports and rows
that already exist in the tracker only describe how things were graded at the
time; they must never be used to derive the current rules.

## 1. Scope

Every task folder under `tasks/pool/` is in scope, including task folders under
`tasks/pool/maintenance/`. The maintenance-category exemption that existed in
version 2.0 has been REMOVED: maintenance tasks are graded like any other task
and must appear in the Task Tracker.

## 2. Required files

A task folder must contain all four of the following files:

- `docs/task.md`
- `evaluation/main.py`
- `solution/main.py`
- `README.md`

If ANY of the four files is missing, the task status is `in progress`,
regardless of the checklist score.

## 3. Checklist score

Each task folder carries a `task.json` manifest with a `checklist_score` field
between 0.00 and 1.00 (two decimals). Use the value exactly as written; do not
round it and do not recompute it. If `task.json` has no `checklist_score`
field, treat the score as 0.00.

## 4. Status bands

When all four required files are present:

- `checklist_score >= 0.90` → status `ready`
- `0.70 <= checklist_score < 0.90` → status `in review`
- `checklist_score < 0.70` → status `in progress`

## 5. Tracker columns

For every in-scope task folder, the Task Tracker row must record:

- Task Name: the task folder name
- Status: one of `ready`, `in review`, `in progress` (see section 4)
- Implementor: the `implementor` field of `task.json`
- Checklist Score: the checklist score written with exactly two decimals
  (a missing score is recorded as `0.00`)

Rows that already exist in the tracker are not re-graded.
