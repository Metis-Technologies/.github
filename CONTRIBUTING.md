# Contributing to Metis Technologies projects

Thanks for your interest in contributing! 🎉

Each repository may have its own `CONTRIBUTING.md` with specifics; this file is the org-level default for repositories that don't ship one.

## Before you start

1. Open an **issue** to discuss the change before writing code (especially for non-trivial work)
2. For internal contributors: create the corresponding **Linear ticket** first
3. Check existing issues and PRs to avoid duplicates

## Workflow

### External contributors

1. Fork the repo
2. Create a branch from `develop` (or `main` if no `develop`): `feature/<short-slug>`, `fix/<short-slug>`, `chore/<short-slug>`
3. Make your changes, keeping commits focused
4. Open a PR against `develop` (or `main`)
5. Wait for review — at least one maintainer approval required

### Internal contributors (Metis team)

Branch and commit convention is enforced per repo. Linear team keys:

- `beautyflow` → team `BF`
- `beautyflow-mobile` → team `BFM`
- `metis-website`, `metis-agent-engine`, `.github`, `.github-private` → no Linear team yet (workspace on the Free plan) → branch `chore|feature|fix/<slug>`, tracked via branches/commits/PRs only. Do **not** open GitHub Issues for these — that's a deliberate policy choice, not an oversight

Branch format: `feature|fix|chore/<KEY>-<N>-<slug>`
Commit format: `<KEY>-<N> <type>: <description>` (`type` ∈ `feat`, `fix`, `refactor`, `chore`, `docs`, `test`)

Local hooks (`.githooks/pre-push`, `.githooks/commit-msg`) enforce the convention. Setup once with `sh scripts/setup-hooks.sh`.

## Code style

- TypeScript: strict mode, no `any`
- Dart: `dart format` + `flutter analyze`
- Match the existing style of the file you're editing
- Add tests for new logic

## Reviews

- One approval from a maintainer is required to merge
- Reviewers may suggest changes; address them with new commits (don't force-push during review)
- Squash-and-merge is the default

## Code of Conduct

By contributing you agree to abide by our [Code of Conduct](CODE_OF_CONDUCT.md).
