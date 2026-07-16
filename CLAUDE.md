@~/Foundry/AGENT.md

# media-knowledge-projects — Repo Guide

> **State:** active | **Last updated:** 2026-06-26
> **Role:** Totebox sub-clone under project-knowledge cluster
> **Workspace AGENT.md takes precedence on conflict.**

---

## Repo scope

Wiki content for the Woodfine Projects knowledge base
(projects.woodfinegroup.com). Articles cover:

- Co-location methodology and ranking system
- Regional site indices (North America, Europe)
- Asset architecture standards
- BIM methodology
- GIS data standards
- Release communications (`comms/` subdirectory)

No project registry, no Cargo workspace.

**Category layout (corrected 2026-07-15 — was stale since the 2026-07-02
Phase C redesign; see `BRIEF-category-redesign-phase-c.md` in
project-editorial).** Canonical source is this repo's own root
`categories.yaml` — read that directly if this table and it ever
disagree again. Eleven categories, all with bilingual MOC pages:

| Category | Scope |
|---|---|
| `buildings/` | What we build — the six Development Classes |
| `building-design/` | How we build — Key Plans, Tiles, fixed floor plates |
| `site-selection/` | How we choose sites — anchors, catchment, co-location scoring (supersedes the old `co-location/` name) |
| `markets/` | The places, ranked — screening universe and market atlas |
| `rollout/` | The Rollout Program — planned country-by-country sequencing |
| `industry/` | The commercial real-estate market generally — rents, cap rates |
| `urban/` | Why places grow — commuters, urban fringe, demographics |
| `architecture/` | Architectural styles and movements |
| `gis/` | Maps and data — spatial-data sourcing and provenance |
| `research/` | Flagship long-form research (JOURNAL never publishes here — see `research`-category retirement in `BRIEF-journal-and-taxonomy-redesign.md`) |
| `reference/` | Glossary and terminology |
| `news/` | Release notes for new datasets/coverage |

No flat `topic-*.md` articles remain — migration to category
directories completed as part of Phase C (2026-07-03). New articles
go directly into the category their subject matter belongs to.
`comms/` subdirectory unchanged.

---

## Commit flow

- Branch: `main`
- Commits via `~/Foundry/bin/commit-as-next.sh "<message>"`
- Stage 6 promotion from Command Session via `~/Foundry/bin/promote.sh`
- Do not `git push` directly — all pushes go through promote.sh

---

## Artifacts produced here

All files are **TOPIC-*** or **COMMS-*** artifacts:
- `topic-*.md` / `topic-*.es.md` → project-editorial gateway → media-knowledge-projects
- `comms/text-*.md` → project-editorial gateway (release communications)

Self-contained content repo — stage directly to this repo; no `drafts-outbound/` needed.

---

## File conventions

- Frontmatter: `schema: foundry-doc-v1`, `language_protocol: PROSE-TOPIC` (EN),
  `TRANSLATE-ES` (ES), `bcsc_class: current-fact`
- All articles: bilingual pair required (`paired_with:` field in both directions)
- Category values: one of the 6 defined categories above (for new articles); legacy `governance` on existing flat articles until migrated
- Slug: inside categories uses bare slug without `topic-` prefix (e.g., `slug: co-location-methodology`); existing flat articles keep `topic-*` slug until migrated

---

## Known gotchas

- `paired_with:` YAML key was missing in 5 ES country index stubs (fixed PJ2 `b138b99`).
  If adding new ES files, double-check `paired_with:` is keyed, not a bare line.
- Comms releases use `text-{topic}-{YYYY-MM}` slug pattern (no `-release` suffix).
- Canada co-location index is `quality: complete` with a full ranked table.
  Other country indices defer ranked tables to gis.woodfinegroup.com.
