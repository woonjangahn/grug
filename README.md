# grug

Complexity is the enemy. This plugin does two things:

**`/grug:init`** — Adds [Grug Brain](https://grugbrain.dev/) + [Radical Simplicity](https://www.radicalsimplicity.com/) principles to your global `~/.claude/CLAUDE.md`. Run once.

**`/grug:harness`** — For big features only. Defines acceptance criteria before coding, runs implementation in a worktree, evaluates with a separate agent. [Based on this](https://www.anthropic.com/engineering/harness-design-long-running-apps) and [this](https://www.anthropic.com/engineering/effective-harnesses-for-long-running-agents).

## Install

```bash
/plugin marketplace add woonjangahn/grug
/plugin install grug@grug
```

Requires [superpowers](https://github.com/anthropics/claude-code) plugin for `/grug:harness`.

## License

MIT
