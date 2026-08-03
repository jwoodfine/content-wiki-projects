---
schema: foundry-doc-v1
title: "Key Plan development methodology"
slug: key-plan-development-methodology
category: building-design
type: topic
content_type: topic
quality: complete
status: pre-build
audience: operator
bcsc_class: vendor-internal
language_protocol: PROSE-TOPIC
last_edited: 2026-08-03
editor: pointsav-engineering
short_description: "How an individual Key Plan is developed from furniture and equipment geometry and combined, with others, into a Tile and a Floor Plate — tenant category and zone sizing, the letter identifier scheme, washroom minimums, Tile family selection, corner and end-cap treatment, Special Tiles, and the Alternative Tiles comparison study."
aliases:
  - build-a-key-plan-step-by-step
paired_with: building-design/key-plan-development-methodology.es.md
cites: []
---

Key Plan development is the process that turns a tenant's furniture and equipment inventory into an assembled [[bim-tile-system|Tile]] and, combined with the other Tiles on a floor, a Floor Plate. It sits one level below [[bim-floor-plate-methodology|floor plate methodology]], whose FP-* composition rules (FP-SUM, FP-ENDCAP, FP-CORE, FP-SNAP, FP-CLIMATE, FP-DOORS, FP-CORNER) govern what a finished Floor Plate must satisfy — this article covers how an individual Key Plan is built and carried through composition toward that end, not the composition rules themselves. It assumes the vocabulary set out in [[key-plans-and-tiles|Key Plans and Tiles]] — what a Key Plan, Tile, or Floor Plate is, and why the system is geometric, self-similar, and aperiodic — and uses the [[bim-building-width-method|Building Width Calculator]]'s three-zone method as one stage in the sequence, without re-deriving its formula or figures.

The three stages differ in scale. Developing a single Key Plan from a furniture inventory, once that inventory is in hand, is typically a one-session exercise. Grouping Key Plans into a Tile and checking the Tile against the composition rules adds a second session. Assembling a full Floor Plate — which requires running the Alternative Tiles comparison study across every tenant category on the floor — is a longer, separate exercise measured in days rather than hours, because it depends on reconciling multiple tenant categories against one shared structural grid.

## Tenant category and furniture geometry as the starting point

Every Key Plan begins with the professional occupier category it serves — Private Office, a Professional Office sub-type (Medical, Business, Laboratory, Academic, Civic), or Corporate Office. This category is confirmed first because it determines which furniture set and which zone-depth values apply; everything downstream depends on it. From there, the method requires the physical footprint of the primary equipment configuration for that category — the workstation or treatment-area footprint, the circulation clearance required on each side, and any secondary adjacency (filing, storage, or fixed equipment) that must sit within the same zone. This footprint has to come from real measured dimensions for desks, workstations, treatment tables, lab benches, or their equivalents. The method does not proceed from assumed or rounded figures — the furniture inventory is the geometric input that every later stage traces back to.

## Sizing the three zones

The furniture inventory is run through the [[bim-building-width-method|Building Width Calculator]] to establish the Zone 1 (Habitat), Zone 2 (Magazine), and Zone 3 (Corridor) depths for the tenant category in question. Two properties of this sizing are worth carrying forward beyond what the calculator article itself covers:

- Zone 1's depth is not fixed once set — it can trade against Zone 2's depth, provided the furniture arrangement and circulation clearances are preserved. A wider Magazine can absorb a narrower Habitat and vice versa.
- Zone 2's minimum depth is set by whichever is larger: the staff/conference room requirement or the tenant washroom requirement (see below). Any depth beyond that minimum is available for informal interior-design use — the method itself does not commit it to a specific function.

## The Key Plan letter identifier

Every Key Plan in the Professional and Suburban Development Class carries a letter identifier (A through DD) tied to a specific program or room type — Private Office, a Professional Office sub-type, Corporate Office, Tenant Lounge, Building Manager Office, Mail Room, corridors, restrooms, or a Main Floor amenity space (loading, recycling, bike room, coffee/bread service). The letter assigned matches the program identified by the tenant category above, and functions as the Key Plan's permanent reference through every later stage of assembly.

## Washroom and shared-room minimums

Where a Key Plan includes a tenant washroom, the fixture count follows the configuration already documented for that tenant category's own Key Plan article, rather than any general rule — Business, for example, runs a flat 2-stall count across its five washroom configuration options, a count that does not scale with Tile tier. A fixture count should not be assumed to scale by Small/Medium/Large tier unless the category's own article states that it does. This washroom requirement is one of the two constraints — together with the staff/conference room requirement — that sets Zone 2's minimum depth above; getting it wrong is costly precisely because it forces the zone-sizing stage to be re-run.

## Grouping Key Plans into a Tile

Key Plans combine — a single Key Plan, or several for a Compound Tile — into a Tile under the one-Tile-one-climate-zone rule: every Key Plan inside a Tile shares one HVAC/thermostat control, and no Tile may be split across two Climate Zones. This is why smaller tenants generally favor smaller Tiles — a smaller Tile means the tenant is not sharing climate control with a neighbor. The assembled Key Plan total is then matched against the Small, Medium, or Large [[bim-tile-system|Tile family]]: smaller tenants who want climate-zone autonomy select smaller families, while larger, contiguous-space tenants accept a larger family in exchange for fewer zones.

## Corner and end-cap Tiles

A Tile positioned at a building corner or an end condition is not a plain resize of a mid-building Tile of the same size class — it carries its own door-placement and natural-light treatment. The end-cap variant needs natural light on both perpendicular axes; a worked comparison of Professional Office and Private Office end-cap layouts shows that an end cap without natural light on both axes falls short of 100% efficiency in leasehold terms. Where a corner condition also lands a Small-family Tile at a structural bay, this is flagged for a structural-grid review before finalizing, since Small Tiles can conflict with the structural module at a corner.

## Special Tiles and the Building Core

Special Tiles fill the residual area adjacent to the Building Core, positioned so that a tenant occupying an entire short side of the building retains full control of one Climate Zone, no door in a core-adjacent Special Tile aligns directly opposite the elevator opening, and any mismatch between the aggregate square footage of the Key Plans already assembled and the Special Tile's own square footage is reconciled by adjusting the Special Tile rather than leaving a gap.

## Assembling the Floor Plate

The Basic Tiles, Compound Tiles, Special Tiles, and the Building Core sum to the Floor Plate, and this total is checked against the Net Leasable Area for the Floor Plate at this final-assembly stage — the FP-SUM tolerance band itself belongs to [[bim-floor-plate-methodology|floor plate methodology]], not here. Demising lines are expected to fall on Tile boundaries rather than ad hoc cuts, which is what allows 100% leasing efficiency to be recaptured whenever a tenant vacates — a property referred to as rolling efficiency.

Where an assembled Floor Plate needs to be larger than the tenant mix requires, the method adds a staggered offset structural bay rather than stretching an existing one. Bay-stretching and bay-addition are treated as distinct operations, and only bay-addition preserves the aperiodic Tile geometry established during Tile grouping and Special Tile placement above.

## The Alternative Tiles comparison study

Before any specific combination of Tiles is treated as final, it is compared against the study's four base combinations (Tiles A through D, spanning Private Office through Corporate Office scale) plus their corner and end-cap variants. The study exists to identify which combination yields the most efficient, flexible Tile set for the tenant mix on a given floor — a combination chosen without this comparison has not been checked against the alternatives the method is built to weigh.

## An unresolved condition: cross-boundary leasing

A tenant may lease space that crosses a Tile boundary, provided the demising walls still align to Tile boundaries — but doing so forfeits single-Climate-Zone control for that tenant. This condition is currently unresolved by Building Services design, and is treated as an exception to route to Building Services review rather than as a variant the standard Tile assembly rules already cover.

## See also

- [[key-plans-and-tiles]]
- [[bim-floor-plate-methodology]]
- [[bim-building-width-method]]
- [[bim-zone-depths-per-use-type]]
- [[bim-floor-plate-tile-combinations]]
- [[bim-tile-system]]
