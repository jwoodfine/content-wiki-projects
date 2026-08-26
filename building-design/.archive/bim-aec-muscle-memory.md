---
schema: foundry-doc-v1
title: "AEC muscle memory and interface patterns"
slug: bim-aec-muscle-memory
category: building-design
index_group: design-philosophy-and-system
type: topic
content_type: topic
status: archived
archived: 2026-08-26
archived_reason: "PointSav software/platform architecture content misplaced on a real-estate wiki. Per the operator's own framing: the projects wiki 'is not for software or PointSav, it is for real estate' -- there is something wrong with content that needs a link to documentation.pointsav.com; it needs to be rewritten to fit corporate or projects, or moved. This article described planned UI/UX interface-pattern decisions (adopting AEC authoring-tool muscle memory, extending into facility-management workflows) -- platform interface design, not Woodfine real-estate content. Consolidated into media-knowledge-documentation patterns/aec-interface-conventions (2026-08-26); property-manager-bim-gap (unchanged, stays on this wiki) already carries the real-estate-facing version of the facility-management framing."
superseded_by: none
audience: customer-woodfine
bcsc_class: current-fact
language_protocol: PROSE-TOPIC
last_edited: 2026-08-24
editor: pointsav-engineering
short_description: "The Building Design System is planned to adopt interface patterns already familiar from industry-standard AEC tools, so practitioners arrive with zero learning curve, and to extend that same familiar interface into facility-management workflows — linking maintenance, leases, and live sensor data to the building model."
paired_with: building-design/bim-aec-muscle-memory.es.md
cites: [ifc-4-3]
---

The [[design-system-bim|Building Design System]] is planned to adopt interface patterns already familiar from industry-standard AEC authoring tools, so a practitioner arrives with a zero learning curve rather than needing to learn a new tool's conventions before doing any real work. This is the same shared interface vocabulary described in [[aec-interface-conventions]] — mirroring it is intended to let attention go to the platform's actual differentiators, such as the flat-file archive, rather than basic tool navigation.

## Extending into facility management

Existing BIM tools are built primarily for designers, and most of a model's value is lost once it reaches a facility manager who was never part of its authoring workflow. The Building Design System is intended to extend the same familiar interface into the facility-management and property-manager workflow: linking maintenance status to building elements, connecting spaces to lease records, and layering live sensor data onto the model. This is intended to turn a BIM model from a design-and-handoff artifact into an operating record a property manager actually uses day to day.

## Where the specification lives

The full interface convention catalog and facility-management workflow specification are maintained directly at [bim.woodfinegroup.com](https://bim.woodfinegroup.com).

## See also

- [[bim-design-philosophy]]
- [[bim-objects-substrate]]
