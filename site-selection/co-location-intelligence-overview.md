---
schema: foundry-doc-v1
title: "Retail co-location intelligence — overview"
slug: co-location-intelligence-overview
category: site-selection
index_group: the-method
type: topic
index_type: thematic
content_type: topic
quality: complete
status: active
audience: customer-woodfine
bcsc_class: current-fact
language_protocol: PROSE-TOPIC
last_edited: 2026-08-26
editor: pointsav-engineering
short_description: "Systematic geographic analysis identifying and classifying retail sites where large-format categories converge within defined catchment radii."
paired_with: site-selection/co-location-intelligence-overview.es.md
cites:
  - overture-maps-cdla-2-0
  - osm-odbl
  - ni-51-102
  - osc-sn-51-721
---

MCorp's co-location intelligence platform classifies commercial nodes across a cross-border network of North American and European retail markets by anchor convergence — the independent co-location of hypermarkets, warehouse clubs, and home improvement superstores at the same trade area. Each node is validated not by analyst forecasts, but by the independent capital commitments of the retailers who located there. Convergence is measured per the [[co-location-methodology|co-location methodology]] and classified by the [[co-location-ranking-system|deterministic ranking system]]; the population and spend inputs are documented in [[trade-area-data-sources|trade-area data sources]] and the geographic policy in the [[about-regional-markets-system|regional market matrix]].

The platform is operated at [gis.woodfinegroup.com](https://gis.woodfinegroup.com).

## Strategic objective

Large-format retailers do not locate arbitrarily. Supercenter operators, warehouse clubs, and home improvement superstores each independently apply capital-intensive site selection criteria — traffic counts, household income density, road-network accessibility, and competitive positioning. When two or three such operators converge on the same node within a given corridor, that convergence signals a validated commercial location: one where multiple independent parties have independently committed capital to serve the same trade area. The qualifying [[co-location-anchors|anchor]] adjacency requirement is binary, not a matter of degree.

The co-location intelligence system identifies and classifies those nodes using a deterministic predicate-gate model. The output is a tiered index of sites — Regional, District, Local, Fringe — which can be filtered by region, country, and secondary radius.

## Geographic coverage and scale

As of the most recent full processing run (2026-08-06), the platform evaluates co-location clusters across 24 countries spanning North America and Europe, providing a cross-border view of retail density and commercial defensibility. Country coverage expands as new chain data is ingested; the live GIS platform always reflects current coverage, and the table below is a dated snapshot verified against that same run.

| Region | Countries | Anchor operators |
|--------|-----------|-----------------|
| United States | US | Walmart, Target, IKEA, The Home Depot, Costco |
| Canada | CA | Walmart, IKEA, Real Canadian Superstore |
| Mexico | MX | Walmart, IKEA, The Home Depot |
| Spain | ES | IKEA, Carrefour, Alcampo, E.Leclerc |
| Italy | IT | IKEA, Carrefour, Ipercoop, Bennet |
| France | FR | Carrefour, Auchan, IKEA, Leroy Merlin, Costco |
| Germany | DE | Kaufland, IKEA, OBI, Hornbach |
| United Kingdom | GB | Tesco, Sainsbury's, IKEA, B&Q |
| Netherlands | NL | Albert Heijn XL, IKEA, Praxis |
| Austria | AT | Interspar, IKEA, Hornbach |
| Portugal | PT | Continente, Auchan, IKEA, Leroy Merlin |
| Greece | GR | IKEA, Sklavenitis, Praktiker |
| Poland | PL | IKEA, Carrefour, E.Leclerc, Auchan |
| Czechia | CZ | Kaufland, IKEA, OBI |
| Hungary | HU | Tesco, Auchan, IKEA, OBI |
| Slovakia | SK | Kaufland, IKEA, OBI |
| Romania | RO | Carrefour, IKEA, Dedeman |
| Bulgaria | BG | Kaufland, IKEA, Praktiker |
| Croatia | HR | Kaufland, Interspar, Super Konzum, Bauhaus |
| Nordics | SE · NO · DK · FI · IS | IKEA, Bilka, Prisma, K-Citymarket, OBS Coop |

## Data foundations

The platform integrates three primary data sources to ensure high-fidelity spatial analysis:

1.  **Business location data (Retail Operators):** Sourced from OpenStreetMap contributors, filtered by canonical brand Wikidata identifiers to ensure consistent brand-family matching across borders. As of 2 May 2026, the dataset contains 31,219+ individual retail locations across 60+ chains.
2.  **Place data (Civic Infrastructure):** Hospital and medical center records sourced from the Overture Maps Foundation Places dataset (2026-04-15 release). This tertiary layer provides the civic context required for the Regional and District tier gates.
3.  **Transportation data (Logistics Support):** Aviation facility records from Overture Maps Foundation, retained for future tertiary scoring dimensions.

*Material assumptions for current dataset counts include the continued availability of OpenStreetMap and Overture Maps Foundation data under their respective licenses (ODbL and CDLA Permissive 2.0). [osm-odbl] [overture-maps-cdla-2-0]*

## Site index and tier classification

Every scored node is classified into one of four tiers — **Regional**, **District**, **Local**, **Fringe** — covered by the [[co-location-tier-system|co-location tier system]]. A cluster earns its tier by clearing predicate gates on anchor composition, national catchment rank, civic infrastructure, and spatial non-overlap, described in full in the [[catchment-ranking-methodology-v3|V3 catchment ranking methodology]].

Current site counts by tier and country are published live on the GIS platform rather than restated here; a wiki snapshot goes stale between data-refresh cycles, while the platform updates on every processing run.

## Interactive surface

The Geographic Information System (GIS) platform renders the tiered site index as an interactive map at [gis.woodfinegroup.com](https://gis.woodfinegroup.com). The interface supports real-time filtering by cluster tier and catchment radius (1 km, 2 km, or 3 km).

The platform is updated when new chain data is ingested or when tier assignment is recalibrated. All dataset counts and version identifiers are displayed in the platform header to ensure operational transparency.

## Provenance
- **Verification:** Country coverage verified against the GIS platform's live cluster dataset and its most recent full processing run, as of 2026-08-06.
- **Forward-looking disclosure:** European tertiary data expansion targets are intended outcomes, labeled per [ni-51-102].

## See also
*   [[co-location-methodology]]
*   [[co-location-ranking-system]]
*   [[co-location-tier-system]]

## References

- [Retail park](https://en.wikipedia.org/wiki/Retail_park) — Wikipedia, accessed 2026-06-14
- [Big-box store](https://en.wikipedia.org/wiki/Big-box_store) — Wikipedia, accessed 2026-06-14

---

*Copyright © 2026 Woodfine Capital Projects Inc. Licensed under [Creative Commons Attribution-NoDerivatives 4.0 International](https://creativecommons.org/licenses/by-nd/4.0/).*
