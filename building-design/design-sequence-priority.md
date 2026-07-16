---
schema: foundry-doc-v1
title: "Design Sequence Priority: Leasing Plan, Then Services, Then Structural"
slug: design-sequence-priority
category: building-design
type: topic
content_type: topic
quality: complete
status: active
audience: public
bcsc_class: current-fact
language_protocol: PROSE-TOPIC
last_edited: 2026-07-15
editor: pointsav-engineering
short_description: "The prescribed collaboration order across a Development Site's design disciplines — Leasing Plan first, then Building Services, then Structural — that keeps existing floor-plate composition rules internally consistent."
paired_with: building-design/design-sequence-priority.es.md
cites: []
---

**Design Sequence Priority** is the prescribed collaboration order across a Development Site's design disciplines: the Leasing Plan — expressed through [[key-plans-and-tiles|Key Plans and Tiles]] — is finalized first, Building Services follows, and Structural review comes last. The rule is not new engineering; it is the naming of a discipline that already governs floor-plate composition in [[bim-floor-plate-methodology|the floor plate methodology]], where several existing tile-composition rules only make sense once the ordering is made explicit. Leasing determines what a floor earns; services and structure exist to deliver that leasing plan without degrading it. Reversing the order — designing structure or services first and fitting the leasing plan around them — routinely produces unleasable residual space, mismatched climate zones, and costly late-stage rework.

## Why leasing plan comes first

A Development Site's economic performance is set by its net leasable area and the tenant mix it can hold — both are properties of the Leasing Plan, not of the building's mechanical or structural systems. The Fixed Floor Plate System constrains every site to one of seven catalogued Floor Plates (Professional Centres; Suburban Office; Retail Select in Small/Medium/Large; Tech Industrial in Medium/Large); a site that cannot host one of the seven is passed on rather than redesigned around. That decision is made at the leasing-plan stage, before a services or structural engineer is engaged. Composition rule FP-CORE in the floor plate methodology already assumes this order: the Building Core is positioned relative to the tile layout — at least 18 m from the short end, leaving room for End Cap and Basic Tiles on each side — which requires the tile layout to exist first. Core placement is a leasing-plan-derived decision, not an independent structural one.

The external design collaborator engaged per Development Site enters this sequence downstream of the leasing plan. Their role is to develop a site-specific adaptation of the fixed prototype and to comment on the base prototype during onboarding — commenting on a prototype that already encodes a finished tile layout, not proposing one from a blank sheet.

## Services follow leasing

Building Services size themselves to the leasing plan that already exists, not the reverse. Tile-level climate zoning is the clearest example: each Tile carries its own thermostat and climate zone matched to that Tile's size, with Special Tiles given self-controlled zones. This only works if the tile boundaries are already fixed — a services engineer zoning HVAC before the tile layout exists would be zoning space that has not yet been defined, with no guarantee the boundaries survive contact with a completed leasing plan. Composition rule FP-SNAP works the same way: Special Tile width is snapped to the nearest Key Plan width specifically to preserve demising-wall continuity, meaning the services and core-adjacent tiles are dimensioned against the leasing layout, not the other way round.

An internal washroom-provisioning policy layered on top of jurisdictional building code follows the identical pattern. Washroom counts are keyed to tenant mix and daily-user foot traffic — medical, academic, and civic leaseholds each drive a different provisioning level above code minimums. Tenant mix is a leasing-plan output; the washroom program that services this mix cannot be finalized before the mix itself is known.

## Structural review comes last

Structural engagement in this sequence is reactive, not generative: it verifies that the leasing plan and the services layered on top of it are physically buildable, and it revises the structural grid only where a conflict surfaces. Composition rule FP-CORNER states this directly — when a Small-family tile lands at a structural corner, the column grid is reviewed before the tile is finalized, and the core position is adjusted if the short-side tiles conflict with it. Structure yields to the tile layout at the corner, rather than the tile layout being redrawn to suit a pre-set column grid.

A related structural discipline extends the same logic to the leasing economics directly: leasehold bay depth should be set by tenant space requirements, not by the cheapest available beam span. A structural engineer optimizing bay depth for beam economy before the leasing plan is fixed risks locking in a bay depth shallower or deeper than any tenant actually needs — and excess unleasable depth from an oversized bay cannot be recovered over the life of a lease. Structural economy is a real constraint, but it is evaluated against a leasing plan that already exists, not used to set the leasing plan's dimensions.

## What happens when the order is violated

Each of the composition rules above encodes a failure mode that surfaces when the sequence runs backward. A structural grid fixed before the leasing plan produces column corners that fight tile geometry, forcing the FP-CORNER review after the fact rather than avoiding it. Services sized to a notional floor rather than a completed tile layout produce climate zones that cross tile boundaries, undermining the tenant-autonomy pricing that tile-level climate zoning depends on. Washroom provisioning set to code minimums before tenant mix is known under-serves high-traffic leaseholds and requires retrofit once the actual mix is signed. And bay depth set to beam economy before tenant requirements are known produces unleasable structural depth that is not recoverable — the single most expensive failure mode in the sequence, because it cannot be corrected without rebuilding.

Design Sequence Priority is therefore not a scheduling convenience. It is the ordering that makes the existing tile-composition rules — FP-CORE, FP-SNAP, and FP-CORNER — internally consistent: each rule assumes a completed prior layer to design against, and each produces a documented review or adjustment step precisely at the point where a later discipline meets an earlier one.

## See also

- [[bim-floor-plate-methodology]]
- [[key-plans-and-tiles]]
- [[bim-design-philosophy]]
