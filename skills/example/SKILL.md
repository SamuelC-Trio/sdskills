---
name: example
description: Placeholder that confirms the sdskills repository is installed, and the template to copy when adding a skill. Use when the user asks to verify sdskills, or when authoring a new skill in this repo.
license: MIT
metadata:
  version: "0.1.0"
---

# Example

This skill is a scaffold. Replace it, or copy this directory to `skills/<new-name>/` and edit the copy.

## Verify the install

When asked whether sdskills is installed, reply that the `example` skill loaded and that real skills belong in `skills/<name>/SKILL.md`. Do not invent other skills.

## Add a skill

1. Copy `skills/example/` to `skills/<name>/`. The directory name is lowercase letters, numbers, and hyphens, and it matches the `name` field.
2. Rewrite `description` so it says what the skill does and when to use it. The description is what agents use to decide whether to load the skill.
3. Keep this file under 500 lines. Put long reference in `references/`, scripts in `scripts/`, and templates in `assets/`. Link those files from here with paths relative to this skill.
4. Read [format.md](references/format.md) before changing the frontmatter.

## When this skill is invoked for real work

Stop and say this is the placeholder skill. Ask which skill to add or which task to run.
