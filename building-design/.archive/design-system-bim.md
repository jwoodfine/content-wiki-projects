---
schema: foundry-doc-v1
title: "Building design system"
slug: design-system-bim
language: en
category: building-design
index_group: design-philosophy-and-system
type: topic
content_type: topic
status: archived
archived: 2026-08-26
archived_reason: "PointSav software/platform architecture content misplaced on a real-estate wiki. Per the operator's own framing: the projects wiki 'is not for software or PointSav, it is for real estate' -- there is something wrong with content that needs a link to documentation.pointsav.com; it needs to be rewritten to fit corporate or projects, or moved. This article described the planned Building Design System coordination-layer platform -- platform architecture, not Woodfine real-estate content. Migrated to media-knowledge-documentation architecture/building-design-system (2026-08-26)."
superseded_by: none
last_edited: 2026-08-24
editor: pointsav-engineering
short_description: "A planned design-system platform for the built environment — the missing coordination layer that would let independent BIM authoring surfaces work from a shared specification vocabulary, the way a software design system keeps independent product teams consistent."
cites: [ifc-4-3, uniclass-2015, bsdd-v1]
paired_with: building-design/design-system-bim.es.md
---

Major software design systems solve a coordination problem at scale: when independent teams build interfaces in parallel, consistency breaks down unless design decisions are encoded in a shared layer that every surface consumes by reference. No equivalent has existed for the built environment. Building Information Modelling production is coordinated through shared standards (IFC, Uniclass, bSDD) and shared authoring tools, but there has been no common specification layer — no canonical, machine-readable library of building-element specifications that independent authoring surfaces consume by reference. The Building Design System is intended to fill that gap.

## Why the space has been empty

Three structural factors have kept it empty. Proprietary BIM authoring tools have historically stored element specifications in formats locked to a single tool, not designed to carry normative regulatory data across tools. IFC is a neutral exchange format — it expresses what a model contains, not what a specification requires — so it was never designed to be a design system on its own. And the wider built-environment standards stack evolved in parallel across jurisdictions, with no single standard providing a composable specification layer that ties the others together.

## What it is made of

The Building Design System is organized into two layers: a library of [[bim-objects-substrate|BIM Object primitive categories]] — the specification units for spatial elements, physical elements, materials, systems, and more — and a set of [[aec-interface-conventions|shared interface components]] that any BIM-capable surface can build on. Together they are intended to give independent authoring surfaces a common vocabulary to coordinate around, without a practitioner moving between them needing to learn a new interface each time.

## An owned archive, not a hosted service

The Building Design System is not planned as a hosted service — it is a set of files in a git repository that an organization clones and extends with its own jurisdiction-specific and site-specific data. This is the same sovereignty model that underlies Woodfine's flat-file BIM archive more broadly. Nothing is required to flow back to a central vendor for an organization to keep using its own copy.

## Where the specification lives

The full object category catalog, interface component library, and current implementation status are maintained directly at [bim.woodfinegroup.com](https://bim.woodfinegroup.com).

## See also

- [[bim-objects-what-they-are]]
- [[bim-objects-three-layers]]
- [[bim-objects-substrate]]
