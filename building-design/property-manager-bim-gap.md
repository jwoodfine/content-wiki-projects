---
schema: foundry-doc-v1
title: "Property manager BIM gap"
slug: property-manager-bim-gap
language: en
category: building-design
index_group: design-philosophy-and-system
type: topic
content_type: topic
status: active
last_edited: 2026-08-24
editor: pointsav-engineering
short_description: "A substantial share of facilities managers do not actively use the BIM models delivered at project handover, due to software cost, training requirements, and file format opacity — a gap Woodfine's building records are designed to close."
cites: [ifc-4-3, iso-19650]
paired_with: building-design/property-manager-bim-gap.es.md
---

Building Information Models are authored by architects and structural engineers, delivered to contractors for construction, and then handed to property managers at practical completion. In practice, most of that model's value is never realized — a facilities manager who lacks a BIM viewer, the training to use one, or the budget for an authoring-tool licence cannot make use of the file they've been handed. See [[bim-design-philosophy|Woodfine's design philosophy]] for how Woodfine's approach addresses this.

## A documented industry gap

The gap between BIM production and BIM consumption in facilities management is documented in peer-reviewed literature: a substantial share of facilities managers do not actively use the BIM models they receive at handover. The recurring barriers cited are software cost, a significant training requirement, and file format opacity. Several researchers call this the "BIM handover gap" — a detailed digital model exists, was paid for by the developer, and meets the contractual delivery requirement, yet sits unused.

Facilities management platform vendors have begun addressing this by building BIM viewer integrations directly into their CAFM/CMMS software. Importing BIM data into a CAFM platform is typically lossy, though: property attributes the CAFM schema doesn't recognize are discarded, and the imported data drifts out of sync with the canonical model as the building is renovated.

## Woodfine's approach

Woodfine's building records are designed to give a facilities manager direct, read-only access to the full-fidelity model data — without requiring an authoring-tool licence, and without a lossy CAFM import that drifts out of sync over time. The same approach is designed to extend to lease-register data, keeping a building's spatial, operational, and financial records as one system rather than three that must be reconciled by hand.

## Where the specification lives

The interface components, data-access mechanism, and implementation detail behind this approach are maintained directly at [bim.woodfinegroup.com](https://bim.woodfinegroup.com).

## See also

- [[bim-design-philosophy]] — why Woodfine's records are designed to stay independently usable over a building's life
