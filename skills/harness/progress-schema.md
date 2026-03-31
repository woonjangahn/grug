# progress.json Schema

Write this file to `.claude/harness/progress.json` in the worktree.

```json
{
  "task": "short description of the feature",
  "created": "YYYY-MM-DD",
  "phase": "contract | implementation | evaluation | ship",
  "plan_file": "docs/superpowers/plans/YYYY-MM-DD-feature.md",
  "worktree_branch": "harness/feature-name",
  "acceptance_criteria": [
    {
      "id": 1,
      "description": "verifiable statement of what must be true",
      "tags": [],
      "status": "pending",
      "note": null
    },
    {
      "id": 2,
      "description": "UI-related criterion",
      "tags": ["browser"],
      "status": "pending",
      "note": null
    }
  ],
  "current_task": 0,
  "session_notes": "",
  "eval_history": []
}
```

## Field rules

| Field | Who updates | When |
|-------|------------|------|
| `phase` | Orchestrator | On entering each phase |
| `status` | Evaluator subagent only | During Phase 3 |
| `note` | Evaluator subagent | With evidence for pass/fail |
| `current_task` | Implementation agent | After completing each plan task |
| `session_notes` | Implementation agent | After each work session |
| `eval_history` | Orchestrator | After each evaluation round |

## eval_history entry

```json
{
  "round": 1,
  "timestamp": "YYYY-MM-DDTHH:mm:ss",
  "results": { "pass": 4, "fail": 1, "pending": 0 },
  "failures": [
    {
      "id": 2,
      "description": "criterion that failed",
      "note": "evaluator's evidence for why it failed"
    }
  ]
}
```

## Criteria immutability

- Descriptions are **append-only** — never modify or delete existing criteria
- New criteria can be added with the next available `id`
- Tags are set at creation time and do not change
