# Metis Technologies Public GitHub Configuration — Agent Guidelines

> This file is the cross-tool source of truth for AI agents and humans working in `.github`. Claude Code loads it through [`CLAUDE.md`](CLAUDE.md); Codex, OpenCode, Gemini CLI, Cursor, and other AGENTS.md-compatible tools read it directly.

## Scope

This public repository contains the organization profile, community health files, issue and pull-request templates, and reusable public GitHub configuration. It has no application runtime or build toolchain.

Read [`CONTRIBUTING.md`](CONTRIBUTING.md) before changing contribution workflow. Read the specific template or profile file in full before editing it. Internal organization policy lives in the private `.github-private` repository and must not be copied here unless it is intentionally public.

## Git workflow

- No Linear team and no internal GitHub Issues: track organization-maintenance work through branches, commits, and pull requests.
- Branches: `chore/<kebab-description>` for normal meta-repository work. Use `fix/` or `feature/` only when appropriate.
- Commits: Conventional Commits without a ticket prefix.
- Default branch: `main`.
- Require review and use squash merge. Delete merged branches locally and remotely.

## Editing rules

- Assume every committed file is public. Never add personal contact details, credentials, secret names that reveal sensitive architecture, private repository links, or internal incident information.
- Keep default community files repository-agnostic. A product repository's own instructions override these defaults.
- Preserve the distinction in [`CONTRIBUTING.md`](CONTRIBUTING.md): external contributors may use public issues where a product accepts them; internal ticketless repositories are tracked only through branches, commits, and pull requests.
- Keep `AGENTS.md` canonical. `CLAUDE.md` is only a compatibility pointer and must not contain independent rules.
