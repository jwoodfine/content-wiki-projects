---
schema: foundry-doc-v1
title: "Retail co-location ranking system"
slug: co-location-ranking-system
category: site-selection
index_group: scoring-and-clustering
type: topic
content_type: topic
quality: complete
status: active
audience: customer-woodfine
bcsc_class: current-fact
language_protocol: PROSE-TOPIC
last_edited: 2026-08-25
editor: pointsav-engineering
short_description: "The deterministic mechanics behind cluster ranking on the co-location platform — country-relative percentile axes, the overlap test between neighbouring clusters, and the tiebreak order applied within a tier."
paired_with: site-selection/co-location-ranking-system.es.md
---

The Woodfine [[co-location-methodology|co-location methodology]] assigns each cluster's tier through binary predicate gates, not a composite score — no cluster earns a tier by accumulating points toward a threshold. This article covers the mechanics behind those gates: how a cluster's catchment position is measured against its national peers, how competing clusters are compared for overlap, and how clusters are ordered once ranked. The gate definitions themselves — which combination of tests each tier requires — are set out in the [[catchment-ranking-methodology-v3|V3 catchment ranking methodology]]; the tier labels are described in [[co-location-tier-nomenclature|tier nomenclature]].

## Country-relative percentile axes

A cluster's tier depends on where it stands against every other cluster in its own country, not against a fixed global threshold. Each cluster is ranked against its national peers on eight measures: primary and secondary catchment population, and primary and secondary spend across grocery, hardware, and wholesale categories. A cluster's percentile on each axis is its rank divided by the country's total cluster count — a cluster in the top 10% by primary population carries a percentile of 0.10 on that axis.

Two catchment zones feed the population and spend axes: a primary zone within 35 km of the cluster and a secondary zone between 35 km and 150 km, per the [[od-catchment-methodology|O-D catchment methodology]]. Spend estimates draw on national household-spending surveys applied to the same population grid. Ranking within-country, rather than against one global bar, keeps a smaller market's structure intact against a larger one.

These thresholds are intentionally coarse. The system is built to separate nationally significant clusters from local nodes, not to finely rank clusters against one another within a tier.

## The overlap test

A cluster is only credited for its tier when it is not dominated by a stronger neighbour nearby. Overlap between two clusters is measured as the intersection-over-union (IoU) of two equal-radius disks, each 3.0 km, centred on the cluster anchors — the shared area between the disks, relative to their combined area. As two cluster centroids move apart, IoU falls toward zero and the clusters are treated as spatially independent. A cluster whose disk substantially overlaps a stronger cluster's disk is held below the tier its composition and catchment would otherwise earn. Regional carries the strictest overlap limit of any tier, per the [[catchment-ranking-methodology-v3|gate definitions]].

## Ordering within a tier

Clusters that share a tier and a country are ordered by three criteria, applied in sequence: store count within 3.0 km, then primary catchment population, both highest first. The cluster identifier breaks any remaining tie, guaranteeing a deterministic order.

## Provenance

- **Verification:** Ranking mechanics confirmed against the GIS platform's V3 scoring methodology.

## Data Sources

Map and location data © [OpenStreetMap contributors](https://www.openstreetmap.org/copyright) / [ODbL](https://opendatacommons.org/licenses/odbl/).

## See also

- [[co-location-methodology]]
- [[co-location-intelligence-overview]]
- [[catchment-ranking-methodology-v3]]

## References

- [Big-box store](https://en.wikipedia.org/wiki/Big-box_store) — Wikipedia, accessed 2026-06-14
- [DBSCAN](https://en.wikipedia.org/wiki/DBSCAN) — Wikipedia, accessed 2026-06-14

---

*Copyright © 2026 Woodfine Capital Projects Inc. Licensed under [Creative Commons Attribution-NoDerivatives 4.0 International](https://creativecommons.org/licenses/by-nd/4.0/).*
