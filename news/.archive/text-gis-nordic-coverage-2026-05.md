---
schema: foundry-doc-v1
title: "GIS coverage expansion — Norway, Sweden, United Kingdom (May 2026)"
slug: text-gis-nordic-coverage-2026-05
short_description: "Internal client communication announcing GIS coverage expansion to Norway (66 T2 Hub clusters), material additions in Sweden via Bauhaus Sverige, and 24 confirmed UK clusters — bringing the Europe dataset to 479 scored co-location clusters at 3 km radius."
category: news
type: release-text
content_type: topic
status: archived
archived: 2026-08-24
archived_reason: "Retracted -- carried a literal 'For internal use -- Woodfine client communications' banner and real internal tier thresholds; should never have been published on the public wiki. Track-B integrity review, 2026-08-24."
superseded_by: none
audience: customer-woodfine
bcsc_class: current-fact
last_edited: 2026-07-11
editor: pointsav-engineering
paired_with: text-gis-nordic-coverage-2026-05.es.md
cites:
  - ni-51-102
  - osc-sn-51-721
---

**For internal use — Woodfine client communications**

---

## Norway coverage via Obs Bygg

The Woodfine [[co-location-strategy|co-location]] intelligence platform now covers Norway, with 66 scored retail nodes — the first time Norwegian retail corridors have appeared in the dataset. The expansion reflects the completion of location data for Obs Bygg, the DIY hardware format operated by Coop Norge, and its systematic co-occurrence with Obs Coop hypermarket sites across the country.

## Sweden and United Kingdom additions

Sweden and the [[atlas-united-kingdom|United Kingdom]] also saw material coverage improvements. In Sweden, the addition of Bauhaus Sverige as a qualifying secondary hardware anchor unlocked co-location scoring at IKEA nodes in Stockholm, Gothenburg, and six other metropolitan areas. In the United Kingdom, the confirmation of 356 verified B&Q locations resolved a prior data gap, producing 24 scored nodes at the 3 km radius — including sites near London, Birmingham, and Edinburgh.

**Correction (2026-08-02):** "and six other metropolitan areas" contradicts this
article's own "Key figures" section below, which names exactly four Swedish cities
(Stockholm, Gothenburg, Uppsala, Malmö) — matching the sibling article
[[nordic-uk-coverage]], which confirms the four-city figure for the same event. The
"six other" phrase appears to be the wrong element. **Flagged, not resolved.**

## Dataset totals

The Europe dataset now includes 479 scored clusters at the standard 3 km radius, up from 466.

---

**Key figures (as of May 6, 2026):**

- Norway: 66 T2 Hub clusters (previously: none)
- Sweden: T2 Hub clusters active in Stockholm, Gothenburg, Uppsala, Malmö corridors
- United Kingdom: 24 clusters at 3 km; 11 at 1 km
- Europe total: 479 clusters (3 km); 314 clusters (1 km)
- Global total: 4,237 scored clusters across North America and Europe

---

*All figures reflect OSM-sourced location data ingested through the Overpass API as of May 6, 2026. Cluster counts vary by radius selection (1 km / 3 km) and reflect the V2 scoring methodology (T3 Apex ≥ 700, T2 Hub ≥ 450, T1 Valid ≥ 150).*

**Correction (2026-08-02):** the V2 scoring methodology (T3 Apex/T2 Hub/T1 Valid with
these specific point thresholds) is the Walmart/Home Depot/Costco-anchored system
used for North America ([[geographic-co-location-methodology]],
[[gis-cluster-scoring-glossary]]) — none of those retailers operate in Norway,
Sweden, or the UK. This article's own sibling, [[nordic-uk-coverage]], describes a
different mechanism for this same dataset: a binary Alpha/Generic chain-promotion
system with no numeric point thresholds. Citing the North America methodology here
is a genuine cross-system mismatch, not just loose wording — this wiki maintains
several parallel scoring systems that reuse the same T1/T2/T3 tier labels with
different underlying definitions, and this is the clearest instance found of an
article borrowing the wrong family's citation. **Flagged, not resolved.**
