# Laravel Production Readiness Skill

AI-ready, production-grade checklist and guidance for modern Laravel applications.
Designed for humans **and** AI agents to ship changes safely with scalable architecture.

![Laravel](https://img.shields.io/badge/Laravel-latest%20stable-red)
![License](https://img.shields.io/badge/License-MIT-green)
![CI](https://github.com/CesarMdz/skill-laravel-production/actions/workflows/markdown-lint.yml/badge.svg)
![Version](https://img.shields.io/badge/version-1.1.0-blue)

## What this is

A structured “production readiness” skill that evaluates:

- Architecture quality (thin controllers, actions/services, domain boundaries)
- Security posture (config/env, rate limits, auth patterns)
- Database safety (safe migrations, indexes, N+1 prevention)
- Performance (cache, queues, config caching)
- Quality gates (tests, formatting, static analysis)
- Deployment safety (zero-downtime mindset, post-deploy checks)
- Git discipline (commits/PRs/releases)

## Compatible with

- Claude Skills (`SKILL.md`)
- ChatGPT / OpenAI Agents
- Copilot Agents
- Any LLM-based dev assistant

## How to use (human)

Use this as a pre-PR/pre-deploy gate:

1. Pick the relevant module(s) in `/modules`
2. Run the checks
3. Document results in PR + deploy notes

## Install (add this skill to your project)

You can use this repository in any Laravel project in three ways.  
Recommended path inside your project: `.ai/skills/laravel-production-readiness/`

### Option A — Copy/Paste (fastest, simplest)
1) Download this repository as ZIP (or clone it temporarily).
2) Copy these folders/files into your project:

- `SKILL.md`
- `modules/`
- (optional) `.github/` templates/workflows if you want them too

Example destination:

- your-laravel-project/
- .ai/
- skills/
- laravel-production-readiness/
- SKILL.md
- modules/

This option is best if you just want a stable snapshot and don’t care about updates.

### Option B — Git Submodule (best for keeping it updated)
From your Laravel project root:

```bash
mkdir -p .ai/skills
git submodule add https://github.com/CesarMdz/skill-laravel-production.git .ai/skills/laravel-production-readiness
git commit -m "chore: add laravel production readiness skill (submodule)"

---

## How to use (AI)

Copy this prompt into your AI assistant:

> You are my Laravel Production Readiness auditor. Apply the modules in this repository to review my change.  
> Output: (1) risks, (2) checklist with commands, (3) safe migration strategy if DB changes, (4) PR description, (5) deploy notes, (6) recommended commit message(s).

More examples: `modules/08-ai-usage.md`.

## Modules

- `modules/00-overview.md`
- `modules/01-architecture.md`
- `modules/02-security.md`
- `modules/03-database.md`
- `modules/04-performance.md`
- `modules/05-quality.md`
- `modules/06-deploy.md`
- `modules/07-git.md`
- `modules/08-ai-usage.md`

## Versioning

We use **Semantic Versioning** (`MAJOR.MINOR.PATCH`). See `CHANGELOG.md`.

## Contributing

See `CONTRIBUTING.md`. Security issues: see `SECURITY.md`.

## License

MIT — see `LICENSE`.
