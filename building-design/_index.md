---
schema: foundry-doc-v1
title: "Building Design"
slug: building-design-index
category: building-design
type: topic
content_type: topic
quality: complete
short_description: "The design system: buildings designed from the tenant out, fixed floor plates, the offset core, key plans and tiles, measurement standards, and BIM practice."
index_type: thematic
index_scope: building-design
status: active
bcsc_class: current-fact
language_protocol: PROSE-TOPIC
last_edited: 2026-08-26
editor: pointsav-engineering
paired_with: _index.es.md
---

Building Design covers the design system behind every Woodfine building: a fixed leasing geometry, an open-standards BIM practice, and the site-and-building disciplines that turn that geometry into a buildable, sustainable property.

<!-- START-HERE-HIGHLIGHT: engine reads this block to render the single "start here" card (reuses the existing cluster-card--start-here component). Do not add more than one. -->

**Start here:** [[bim-design-philosophy|BIM Design Philosophy]]

<!-- END-START-HERE-HIGHLIGHT -->

## Design Philosophy and System

[[bim-design-philosophy|BIM Design Philosophy]] states the core commitment: buildings are designed to comply with jurisdictional code at the design stage, not checked for compliance afterward. [[design-system-bim|The Building Design System]] and [[flat-file-bim-leapfrog|Flat-File BIM Leapfrog]] set out the planned coordination layer and the five architectural constraints — flat-file storage, open standards, offline-first operation, and Apache 2.0 licensing — that keep a building's digital record usable independent of any vendor. [[bim-market-context|BIM Market Context]] and [[open-bim-regulatory-acceptance|Open BIM and Regulatory Acceptance]] cover the government mandates already pushing the AEC industry toward the same open standards. [[aec-interface-conventions|AEC Interface Conventions]], [[bim-aec-muscle-memory|AEC Muscle Memory]], and [[property-manager-bim-gap|the Property Manager BIM Gap]] cover the interface conventions the planned tools borrow and the handover problem — models most facility managers never actually use — that this practice is designed to close.

<!-- AUTO-GENERATED MEMBERSHIP: DO NOT EDIT BELOW — regenerate from index_group: design-philosophy-and-system -->
- [[bim-design-philosophy]] — Woodfine's buildings are designed to comply with jurisdictional codes at the design stage, rather than being checked for compliance after the fact — a consequence of building on open, portable standards from the outset.
- [[design-system-bim]] — A planned design-system platform for the built environment — the missing coordination layer that would let independent BIM authoring surfaces work from a shared specification vocabulary, the way a software design system keeps independent product teams consistent.
- [[flat-file-bim-leapfrog]] — The Building Design System is constructed on five architectural constraints — flat-file storage, open standards, Rust and Tauri, offline-first operation, and Apache 2.0 licensing — enabling vendor-obsolescence-survivable building information models. Asset-anchored ownership, offline capability, IoT integration, and convergence of BIM with lease and financial ledgers follow from the architecture itself.
- [[bim-market-context]] — Government BIM mandates across the UK, EU, and other jurisdictions require open, vendor-neutral data formats; Woodfine's buildings are designed and specified against those open standards from the outset.
- [[open-bim-regulatory-acceptance]] — Building Information Modelling is mandated across most G7 economies for public procurement, with open, vendor-neutral standards as the delivery requirement rather than proprietary formats.
- [[aec-interface-conventions]] — BIM authoring tools across the industry share a common interface vocabulary — a spatial hierarchy, an element properties panel, a 3D viewport, and saved views — because they build on the same underlying IFC data model, giving PointSav's planned interface layer a shared foundation to build on rather than inventing a new one.
- [[bim-aec-muscle-memory]] — The Building Design System is planned to adopt interface patterns already familiar from industry-standard AEC tools, so practitioners arrive with zero learning curve, and to extend that same familiar interface into facility-management workflows — linking maintenance, leases, and live sensor data to the building model.
- [[property-manager-bim-gap]] — A substantial share of facilities managers do not actively use the BIM models delivered at project handover, due to software cost, training requirements, and file format opacity — a gap Woodfine's building records are designed to close.
<!-- END AUTO-GENERATED -->

## BIM Objects and the Digital Record

[[bim-objects-what-they-are|BIM Objects]] are Woodfine's term for a reusable building-element specification that carries its own code and performance requirements with it. [[bim-objects-substrate|BIM Objects — Substrate]] and [[bim-objects-three-layers|BIM Objects — Three Layers]] cover the fixed primitive categories objects are organized into and the three information layers — what it is, what jurisdiction requires, what climate requires — every object carries at once. [[city-code-as-composable-geometry|City Code as Composable Geometry]] and [[gis-as-bim-substrate|GIS as a BIM Substrate]] cover how regulatory requirements and location data feed directly into that specification. [[asset-anchored-bim-vault|The Asset-Anchored BIM Vault]] and [[3d-asset-tokens|the Three-Dimensional Asset Token]] cover how a building's own digital record is stored and versioned.

<!-- AUTO-GENERATED MEMBERSHIP: DO NOT EDIT BELOW — regenerate from index_group: bim-objects-and-the-digital-record -->
- [[bim-objects-what-they-are]] — A BIM Object is Woodfine's term for a reusable building-element specification that carries its applicable code and performance requirements with it, so non-compliant configurations are caught at design time rather than at inspection.
- [[bim-objects-substrate]] — BIM Objects are organized into a small, fixed set of primitive categories — spatial elements, physical elements, materials, systems, performance thresholds, and more — each anchored to open industry standards (IFC, Uniclass, bSDD) rather than a proprietary schema, so a specification stays portable and verifiable across tools and vendors.
- [[bim-objects-three-layers]] — A BIM Object carries three layers of information at once — what it is, what its jurisdiction requires of it, and what its climate requires of it — with the stricter of the two requirement layers governing whenever both apply to the same property.
- [[city-code-as-composable-geometry]] — An architectural model that encodes regulatory requirements directly into element specifications as geometric and numeric constraints rather than applying them post-design, making non-compliant configurations structurally impossible by construction.
- [[gis-as-bim-substrate]] — What the PointSav GIS co-location dataset offers a BIM composition pipeline: cluster manifold fields, civic context layers, and stability guarantees.
- [[asset-anchored-bim-vault]] — A building's authoritative digital record structured as plain-text and standardized-binary files in a git-versioned directory, qualifying as an ISO 19650-conforming Common Data Environment that travels with the property deed.
- [[3d-asset-tokens]] — The archive's unit of stored data, combining an immutable binary payload, machine-readable metadata skeleton, and live taxonomic graph connection encoding provenance and context.
<!-- END AUTO-GENERATED -->

## The Leasing Geometry

[[fixed-floor-plates|Fixed Floor Plates]] and [[key-plans-and-tiles|Key Plans and Tiles]] set out the standardized structural base and the self-similar space-planning system every Woodfine building is derived from. [[boma-standard|The BOMA Standard]] is the shared measurement basis for every lease area and building comparison. [[asset-architecture-standard|The Asset Architecture Standard]] fixes the uniform structural requirements — concrete and steel construction, pre-acquisition dimensioning — applied across the portfolio.

<!-- AUTO-GENERATED MEMBERSHIP: DO NOT EDIT BELOW — regenerate from index_group: the-leasing-geometry -->
- [[fixed-floor-plates]] — The standardized, immutable structural base used in all Woodfine buildings, derived from optimized equipment geometry to enable repeatable construction and predictable space performance.
- [[key-plans-and-tiles]] — A geometric, self-similar space planning system derived from tenant equipment and circulation geometry, used to derive fixed floor plate dimensions.
- [[boma-standard]] — The Building Owners and Managers Association measurement standard for commercial floor area, used as the common measurement basis for Woodfine lease areas and building comparisons.
- [[asset-architecture-standard]] — Uniform structural requirements for Woodfine developments: concrete and steel construction, pre-acquisition dimensioning, and standardized configuration applied across the portfolio.
<!-- END AUTO-GENERATED -->

## Site and Building Disciplines

[[design-sequence-priority|Design Sequence Priority]] fixes the collaboration order behind every design package: Leasing Plan first, then Building Services, then Structural. [[four-to-one-parking-ratio|The 4:1 Parking Ratio]] and [[water-management-system|the Water Management System]] apply at the site level. [[common-building-code|The Common Building Code]], [[tile-level-climate-zoning|tile-level climate zoning]], and [[structural-bay-depth-discipline|structural bay depth discipline]] apply at the building and leasehold level. [[geometry-of-sustainability|Geometry of Sustainability]] and [[dual-mandate-building-certifications|Dual-Mandate Building Certifications]] cover the operating-cost engineering and the BREEAM/WELL certification strategy that follow.

<!-- AUTO-GENERATED MEMBERSHIP: DO NOT EDIT BELOW — regenerate from index_group: site-and-building-disciplines -->
- [[design-sequence-priority]] — The fixed collaboration order behind every Woodfine design package — the Leasing Plan first, then Building Services, then Structural — each discipline designing against a completed prior layer instead of in parallel.
- [[four-to-one-parking-ratio]] — The four-stalls-per-1,000-square-foot parking standard Woodfine applies in Regional Markets, where the private automobile is the only practical way a tenant's customers reach the building.
- [[water-management-system]] — A day-to-day water-conservation mechanism — cistern and irrigation-gallery storage, a greywater plumbing system, permeable paving, and bioswales — that makes Development Site landscaping self-sufficient rather than dependent on municipal stormwater infrastructure.
- [[common-building-code]] — Woodfine's internal washroom-provisioning standard, layered on top of jurisdictional building code and keyed to Tenant Mix and daily foot traffic rather than code minimums alone.
- [[tile-level-climate-zoning]] — Woodfine's building-services granularity standard: every Tile carries its own thermostat, with Special Tiles given a self-controlled climate zone, rather than zoning at the individual-leasehold or whole-floor level.
- [[structural-bay-depth-discipline]] — A structural-grid discipline requiring leasehold bay depth to be set by tenant space requirements rather than the cheapest available beam span, since unleasable depth from an oversized bay is never recoverable over the life of a lease.
- [[geometry-of-sustainability]] — Engineering discipline applying European lighting, Swiss air-exchange, and German circulation standards to the fixed floor plate, for improved building operating-cost efficiency.
- [[dual-mandate-building-certifications]] — Leasing strategy certifying every Woodfine Building to both BREEAM environmental and WELL wellness standards, targeting National Tenants exiting legacy office inventory.
<!-- END AUTO-GENERATED -->

## See also

- [[buildings-index|Buildings]]
- [[site-selection-index|Site Selection]]
