---
schema: foundry-doc-v1
title: "Pure-predicate catchment ranking methodology (V3)"
slug: catchment-ranking-methodology-v3
category: site-selection
index_group: site-scoring-and-trade-areas
type: topic
content_type: topic
quality: complete
status: active
audience: customer-woodfine
bcsc_class: current-fact
language_protocol: PROSE-TOPIC
last_edited: 2026-08-26
editor: pointsav-engineering
short_description: "The V3 tier-assignment methodology assigns each co-location cluster to one of four tiers using binary predicate gates — composition, national catchment rank, civic classification, and spatial overlap — replacing the prior composite-score system (May 2026)."
paired_with: site-selection/catchment-ranking-methodology-v3.es.md
cites:
  - osm-odbl
  - overture-maps-cdla-2-0
  - ni-51-102
  - osc-sn-51-721
---

The [[co-location-methodology|co-location]] tier system assigns each cluster to one of four tiers — Regional, District, Local, or Fringe (labelled per the [[co-location-tier-nomenclature|tier nomenclature]]) — using binary predicate gates rather than a composite score. A cluster must pass every gate in a tier's gate set to qualify for that tier; partial scores do not accumulate. This methodology describes the current implementation, introduced in May 2026. It complements the [[co-location-ranking-system|deterministic ranking system]] and draws its trade-area inputs from the [[od-catchment-methodology|distance-band methodology]] and the [[trade-area-data-sources|trade-area data sources]].

## Why Predicate Gates Replace Composite Scores

The prior V2 system assigned tiers by summing a base score, count bonus, diversity bonus, civic depth term, and overlap penalty. The resulting composite score was internally consistent but difficult to explain: a cluster could reach Tier 2 via a high diversity bonus even if it lacked the population catchment and civic infrastructure that the tier was intended to signal.

Binary gates make the qualification criteria explicit and independently verifiable. A Regional cluster must have national-scale population reach, a specific anchor composition, regional hospital access, and spatial independence from stronger clusters. None of these requirements are satisfied by proxy.

## Population Catchment Ranks

Catchment population is computed using a fixed-resolution geographic grid over crow-flies distance, per the [[od-catchment-methodology|distance-band methodology]]. Two zones are defined for each cluster:

- **Primary zone**: all grid cells within 35 km of the cluster anchor
- **Secondary zone**: all grid cells between 35 km and 150 km of the cluster anchor

Population totals draw from WorldPop 2026 gridded population data, aggregated to the same grid used for catchment analysis (see [[trade-area-data-sources|trade-area data sources]]). Clusters are ranked within their ISO country on each of eight axes: primary population, secondary population, primary grocery spend, secondary grocery spend, primary hardware spend, secondary hardware spend, primary wholesale spend, and secondary wholesale spend.

The rank is expressed as a percentile fraction within the cluster's country: a lower value indicates a higher relative reach. This puts countries with very different total cluster counts on a common scale.

Spend estimates are derived from per-capita household spending surveys (BLS for the United States, StatCan for Canada, Eurostat HBS for European Union member states, INEGI for Mexico) applied to the population grid, stratified by grocery, hardware, and wholesale category shares.

## Tier Gate Definitions

### Tier 1 — Regional

A cluster qualifies as Regional if all five of the following conditions are true:

1. **Composition**: The cluster contains a Warehouse anchor (Costco, Sam's Club, Makro, or equivalent) and a Hypermarket anchor (Walmart, Target, Mercadona, Tesco, Sainsbury's, or equivalent); or it contains a Lifestyle anchor (IKEA) and a Hypermarket anchor.
2. **Primary catchment**: The cluster's primary-population rank within its country must be among the highest in the country — this is the tightest primary-catchment bar of any tier.
3. **Secondary catchment**: The cluster's secondary-population rank within its country must also be well above the country median, though the bar here is looser than the primary-catchment gate.
4. **Civic — regional hospital**: At least one hospital classified as "regional" by the OSM-derived civic classification is present within a defined civic-proximity ring around the cluster anchor.
5. **Spatial independence**: The overlap between this cluster's trade-area disk and the equivalent disk of any cluster in the same country with a higher primary-population rank must stay low — Regional carries the strictest independence bar of any tier.

### Tier 2 — District

A cluster qualifies as District if all five of the following conditions are true:

1. **Composition**: The cluster contains a Hypermarket anchor and a Hardware anchor (Home Depot, Lowe's, Leroy Merlin, or equivalent) or a Warehouse anchor.
2. **Primary catchment**: The cluster's primary-population rank within its country must clear a materially lower bar than Regional, but still well above the country median.
3. **Spend reach**: The cluster's rank within its country on at least one of grocery spend, hardware spend, or wholesale spend must also clear that same bar.
4. **Civic — hospital present**: At least one hospital classified as "regional" or "district" is present within the civic-proximity ring.
5. **Spatial independence**: The overlap between this cluster's trade-area disk and the equivalent disk of any Regional cluster in the same country is allowed to run somewhat higher than the Regional-tier limit, but is still bounded.

### Tier 3 — Local

A cluster qualifies as Local if all three of the following conditions are true:

1. **Composition**: The cluster contains a Hardware or Warehouse anchor.
2. **Primary catchment**: The cluster's primary-population rank within its country must be at or above the country median.
3. **Civic — any hospital**: At least one hospital of any classification is present within the civic-proximity ring.

### Tier 4 — Fringe

A cluster that does not qualify for Regional, District, or Local is classified as Fringe. A Fringe cluster may still contain significant retail co-tenancy; the classification indicates that one or more required conditions for Local or above were not met.

## Overlap Measurement

The spatial independence gate measures overlap between two clusters' trade-area disks, each drawn at a fixed radius held constant across tiers, using a standard geometric intersection-over-union (IoU) calculation — the area shared by both disks, relative to their combined area. Two clusters whose centroids are far enough apart that their disks no longer overlap are treated as fully independent (IoU = 0); as the disks increasingly overlap, IoU rises, and the weaker cluster's tier is capped accordingly.

## Civic Classification

Hospital and university tier assignments are produced from OpenStreetMap data. Hospitals are classified as `regional` (major general hospitals with emergency departments), `district` (secondary hospitals and specialist centres), or `clinic` (general practice and walk-in clinics). Clinics do not contribute to Regional or District civic gates.

## Threshold Summary

The catchment and spend bars tighten moving from Local up through Regional, and the spatial-independence allowance tightens correspondingly — Regional clusters face both the highest catchment bar and the strictest overlap limit, while Local clusters face the lowest catchment bar and no explicit overlap gate. The civic-ring radius and the spatial-independence disk radius are each held constant across tiers.

Thresholds are intentionally coarse — designed to distinguish nationally significant clusters from local nodes, not to finely rank within a tier. Refinement is planned for a future update as additional catchment data becomes available.

## See Also

- [[co-location-tier-nomenclature]]
- [[co-location-methodology]]
- [[co-location-ranking-system]]

## References

*Hospital, university, and retailer location data used to derive cluster catchments is sourced from OpenStreetMap contributors and licensed under the Open Database Licence (ODbL). OpenStreetMap data © OpenStreetMap contributors.*
