# grug

A Claude Code plugin for developers who believe complexity is the enemy.

Two tools: **`/grug:init`** injects Radical Simplicity principles into your global CLAUDE.md so every session follows the Grug Brain philosophy. **`/grug:harness`** runs substantial features through a structured Planner → Generator → Evaluator pipeline with acceptance criteria, worktree isolation, and independent evaluation by a separate subagent.

## Inspired by

- [The Grug Brained Developer](https://grugbrain.dev/) — the philosophy
- [Radical Simplicity](https://www.radicalsimplicity.com/) — the principles
- [Effective Harnesses for Long-Running Agents](https://www.anthropic.com/engineering/effective-harnesses-for-long-running-agents) — session management, JSON feature tracking, structured handoffs
- [Harness Design for Long-Running Application Development](https://www.anthropic.com/engineering/harness-design-long-running-apps) — Generator/Evaluator separation, sprint contracts, Playwright verification

## Install

```bash
/plugin marketplace add woonjangahn/grug
/plugin install grug@grug
```

Or test locally:

```bash
claude --plugin-dir /path/to/grug
```

<details>
<summary>For LLMs: copy this prompt to install grug</summary>

<pre>
Install the grug plugin for Claude Code. Follow these steps exactly:

1. Add the grug marketplace:
   Run: /plugin marketplace add woonjangahn/grug

2. Install the grug plugin:
   Run: /plugin install grug@grug

3. Install required dependencies (superpowers plugin):
   Run: /plugin marketplace add anthropics/claude-code
   Run: /plugin install superpowers@claude-plugins-official

4. (Optional) Install Playwright for browser-based acceptance criteria verification:
   Run: /plugin install playwright@claude-plugins-official

5. Verify installation:
   Run: /help
   Confirm /grug:init and /grug:harness are listed.

6. Run /grug:init to inject Radical Simplicity principles into ~/.claude/CLAUDE.md.

After setup, use /grug:harness for substantial multi-step features.
</pre>

</details>

## Commands

### `/grug:init`

Adds Radical Simplicity + Grug Brain principles to `~/.claude/CLAUDE.md`. Run once — every Claude Code session will follow these rules:

- Say no to complexity
- Don't over-abstract early
- Locality of behavior over separation of concerns
- Reuse what you have
- Code runs on people first
- Integration tests over unit tests
- No premature scaling
- 80/20 solutions

### `/grug:harness`

Structured development pipeline for substantial features (3+ files). Small tasks are actively rejected — "This is faster without the harness."

**Flow:**

```
Phase 0: Gate        — scan codebase, reject small tasks
Phase 1: Contract    — brainstorm, create worktree, define acceptance criteria
Phase 2: Implement   — parallel/sequential execution with progress tracking
Phase 3: Evaluate    — independent subagent verifies criteria with evidence
Phase 4: Ship        — PR with acceptance criteria checklist
```

**Key properties:**

- The agent that builds never evaluates its own work
- Acceptance criteria defined before implementation, verified after
- `[browser]` tagged criteria are verified via Playwright
- Failed criteria loop back with specific feedback — only fix what failed
- Max 3 evaluation rounds per criterion before asking for guidance
- All work happens in an isolated git worktree
- PR description includes acceptance criteria as a checklist

**Composes existing skills:**

| Phase | Skills used |
|-------|------------|
| Contract | `superpowers:brainstorming`, `superpowers:using-git-worktrees`, `superpowers:writing-plans` |
| Implement | `superpowers:dispatching-parallel-agents`, `superpowers:executing-plans`, `superpowers:verification-before-completion` |
| Evaluate | Playwright MCP, `superpowers:requesting-code-review` |
| Ship | `superpowers:finishing-a-development-branch` |

## Prerequisites

Claude Code 1.0.33+ required. Run `claude --version` to check.

### Required plugins (for `/grug:harness`)

The harness skill orchestrates existing superpowers skills. Install them first:

```bash
# Add the official Anthropic marketplace (if not already added)
/plugin marketplace add anthropics/claude-code

# Superpowers — brainstorming, planning, execution, verification, code review
/plugin install superpowers@claude-plugins-official
```

### Optional plugins

```bash
# Playwright — required only if you use [browser] tagged acceptance criteria
/plugin install playwright@claude-plugins-official

# Code review — used in Phase 3 evaluation (installed with superpowers)
/plugin install code-review@claude-plugins-official
```

### Install grug

```bash
# Add the grug marketplace
/plugin marketplace add woonjangahn/grug

# Install
/plugin install grug@grug

# Or test from local directory
claude --plugin-dir /path/to/grug
```

### Verify installation

```
/help
```

You should see `/grug:init` and `/grug:harness` listed.

## License

MIT
