# SCAFFOLD by specdriver.dev

Build Software Specs Level by Level

SCAFFOLD is an AI-powered framework for turning high-level requirements into structured, verifiable software specifications and exportable prompts. Teams organize work into a hierarchical workspace, validate dependencies, and human‑lock specs before handing them off to AI coding agents with confidence.

This is a public-facing overview repository. The core product is closed-source.

---

## 🔗 Live Product

- Website: https://specdriver.dev

---

## What SCAFFOLD does

- Structure complex initiatives into clear, navigable specs
- Enforce dependency integrity with a directed acyclic graph (DAG)
- Gate changes with human-controlled locking for immutability and auditability
- Generate AI-ready prompts from approved specs for precise implementation

Who it’s for:
- Engineering leads who need predictable, reviewable implementation plans
- Product teams who want traceable decisions and change control
- Individual developers who want strong guardrails for AI-assisted coding

---

## Key Features

- Hierarchical Workspace
  - Project → Category → Implementation nodes (purpose, file paths, requirements)
  - Tree-first interface; legacy canvas view for visual mapping
- Human‑Controlled Locking
  - Lock nodes only when metadata and upstream dependencies are satisfied
  - Locked specs become read‑only; unlocking is dependency‑aware
- DAG Validation
  - Dependency graph must be acyclic; backend enforces invariants
- AI Blueprint & Export
  - Generate/refine specs with AI; export approved nodes as rich prompts
  - Designed for tools like Cursor, Claude Code, and GitHub Copilot agents
- Operational Guardrails
  - Auth via Supabase, billing via Stripe, rate‑limits via Vercel KV
  - Versioned API for stable integrations

---

## How it works (at a glance)

1) Capture scope as nodes with purpose, file path, requirements, dependencies
2) Iterate with AI to refine content (humans stay in control)
3) Validate pre‑lock requirements and the dependency graph
4) Lock nodes (immutable, audit‑ready)
5) Export prompts and implement with your preferred AI coding tooling

---

## Architecture at a glance

- Frontend: Next.js (App Router), React, Tailwind CSS
- State: Zustand (optimistic updates)
- Backend/API: Next.js route handlers (versioned under /api/v1)
- Database: PostgreSQL (Prisma ORM)
- Auth: Supabase Auth
- AI: Azure OpenAI (GPT‑4o family) via AI SDK
- Payments: Stripe (checkout, webhooks)
- Hosting: Vercel + Vercel KV (rate limiting)
- Testing: Playwright (E2E) + Vitest (unit)

---

## Status

SCAFFOLD is live and under active development. Public docs and examples will expand here over time.

For product updates, follow this repository or visit https://specdriver.dev.

---

## Roadmap (high level)

- Public docs and end‑to‑end examples
- Spec export formats (Markdown + YAML front‑matter, MCP)
- Enhanced analytics and activity views
- Workspace UX refinements and accessibility passes

---

## Security & Privacy

- Human‑controlled locking prevents drift between approved spec and output
- Separation between public information and proprietary implementation details
- Secrets and credentials are never stored in this repository

If you find a security issue, please open a private advisory or reach out via the website.

---

## License

This repository’s contents are licensed under the license in [LICENSE](./LICENSE). The core product and hosted service remain proprietary.

---

## Support

- Questions or feedback: open a GitHub issue in this repository
- Product information: https://specdriver.dev
