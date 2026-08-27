---
schema: foundry-doc-v1
slug: about-regional-markets-system
title: "Regional Markets intelligence system"
language: en
language_protocol: PROSE-TOPIC
category: markets
index_group: market-coverage
type: reference
content_type: topic
quality: complete
status: active
audience: customer-woodfine
bcsc_class: current-fact
short_description: "Reference article for the co-location analysis system that identifies suburban retail markets in North America and Europe."
paired_with: markets/about-regional-markets-system.es.md
last_edited: 2026-08-26
editor: editorial
---

# Regional Markets Intelligence System

The Regional Markets Intelligence System is a continental-scale geographic analysis framework that identifies suburban retail markets — named suburbs and satellite municipalities lying within commuting distance of major metropolitan centres — defined by the convergence of large-format retail anchors, civic infrastructure, and demographic catchment.

The research addresses a gap in institutional commercial real estate analysis. Major research organisations, including Oxford Economics, CBRE, and Colliers International, produce extensive coverage of primary metro markets: London, Paris, New York, Chicago, Dallas, Toronto, and their immediate urban cores. The suburban ring — the belt of named municipalities 15 to 80 kilometres from a major metro centre — is systematically underanalysed by institutional research. This is where large-format retail, hospital systems, and university campuses co-locate in patterns that function as leading indicators of demographic and economic activity at the sub-metropolitan scale. The Regional Markets dataset is the analytical surface for that suburban ring.

The current dataset spans 7,567 co-location clusters across 24 countries in North America and Europe, classified into three compositional tiers (T1, T2, T3) and aggregated into 4,436 named Regional Markets. The Top 400 is the flagship published output of this system: a curated, editorially-selected subset of roughly 400 markets for each continent. Selection method below.

## Dataset Scope

The current build covers 7,567 co-location clusters across 24 countries on two continents.

| Region | Countries |
|---|---|
| North America | United States, Canada, Mexico |
| Europe — west and south | Spain, Italy, Greece, France, Germany, Portugal, Netherlands, Austria |
| Europe — Nordic | Sweden, Norway, Denmark, Finland, Iceland |
| Europe — central | Poland, United Kingdom, Czechia, Hungary, Slovakia |
| Europe — southeast | Bulgaria, Croatia, Romania |

Cluster counts by tier: **T1 = 1,746** (Regional anchors), **T2 = 2,726** (District anchors), **T3 = 2,021** (Local anchors). The build pipeline draws on four primary data sources.

### Primary data sources

**OpenStreetMap (ODbL licence).** Retail chain locations filtered by Wikidata QID via the Overpass API. The current ingest covers more than sixty chains spanning hypermarkets, hardware superstores, warehouse clubs, electronics retailers, sporting-goods stores, and pharmacies.

**Overture Maps Foundation (CDLA Permissive 2.0).** Civic anchor locations extracted from the Places dataset using the `taxonomy.primary` field. Current coverage includes 27,833 medical and 28,846 higher-education records across the 24 countries.

**Kontur Population 2023 (CC BY 4.0).** A global H3 resolution-8 population hex grid covering all 24 countries; aggregated to H3 resolution-7 (≈1.22 km² per cell) for catchment calculations.

**WorldPop 100-metre raster (2026 release, CC BY 4.0).** Used in combination with per-country spend multipliers from BLS (United States), Statistics Canada, and Eurostat household budget surveys to model grocery, hardware, and wholesale spend potential at the catchment level.

The clustering methodology is a two-pass DBSCAN: a first pass identifies hypermarket and full-anchor cores, a second pass adds peripheral hardware and warehouse-club anchors within a span constraint.

## Co-location Tier System

Each cluster is assigned one of three tiers based on the composition of retail anchors present within the cluster boundary.

| Tier | Label | Composition rule |
|---|---|---|
| **T1** | Regional | Hypermarket + hardware + warehouse-club (or full equivalent across three independent anchor categories) |
| **T2** | District | Hypermarket + hardware (two independent anchor categories) |
| **T3** | Local | Any single qualifying anchor category |

The tier rule is compositional rather than count-based. A site with four co-located hypermarket banners and no hardware or warehouse-club anchor remains T3, because the compositional signal that distinguishes regional draw from local convenience is the presence of *independent* anchor categories, not the count of stores within a single category.

### Span ranking and anchor categories

**Geometric span ranking within tiers.** Within each tier, clusters are ordered by `span_km` — the diameter of the smallest enclosing circle that contains all member anchors. Compact clusters (`span_km` below 2.5) rank ahead of dispersed clusters. A cap is applied to prevent the algorithm from extending an arterial corridor into a single notional cluster.

**Anchor categories.** Six anchor categories are recognised in the current build: `hypermarket`, `hardware`, `warehouse_club`, `electronics`, `sporting_goods`, and `pharmacy`. Hypermarket, hardware, and warehouse-club are weighted as tier-determining; electronics, sporting-goods, and pharmacy are recognised as supporting anchors and contribute to the descriptive fields but do not alter tier classification.

## Regional Markets

A Regional Market is a named municipality or equivalent administrative unit that contains one or more co-location clusters and lies within commuting distance of a major metropolitan centre. Three settlement types are distinguished:

| Type | Distance from major metro | Top 400 status |
|---|---|---|
| **Metro-core** | < 15 km | Excluded from Top 400 (covered by institutional metro-market research) |
| **Suburban-regional** | 15–80 km | Included in the Top 400 (the research gap) |
| **Standalone-secondary** | > 80 km | Excluded from Top 400 (separate analysis category) |

### Suburban-regional band and coherence constraint

The suburban-regional type is the Top 400 pool. Markets closer than 15 km from a major metro centroid are treated as extensions of the metro core. Markets further than 80 km from any major metro centroid are standalone secondary cities that function independently rather than as satellites; they are tracked separately and do not appear in the Top 400. A geographic coherence constraint excludes name-collision aggregations: any settlement whose constituent clusters span more than 200 km is excluded as an administrative artefact rather than a functioning market.

**Total count: 4,436 Regional Markets** (all three types combined). Of these, **2,327 are in North America** and **2,109 are in Europe**.

## Top 400 Qualification Method

The Top 400 Regional Markets list is a curated set of suburban-regional settlements, not a numeric ranking. The set is produced separately for North America and Europe, yielding two lists of 400 markets each, ordered alphabetically rather than by any score. No rank or score field is published for any market. The suburban-regional classification (15–80 km, described above) is a pre-filter: every market in the set is already in the correct proximity band.

### Qualification gates

A market qualifies for the Top 400 by clearing one of three compositional gates, applied to its co-location clusters:

1. **Main gate.** A hypermarket anchor plus at least two of: hardware, price club, lifestyle, electronics, or sport.
2. **Narrower gate.** A hypermarket anchor plus a hardware anchor only, present across at least two distinct clusters.
3. **Isolated-market gate.** The same narrower gate (hypermarket plus hardware, across at least two distinct clusters), applied to markets that are geographically isolated from other qualifying markets.

A composite score exists internally to support selection but is not published and is not a market-facing ranking. It has no bearing on how a market is described in this wiki.

No metro-distance multiplier is applied. Under a previous iteration of the methodology, a distance bonus inadvertently caused standalone secondary cities to outrank genuine suburbs of major metros. The current design separates classification from selection: the 15–80 km filter determines whether a market is eligible for the suburban-regional pool; anchor composition determines whether it qualifies.

The full lists are published separately: see [[atlas-top-400-north-america|Top 400 Regional Markets — North America]] and [[atlas-top-400-europe|Top 400 Regional Markets — Europe]].

## Civic Infrastructure Layer

The civic infrastructure layer adds medical and higher-education anchor presence to the cluster member data. The source is the Overture Maps Foundation Places dataset, queried for the `healthcare` and `higher_education` primary categories.

**Coverage.** 27,833 medical records and 28,846 higher-education records across the 24 countries.

**Encoding.** Civic presence is encoded as a binary flag per cluster: if any cluster member is classified as medical or higher-education, the cluster carries `civic = True`. The Regional Market inherits the civic flag from any constituent cluster. The civic flag is a descriptive dataset field, not a public ranking input.

The civic layer is conceptually distinct from the retail layer. A hospital adjacent to a hypermarket-and-hardware cluster does not turn T2 into T1 — the tier classification is anchor-composition only. The civic flag operates orthogonally as a market-quality signal.

## AEC Data Layers

The AEC (architecture, engineering, construction) data layers add climate, regulatory, and ecological context to each Regional Market and to the surrounding development envelope. Four layers are currently delivered; two further layers are in preparation.

**Delivered layers.**

| Layer | Source | Coverage |
|---|---|---|
| ASHRAE 169-2013 climate zones | ASHRAE standard, US extent | 94.4% of US Regional Markets |
| EU regulatory energy climate zones | Per-country building-energy regulations | Variable — Germany and France near 100%, Spain and United Kingdom partial |
| Köppen-Geiger climate class | Beck et al. 2018 global raster (CC BY 4.0) | 100% of all Regional Markets |
| WWF Ecoregions 2017 | World Wildlife Fund global vector (CC BY 4.0) | 99.5% of all Regional Markets |

**Layers in preparation.**

| Layer | Source | Status |
|---|---|---|
| Seismic peak ground acceleration | USGS (United States) and EFEHR (Europe) | Re-run scheduled for 1 June 2026 |
| Flood hazard | FEMA (United States) and EU JRC | Build scheduled for 31 May 2026 |

## Catchment Model

The catchment model assigns each cluster a primary and secondary trade area defined by crow-flies radius from the cluster centroid.

| Ring | Radius | Role |
|---|---|---|
| Primary | 35 km | Local-residence trade area |
| Secondary | 150 km | Regional draw |

Catchment population and spend are calculated by intersecting these rings with H3 resolution-7 hexagons (≈1.22 km² per cell) populated from Kontur Population 2023 and modelled spend from WorldPop combined with per-country household-budget multipliers.

### Catchment dimensions and mobility catchments

**Catchment dimensions.** Each cluster carries four independent catchment measures: population, grocery spend, hardware spend, and wholesale spend — each based on combined primary and secondary catchment totals. These are descriptive dataset fields, not a published ranking.

**Mobility-derived catchments.** A mobility-defined catchment layer sits alongside the radius-based model. For United States clusters, the US LODES origin-destination employment dataset provides a worker-commute catchment per H3 cell. For Spain, the Ministerio de Transportes (MITMA) mobility dataset provides a parallel surface.

## Forward-Looking Work

Work planned or intended for the next iterations of the system.

**Climate and hazard layer completion.** The seismic peak-ground-acceleration layer and the flood-hazard layer are scheduled for build in May–June 2026. Once delivered, every Regional Market will carry a complete envelope record covering climate zone, ecoregion, seismic design category, and flood-zone designation.

**OLS regression on span_km.** A cluster-level ordinary-least-squares regression of `span_km` against catchment population density, modelled spend, and mobility-derived activity is in preparation. Country fixed effects and an urban-core versus peri-urban interaction term are intended.

**Per-market article surfaces.** Dedicated wiki articles for each of the 400 Regional Markets in the Top-400 list are planned. The articles are intended to combine the data fields described here with locally-resolved narrative drawn from public sources.

**FX normalisation for cross-country spend.** A foreign-exchange normalisation pass on the modelled spend layer is planned, enabling direct comparison of grocery, hardware, and wholesale spend between countries.

---

*Reference data current as of 30 May 2026. Sources: OpenStreetMap contributors (ODbL); Overture Maps Foundation (CDLA Permissive 2.0); Kontur Population 2023 (CC BY 4.0); WorldPop 2026 (CC BY 4.0); Beck et al. 2018 Köppen-Geiger raster (CC BY 4.0); WWF Ecoregions 2017 (CC BY 4.0); US LODES (public domain); Spain MITMA mobility (open data).*

## See Also

- [[regional-market-definition|Regional market definition]]
- [[co-location-methodology|Co-location Methodology]]
- [[co-location-intelligence-overview|Co-location Intelligence Overview]]
- [[od-catchment-methodology|Distance-Band Methodology]]
- [[atlas-top-400-north-america|Top 400 Regional Markets — North America]]
- [[atlas-top-400-europe|Top 400 Regional Markets — Europe]]
- [[development-regions|Development Regions]]
