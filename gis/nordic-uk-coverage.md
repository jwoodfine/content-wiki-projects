---
schema: foundry-doc-v1
title: "Nordic and UK coverage expansion"
slug: nordic-uk-coverage
category: gis
index_group: coverage-expansion
type: topic
content_type: topic
quality: complete
status: active
audience: customer-woodfine
bcsc_class: current-fact
language_protocol: PROSE-TOPIC
last_edited: 2026-08-25
editor: pointsav-engineering
short_description: "How Norway, Sweden, and the United Kingdom entered the co-location intelligence dataset through three Alpha-tier chain promotions in May 2026."
paired_with: gis/nordic-uk-coverage.es.md
cites:
  - ni-51-102
  - osc-sn-51-721
---

The Woodfine [[co-location-intelligence-overview|co-location intelligence map]] added substantive coverage in Norway, Sweden, and the United Kingdom on May 6, 2026, through the promotion of three hardware chains to the Alpha tier and the first ingest of Norwegian Obs Bygg location data. The qualification logic is the [[co-location-methodology|co-location methodology]] operationalised by the [[co-location-ranking-system|deterministic ranking system]]; chain-to-family mappings are documented in the [[retail-brand-family-taxonomy|retail brand family taxonomy]].

## What Changed

**Note on terminology (added 2026-08-24):** the tier labels in this article — T2 Hub, T3, and the Alpha/Generic chain classification described below — reflect the points-based scoring system that was current on the event date, May 6, 2026. That system was retired platform-wide on 2026-05-16 and replaced with the current predicate-gate tier system (Regional, District, Local, Fringe; see [[gis-cluster-scoring-glossary|the cluster scoring glossary]]). The coverage figures below — store counts, cluster counts, and dates — are unaffected by that change and remain accurate; only the tier vocabulary describing them is historical.

At the time, the platform's tier system classified hardware and warehouse retailers into two groups: Alpha chains, which alone were sufficient to qualify a co-location as a T2 Hub, and Generic chains, which produced only the lowest qualifying tier. Three chains previously held at the Generic level were promoted to Alpha following confirmation of sufficient data coverage. (Map-facing labels follow the ICSC hierarchy described in [[co-location-tier-nomenclature|tier nomenclature]].)

**Bauhaus Sverige** (Sweden) — 40 locations. Bauhaus is the dominant large-format home improvement chain in Sweden. Its national footprint overlaps directly with IKEA's retail corridor presence. Promotion to Alpha immediately activated T2 status at IKEA-adjacent nodes across Stockholm, Gothenburg, Uppsala, and Malmö.

**B&Q** (United Kingdom) — 356 locations. B&Q is the primary mass-market home improvement retailer in Great Britain, operating large-format stores in suburban and edge-of-town retail parks. The chain had been held at Generic pending an OSM re-ingest, which completed with 356 verified locations. Promotion to Alpha unlocked T2 and T3 designations at IKEA nodes across Greater London, the Midlands, and Scotland.

**Obs Bygg** (Norway) — 63 locations. Obs Bygg is the DIY hardware format operated by Coop Norge, Norway's largest retail cooperative. The chain had not previously been ingested due to sparse OpenStreetMap brand tag coverage; a name-prefix ingest query resolved 63 active stores. Obs Coop, the hypermarket format from the same parent, serves as the cluster anchor in Norway — the first time any Norwegian clusters have been scored.

## Coverage Before and After

| Market | T2 Clusters Before | T2 Clusters After |
|---|---|---|
| Norway | 0 | 66 |
| Sweden (1 km radius) | 0 | 4+ |
| United Kingdom (1 km radius) | 0 | 9+ |
| EU total (1 km) | 162 | 229 |

At the time, all new Norwegian clusters carried T2 Hub designation, reflecting the combination of Obs Coop (anchor) and Obs Bygg (alpha hardware) within a 1 km radius — the characteristic footprint of the Coop Norge co-tenancy format. Under the current tier system, the same Obs Coop / Obs Bygg composition feeds the composition gate for District; the actual tier a given cluster now carries also depends on catchment rank and civic presence, which are not restated here.

## Significance

Norway's retail park format is structurally distinct from North American or Central European patterns. The Obs Coop / Obs Bygg co-tenancy is a national standard: Coop Norge deliberately co-locates its hypermarket and DIY formats to anchor retail corridors in mid-sized Norwegian cities. The 66 new T2 clusters represent the first systematic map of this format in the platform.

The B&Q promotion resolves the most significant prior data gap in the UK dataset. With 356 locations verified, the UK cluster set now reflects the actual distribution of IKEA-adjacent retail parks rather than anchor-only nodes.

## See Also

- [[atlas-co-location-index-nordics]] — ranked index of Nordic commercial convergence sites
- [[co-location-ranking-system]] — the current named-anchor ranking model
- [[co-location-methodology]] — the linear-geometry scoring model underlying all rankings
- [[co-location-tier-system]] — the co-location tier system, including European application

---

*reviewed by editorial · last editorial review 2026-06-14*
