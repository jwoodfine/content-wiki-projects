# Cleanup Log — media-knowledge-projects

Living record of in-flight cleanup work, open questions, and decisions.
Read at session start. Update when meaningful cleanup occurs.

Last updated: 2026-07-28.

---

## Active issues

### 17 ES articles' broken `.es`-suffixed slug — FIXED 2026-07-28

Found as part of a corpus-wide sweep triggered by the same bug found in
`media-knowledge-documentation` (91 files there — see that repo's cleanup-log.md for
the full technical writeup, confirmed against `app-mediakit-knowledge/src/content/
walk.rs`'s actual resolve/fallback logic). 17 files here had `slug: <name>.es` instead
of `slug: <name>` — the engine indexes documents by `(slug, lang)` and falls back to
English on a lookup miss, so Spanish readers of these 17 articles were silently served
the English version. Fixed: stripped the trailing `.es`, verified 0 remaining mismatches
against EN siblings corpus-wide. Frontmatter-only change, no prose touched.
`media-knowledge-corporate` was checked and is clean (0 files affected).

### ~145 articles carry no per-article licence footer at all (not fixed)

Surfaced while closing the `by/4.0` → `by-nd/4.0` mismatch below: of ~183 articles, only
38 now carry any per-article licence footer (the 34 just fixed + 4 already correct). The
remaining ~145 have none. Site-wide policy (`important-information.md`/`disclaimers.md`)
covers the gap in aggregate, but adding ~145 per-article footers from scratch is a much
larger, separate correctness call than the 34-file mechanical fix just done — not
actioned this session.

### 2 pages have the license correctly CC BY-ND but with an untranslated English license name in Spanish prose (not fixed)

`disclaimers.es.md` and `important-information.es.md` both correctly link
`creativecommons.org/licenses/by-nd/4.0/` but the visible link text reads "Creative
Commons Attribution-NoDerivatives 4.0 International" (English) inside otherwise-Spanish
prose, rather than "Atribución-SinDerivadas 4.0 Internacional" as used everywhere else.
Pre-existing, not touched by the 34-file batch below (these 2 policy pages weren't in
that grep — they were already on the correct license, just with an untranslated label).
Small, cosmetic, easy follow-up.

---

## Recently closed

### 2026-07-10 — 34-article `by/4.0` → `by-nd/4.0` footer fix: DONE

Closes the item flagged below (2026-07-09) after Command confirmed no reply was needed —
operator authorized the fix directly. Mechanical, well-scoped: license type + URL fixed in
all 34 (`Attribution 4.0 International` → `Attribution-NoDerivatives 4.0 International`,
`/by/4.0/` → `/by-nd/4.0/`), and for `.es.md` files, the license name fully translated to
match the 4 already-correct articles' exact wording ("Licenciado bajo [Creative Commons
Atribución-SinDerivadas 4.0 Internacional]") rather than the mix of untranslated-English
and Spanish-prose-with-English-license-name found across the 34. Commit `d046aae`. The
2 remaining active issues above (145 articles with no footer at all; 2 policy pages with
an untranslated license label) are separate, smaller follow-ups, not part of this fix.

### 2026-07-09 (superseded note) — original flag

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
