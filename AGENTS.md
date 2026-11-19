# Repository Agent Instructions

## Required reading at the start of every session

Before changing any code or documentation, read these files in order:

1. `BRIEFING.md` for authoritative HealthCore facts, departments, processes, and constraints.
2. `memory-bank/projectbrief.md` for project objectives and milestone scope.
3. `memory-bank/techContext.md` for repository architecture, path ownership, and technical/regulatory constraints.
4. `memory-bank/progress.md` for verified status, completed work, and planned next steps.

If any required file is missing or conflicts with another source, do not infer a replacement or proceed with a consequential change. Report the gap or conflict to the developer. Before working in a repository area, read its `README.md` and any narrower applicable guidance.

## Before every commit

Complete these steps in order before a commit is proposed:

1. **Verify branch and scope.** Check the active branch and compare the change with `BRIEFING.md`, `memory-bank/projectbrief.md`, and `memory-bank/progress.md`. Confirm the work belongs to the approved HealthCore milestone.
2. **Check ownership and protected areas.** Read the relevant folder `README.md`, verify that each file is in its proper repository area, and identify any protected paths the change would touch. Obtain explicit developer confirmation before changing protected content.
3. **Validate the change.** Check acceptance criteria, consistency with the HealthCore context, formatting, and available relevant tests/checks. Review the full status and diff; ensure there are no orphaned files, accidental scope changes, or product code outside its designated folders.
4. **Update and present.** Update `memory-bank/progress.md` with completed work and validation results. Present a concise summary and diff to the developer and wait for approval before any commit.

The agent must not run `git commit` or `git push`. A commit, if approved, is performed manually by the developer.

## Protected paths

Without explicit developer confirmation, do not modify, move, overwrite, or delete:

- `BRIEFING.md`, `CONTEXT-healthcore-briefing.md`, or `CONTEXT.md`.
- `.git/` or Git metadata.
- Credentials, tokens, private keys, `.env` files, or other sensitive configuration/data.
- Existing product and infrastructure areas, including `/services`, `/uis`, `/infra`, `/data`, `/agents`, `/skills`, `/mcps`, `/workflows`, `/packages`, `/shared`, `/scripts`, and `/internal`.
- Existing base `README.md` files, including the root README and folder-level guides.

An explicit instruction to work in one of these paths authorizes only the specifically requested scope; it does not authorize unrelated cleanup. Never expose secrets or patient-identifying data in generated documentation, examples, logs, or repository content.

## Scope and placement

- Follow the root README and the relevant folder README; do not invent parallel trees or put product deliverables in the root.
- Keep development-agent configuration (`.agents/`, `AGENTS.md`, `memory-bank/`) separate from product assets (`/agents`, `/skills`, `/uis`, `/services`).
- The current milestone covers governance and HealthCore context only. Do not create product applications or product code unless the developer explicitly authorizes a later implementation milestone.
- Respect HIPAA in the US and UK GDPR in the UK. Treat the two EHR platforms and existing billing/scheduling systems as disconnected until verified otherwise. Preserve auditability and avoid premature microservices.
