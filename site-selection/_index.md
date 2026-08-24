---
schema: foundry-doc-v1
title: "How We Choose Sites"
slug: site-selection-index
category: site-selection
type: topic
content_type: topic
quality: complete
short_description: "The method behind near Power Centres: the retail anchors, catchment and cluster analysis, scoring, and the tests a site must pass before land is bought."
index_type: thematic
index_scope: site-selection
status: active
bcsc_class: current-fact
language_protocol: PROSE-TOPIC
last_edited: 2026-08-24
editor: pointsav-engineering
paired_with: _index.es.md
---

How We Choose Sites covers the method behind "near Power Centres" — the discipline that decides where a building goes before land changes hands.

<!-- START-HERE-HIGHLIGHT: engine reads this block to render the single "start here" card (reuses the existing cluster-card--start-here component). Do not add more than one. -->

**Start here:** [[co-location-intelligence-overview|Retail Co-Location Intelligence]]

<!-- END-START-HERE-HIGHLIGHT -->

## The Method

[[co-location-intelligence-overview|Retail Co-Location Intelligence]] is the entry point: systematic geographic analysis that ranks sites by where large-format national retailers converge. [[co-location-methodology|Co-Location Methodology]], [[co-location-strategy|Co-Location Strategy]], and [[co-location-investment-thesis|the Co-Location Investment Thesis]] set out the deterministic framework, the site-positioning logic, and the underlying investment case in turn. [[power-centre-co-location-thesis|The Power Centre Co-Location Thesis]] and [[institutional-retail-halo|the Institutional Retail Halo]] describe how proximity to an operating Power Centre transfers necessity-retail demand stability onto adjacent office space. [[power-centre-land-availability|Power Centre Land Availability]] covers where Woodfine's Development Sites come from, and [[co-location-convergence-thesis|the Co-Location Convergence Thesis]] connects that land-sourcing method to extended-hours professional occupancy and the live/work/play shift in shopping-centre design. [[location-intelligence-strategy|Location Intelligence Strategy]] and [[location-intelligence-archetypes|Location Intelligence Archetypes]] cover the platform's flat-file, offline-first architecture and the three co-location archetypes a site can belong to.

<!-- AUTO-GENERATED MEMBERSHIP: DO NOT EDIT BELOW — regenerate from index_group: the-method -->
- [[co-location-intelligence-overview]] — Systematic geographic analysis identifying and ranking retail sites where large-format categories converge within defined catchment radii.
- [[co-location-methodology]] — A deterministic spatial-analysis framework that ranks commercial real-estate nodes by the objective convergence of independent, capital-intensive retail operators — independent corroboration in place of market sentiment.
- [[co-location-strategy]] — The strategy of positioning professional centres adjacent to national retail anchors to transpose retail resilience onto office demand.
- [[co-location-investment-thesis]] — The investment thesis that commercial nodes where institutional-grade retailers converge within defined catchment radii present objectively verifiable, superior site characteristics.
- [[power-centre-co-location-thesis]] — Site-selection discipline requiring Qualified Investment sites to co-locate with operating Power Centre anchors, aligning development to proven National Retailer Rollout Programs.
- [[institutional-retail-halo]] — Economic thesis that co-location with grocery-anchored Power Centres transfers the cash-flow stability of necessity retail to adjacent Woodfine professional office space.
- [[power-centre-land-availability]] — Woodfine's land-sourcing thesis: the excess parking Power Centre owners reserve against future National Retailer demand is frequently underutilized and available for purchase.
- [[co-location-convergence-thesis]] — Three trends converge at a Power Centre — live/work/play shopping-centre design, underutilized parking land, and a shortage of professional leasable space — and Woodfine's professional-hours tenancy is built to capture each of them.
- [[location-intelligence-strategy]] — The strategic and architectural frame for the platform's Location Intelligence substrate: a flat-file open-GIS approach that lets customers own their location data end-to-end, running offline, without ongoing per-seat or per-request vendor costs.
- [[location-intelligence-archetypes]] — Three co-location archetypes — Retail Centres (PRO), Urban Fringe (VWH), and Commuter (PKS) — identifying distinct commercial clustering patterns across 17 countries in North America and Europe.
<!-- END AUTO-GENERATED -->

## Anchors and Tenants

[[power-centres|Power Centres]] are the retail hubs a site is measured against, and [[co-location-anchors|Co-Location Anchors]] defines the large-format national retailers whose presence qualifies a commercial node. [[co-location-target-hierarchy|The Target Hierarchy]] and [[co-location-tier-nomenclature|Tier Nomenclature]] rank a site's retail neighbours into Primary, Secondary, and Tertiary targets under the four ICSC-aligned tier labels. [[national-tenants|National Tenants]] and [[retail-brand-family-taxonomy|the Retail Brand Family Taxonomy]] classify the occupiers and chains that anchor building credibility, and [[retail-centres|Retail Centres (PRO)]] is the base map product — neighbourhood centres anchored by grocery, pharmacy, bank, and casual dining.

<!-- AUTO-GENERATED MEMBERSHIP: DO NOT EDIT BELOW — regenerate from index_group: anchors-and-tenants -->
- [[power-centres]] — Retail hubs anchored by multiple big-box national retailers, serving as the primary site-selection anchors for Woodfine co-location deployments.
- [[co-location-anchors]] — Large-format national retailers whose verified presence within defined proximity thresholds is the binary qualifying criterion for commercial node inclusion.
- [[co-location-target-hierarchy]] — Three-tier target classification in Woodfine's co-location dataset — Primary (Walmart Supercentre), Secondary (Home Depot, Costco), Tertiary (universities, medical centres).
- [[co-location-tier-nomenclature]] — The four tier labels — Regional, District, Local, Fringe — visible on the co-location map follow the International Council of Shopping Centres retail property hierarchy, providing a nomenclature that carries meaning independently of the platform itself. Sprint 17 (May 2026) introduced both the ICSC labels and the V3 pure-predicate tier engine.
- [[national-tenants]] — Revenue-driving professional occupiers — academic, medical, and civic — whose institutional identity anchors building credibility and stabilizes the mix-of-use tenant composition.
- [[retail-brand-family-taxonomy]] — Every retail location on the co-location map carries a brand family classification that determines how the location is displayed and, for some families, whether it contributes to cluster scoring. The taxonomy was designed around the anchor types used in the co-location methodology while remaining extensible to the full range of ingested operators.
- [[retail-centres]] — Retail Centres (PRO) are neighbourhood commercial centres anchored by grocery, pharmacy, bank, and casual dining — one of three Location Intelligence co-location archetypes, and the base map product for the site-selection dataset.
<!-- END AUTO-GENERATED -->

## Scoring and Clustering

[[co-location-cluster-formation|Cluster Formation]] and [[cluster-deduplication-threshold|the Deduplication Threshold]] describe how a qualifying anchor becomes a candidate cluster and how overlapping candidates are resolved. [[co-location-ranking-system|The Ranking System]], [[co-location-tiering-scoring|Tiering and Scoring]], and [[catchment-ranking-methodology-v3|the V3 Catchment Ranking Methodology]] set out the deterministic scoring algorithm and its current binary-predicate tier engine. [[geographic-co-location-methodology|Geographic Co-Location Methodology]] and [[geometric-site-selection-national-tenancy|Retail Anchor Co-Location as a Spatial Indicator]] cover the continental-scale cluster framework behind the method. [[od-catchment-methodology|O-D Catchment Methodology]] and [[trade-area-methodology|Trade-Area Methodology]] define the primary and secondary trade areas — and the honest limits of straight-line catchment measurement — that scoring runs against.

<!-- AUTO-GENERATED MEMBERSHIP: DO NOT EDIT BELOW — regenerate from index_group: scoring-and-clustering -->
- [[co-location-cluster-formation]] — The pipeline step that converts each qualifying anchor store into a candidate co-location cluster; overlapping candidates from a single trade area are resolved by deduplication before ranking inputs are aggregated.
- [[cluster-deduplication-threshold]] — The co-location index pipeline deduplicates overlapping clusters that represent the same commercial zone using a fixed, tightly-set proximity threshold, retaining the cluster with the higher secondary operator count. An earlier, substantially wider threshold was found to suppress legitimately distinct commercial nodes in dense suburban corridors.
- [[co-location-ranking-system]] — Deterministic 12-rank scoring algorithm evaluating retail co-location sites by named-anchor convergence across defined catchment radii.
- [[co-location-tiering-scoring]] — Tier scoring for co-location clusters — what the T1–T3 composition tiers measure, the DBSCAN parameters that form clusters, and what the tiers do not claim.
- [[catchment-ranking-methodology-v3]] — The V3 tier-assignment methodology assigns each co-location cluster to one of four tiers using binary predicate gates — composition, national catchment rank, civic classification, and spatial overlap — replacing the prior composite-score system introduced in Sprint 17 (May 2026).
- [[geographic-co-location-methodology]] — Five-degree cluster system scoring retail node proximity from Primary, Secondary, and Tertiary target co-occurrence to rank development sites by anchor strength.
- [[geometric-site-selection-national-tenancy]] — A continental-scale cluster analysis framework identifying retail anchor co-location clusters and their tier classification across thirteen countries.
- [[od-catchment-methodology]] — Trade areas for each co-location cluster are defined using crow-flies H3 hexagonal distance rings: a 35 km primary zone and a 35–150 km secondary zone, both computed from WorldPop 2026 population data.
- [[trade-area-methodology]] — Honest labelling of demand geography — why straight-line distance bands are never called catchments, and the planned move to isochrones and observed origins.
<!-- END AUTO-GENERATED -->

## Before Land Is Bought

[[zoning-acquisition-rules|Zoning Acquisition Rules]] requires confirmed zoning on every parcel before purchase. [[asset-evaluation-protocol|The Asset Evaluation Protocol]] sets tier score as the entry criterion and independent GIS analysis as the verification method a candidate site must clear.

<!-- AUTO-GENERATED MEMBERSHIP: DO NOT EDIT BELOW — regenerate from index_group: before-land-is-bought -->
- [[zoning-acquisition-rules]] — Pre-purchase verification requirements ensuring every parcel acquired has confirmed zoning for the intended development, eliminating speculative land banking.
- [[asset-evaluation-protocol]] — How the co-location ranking matrix drives Woodfine's commercial asset acquisition targeting: tier score as the entry criterion, independent GIS analysis as the verification method.
<!-- END AUTO-GENERATED -->

## See also

- [[markets|The Markets]]
- [[gis|Maps and Data]]
