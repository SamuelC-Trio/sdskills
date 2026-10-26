# sdskills

Agent Skills for Claude Code, Codex, Cursor, Pi, OpenCode, and other coding agents.

Each skill is a folder of plain markdown, `skills/<name>/SKILL.md`, in the [Agent Skills](https://agentskills.io/) format. The layout follows the same idea as [pstack](https://github.com/backnotprop/pstack): one repository, one plugin, and a `skills/` directory the skills CLI can install without Cursor.

## Install

From a published GitHub repository, replace `<owner>` with the GitHub account or organization:

```bash
npx skills add <owner>/sdskills
```

The CLI lists every skill. Pick the skills, then pick the agents. Add `-g` to install for every project, `--skill <name>` to install one skill, and `-y` to skip the prompts.

Before this folder is on GitHub, install it from the checkout:

```bash
npx skills add .
```

That covers Claude Code, Codex, Pi, Cursor, OpenCode, and the other agents the [skills CLI](https://github.com/vercel-labs/skills) supports. The manifests below are for each product's own plugin installer.

### Cursor

This repo is a Cursor plugin (`.cursor-plugin/plugin.json`) and a one-plugin marketplace (`.cursor-plugin/marketplace.json`).

- In Customize, import the GitHub repository. Cursor reads the marketplace manifest and installs the `sdskills` plugin.
- To try it before publishing, copy this directory to `~/.cursor/plugins/local/sdskills` and reload the window. A symlink that points outside that folder is ignored.

### Claude Code

```bash
claude plugin marketplace add <owner>/sdskills
claude plugin install sdskills@sdskills
```

Claude Code prefixes plugin skills, so the example skill is `/sdskills:example`. From a local checkout, `claude plugin marketplace add .` uses the same marketplace file.

### Codex

The Codex manifest is `.codex-plugin/plugin.json`. The marketplace entry is `.agents/plugins/marketplace.json`, with the plugin at the repository root. Install the folder as a local plugin, or add the published repository in Codex.

## Skills

| Skill | What it is |
| --- | --- |
| [exec-design-plan](skills/exec-design-plan/SKILL.md) | Execute `Design-Plan-[version].md`. Optional `version` (for example `v0.1.3`); otherwise the latest plan. |
| [example](skills/example/SKILL.md) | Placeholder that confirms the install, and the folder to copy when you add a skill. |

`agents/example-agent.md` is the matching placeholder subagent. Delete both once real skills and agents replace them.

## Add a skill

Copy `skills/example/` to `skills/<name>/`, then edit `SKILL.md`. The directory name and the `name` field must match. Details are in [docs/adding-a-skill.md](docs/adding-a-skill.md).

## Repository layout

```text
skills/<name>/SKILL.md          canonical skill
agents/<name>.md                optional subagents
plugin.json                     Agent Plugins manifest
.cursor-plugin/                 Cursor plugin and marketplace
.claude-plugin/                 Claude Code plugin and marketplace
.codex-plugin/plugin.json       Codex plugin
.agents/plugins/marketplace.json
docs/                           how to add a skill
assets/logo.svg                 plugin logo
```

After you create the GitHub repository, set `homepage` and `repository` in the manifests if you want those links on the plugin page.

## License

MIT. See [LICENSE](LICENSE).
