---
schema: foundry-doc-v1
title: "BIM objects — three composition layers"
slug: bim-objects-three-layers
language: en
category: building-design
type: topic
content_type: topic
status: active
last_edited: 2026-08-24
editor: pointsav-engineering
short_description: "A BIM Object carries three layers of information at once — what it is, what its jurisdiction requires of it, and what its climate requires of it — with the stricter of the two requirement layers governing whenever both apply to the same property."
cites: [ifc-4-3]
paired_with: building-design/bim-objects-three-layers.es.md
aliases:
  - bim-token-three-layers
---

A [[bim-objects-what-they-are|BIM Object]] carries three layers of information at once: Specification, Regulation, and Climate Zone. None of the three is a choice a designer makes at design time. A building element has a fixed type, sits in a fixed jurisdiction, and performs in a fixed climate, so the object reflects all three as facts about its physical context rather than as user preferences.

## Why three layers, not one

A built-environment element specification has to answer three different questions at once: what the element is — a stable, tool-independent identity; what the jurisdiction where it is built legally requires of it; and what the climate it sits in requires of it to perform. Regulatory requirements vary by jurisdiction and change as codes are updated; climate performance requirements vary by zone and change as energy codes are revised. Keeping these as separate layers, rather than folding them into a single number, means each concern can be tracked, sourced, and updated independently without disturbing the other two.

## What each layer carries

The Specification layer is the object's permanent identity — what kind of element it is, independent of where it is built. The Regulation layer holds the jurisdiction-specific legal requirements that apply where the building actually sits. The Climate Zone layer holds the performance requirements that follow from the building's physical climate, sourced from the applicable energy code. Regulation and Climate Zone are each authored as a growing table of every registered requirement rather than a single value, because a jurisdiction or a climate zone is a fact about the site, not a setting a user selects.

## When both a regulatory and a climate requirement apply

Where a regulatory requirement and a climate-zone requirement both constrain the same property, the stricter of the two governs. Both layers express performance minimums, so the binding requirement is always whichever minimum is higher — a straightforward most-restrictive-wins rule, not a negotiated tradeoff.

## Where the specification lives

The full field-level schema, jurisdiction overlay structure, and composition rule behind these three layers are maintained directly at [bim.woodfinegroup.com](https://bim.woodfinegroup.com).

## See also

- [[bim-objects-what-they-are]] — what a BIM Object is and how it differs from IFC entity types, proprietary BIM Family formats, and property sets
- [[bim-objects-substrate]] — the eight BIM Object primitive categories and their delivery format
- [[open-bim-regulatory-acceptance]] — how jurisdictions are adopting open BIM standards
- [[design-system-bim]] — the broader Building Design System for the built environment
