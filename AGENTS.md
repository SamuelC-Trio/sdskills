# AGENTS.md

This repository is a catalog of Agent Skills. The canonical skill is `skills/<name>/SKILL.md`.

## Rules

- Add a skill by creating `skills/<name>/SKILL.md`. `name` matches the directory: lowercase letters, numbers, and hyphens, no leading or trailing hyphen.
- Keep each `SKILL.md` under 500 lines. Put long material in that skill's `references/`, `scripts/`, or `assets/`.
- Do not put skill files inside `.cursor-plugin/`, `.claude-plugin/`, `.codex-plugin/`, or `.agents/`. Those directories are install manifests.
- A new subagent is one file, `agents/<name>.md`, with `name` and `description` frontmatter.
- When skill contents change, bump `version` in `plugin.json`, `.cursor-plugin/plugin.json`, `.claude-plugin/plugin.json`, and `.codex-plugin/plugin.json` together.
- Write skills so they do not depend on one product's tools. If a step needs a product-specific tool, say which host it applies to and what to do on the others.

## Layout

See [docs/adding-a-skill.md](docs/adding-a-skill.md).
