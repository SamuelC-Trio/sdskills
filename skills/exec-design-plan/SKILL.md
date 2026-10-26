---
name: exec-design-plan
description: Execute a Design-Plan markdown file for a named version, or the latest Design-Plan when no version is given. Use when the user runs /exec-design-plan, asks to execute a design plan, or supplies a plan version such as v0.1.3.
disable-model-invocation: true
license: MIT
---

# exec-design-plan

Find the corresponding plan file (e.g. Design-Plan-[version].md), use latest if no version provided.  Clarify version/tasks if necessary before executing the plan.

## Parameter

`version` is optional. `v0.1.3` selects `Design-Plan-v0.1.3.md`.

## Find the plan

Search the workspace for `Design-Plan-*.md`.

- With `version`: open `Design-Plan-<version>.md`. If that file is missing, or more than one path matches, list the matches and ask which file to use.
- Without `version`: pick the latest `vMAJOR.MINOR.PATCH` suffix, compared as a version. If no file has that suffix, or two files tie, ask which file to use.

## Clarify, then execute

Clarify before doing the work when the version is ambiguous, or when the plan's tasks are ambiguous, partial, or in conflict. State the file and the task list in that question.

When the file and the full task list are clear, execute the tasks in the order written. Stop and report if a task fails, and do not start a later task that depends on it.
