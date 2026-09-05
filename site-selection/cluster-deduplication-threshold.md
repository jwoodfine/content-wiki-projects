---
schema: foundry-doc-v1
title: "Cluster deduplication threshold"
slug: cluster-deduplication-threshold
category: site-selection
index_group: site-scoring-and-trade-areas
type: topic
content_type: topic
quality: complete
status: active
audience: customer-woodfine
bcsc_class: current-fact
language_protocol: PROSE-TOPIC
last_edited: 2026-09-04
editor: pointsav-engineering
short_description: "The co-location index pipeline deduplicates overlapping clusters that represent the same commercial zone using a fixed, tightly-set proximity threshold, retaining the cluster with the higher secondary operator count."
paired_with: site-selection/cluster-deduplication-threshold.es.md
cites:
  - ni-51-102
  - osc-sn-51-721
---

The [[co-location-methodology|co-location index]] pipeline produces one cluster per [[co-location-anchors|anchor]] store — every qualifying hypermarket, hardware retailer, and warehouse club generates a candidate cluster centred on that store's coordinates, per the [[co-location-cluster-formation|cluster formation]] rules. When two anchors occupy the same commercial zone, the result is two overlapping clusters representing the same trade area. The deduplication step resolves that redundancy. Trade-area inputs to the [[co-location-ranking-system|ranking system]] are aggregated after deduplication runs.

## The same-parking-lot problem

Large commercial zones frequently host two or more anchor-category stores within metres of each other — a home-improvement superstore and a warehouse club sharing a single parking lot is the common case. Without deduplication, both stores produce clusters with nearly identical catchment geometry, co-tenants, and scores. The map displays two concentric rings covering the same zone — neither wrong in isolation, but together misleading about the number of distinct commercial nodes in that corridor.

## Threshold selection

The deduplication step removes any cluster whose anchor store falls within a fixed, tightly-set radius of a higher-ranked cluster anchor already confirmed for retention. The radius is narrow enough that only stores genuinely sharing a single parking lot or immediate building complex are collapsed. Anchors in adjacent strip malls separated by a service road are treated as distinct nodes and retained.

The calibration is deliberately conservative in that direction. A threshold set too wide collapses separately operated commercial blocks — blocks that serve different residential catchments — into a single node, understating the number of distinct sites in a corridor. Suppressing a legitimate node is the more damaging error of the two, because it removes a site from consideration without surfacing that anything was removed.

## Ranking the survivor

When two anchors fall within the threshold distance, the retained cluster is the one with the higher count of co-tenants inside its catchment. Where that count ties, the tiebreak falls to the co-tenant count inside a tighter inner radius. This ensures that the cluster representing the fuller commercial zone — more stores, broader multi-purpose draw — survives, regardless of which anchor happened to be processed first.

## Pipeline effect

Deduplication removes a meaningful share of candidate clusters as same-zone duplicates in a representative pipeline run. The reduction is concentrated in dense commercial corridors where multiple anchor formats co-locate in close proximity. Tier distribution and national rankings are assigned after deduplication runs, so the published counts reflect deduplicated zones only. Current production counts are published in [[about-regional-markets-system|Regional Markets Intelligence System]].

## See also

- [[co-location-methodology]]
- [[co-location-tier-system]]
