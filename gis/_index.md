---
schema: foundry-doc-v1
title: "Maps and Data"
slug: gis
category: gis
type: topic
content_type: topic
quality: complete
short_description: "The maps and data behind the analysis: where the spatial data comes from, what it covers, and the methods used to screen markets and evaluate sites."
index_type: thematic
index_scope: gis
status: active
bcsc_class: current-fact
language_protocol: PROSE-TOPIC
last_edited: 2026-08-26
editor: pointsav-engineering
paired_with: _index.es.md
---

Maps and Data covers the spatial data behind the analysis: where it comes from, what it covers, and the methods used to screen markets and evaluate sites.

<!-- START-HERE-HIGHLIGHT: engine reads this block to render the single "start here" card (reuses the existing cluster-card--start-here component). Do not add more than one. -->

**Start here:** [[gis-data-overview|Data Overview]]

<!-- END-START-HERE-HIGHLIGHT -->

## Data Overview and Sources

[[gis-data-overview|Data Overview]] is the entry point — an orientation to the location intelligence clusters, co-location tiers, and the tile pipeline that turns raw spatial data into a scored map. [[poi-data-schema|POI Data Schema]] and [[regional-name-resolution-architecture|Regional Name Resolution]] cover how individual points of interest and cluster labels are built from OpenStreetMap and Overture Maps Foundation sources. [[trade-area-data-sources|Trade Area Data Sources]] and [[spend-population-provenance|Spend and Population Provenance]] document where the population and spend estimates behind every trade area figure originate.

<!-- AUTO-GENERATED MEMBERSHIP: DO NOT EDIT BELOW — regenerate from index_group: data-overview-and-sources -->
- [[gis-data-overview]] — An orientation to the platform's data layers: location intelligence clusters, co-location tiers, and the GIS tile pipeline.
- [[poi-data-schema]] — The POI data schema defines record structures for location data ingested from OpenStreetMap and Overture Maps Foundation, normalized into a unified JSONL format before cluster analysis. Wikidata QIDs serve as the primary chain identifier, and parent-child sub-location models handle co-branded ancillary services.
- [[regional-name-resolution-architecture]] — Each co-location cluster is labelled with a human-readable regional name — a North American Metropolitan Area, a European NUTS-3 region, a Mexican municipio, a Canadian Census Subdivision. That name is the output of a layered offline reverse-geocoding pipeline that draws from a stack of open boundary datasets without requiring external API calls.
- [[trade-area-data-sources]] — Population estimates from WorldPop 2026 and annual per-capita spend proxies from national household surveys underpin the trade area statistics for each co-location cluster.
- [[spend-population-provenance]] — Provenance chain behind catchment population and spend estimates — WorldPop rasters, H3 aggregation, and per-capita multipliers, with their stated weaknesses.
<!-- END AUTO-GENERATED -->

## Coverage Expansion

[[nordic-uk-coverage|Nordic and UK Coverage]] and [[uk-eu-food-retail-coverage|UK/EU Food-Retail Coverage]] record when and how new countries and chain categories entered the dataset.

<!-- AUTO-GENERATED MEMBERSHIP: DO NOT EDIT BELOW — regenerate from index_group: coverage-expansion -->
- [[nordic-uk-coverage]] — How Norway, Sweden, and the United Kingdom entered the co-location intelligence dataset through three Alpha-tier chain promotions in May 2026.
- [[uk-eu-food-retail-coverage]] — The co-location index distinguishes between chains that participate in cluster scoring — anchors, hardware, warehouse — and chains that appear on the map as supporting context without affecting cluster grades. The Food family is the latter. This article documents United Kingdom and European Union food-retail coverage as of the May 2026 expansion.
<!-- END AUTO-GENERATED -->

## Site and Transaction Integration

[[site-ledger-integration|Site Ledger Integration]] binds each physical construction site to an isolated digital archive container, maintaining immutable audit records from groundbreak through commissioning. [[transaction-summary-report-protocol|The Transaction Summary Report Protocol]] advances shortlisted Development Site candidates from geographic scoring to Independent Director review.

<!-- AUTO-GENERATED MEMBERSHIP: DO NOT EDIT BELOW — regenerate from index_group: site-and-transaction-integration -->
- [[site-ledger-integration]] — Operational link binding each physical construction site to an isolated digital archive container, maintaining immutable audit records from groundbreak through commissioning.
- [[transaction-summary-report-protocol]] — Site-approval protocol advancing shortlisted Development Site candidates from geographic scoring to Independent Director review via the Transaction Summary Report.
<!-- END AUTO-GENERATED -->

## See also

- [[site-selection-index|Site Selection]]
- [[markets|The Markets]]
