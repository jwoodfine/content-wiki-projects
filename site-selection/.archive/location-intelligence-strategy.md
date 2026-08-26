---
schema: foundry-doc-v1
title: "Location intelligence platform — strategy and architecture"
slug: location-intelligence-strategy
language: en
category: site-selection
index_group: the-method
type: topic
content_type: topic
status: archived
archived: 2026-08-26
archived_reason: "Retracted, not migrated -- redundant third copy of content already de-duplicated on media-knowledge-documentation. Per two independent audits (Fable and Opus, 2026-08-26): media-knowledge-documentation/substrate/location-intelligence-substrate.md already carries this article's flat-file/tile-stack/co-location architecture thesis (near-identical short_description; aliased pointsav-gis-engine), and applications/location-intelligence-platform.md + patterns/location-intelligence-ux.md cover the remaining application/UX ground -- this projects-wiki copy escaped an earlier cross-wiki de-duplication pass only because it lived in the wrong repo. The one genuinely site-selection-relevant passage (the Spain Bricomart/Obramat brand-family research) was salvaged into site-selection/retail-brand-family-taxonomy.md before archival. The named-competitor market survey (Carto, Esri, Mapbox, Placer) and the internal week-by-week implementation plan are retracted, not republished anywhere, per the workspace's structural-positioning-only rule."
superseded_by: none
last_edited: 2026-06-20
editor: pointsav-engineering
short_description: "The strategic and architectural frame for the platform's Location Intelligence substrate: a flat-file open-GIS approach that lets customers own their location data end-to-end, running offline, without ongoing per-seat or per-request vendor costs."
cites:
 - geoparquet-spec
 - flatgeobuf
 - overture-maps
 - foursquare-os-places
 - maplibre-gl-js
 - martin-tile-server
 - pmtiles-spec
 - tippecanoe
 - meteoblue-maps-api
 - mdpi-vector-rendering-2025
 - carto-tile-architecture
 - esri-arcgis-online-pricing
 - mapbox-pricing
 - placer-ai
 - planetizen-retail-clusters
 - nber-w17220-costco
 - walmart-store-count-2025
 - homedepot-store-count-2025
 - costco-store-count-2025
 - ikea-spain-stores
 - bricomart-spain
 - leroy-merlin-spain
 - nominatim-osm
 - photon-geocoder
 - deck-gl
 - eupl-1-2
 - ni-51-102
 - osc-sn-51-721
paired_with: site-selection/location-intelligence-strategy.es.md
---

The Location Intelligence substrate gives customers a dataset of place records — businesses, points of interest, parking geometries — stored as flat files the customer owns, versioned in the same ledger as every other Totebox record, and rendered through an open-source mapping stack with no per-request or per-seat costs. The first application is a co-location map: every Walmart-family, Home-Depot-family, and Costco location across the United States, Canada, Mexico, and Spain, with retail clusters that fall within defined proximity ranges surfaced as the visible analytic. See the Location Intelligence platform and the substrate composition.

This article describes the market context, the architectural decisions, the technical stack, and the planned implementation path.

## The Location Intelligence market — structural patterns

The Location Intelligence segment in 2026 organises into four architectural families, each with a structural revenue mechanism that constrains what it can offer.

**Cloud-native query-on-warehouse platforms.** These platforms execute spatial queries directly inside a customer's data warehouse, then render tiles from query results [carto-tile-architecture]. The architecture requires no data copy. It also requires the customer to maintain a data warehouse; customers who want to operate without one are not addressed.

**Legacy enterprise GIS.** Products in this category sell progressive user-type licences and use credits as the in-platform currency for storage, analysis tools, and premium data [esri-arcgis-online-pricing]. The licensing model makes them a poor fit for SMB customers operating a small, owned dataset without seat-by-seat budget allocation.

**Developer-tier mapping platforms.** These price on monthly active users, map loads, tile-API requests, and tileset-processing volume [mapbox-pricing]. The open-source fork of the leading platform (MapLibre GL JS) is now the standard for vector-tile rendering. The proprietary side ties cost to traffic; a public-facing site with substantial traffic generates a proportionally large bill.

**Foot-traffic and movement analytics.** These operate a panel of mobile devices and extrapolate store visitation through statistical methods [placer-ai]. The data is additive for retail-strategy work. The architecture is necessarily centralised and privacy-aggregated — a customer cannot operate an equivalent instance on their own data while remaining a customer.

**Open-data foundations.** Two public initiatives reset the substrate floor: Foursquare released its 100M+ POI dataset as Apache-2.0-licensed monthly Parquet drops in late 2024 [foursquare-os-places], and the Overture Maps Foundation publishes places, buildings, transportation, and addresses as GeoParquet on public cloud storage [overture-maps]. A Location Intelligence platform built in 2026 that does not draw from these substrates duplicates work the open-data community has already completed.

Each platform family ties revenue to something the customer's data passes through — warehouse compute, seat licences, request volume, or panel access. None can offer the inverse: a substrate the customer owns end-to-end, runs offline, and replicates without paying recurring costs. The platform's Location Intelligence substrate occupies that position.

## Architectural commitments — flat-file, open standards, optional intelligence

Three commitments carried forward from the rest of the platform define what the Location Intelligence substrate can show that no service in the market above can:

**The customer's location dataset is a customer-owned directory.** `service-business`, `service-places`, and `service-parking` are not databases living in a vendor cloud — they are GeoParquet files (with JSONL siblings for git-diff readability) inside a Totebox Archive the customer signs and stores. A customer who adds 200 retail locations of their own owns those records the same way they own their documents.

**Intelligence is optional.** The map renders, the co-location query runs, and the layers compose without any AI compute. `service-slm` becomes available for annotation work — suggesting categories for newly-ingested POIs, summarising dataset deltas, flagging anomalies — but the platform operates fully with the Doorman shut down.

**The substrate composes with the rest of the platform.** Co-location triples produced in `service-business` today can compose with building envelopes from `service-bim` tomorrow. Two clusters, one coordinate system, one WORM ledger, one identity model.

## Data architecture — flat-file canonical for service-business

The operator-facing question is whether `service-business` keeps records flat or in a database. Three options are viable:

**Flat-file canonical.** JSONL for human-readable change tracking; GeoParquet for performant analytic reads; FlatGeobuf for browser-side spatial bounding-box streaming. GeoParquet is an OGC incubating standard that adds Point, Line, and Polygon types to columnar Parquet [geoparquet-spec]. FlatGeobuf carries a Hilbert R-tree at the file header that lets a browser stream only the features inside the current viewport over HTTP range requests [flatgeobuf]. Advantages: sovereign by construction, version-controllable, customer-portable, zero infrastructure to operate. Constraint: writes are single-author-at-a-time (the file is rewritten on update).

**Database canonical.** PostgreSQL with PostGIS. Advantages: rich spatial SQL, multi-writer concurrency. Constraint: the customer's data lives in a running daemon; portability requires a dump-and-restore, not a directory move.

**Hybrid.** Flat-file canonical; ephemeral database materialised from the flat file as a query cache. This matches the vault-as-canonical, derived-tables-as-cache pattern the platform already uses for bookkeeping.

For the current workload — tens of thousands of POI records across four countries, three brand families, infrequent batch writes, read-mostly query — flat-file is sufficient. Foursquare and Overture Maps Foundation chose the same format for their substrate releases [foursquare-os-places][overture-maps]. The recommendation: **GeoParquet as the canonical at-rest format** (one file per country per service, rolled monthly), **JSONL siblings for git-tracked history**, **FlatGeobuf as the browser-streamable derivative**. If a future workload introduces real-time concurrent writes across multiple browsers simultaneously, the hybrid pattern is the migration path.

## Per-record schema

A single record shape covers the Ring 1 place-data services, distinguished by a service
discriminator, and is stored as JSONL for git readability, batch-rolled monthly into
per-country GeoParquet and FlatGeobuf. Each record carries the operator and brand family, a
localised name, country and address, coordinates and geometry, a store or place type, the
opening year where known, and a data-provenance source and URL. That is enough to support
the co-location query and honest sourcing, without over-specifying the wire format here. The
full schema is maintained on the specialist GIS site (`gis.woodfinegroup.com`) for readers
who need the exact field-level specification.

Brand-family normalisation lets the co-location query treat regional equivalents as one
logical operator across countries. Walmart groups with its Spanish general-merchandise
equivalent; Home Depot groups with its Spanish trade-warehouse equivalent; Costco stays a
single family, present directly in all four countries.

## Spain Home Depot equivalent — research finding

Identifying the Home Depot structural analog in Spain requires distinguishing between consumer-DIY format and trade-warehouse format.

**Bricomart (rebranded Obramat in 2024)** — owned by the Adeo group (the same parent as Leroy Merlin), warehouse format oriented towards professional trade and self-builder customers, approximately 22 locations in Spain [bricomart-spain]. The format match — warehouse-scale, professional-trade-focused, large-volume positioning — is the closest structural analog to Home Depot.

**Leroy Merlin** — also Adeo group, the dominant consumer-DIY brand in Spain at 120+ locations [leroy-merlin-spain]. The closest analog by store count and consumer visibility, but the format is consumer-DIY rather than trade-warehouse; the Lowe's comparison fits it better than the Home Depot one.

**Recommendation: Bricomart (Obramat) maps to Home Depot** in the brand-family schema. Leroy Merlin maps to the Lowe's position. Costco has direct Spain presence at five warehouses [costco-store-count-2025], so the co-location query in Spain is genuinely cross-brand, not a synthesis across regional substitutes.

## Map tile and layer delivery

The visual quality target is WebGL-rendered vector tiles styled in the browser. The recommended open-source stack:

- **Renderer**: MapLibre GL JS [maplibre-gl-js] — the community-maintained fork that supports vector tiles and WebGL, dynamic styling, and 3D without per-traffic licence cost. Benchmarks confirm WebGL renderers outperform raster-based alternatives at high feature counts [mdpi-vector-rendering-2025].
- **Data-visualisation overlays**: deck.gl [deck-gl] when scatter, heatmap, arc, or polygon-extrusion layers are needed.
- **Tile generation**: Tippecanoe for converting GeoJSON to MBTiles or PMTiles, with 85–95 percent file-size reductions over raw GeoJSON [tippecanoe].
- **Tile serving**: Martin, the MapLibre Foundation's Rust tile server [martin-tile-server]. Supports PostGIS, MBTiles, and PMTiles. Rust-aligned with the rest of the platform stack.
- **Tile archive format**: PMTiles [pmtiles-spec] — a single-file archive that supports HTTP range requests, allowing the deployment to serve tiles directly from nginx without running Martin when tiles are pre-baked.

Implementation rule: bake static tiles for brand-family POIs and co-location radius circles via Tippecanoe and PMTiles; serve directly from nginx. Move to Martin only when dynamic tile generation is needed.

## Co-location analysis algorithm

The surface use case: show where Walmart-family, Home-Depot-family, and Costco co-locate,
graded by how tightly the three anchors cluster together. Retail co-location clustering is
a recognised analytical method; the tendency of complementary large-format retailers to
cluster near each other is documented in the literature [planetizen-retail-clusters][nber-w17220-costco].

At a conceptual level, the pipeline runs a nearest-neighbour search: for each Walmart-family
location, it finds the closest Home-Depot-family location and the closest Costco location,
forming a triple. Each triple is then graded by how close together its three members sit;
tighter triples earn a stronger co-location grade. The result is rendered as a lightweight
geographic feature set — the triple's centroid, a connecting shape between the three points,
and a grade property the map can style by. The nearest-neighbour search itself runs
comfortably at interactive speed even across a full national dataset.

Browser visualisation (MapLibre GL):

- Layer 1: POIs as circles, coloured by brand family, sized by store format.
- Layer 2: co-location triples shown as filled shapes and proximity haloes, styled by
  co-location grade, with looser grades toggleable independently of tighter ones.
- Layer 3: country boundary; brand-family filter chips.
- Hover popovers: brand, format, year opened, distances to co-located neighbours, cluster grade.

The current dataset is approximately 15,000 records (combined US/CA/MX/ES across three brand families) — client-side rendering is sufficient at this scale. US breakdown: Walmart 4,605 [walmart-store-count-2025]; Home Depot 2,359 [homedepot-store-count-2025]; Costco (US + Puerto Rico) 623 [costco-store-count-2025]. Spain: IKEA approximately 28 [ikea-spain-stores]; Bricomart approximately 22 [bricomart-spain]; Costco 5 [costco-store-count-2025].

## Planned implementation path

All milestones below are intended targets, subject to acceptance criteria and operator review at each stage. [ni-51-102] [osc-sn-51-721]

**Week 1 — Deployment frame.** A dedicated deployment instance is provisioned, with its standard manifest and bilingual README documentation. A public web host for `gis.woodfinegroup.com` serves HTTP first; HTTPS via Let's Encrypt once DNS resolves. Supporting engineering and documentation working copies are set up, and initial GUIDE drafts are started.

**Week 2 — Application scaffold.** The GIS application server (Rust backend, MapLibre GL JS front end) binds to an available local port. Initial HTML shell with map container, brand-family filter chips, and country selector. Static dummy POI data verifies the rendering pipeline end-to-end.

**Week 3 — US data ingestion.** The Walmart, Home Depot, and Costco subset is drawn from Foursquare's Open Source Places monthly Parquet drop or the Overture Maps Foundation places dataset [foursquare-os-places][overture-maps], filtered by operator name and country, normalised into the `service-business` schema, and written as JSONL, GeoParquet, and FlatGeobuf. Approximately 7,600 records. Co-location algorithm runs in seconds at this scale.

**Week 4 — Co-location surface ready for demonstration.** MapLibre GL layers for POIs, co-location triples, and proximity radius circles at each co-location grade. Click-through detail: brand, format, distance, cluster grade.

**Weeks 5–6 — Canada and Mexico.** Canada: Walmart 404, Home Depot 182, Costco 109. Mexico: Walmart 3,191, Home Depot 142, Costco 41. Total dataset approximately 12,000 records before Spain.

**Week 7 — Spain.** IKEA Spain under `walmart_family`, Bricomart under `homedepot_family`, Costco Spain. Approximately 55 records — illustrative of the cross-regional brand-family abstraction.

**Weeks 8+ — places and parking data, offline desktop shell, editorial fan-out.** A Tauri-based offline desktop shell for the GIS workplace surface; ingestion of institutional place data (hospitals, universities, airports) and parking geometries; TOPIC drafts for the documentation wiki; COMPONENT drafts for the design system.

## See also

- three-ring-architecture — the Ring 1 / Ring 2 / Ring 3 composition that service-business, service-places, and service-parking implement
- compounding-substrate — the sovereignty and optional-intelligence properties this substrate implements
- worm-ledger-architecture — the append-only ledger that anchors co-location records in the customer's Totebox Archive
- service-slm — the optional Ring 3 service available for annotation and anomaly detection on ingested POI records
