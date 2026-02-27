# AI Usage (Copy/Paste)

## Prompt (repo audit)

You are a senior Laravel architect + release engineer.
Audit my changes using this repository modules.

Return:

1. Risks (high/medium/low) with reasons
2. Checklist with commands
3. Safe migration plan (if DB changes)
4. PR description (summary + testing + env vars + deploy notes)
5. Suggested commit message(s) using Conventional Commits

Constraints:

- Prefer minimal, production-safe changes
- Assume latest stable Laravel
- If uncertainty exists, state assumptions explicitly
