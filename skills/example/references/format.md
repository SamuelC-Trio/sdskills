# Skill format

One skill is one directory. `SKILL.md` is required. `scripts/`, `references/`, and `assets/` are optional.

## Frontmatter

| Field | Required | Rule |
| --- | --- | --- |
| `name` | yes | Max 64 characters. Lowercase letters, numbers, and hyphens. Must match the directory name. Must not start or end with a hyphen. |
| `description` | yes | Max 1024 characters. What the skill does and when to use it. Written in third person. |
| `license` | no | License name, or a path to a license file in the skill. |
| `compatibility` | no | Max 500 characters. Environment requirements. |
| `metadata` | no | String keys to string values. |
| `allowed-tools` | no | Space-separated tool names. Experimental. |

Agents load `name` and `description` up front, the rest of `SKILL.md` when the skill runs, and other files only when the skill points at them.
