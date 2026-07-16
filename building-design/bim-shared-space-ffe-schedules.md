---
schema: foundry-doc-v1
title: "Building-core shared-space furniture and fixture schedules"
slug: bim-shared-space-ffe-schedules
short_description: "Furniture, Fixtures, and Equipment (FFE) schedules for the five building-wide shared-space components — Loading and Recycling, Upper Floors Building Core, Public Lobby Washroom, Auxiliary Structure, and Building Manager Office plus Mail Room — and how the Availability per Tile coefficient ties each schedule's furniture load back to Tile size."
category: building-design
type: topic
content_type: topic
quality: complete
status: pre-build
audience: operator
bcsc_class: vendor-internal
language_protocol: PROSE-TOPIC
last_edited: 2026-07-15
editor: pointsav-engineering
paired_with: building-design/bim-shared-space-ffe-schedules.es.md
cites: []
---

**Building-Core Shared-Space FFE Schedules** are the five Furniture, Fixtures, and Equipment (FFE) schedules in the Key Plan workbook that furnish building-wide shared infrastructure, as distinct from a single tenant suite: Loading and Recycling, Upper Floors — Building Core, Public Lobby Washroom, Auxiliary Structure, and Building Manager Office + Mail Room. Where the [[bim-key-plans-index|Key Plans index]] catalogues these spaces by Development Class, Typology, and index code, this article inventories the furniture and fixture content that fills them and explains how the workbook's Availability per Tile coefficient ties each schedule's furniture load back to the [[bim-tile-system|Tile]] that hosts it. Of the workbook's thirteen per-space FFE schedules, these five are the building-wide set; the remaining eight — Business, Academic, Medical, Labs, Civic, and Private Office — are tenant-specific and are catalogued separately.

## Loading and Recycling

The Loading and Recycling schedule furnishes the building's freight and waste-handling function: loading-dock doors, refuse and recycling bin banks sorted by stream, and the adjoining Bike Room. In the [[bim-key-plans-index|Key Plans index]], these three functions correspond to three separate Professional Centre index entries — Loading (X-1), Recycling (Y-1), and Bike Room (Z-1) — each carrying its own index row even though the FFE workbook groups them into a single furnished schedule. The Suburban Office class repeats the same vocabulary under the "-2" suffix.

## Upper Floors — Building Core

The Upper Floors — Building Core schedule furnishes the vertical circulation and building-systems spine that repeats on every floor above grade: the elevator lobby, the service staircase, a floor-level washroom, and the meter room. The Elevator Lobby (S-1) and Tenant Restroom (U-1) entries in the Key Plans index name the leasable-adjacent components; the Meter Room (V-1) is indexed separately in the General class (Index 25) as a Special Tile, reflecting that it is a residual-area fixture rather than a leasable Key Plan. This schedule is the one most directly tied to Tile geometry: the elevator lobby and its front apron are sized against the [[bim-tile-system|Tile system]]'s Special Tile SP-C (approximately 4,700 SF), while the meter room and core-adjacent filler areas draw on the smaller SP-A and SP-B Special Tile classes rather than the regular Small/Medium/Large tenant tile families.

## Public Lobby Washroom

The Public Lobby Washroom schedule furnishes the ground-floor washroom serving building visitors and lobby traffic, distinct from the per-floor Tenant Restroom (U-1) covered under Upper Floors — Building Core. In the Key Plans index this maps to the Public Restrooms entry (DD-1), one of the thirteen Professional Centre amenity codes (Index 26–38). Fixture counts scale with lobby traffic volume rather than with tenant headcount, which is why the workbook treats it as a standalone schedule rather than folding it into the per-floor washroom count.

## Auxiliary Structure

The Auxiliary Structure schedule furnishes exterior and back-of-house site infrastructure that supports the building but sits outside its leasable envelope: the garbage enclosure, transformer pads, and a landscaping shed. None of these three components currently carries a distinct entry in the [[bim-key-plans-index|Key Plans Directory]] — the Directory's Landscaping class (Index 59–62) covers Bioswales and the Irrigation Gallery, a related but separate site-landscaping scope. Auxiliary Structure is accordingly the one building-core FFE schedule without a one-to-one Key Plan index code; closing that gap is an open item for the Directory, not a defect in this schedule.

## Building Manager Office + Mail Room

The Building Manager Office + Mail Room schedule furnishes the building's on-site administrative and logistics staff: management and assistant furniture sets for the Building Manager Office, a mail-room-supervisor set for the Mail Room, and a night-watch set covering after-hours coverage. The Key Plans index carries the Building Manager (O-1) and Mail Room (P-1) entries as separate Professional Centre codes; the FFE workbook combines them into one furnished schedule because the two functions typically share a single back-of-house suite. The Tenant Lounge (N-1) and Lobby Atrium (EE-1) codes sit adjacent to this pairing in the index but are furnished under a different schedule; Building Staff Lockers (BB-1) and Workbench (AA-1) are the maintenance-staff equivalents and also fall outside this schedule's scope.

## Availability per Tile — the sizing coefficient

Availability per Tile is the methodology coefficient the workbook records on every per-space FFE schedule, tenant and building-core alike: the fraction of a Tile's floor area left unallocated once that schedule's furniture is placed. On the tenant-tier schedules already published, the pattern is legible — Business, Academic, and Civic run 0.2 / 0.6 / 0.2 across Small / Medium / Large; Medical and Labs run 0.4 / 0.4 / 0.2; Private Office, the sparsest schedule, runs 0.8 / 0.1 / 0.1. A lower Availability figure signals a more furniture-dense tier relative to its Tile footprint, and the coefficient is what lets the [[bim-tile-system|Tile system]] validate that a proposed furniture layout actually fits the Tile it is assigned to, rather than merely approximating it by square footage.

The building-core schedules in this article sit on Special Tiles (SP-A, SP-B, SP-C) rather than the regular Small/Medium/Large families the tenant-tier coefficients above describe, and the source workbook does not carry filled Availability values against any of the five building-core schedules specifically. Confirming per-schedule Availability for Loading and Recycling, Upper Floors — Building Core, Public Lobby Washroom, Auxiliary Structure, and Building Manager Office + Mail Room is an open item against the Key Plan workbook, not yet resolved by this extraction pass.

## See also

- [[bim-key-plans-index]]
- [[bim-tile-system]]
- [[bim-zone-depths-per-use-type]]
