# Technical Context

## Monorepo structure and ownership

Use the existing top-level folders and their `README.md` files as the routing authority. Do not invent parallel top-level trees or place all work in the repository root.

- `./uis/website`: public-facing website, served at `/` in its own deployment or development environment.
- `./uis/backoffice`: internal application, served at `/` in its own deployment or development environment.
- `/services`: the company's centralized FastAPI API. Keep domain endpoints in the central application; extract a worker only when a genuinely separate runtime is needed. Do not introduce premature microservices.
- `data/`: raw inputs, pipelines, processed artifacts, and evaluation sets. Keep raw and processed data distinct, document provenance/schema/refresh and quality, and do not commit sensitive patient data; prefer synthetic or anonymized evaluation data.
- `agents/`: product agents, one concrete agent per subfolder with its own documentation, prompts/tools wiring, and tests.
- `skills/`: reusable product-agent capabilities, organized as discoverable skill folders and documented with their use, inputs/outputs, and examples.
- `mcps/`: MCP servers, one server per subfolder with documentation of exposed tools and resources.
- `workflows/`: operational automation; document triggers, inputs/outputs, credentials, steps, and error handling.
- `packages/`: versionable shared code packages, each with a README and documented public API/consumption.
- `shared/`: smaller unbundled schemas, templates, assets, and shared configuration; document consumers.
- `docs/`: cross-cutting architecture, decisions, security, observability, and conventions.
- `infra/`: infrastructure and deployment configuration.
- `scripts/`: small repeatable helper scripts with usage and requirements documented.
- `internal/`: structured engineering tools with their own dependencies, tests, and installation guidance.

The root README describes this repository as a starter structure rather than a runnable product stack; it reports no root workspace runner. Verify actual folder guidance before adding files. In particular, the root README specifies a centralized FastAPI backend and advises against splitting into many microservices early.

## Development-agent configuration vs. product assets

These locations have different purposes and must not be conflated:

- `.agents/`, root `AGENTS.md`, and `memory-bank/` are development-agent configuration, instructions, and project context. They guide work performed on the repository; they are not HealthCore runtime features.
- `/agents`, `/skills`, `/uis`, and `/services` hold product deliverables (agents, reusable product capabilities, user interfaces, and backend/API code) and must follow their own folder READMEs.

Do not create product assets under `.agents/` or put development-agent rules in product folders.

## HealthCore integration and safeguards

- HealthCore operates under HIPAA in the United States and UK GDPR in the United Kingdom. Treat jurisdiction, access, retention, disclosure, and audit requirements as design constraints; do not imply that one policy automatically satisfies both regimes.
- The two EHR platforms and the billing and scheduling processes are disparate and currently lack a shared data layer. Any future integration must preserve source-system traceability and support auditable access; do not assume integrations or unified records already exist.
- Audit trails and access records are currently incomplete or separate. Changes involving patient data must make authorization and traceability explicit and be reviewed against the applicable jurisdiction.
- Do not place real patient data, credentials, secrets, or `.env` files in the repository. Follow data-folder guidance on provenance and privacy; use synthetic or anonymized data for examples and evaluation where appropriate.
- Prefer the smallest architecture that fits the approved milestone and the six-person technology team. Keep a centralized API unless a concrete operational need justifies a separate worker; avoid speculative microservices and infrastructure.

## Source of truth

Use `BRIEFING.md` for HealthCore domain facts, `README.md` at the root for monorepo-wide structure, and the relevant folder-level README for local conventions. If instructions conflict, stop and surface the conflict before making a consequential change.
