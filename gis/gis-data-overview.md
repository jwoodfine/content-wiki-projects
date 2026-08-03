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

The cluster dataset groups commercial points of interest into three-tier co-location nodes — T1 (anchor), T2 (developed), T3 (emerging) — using a two-pass DBSCAN algorithm. Three archetypes describe distinct commercial patterns: PRO (professional retail co-location), VWH (vertical warehouse / urban industrial), and PKS (parking structures / transit-adjacent commercial).

**Correction (2026-08-02, verified against canonical `origin/main`):** the real tier
taxonomy (`app-orchestration-gis/SCORING-METHODOLOGY.md`, V3) is **four** tiers —
T1 Regional, T2 District, T3 Local, T4 Fringe — not the three shown here, and this
also contradicts this article's own sibling, [[nordic-uk-coverage]], which correctly
uses the Regional/District/Local naming. Separately, VWH is documented in code
(`test-cluster-archetypes.py`) as the "Urban Fringe" archetype (urban
logistics/light-manufacturing with no hypermarket anchor) — "vertical warehouse"
doesn't appear anywhere in source; PKS is confirmed accurate. **Flagged, not
resolved.**

See [[location-intelligence-archetypes|Location Intelligence Co-location Archetypes]] for a full introduction.

## GIS tile pipeline

Cluster data is compiled into PMTiles and served at `gis.woodfinegroup.com`. The pipeline runs nightly, producing updated archetype GeoJSON files and spatial tile layers. See the Developer Guide Catalog for the nightly rebuild and AEC hazard pipeline guides.

## Methodology articles

- O-D Catchment Methodology — crow-flies origin-destination model and catchment ring rationale
- Catchment Ranking Methodology — combined primary and secondary rank dimensions
- [[co-location-tier-nomenclature|Co-location Tier Nomenclature]] — T1/T2/T3 vocabulary

*This article is a stub. Full content is planned for a future session.*
