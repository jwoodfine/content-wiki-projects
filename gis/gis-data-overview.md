---
schema: foundry-doc-v1
title: "Data overview — location intelligence and GIS data layers"
slug: gis-data-overview
language: en
category: gis
type: concept
content_type: topic
status: active
last_edited: 2026-07-11
editor: pointsav-engineering
short_description: "An orientation to the platform's data layers: location intelligence clusters, co-location tiers, and the GIS tile pipeline."
cites: []
paired_with: gis/gis-data-overview.es.md
---

The PointSav platform produces and serves geospatial data in two primary forms: a location intelligence cluster dataset covering commercial co-location patterns across multiple countries, and a point-of-interest taxonomy that underlies the cluster algorithm. This article orients readers to those layers and links to the substantive methodology and archetype articles.

## Location intelligence clusters

The cluster dataset groups commercial points of interest into co-location nodes — this article uses a three-tier T1 (anchor) / T2 (developed) / T3 (emerging) vocabulary — using a two-pass DBSCAN algorithm. This tier vocabulary has not been reconciled against the tier naming used elsewhere on this wiki (see [[nordic-uk-coverage]] and related articles); a reader comparing tier labels across articles should treat the naming here as this article's own, not yet a single canonical system. Three archetypes describe distinct commercial patterns: PRO (professional retail co-location), VWH (Urban Fringe — urban logistics and light-manufacturing clusters with no hypermarket anchor), and PKS (parking structures / transit-adjacent commercial).

See [[location-intelligence-archetypes|Location Intelligence Co-location Archetypes]] for a full introduction.

## GIS tile pipeline

Cluster data is compiled into PMTiles and served at `gis.woodfinegroup.com`. The pipeline runs nightly, producing updated archetype GeoJSON files and spatial tile layers. See the Developer Guide Catalog for the nightly rebuild and AEC hazard pipeline guides.

## Methodology articles

- O-D Catchment Methodology — crow-flies origin-destination model and catchment ring rationale
- Catchment Ranking Methodology — combined primary and secondary rank dimensions
- [[co-location-tier-nomenclature|Co-location Tier Nomenclature]] — T1/T2/T3 vocabulary

*This article is a stub. Full content is planned for a future session.*
