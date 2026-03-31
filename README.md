# grug

Complexity bad. This plugin does two things:

`/grug:init` — puts [grug brain](https://grugbrain.dev/) principles in your `~/.claude/CLAUDE.md`. Run once.

`/grug:harness` — for big features. Write acceptance criteria first, build in a worktree, let a separate agent decide if it actually works. Based on [this](https://www.anthropic.com/engineering/harness-design-long-running-apps) and [this](https://www.anthropic.com/engineering/effective-harnesses-for-long-running-agents).

## Install

```bash
/plugin marketplace add woonjangahn/grug
/plugin install grug@grug
```

Needs [superpowers](https://github.com/anthropics/claude-code) plugin for `/grug:harness`.

## License

MIT
