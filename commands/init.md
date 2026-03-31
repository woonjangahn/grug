Add the following Radical Simplicity + Grug Brain principles to the user's global CLAUDE.md file at `~/.claude/CLAUDE.md`. If the file already exists, append under a new section. If it already contains a "Radical Simplicity" or "Grug Brain" section, tell the user it's already configured and skip.

Use the `Read` tool to check if `~/.claude/CLAUDE.md` exists and whether it already has these principles. Then use `Edit` (to append) or `Write` (to create) as appropriate.

## Content to add

```markdown
# Radical Simplicity + Grug Brain

Complexity is the enemy. Every line of code, every abstraction, every dependency is a liability until proven otherwise.

## Principles

- **Say no to complexity.** If it can be done with fewer parts, do it with fewer parts. Challenge every new dependency, abstraction, and layer.
- **Don't over-abstract early.** Let good cut-points emerge naturally from the codebase. Three similar lines of code is better than a premature abstraction. DRY is not a religion.
- **Locality of behavior over separation of concerns.** Code that works together should live together. Don't scatter related logic across files for the sake of "clean architecture."
- **Reuse what you have.** Extend existing technology before adding new moving parts. Postgres can be a database, a queue, a cache, and a search engine.
- **Deep domains, shallow tech stacks.** Spend time on business logic and algorithms, not on ceremony around frameworks and serialization layers.
- **Code runs on people first.** Before code runs on a computer it needs to run in your head. If it takes an hour to figure out what's going on, it's too complex.
- **Prototype before architecting.** Real code reveals the right structure. Let reality inform design, not the other way around.
- **Integration tests over unit tests.** Test real behavior through real paths. Mocks hide the bugs that matter most.
- **No premature scaling.** Build for the users you have, not the millions you might have someday. Add complexity only when actual load demands it.
- **80/20 solutions.** A pragmatic solution that covers 80% of cases now beats a perfect solution that takes 5x longer.

## For Claude specifically

- Don't add abstractions, helpers, or utilities for one-time operations
- Don't add error handling for scenarios that can't happen
- Don't refactor code that wasn't asked to be refactored
- Don't add features beyond what was requested
- Prefer simple, direct code over "clever" code
- When suggesting architecture, default to the simplest thing that works — monolith over microservices, server-rendered HTML over SPA, fewer dependencies over more
```

After writing, confirm to the user what was done and where.
