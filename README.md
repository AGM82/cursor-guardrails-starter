# Cursor Guardrails Starter

Thin project template — **guardrails only**, no playbook, Throughline prompts, or scheduled AI-review workflows.

Synced automatically from the [cursor-guardrails](https://github.com/AGM82/cursor-guardrails) hub (guardrail **v1.5.1**). Use this repo for GitHub **Use this template**. Keep a separate plain `git clone` of the **hub** as your reference clone for `/guardrail-upgrade`.

## Setup (new project)

1. GitHub → **Use this template** → create your repository.
2. `npm install` (activates husky). If you use `nvm`, run `nvm use` first.
3. `npm run typecheck`, `npm run lint`, `npm run test`.
4. Fill in `.cursor/rules/90-project-context.mdc` (canonical files, glossary, data classification).
5. Replace the demo app under `src/` with your product.
6. Commit; enable branch protection on `main` (three CI checks — see hub README).
7. For future guardrail updates: clone the **hub** separately and run `/guardrail-upgrade` in this project.

## What is intentionally missing

Hub-only assets stay in [cursor-guardrails](https://github.com/AGM82/cursor-guardrails): `playbook.html`, Throughline handoff docs, bi-weekly/weekly AI review, version propagation to Throughline, Cloudflare playbook hosting. Do not copy those here.

## Docs in this starter

- [docs/bootstrap-guardrail-upgrade.md](./docs/bootstrap-guardrail-upgrade.md) — adopt on an existing repo
- [docs/guardrail-layers.md](./docs/guardrail-layers.md) — layer model
- [docs/guardrail-upgrade-observations.md](./docs/guardrail-upgrade-observations.md) — lessons from real adoption

Consumer adaptations (Next.js, gitleaks placeholders, High-risk B2B patterns) live on the hub: [docs/consumer-adaptations.md](https://github.com/AGM82/cursor-guardrails/blob/main/docs/consumer-adaptations.md).

## Branch protection

Required checks (same names as hub CI):

- `Typecheck, lint, test, build`
- `Secret scan (gitleaks)`
- `SAST (Semgrep OWASP Top Ten)`
