# Task Readiness Policy — Version 2.0 (SUPERSEDED)

Effective date: 2026-06-01
Status: superseded by version 3.2 (`docs/policies/task_readiness_policy.md`)
This version is kept for history only.

## 1. Scope

Task folders under `tasks/pool/`. Task folders under
`tasks/pool/maintenance/` are exempt from tracking and must NOT be added to
the Task Tracker.

## 2. Required files

A task folder must contain `docs/task.md` and `evaluation/main.py`.
If `docs/task.md` is missing, the status is `in progress` regardless of the
checklist score.

## 3. Checklist score

`checklist_score` in `task.json`. If the field is missing, leave the
Checklist Score cell empty.

## 4. Status bands

- `checklist_score >= 0.80` → status `ready`
- `0.60 <= checklist_score < 0.80` → status `in review`
- `checklist_score < 0.60` → status `in progress`
