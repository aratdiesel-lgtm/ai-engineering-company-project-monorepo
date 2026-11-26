# Repository Agent Instructions

## Required reading at the start of every session

Before changing any code or documentation, read these files in order:

1. `BRIEFING.md` for authoritative HealthCore facts, departments, processes, and constraints.
2. `memory-bank/projectbrief.md` for project objectives and milestone scope.
3. `memory-bank/techContext.md` for repository architecture, path ownership, and technical/regulatory constraints.
4. `memory-bank/progress.md` for verified status, completed work, and planned next steps.

If any required file is missing or conflicts with another source, do not infer a replacement or proceed with a consequential change. Report the gap or conflict to the developer. Before working in a repository area, read its `README.md` and any narrower applicable guidance.

## Before every commit

Complete these steps in order before any commit is proposed:

1. **Verify branch and scope.** Confirm the active branch is `feature/agent-memory-bank`. Compare the changes with `BRIEFING.md`, `memory-bank/projectbrief.md`, `memory-bank/techContext.md`, and `memory-bank/progress.md`; confirm they fit the approved HealthCore milestone. This milestone is limited to governance and project context: do not introduce product code or applications outside its scope.
2. **Check repository ownership and compliance.** Read the relevant folder `README.md` and follow the monorepo routes: the public website belongs in `./uis/website`, the internal backoffice in `./uis/backoffice`, and backend/API work in the centralized `/services` application. Keep development-agent configuration (`.agents/`, root `AGENTS.md`, and `memory-bank/`) separate from product assets (`/agents` and `/skills`). Treat HIPAA and UK GDPR as applicable constraints; never add or expose PHI/PII, credentials, secrets, or `.env` files. Identify any protected paths the changes would touch and obtain explicit developer confirmation before changing them.
3. **Validate scope and working tree.** Check acceptance criteria, HealthCore consistency, formatting, and relevant available tests/checks. Review `git status` and the complete `git diff`; confirm there are no orphaned files, unintended changes, or product code outside the approved scope.
4. **Update and present.** Record verified work and validation results in `memory-bank/progress.md`. Present a clear summary and the relevant diff to the developer for review and approval. The agent must never execute `git commit` or `git push`; any commit is performed manually by the developer after explicit approval.

The agent must not run `git commit` or `git push`. A commit, if approved, is performed manually by the developer.

## Protected paths

Without explicit developer confirmation, do not modify, move, overwrite, or delete:

- `BRIEFING.md`, `CONTEXT-healthcore-briefing.md`, and `CONTEXT.md`.
- `.git/` and all Git metadata.
- `.env` files and all credentials, tokens, private keys, secrets, or sensitive configuration/data. Never expose PHI/PII in repository content, examples, or logs.
- Existing root and folder-level `README.md` files, and `docker-compose.yml`.
- Existing product and infrastructure folders: `/services`, `/uis`, `/data`, `/infra`, `/agents`, `/skills`, `/mcps`, `/workflows`, `/packages`, `/shared`, `/docs`, `/scripts`, and `/internal`.

An explicit instruction to work in one of these paths authorizes only the specifically requested scope; it does not authorize unrelated cleanup. Preserve the separation between development-agent configuration (`.agents/` and `memory-bank/`) and product assets.

## Scope and placement

- Follow the root README and the relevant folder README; do not invent parallel trees or put product deliverables in the root.
- Keep development-agent configuration (`.agents/`, `AGENTS.md`, `memory-bank/`) separate from product assets (`/agents`, `/skills`, `/uis`, `/services`).
- The current milestone covers governance and HealthCore context only. Do not create product applications or product code unless the developer explicitly authorizes a later implementation milestone.
- Respect HIPAA in the US and UK GDPR in the UK. Treat the two EHR platforms and existing billing/scheduling systems as disconnected until verified otherwise. Preserve auditability and avoid premature microservices.
