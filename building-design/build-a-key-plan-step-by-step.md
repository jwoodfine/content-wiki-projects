---
schema: foundry-doc-v1
title: "Build a Key Plan, Step by Step"
slug: build-a-key-plan-step-by-step
category: building-design
type: guide
content_type: guide
quality: complete
status: pre-build
audience: operator
bcsc_class: vendor-internal
language_protocol: PROSE-GUIDE
last_edited: 2026-07-15
editor: pointsav-engineering
short_description: "A procedural walkthrough of the Key Plan method: from furniture and equipment geometry through zone sizing, Tile assembly, and Floor Plate combination."
paired_with: building-design/build-a-key-plan-step-by-step.es.md
cites: []
---

This guide walks through the procedure for building a single Key Plan and combining it, with others, into a [[bim-tile-system|Tile]] and ultimately a Floor Plate. It is a procedure, not a concept primer — for the underlying vocabulary (what a Key Plan is, why the system is geometric and self-similar, what a Tile or a Floor Plate means) see the Prerequisites below rather than this guide restating them.

Building a single Key Plan from a furniture inventory, once that inventory is in hand, is typically a one-session exercise. Grouping Key Plans into a Tile and checking the Tile against the composition rules adds a second session. Assembling a full Floor Plate — which requires running the Alternative Tiles comparison study across every tenant category on the floor — is a longer, separate exercise measured in days rather than hours, because it depends on reconciling multiple tenant categories against one shared structural grid.

## Prerequisites

Before starting, understand the following — this guide assumes the concepts below rather than explaining them:

- [[key-plans-and-tiles|Key Plans and Tiles]] — the geometric, self-similar, aperiodic system this guide builds. Read this first if the terms "Key Plan," "Tile," or "aperiodic" are unfamiliar.
- [[bim-floor-plate-methodology|Floor plate methodology]] — the composition rules (FP-SUM, FP-ENDCAP, FP-CORE, FP-SNAP, FP-CLIMATE, FP-DOORS, FP-CORNER) that a finished Floor Plate must satisfy. This guide references these rules by name; it does not restate them.
- [[bim-building-width-method|Building Width Calculator]] — the three-zone (Habitat / Magazine / Corridor) method used to size building width from furniture depth. This guide uses the calculator as a step but does not re-derive its formula or figures — consult that article directly for the zone-depth math.
- [[bim-tile-system|Tile system]] — the catalogue of Small, Medium, and Large Tile families and Special Tiles that this guide's output feeds into.
- A furniture and equipment inventory for the tenant category being planned — real dimensions for desks, workstations, treatment tables, lab benches, or equivalent, not assumed defaults. The method only works from measured geometry.

## Steps

**1. Confirm the tenant category.**
Identify which professional occupier category the Key Plan serves — Private Office, or a Professional Office sub-type (Medical, Business, Laboratory, Academic, Civic), or Corporate Office. The category determines which furniture set and which zone-depth values apply; it is the first decision because everything downstream depends on it.

**2. Take the furniture and equipment inventory.**
Measure the physical footprint of the primary equipment configuration for the confirmed category: the workstation or treatment-area footprint, the circulation clearance required on each side, and any secondary adjacency (filing, storage, or fixed equipment) that must sit within the same zone. Use real dimensions. This measurement is the geometric input to every step that follows — the method does not proceed from assumed or rounded figures.

**3. Size the three zones using the Building Width Calculator.**
Run the furniture inventory through the Building Width Calculator to establish the Zone 1 (Habitat), Zone 2 (Magazine), and Zone 3 (Corridor) depths for this tenant category. Two working notes worth carrying forward from this step, beyond what the calculator article covers:

- Zone 1's depth is not fixed once set — it can trade against Zone 2's depth, provided the furniture arrangement and circulation clearances are preserved. A wider Magazine can absorb a narrower Habitat and vice versa.
- Zone 2's minimum depth is set by whichever is larger: the staff/conference room requirement or the tenant washroom requirement. Any depth beyond that minimum is available for informal interior-design use — it is not committed to a specific function by the method itself.

**4. Assign the Key Plan letter.**
Every Key Plan in the Professional and Suburban Development Class carries a letter identifier (A through DD) tied to a specific program or room type — Private Office, a Professional Office sub-type, Corporate Office, Tenant Lounge, Building Manager Office, Mail Room, corridors, restrooms, or a Main Floor amenity space (loading, recycling, bike room, coffee/bread service). Assign the letter that matches the program identified in Step 1. This letter is the Key Plan's permanent reference for every later assembly step.

**5. Check washroom and shared-room minimums against the Key Plan tier.**
If the Key Plan includes a tenant washroom, confirm the fixture count matches the configuration already documented for that tenant category's own Key Plan article — for example, Business runs a flat 2-stall count across its five washroom configuration options, not a count that scales with tile tier. Do not assume a fixture count scales by Small/Medium/Large tier unless the category's own article states that it does. This is one of the two constraints (with the staff/conference room) that sets Zone 2's minimum depth in Step 3 — verify it here before moving on, since correcting it later means re-running Step 3.

**6. Group Key Plans into a Tile.**
Combine the Key Plan (or Key Plans, for a Compound Tile) into a single Tile. Confirm the one-Tile-one-climate-zone rule: every Key Plan inside a Tile shares one HVAC/thermostat control, and no Tile may be split across two Climate Zones. Smaller tenants generally favor smaller Tiles for this reason — a smaller Tile means the tenant is not sharing climate control with a neighbor.

**7. Select the Tile family matching the assembled square footage.**
Match the assembled Key Plan total against the Small, Medium, or Large Tile family (see [[bim-tile-system|Tile system]] for the family catalogue). Smaller tenants who want climate-zone autonomy select smaller families; larger, contiguous-space tenants accept a larger family in exchange for fewer zones.

**8. Treat corner and end-cap Tiles separately.**
A Tile positioned at a building corner or an end condition is not a plain resize of a mid-building Tile of the same size class — it requires its own door-placement and natural-light treatment. Confirm the end-cap variant receives natural light on both perpendicular axes; a worked comparison of Professional Office and Private Office end-cap layouts shows that an end cap without natural light on both axes is not 100% efficient in leasehold terms. If a corner condition also lands a Small-family Tile at a structural bay, flag it for a structural-grid review before finalizing — Small Tiles can conflict with the structural module at a corner.

**9. Position Special Tiles around the Building Core.**
Special Tiles fill the residual area adjacent to the Building Core. Place them so that:

- A tenant occupying an entire short side of the building retains full control of one Climate Zone.
- No door in a core-adjacent Special Tile aligns directly opposite the elevator opening.
- Any mismatch between the aggregate square footage of the Key Plans already assembled and the Special Tile's own square footage is reconciled by adjusting the Special Tile, not by leaving a gap.

**10. Assemble Tiles, Special Tiles, and the Building Core into the Floor Plate.**
Sum the Basic Tiles, Compound Tiles, Special Tiles, and the Building Core. The total should reconcile with the Net Leasable Area for the Floor Plate (see FP-SUM in the [[bim-floor-plate-methodology|floor plate methodology]]) — this guide does not restate that rule's tolerance band, only that the check happens here, at final assembly, not earlier.

**11. Expand the Floor Plate by adding bays, not by stretching one.**
If the assembled Floor Plate needs to be larger than the tenant mix requires, add a staggered offset structural bay to the plate. Do not stretch an existing bay to gain area — the method treats bay-stretching and bay-addition as distinct operations, and only the latter preserves the aperiodic tile geometry established in Steps 6–9.

**12. Run the Alternative Tiles comparison study before finalizing.**
Before treating any specific combination of Tiles as final, compare it against the study's four base combinations (Tiles A through D, spanning Private Office through Corporate Office scale) plus their corner and end-cap variants. The study exists to identify which combination yields the most efficient, flexible Tile set for the tenant mix on this floor — a single combination chosen without this comparison has not been checked against the alternatives the method is built to weigh.

## Verification

Confirm the following before treating a Key Plan → Tile → Floor Plate assembly as complete:

- The aggregate square footage of Basic Tiles + Compound Tiles + Special Tiles + the Building Core reconciles with the Net Leasable Area (FP-SUM).
- No door in a core-adjacent Special Tile is directly opposite the elevator opening.
- Every tenant occupying a full short side of the building retains control of exactly one Climate Zone — no tenant's HVAC control is split across two Tiles.
- Washroom fixture counts match the configuration documented for that tenant category's own Key Plan article (fixture counts do not necessarily scale by Small/Medium/Large tier — confirm against the category's own source rather than assuming a scaling pattern).
- Every end-cap Tile receives natural light on both perpendicular axes.
- Demising lines fall on Tile boundaries, not on ad hoc cuts — this is what allows 100% leasing efficiency to be recaptured whenever a tenant vacates ("rolling efficiency").
- Any Small-family Tile landing at a structural corner has been through a structural-grid review.

**One open condition to flag, not resolve, at verification:** a tenant may lease space that crosses a Tile boundary provided the demising walls still align to Tile boundaries — but doing so forfeits single-zone Climate Zone control for that tenant. The methodology notes this condition is currently unresolved by Building Services design. Do not treat a cross-boundary lease as routine; flag it for Building Services review rather than assuming the standard Tile assembly rules cover it.

## Next steps

- Consult [[bim-floor-plate-tile-combinations|floor-plate tile combinations]] for worked examples of finished assemblies at each Floor Plate class.
- Read [[bim-zone-depths-per-use-type|zone depths per use type]] if the tenant category in Step 1 is one where Zone 1/Zone 2/Zone 3 figures are still marked pending in the Building Width Calculator article.
- If the Floor Plate under design mixes tenant categories with materially different building-width requirements (for example, a Medical anchor alongside a Private Office cluster), review the reconciliation guidance in [[bim-building-width-method|Building Width Calculator]] before finalizing Step 10.
- Route any cross-boundary leasing question surfaced in Verification to Building Services before the lease is finalized — this guide does not resolve that open condition.
