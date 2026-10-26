# Adding a skill

Skills in this repository follow the [Agent Skills](https://agentskills.io/) format. The same `skills/<name>/SKILL.md` files install into Claude Code, Codex, Cursor, Pi, OpenCode, and the other agents supported by the [skills CLI](https://github.com/vercel-labs/skills).

## Create

```text
skills/
  my-skill/
    SKILL.md          # required
    scripts/          # optional executables
    references/       # optional docs, loaded on demand
    assets/           # optional templates and static files
```

`name` in the frontmatter must match the directory name.

```markdown
---
name: my-skill
description: Do the specific task. Use when the user asks for that task or names its trigger terms.
license: MIT
---

# My skill

Steps the agent should follow.
```

Copy `skills/example/` as a starting point. Keep `SKILL.md` under 500 lines and link out to `references/` for detail.

## Agents

Custom subagents are single markdown files in `agents/`. Each file needs `name` and `description` in its frontmatter. Cursor and Claude Code discover that directory from the plugin root. Delete `agents/example-agent.md` when you no longer need the placeholder.

## Manifests

Do not duplicate skill files into the manifest directories. Those files only point at `skills/` and `agents/`:

| File | Reader |
| --- | --- |
| `plugin.json` | Agent Plugins (Cursor, Codex, and other hosts of the open standard) |
| `.cursor-plugin/plugin.json` | Cursor plugin components, including agents |
| `.cursor-plugin/marketplace.json` | Cursor marketplace import of this repository |
| `.claude-plugin/plugin.json` | Claude Code plugin |
| `.claude-plugin/marketplace.json` | Claude Code marketplace add |
| `.codex-plugin/plugin.json` | Codex plugin |
| `.agents/plugins/marketplace.json` | Codex marketplace entry for this repository |

After adding a skill, bump `version` in each manifest that has one. The skills CLI does not read those manifests; it discovers `skills/*/SKILL.md` directly.
