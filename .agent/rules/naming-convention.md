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

**2026-07-15 — `research` category retired.** Reversal of the 2026-07-02 decision
above and of `BRIEF-category-redesign-phase-c.md`'s locked decision, ratified by
Command via mailbox reply and operator-confirmed before execution. JOURNAL papers
were never actually seeded into this shelf and never will be — the sovereign-
per-surface JOURNAL model (`BRIEF-journal-research-programme.md`, project-editorial)
routes all JOURNAL content to each product site's own `/research` page instead of
the three media-knowledge wikis. The `research/_index.md`(+`.es.md`) empty shell
is removed; `categories.yaml` drops the `research` entry (11 categories remain,
reordered). No articles existed in this category — zero content lost, zero
redirects needed.

## Rationale

Full design, scope boundaries, migration map, and slug grammar:
`/srv/foundry/clones/project-editorial/.agent/audit/2026-07-02-category-redesign/proposal-projects.md`.
