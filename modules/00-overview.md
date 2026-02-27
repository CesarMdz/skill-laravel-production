# Overview

## When to apply

- Before opening a PR
- Before deploying to staging/production
- After touching DB migrations, auth, payments, queues, or caching

## Output contract (for humans + AI)

1. Risk report (high/medium/low) with _reasons_
2. Checklist with commands (Laravel + frontend if applies)
3. Safe migration strategy if DB changes
4. PR body (summary, testing steps, env vars, deploy notes)
5. Suggested commit message(s)

## Quick gate (2–5 min)

- git diff / status
- no secrets (.env, keys, tokens)
- composer validate
- npm run build (if frontend)
- artisan: config:clear, route:clear, view:clear
- artisan test (if exists)
