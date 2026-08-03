---
schema: foundry-doc-v1
title: "Retail co-location methodology"
slug: co-location-methodology
category: site-selection
type: topic
content_type: topic
quality: complete
status: active
audience: customer-woodfine
bcsc_class: current-fact
language_protocol: PROSE-TOPIC
last_edited: 2026-07-11
editor: pointsav-engineering
short_description: "A deterministic spatial-analysis framework that ranks commercial real-estate nodes by the objective convergence of independent, capital-intensive retail operators — independent corroboration in place of market sentiment."
paired_with: site-selection/co-location-methodology.es.md
cites:
  - ni-51-102
  - osc-sn-51-721
  - planetizen-retail-clusters
  - osm-odbl
---

Retail development capital is usually committed on comparables and analyst sentiment. Whether independent demand actually converges at a site — the reason it should succeed — is assumed rather than measured.

The Woodfine co-location methodology measures it. It ranks development sites by the objective convergence of independent, capital-intensive retail operators, not by market sentiment or analyst forecasts. The framework is operationalised by the [[co-location-ranking-system|deterministic ranking system]] and exposed to platform users via the [[co-location-intelligence-overview|co-location intelligence overview]].

A node qualifies when a hypermarket, a warehouse club, and a home-improvement superstore have each independently committed capital within 1.0 to 3.0 km of one another. Each operator runs its own site-selection process; convergence is independent corroboration, not a single forecast. The qualification logic, [[co-location-cluster-formation|cluster formation]], and the [[co-location-anchors|anchor]] adjacency requirement are the three structural inputs to the index.

For a capital allocator the index is a defensive filter: it prioritises the sites where several parties have independently validated the trade area. This article covers the Named-Anchor Model, the three operator tiers, and the five quality tiers; sibling articles describe the [[od-catchment-methodology|O-D catchment methodology]], the [[trade-area-data-sources|trade-area data sources]], and the [[catchment-ranking-methodology-v3|catchment ranking methodology]].

## The Named-Anchor Model

Large-format retailers apply rigorous, data-driven site-selection criteria before committing capital to a market. When several independent operators converge on the same geographic node, that convergence signals a validated commercial corridor — a location where multiple parties have independently confirmed the trade area's strength.

The methodology sorts these operators into three tiers, by commercial function and foot-traffic contribution.

### Primary Targets — the anchor

The foundational requirement for any evaluated node; the core traffic driver.

- **North America:** Walmart Supercentre.
- **Europe:** IKEA, as the operational baseline.

### Secondary Targets — commercial support

Complementary large-format operators that validate the trade area's commercial depth. They are evaluated within a strict 1.0 km to 3.0 km catchment radius of the Primary Target.

- **Secondary-1 (hardware):** Home Depot, Lowe's, Leroy Merlin.
- **Secondary-2 (warehouse club):** Costco, Sam's Club, Makro.

### Tertiary Targets — institutional support

Civic and institutional infrastructure that provides a non-cyclical, stable demographic baseline. Evaluated within a 5.0 km catchment radius.

- **Tertiary-A (healthcare):** major hospitals and medical centres.
- **Tertiary-B (higher education):** universities and colleges.

## Quality tiers and site validation

Sites are evaluated on a 12-rank matrix that maps to five quality tiers, separating commodity retail nodes from the rare locations where critical commercial elements converge. The map-facing labels — Regional, District, Local, Fringe — follow the ICSC retail property hierarchy described in [[co-location-tier-nomenclature|tier nomenclature]].

**Correction (2026-08-02):** two defects. (1) The real ICSC shopping-center hierarchy
is Neighborhood/Community/Regional/Super Regional (plus named specialty types) — it
has no "District," "Local," or "Fringe" tier, and only "Regional" is a real ICSC
term. This "follows the ICSC hierarchy" claim is factually wrong. (2) Separately,
this article's own 5-tier matrix cannot be the same system as
[[co-location-tier-nomenclature]]'s 4-label Regional/District/Local/Fringe scheme —
that scheme is assigned by an unrelated predicate-gate mechanism (population
percentile, IoU overlap, civic classification), not this article's Hardware/
Warehouse/Healthcare/Higher-Ed composition matrix. This wiki maintains at least
three unreconciled co-location scoring systems that reuse overlapping tier
vocabulary — this citation conflates two of them. **Flagged, not resolved.**

| Tier | Description | Commercial validation |
|------|-------------|-----------------------|
| ★★★★★ | Tier 5 — Full co-location | All four categories present: hardware, warehouse club, healthcare, higher education |
| ★★★★ | Tier 4 — Strong co-location | Both commercial secondaries plus one tertiary; one institutional dimension absent |
| ★★★ | Tier 3 — Partial co-location | Two categories present: a full secondary pairing, or one secondary with at least one tertiary |
| ★★ | Tier 2 — Limited co-location | One category present: hardware only, or warehouse club with a single tertiary |
| ★ | Tier 1 — Anchor only | Commercial secondaries largely absent: tertiary-only convergence, or warehouse club only |

See [[co-location-ranking-system]] for the complete 12-rank specification, the rank-to-tier mapping, and site counts by tier.

## Strategy and application

The co-location index acts as a defensive filter for capital deployment. By focusing on Tier 4 and Tier 5 nodes, an investor prioritises sites with the highest level of independent capital validation and the strongest multi-format demographic anchors.

The methodology applies consistently across global markets by mapping regional operators to these canonical roles. A planned expansion integrates logistics and transport data to add a fourth dimension to the matrix; that expansion is forward-looking and framed per `[ni-51-102]` and `[osc-sn-51-721]`.

**Correction (2026-08-02):** the matrix already has four non-primary dimensions
(Hardware, Warehouse, Healthcare, Higher Ed) — a planned addition would be a fifth
dimension, not a "fourth." **Flagged, not resolved.**

## See also

- [[co-location-ranking-system]]
- [[co-location-intelligence-overview]]
- [[co-location-anchors]]

## Data sources

Anchor and secondary operator locations are sourced from **OpenStreetMap contributors** under the [Open Database Licence (ODbL)](https://opendatacommons.org/licenses/odbl/). Records are filtered by canonical Wikidata brand identifiers to ensure consistent chain-family matching across borders. The full chain-to-family mapping is documented in [[retail-brand-family-taxonomy]]. [osm-odbl]

## References

- [Retail park](https://en.wikipedia.org/wiki/Retail_park) — Wikipedia, accessed 2026-06-14
- [Big-box store](https://en.wikipedia.org/wiki/Big-box_store) — Wikipedia, accessed 2026-06-14
- [DBSCAN](https://en.wikipedia.org/wiki/DBSCAN) — Wikipedia, accessed 2026-06-14

*OpenStreetMap data © OpenStreetMap contributors, licensed under ODbL.*

---

*Copyright © 2026 Woodfine Capital Projects Inc. Licensed under [Creative Commons Attribution-NoDerivatives 4.0 International](https://creativecommons.org/licenses/by-nd/4.0/).*
