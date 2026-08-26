---
schema: foundry-doc-v1
title: "BIM objects — substrate"
slug: bim-objects-substrate
language: en
category: building-design
index_group: bim-objects-and-the-digital-record
type: topic
content_type: topic
status: archived
archived: 2026-08-26
archived_reason: "PointSav software/platform architecture content misplaced on a real-estate wiki. Per the operator's own framing: the projects wiki 'is not for software or PointSav, it is for real estate' -- there is something wrong with content that needs a link to documentation.pointsav.com; it needs to be rewritten to fit corporate or projects, or moved. This article described the BIM Object primitive category taxonomy -- a platform data-schema definition, not Woodfine real-estate content. Consolidated (with bim-objects-three-layers and bim-objects-what-they-are) into media-knowledge-documentation substrate/bim-object-specification (2026-08-26) -- three tightly-coupled facets of one concept, previously split into three thin stubs."
superseded_by: none
last_edited: 2026-08-24
editor: pointsav-engineering
short_description: "BIM Objects are organized into a small, fixed set of primitive categories — spatial elements, physical elements, materials, systems, performance thresholds, and more — each anchored to open industry standards (IFC, Uniclass, bSDD) rather than a proprietary schema, so a specification stays portable and verifiable across tools and vendors."
cites: [ifc-4-3, uniclass-2015, bsdd-v1]
paired_with: building-design/bim-objects-substrate.es.md
aliases:
  - bim-token-taxonomy
---

Every [[design-system-bim|Building Design System]] [[bim-objects-what-they-are|BIM Object]] belongs to one of a small, fixed set of primitive categories — spatial elements such as sites and storeys, physical elements such as walls and doors, materials, assemblies, building systems, performance thresholds, climate-zone requirements, and identity codes. Grouping objects this way means a category tells a practitioner what kind of thing an object describes before they open its full specification.

## Anchored to open standards, not a proprietary schema

Each category anchors to the same open standards already used across the AEC industry: the IFC entity hierarchy for what an element is, Uniclass 2015 for how it is classified, and buildingSMART's Data Dictionary (bSDD) for a stable, tool-independent definition. Anchoring to open standards rather than a proprietary schema means an object's meaning does not depend on any one BIM authoring tool remaining in business. The specification stays legible and verifiable however long the building stands, and however many software vendors come and go over its life.

## Where the specification lives

The full category catalog, IFC and Property Set mappings, and delivery format behind this substrate are maintained directly at [bim.woodfinegroup.com](https://bim.woodfinegroup.com).

## See also

- [[bim-objects-what-they-are]] — the pre-constraining thesis and how BIM Objects differ from IFC property sets
- [[bim-objects-three-layers]] — the Specification, Regulation, and Climate Zone layers each object carries
- [[design-system-bim]] — the broader Building Design System for the built environment
