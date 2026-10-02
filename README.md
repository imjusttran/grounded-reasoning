# Grounded Reasoning

An evidence-first Agent Skill for answers that need accurate sourcing, calibrated uncertainty, and a final adversarial check. It uses the open `SKILL.md` format; discovery and tool support vary by agent.

## Install

With the community `skills` CLI:

```sh
npx skills add <owner>/grounded-reasoning --skill grounded-reasoning
```

To target specific supported agents, add options such as `-g -a claude-code -a codex -a antigravity -a antigravity-cli`. Check `npx skills add --help` for current targets and flags.

Or copy `skills/grounded-reasoning/` into the skills directory documented by your agent. Common locations include:

| Agent | Project | User-wide |
|---|---|---|
| Claude Code | `.claude/skills/grounded-reasoning/` | `~/.claude/skills/grounded-reasoning/` |
| Codex | `.agents/skills/grounded-reasoning/` | `~/.agents/skills/grounded-reasoning/` |
| Antigravity IDE | `.agents/skills/grounded-reasoning/` | `~/.gemini/config/skills/grounded-reasoning/` |
| Antigravity CLI | `.agents/skills/grounded-reasoning/` | `~/.gemini/antigravity-cli/skills/grounded-reasoning/` |

See the current [Agent Skills specification](https://agentskills.io/specification), [Claude Code skills guide](https://code.claude.com/docs/en/skills), [Codex skills guide](https://developers.openai.com/codex/skills), [Antigravity IDE guide](https://antigravity.google/docs/skills?app=antigravity-ide), and [Antigravity CLI guide](https://www.antigravity.google/docs/cli/plugins). Hosts differ in discovery paths, activation, and tool access; this format alone cannot guarantee identical behavior everywhere.

## License

MIT. See [LICENSE](LICENSE).
