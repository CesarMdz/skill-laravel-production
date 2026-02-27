# AI Usage Guide

This module helps AI agents produce consistent, high-signal outputs.

## Invocation prompt (generic)
You are a senior Laravel architect and release engineer.
Audit my changes using this repository’s modules.

Output must include:
1) Risk report (High/Med/Low) with concrete reasons
2) Checklist with commands (Laravel + frontend if relevant)
3) Database migration risk plan (safe-migration steps)
4) Architecture recommendations (actions/services/policies/requests)
5) PR description (summary + testing steps + env vars + deploy notes)
6) Suggested commit message(s) following Conventional Commits

## If DB changes exist
- Require: migrate strategy (add nullable → backfill → constraint/index)
- Require: rollback plan
- Require: estimate of table size impact (if unknown, mention as assumption)

## If queues/jobs exist
- Require: idempotency notes
- Require: retry/failure strategy
- Require: Horizon/supervisor notes if relevant

## Minimal output example
- Risks:
- Checklist:
- PR template:
- Deploy notes:
- Commit messages:
