# Naming convention — media-knowledge-projects

## Canonical category taxonomy

The canonical category taxonomy for this wiki is **`categories.yaml` at the repo
root** — the single source of truth. The wiki engine consumes it for the category
nav; it carries the id, display name, scope, audience, and display order for every
category. Any category question resolves against that file, not against prose in
CLAUDE.md or elsewhere.

## Decision log

**2026-07-02 — plain-language category set ratified (12 categories).** This session
ratified the plain-language category set — `buildings`, `building-design`,
`site-selection`, `markets`, `rollout`, `industry`, `urban`, `architecture`, `gis`,
`research`, `reference`, `news` — recorded canonically in `categories.yaml`. It
supersedes the informal category layout previously described in CLAUDE.md. The
per-place slug-band convention that keeps the growing atlas O(1) (`about-*` sorts
before `atlas-*`, which sorts before the ISO-coded `<cc>-<sub>-<place>` place slugs,
so the slug-sorted listing reads framework → indices → places) is specified in the
proposal §4d.

## Rationale

Full design, scope boundaries, migration map, and slug grammar:
`/srv/foundry/clones/project-editorial/.agent/audit/2026-07-02-category-redesign/proposal-projects.md`.
