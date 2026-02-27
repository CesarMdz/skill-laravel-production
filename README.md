# Laravel Production Readiness Skill

> **AI-ready, production-grade readiness framework for modern Laravel applications.**  
> Designed for humans **and** AI agents to ship safely, scale intentionally, and break nothing.

<p align="left">
  <img alt="Laravel" src="https://img.shields.io/badge/laravel-latest%20stable-red" />
  <img alt="License" src="https://img.shields.io/badge/license-mit-green" />
  <img alt="CI" src="https://github.com/CesarMdz/skill-laravel-production/actions/workflows/markdown-lint.yml/badge.svg" />
  <img alt="Version" src="https://img.shields.io/badge/version-1.1.0-blue" />
</p>

---

## Why this exists

Most Laravel production incidents are not caused by syntax errors — they come from:

- Unsafe database migrations
- Weak architectural boundaries (fat controllers, mixed responsibilities)
- Missing deployment discipline and post-deploy checks
- Silent performance regressions (N+1, missing indexes, caching gaps)
- Inconsistent Git and PR hygiene

This repository provides a **repeatable production readiness gate** to prevent those failures.

---

## What this evaluates

- **Architecture**: thin controllers, Actions/Services, Requests, Policies
- **Security**: environment/config discipline, rate limits, safe defaults
- **Database safety**: safe migrations, indexing strategy, N+1 prevention
- **Performance**: caching, queues, config/route/view caching
- **Quality gates**: tests, formatting, static analysis
- **Deploy safety**: zero-downtime mindset, rollback planning
- **Git discipline**: clean commits, structured PRs, semantic releases

---

## Who is this for?

- Laravel developers shipping to staging/production
- Tech leads enforcing consistent quality
- SaaS teams
- AI-assisted development workflows

---

# Installation

Recommended location inside your project:

.ai/skills/laravel-production-readiness/

---

## Option A — Copy (Fastest)

1. Download this repository.
2. Copy into your Laravel project:

your-laravel-project/
.ai/
skills/
laravel-production-readiness/
SKILL.md
modules/

Best for teams who want a stable snapshot.

---

## Option B — Git Submodule

From your Laravel project root:

```bash
mkdir -p .ai/skills
git submodule add https://github.com/CesarMdz/skill-laravel-production.git .ai/skills/laravel-production-readiness
git commit -m "chore: add laravel production readiness skill (submodule)"
```

Update later:

```bash
git submodule update --remote --merge
git commit -m "chore: update laravel production readiness skill"
```

---

## Option C — Git Subtree (Recommended)

```bash
mkdir -p .ai/skills
git subtree add --prefix=.ai/skills/laravel-production-readiness https://github.com/CesarMdz/skill-laravel-production.git main --squash
git commit -m "chore: vendor laravel production readiness skill (subtree)"
```

Update later:

```bash
git subtree pull --prefix=.ai/skills/laravel-production-readiness https://github.com/CesarMdz/skill-laravel-production.git main --squash
git commit -m "chore: update laravel production readiness skill"
```

---

# Usage

## Human Workflow (Pre-PR / Pre-Deploy)

1. Review `modules/00-overview.md`
2. If database changed → apply `modules/03-database.md`
3. Before deploy → apply `modules/06-deploy.md`
4. Before pushing → apply `modules/07-git.md`
5. Document results in your PR

---

## AI Workflow

Copy into your AI assistant:

> Apply the Laravel Production Readiness Skill located at `.ai/skills/laravel-production-readiness/`.  
> Output:
>
> 1. Risks (high/medium/low)
> 2. Checklist with commands
> 3. Safe migration strategy (if DB changes)
> 4. PR description
> 5. Deploy notes
> 6. Suggested commit messages

More examples: `modules/08-ai-usage.md`

---

## Example Output

### Risks

- **HIGH**: Migration drops a column on a large table (locking risk)
- **MEDIUM**: Missing index on frequently filtered foreign key
- **LOW**: Business logic inside controller

### Safe Migration Strategy

1. Add nullable column
2. Backfill in batches
3. Add index
4. Switch application logic
5. Remove old column in later deploy

### Suggested Commit

fix(payments): handle gateway timeout with safe retry logic

---

# Modules

- modules/00-overview.md
- modules/01-architecture.md
- modules/02-security.md
- modules/03-database.md
- modules/04-performance.md
- modules/05-quality.md
- modules/06-deploy.md
- modules/07-git.md
- modules/08-ai-usage.md

---

# Versioning

Semantic Versioning (MAJOR.MINOR.PATCH).  
See CHANGELOG.md.

---

# Contributing

See CONTRIBUTING.md.  
Security issues → SECURITY.md.

---

# License

MIT — see LICENSE.
