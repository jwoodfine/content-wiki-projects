# Cleanup Log — media-knowledge-projects

Living record of in-flight cleanup work, open questions, and decisions.
Read at session start. Update when meaningful cleanup occurs.

Last updated: 2026-07-09.

---

## Active issues

### Per-article content-licence footer inconsistency (flagged, not fixed)

`grep -rl "creativecommons.org/licenses/by-nd/4.0"` returns only 4 of ~183 articles;
`grep -rl "creativecommons.org/licenses/by/4.0"` (plain CC BY, no-derivatives clause)
returns 34. The remaining ~145 articles carry no per-article licence footer at all.
This predates the 2026-07-09 site-wide policy note (below) and was not introduced by
it — surfaced here as a follow-up cleanup item, not actioned in this session (a
34-file mass edit reclassifying an existing licence declaration is a separate,
larger correctness call than adding a new site-wide note). Compare
`media-knowledge-corporate`, which already had 26 of 28 articles on `by-nd/4.0`
before this session (2026-05-25 "Institution quality pass" fixed a `by/4.0` →
`by-nd/4.0` defect there) — `media-knowledge-projects` never received the
equivalent per-article correction pass. Flagged to Command by mailbox
2026-07-09; recommend a dedicated future sweep to bring per-article footers into
line with the site-wide CC BY-ND 4.0 policy now stated in
`important-information.md` / `disclaimers.md`.

---

## Recently closed

### 2026-07-09 — bim-token-* / bim-objects-* consolidation: confirmed already resolved, no action needed

Backlog item (originally logged 2026-07-03) flagged `building-design/bim-token-taxonomy`,
`bim-token-three-layers`, `bim-token-what-it-is` as near-duplicates of `bim-objects-substrate`,
`bim-objects-three-layers`, `bim-objects-what-they-are`. Operator explicitly authorized merging
this 3-pair set this session. Pre-edit history check (`git log --oneline -- building-design/bim-token-*.md
building-design/bim-objects-*.md`) found the merge was **already done** by commit `c3e5d24`
("Follow-on 3/3: consolidate bim-token-* into bim-objects-*", 2026-07-03, Jennifer): all 6
`bim-token-*` files (EN + ES) deleted, unique content folded into the surviving `bim-objects-*`
articles, `redirects.yaml` +13 entries, and a named-competitor violation (Solibri, Archistar,
Revit Family) fixed on the surviving articles in the same pass. Canonical terminology confirmed:
**"BIM Object"** (corpus count 127 vs 33 for "Token" per that commit's own reasoning). Directory
listing confirms no `bim-token-*` files remain. No re-merge performed this session — backlog item
should be considered closed as of `c3e5d24`.

### 2026-07-09 — CC BY-ND 4.0 content-licence policy note added (important-information.md + disclaimers.md, EN/ES)

`3d0ce13` (Peter, 2026-07-09). Closes item 3 of operator decision message
`command-20260706-decisions-journal-important-information-6of7`: "Content licence: CC
BY-ND 4.0, no derivatives... record this as a footer/policy note on the 3 wikis." Added
a **Content licence.** / **Licencia de contenido.** paragraph to `important-information.md`
+ `.es.md` (site-wide band, shown on every page) and a matching `## Licence` / `## Licencia`
section to `disclaimers.md` + `.es.md` (long-form article), placed after the existing
Jurisdiction section in each, mirroring the same placement used in the sibling
`media-knowledge-corporate` repo in the same session. Read-first check before editing:
no existing "CC BY" / "licencia" mention in `important-information.md` or `disclaimers.md`
in this repo (both were license-silent before this change) — see the Active issues entry
above for the separate, pre-existing per-article footer inconsistency this session did
**not** touch.

---

## Open questions

None currently — surface here when editorial decisions are deferred.
