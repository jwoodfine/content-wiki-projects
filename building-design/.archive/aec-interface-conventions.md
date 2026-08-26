---
schema: foundry-doc-v1
title: "AEC interface conventions"
slug: aec-interface-conventions
language: en
category: building-design
index_group: design-philosophy-and-system
type: topic
content_type: topic
status: archived
archived: 2026-08-26
archived_reason: "PointSav software/platform architecture content misplaced on a real-estate wiki. Per the operator's own framing: the projects wiki 'is not for software or PointSav, it is for real estate' -- there is something wrong with content that needs a link to documentation.pointsav.com; it needs to be rewritten to fit corporate or projects, or moved. This article described the shared BIM authoring interface vocabulary (hierarchy tree, properties panel, viewport, saved views) and the planned interface layer built on it -- platform interface architecture, not Woodfine real-estate content. Consolidated (with bim-aec-muscle-memory) into media-knowledge-documentation patterns/aec-interface-conventions (2026-08-26)."
superseded_by: none
last_edited: 2026-08-24
editor: pointsav-engineering
short_description: "BIM authoring tools across the industry share a common interface vocabulary — a spatial hierarchy, an element properties panel, a 3D viewport, and saved views — because they build on the same underlying IFC data model, giving PointSav's planned interface layer a shared foundation to build on rather than inventing a new one."
cites: [ifc-4-3]
paired_with: building-design/aec-interface-conventions.es.md
---

Every major BIM authoring platform ships with the same four interface conventions: a hierarchy tree for the spatial structure, a properties panel for element attributes, a 3D viewport, and a saved-view navigator. These conventions exist because the underlying data model — the IFC entity hierarchy — is the same regardless of which tool authors it. An architect or engineer who has learned this vocabulary in one authoring tool already knows it in the next.

## Why a shared vocabulary matters

BIM project teams routinely work across several authoring tools on a single project. The structural engineer's model, the architect's model, and the MEP engineer's model each export to the same open format, and coordination happens in a common viewer where no one is working in their native authoring environment. A coordination surface built on this shared vocabulary does not introduce a new learning curve on top of the tools practitioners already use.

## The Building Design System's planned interface layer

The [[design-system-bim|Building Design System]] is planned to build its own interface components on this same shared vocabulary, so a practitioner moving between their authoring tool and any PointSav BIM surface finds the same tree, the same properties panel, and the same viewport controls. This layer does not exist in canonical code yet.

## Where the specification lives

The full component catalog and implementation detail behind this interface layer are maintained directly at [bim.woodfinegroup.com](https://bim.woodfinegroup.com).

## See also

- [[design-system-bim]] — the broader Building Design System this interface layer is part of
- [[bim-aec-muscle-memory]] — how this shared vocabulary extends into facility-management workflows
- [[bim-objects-what-they-are]] — the underlying object model this interface exposes
