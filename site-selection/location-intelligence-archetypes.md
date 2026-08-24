---
schema: foundry-doc-v1
title: "Location intelligence co-location archetypes"
slug: location-intelligence-archetypes
category: site-selection
index_group: the-method
type: topic
content_type: topic
quality: complete
status: active
audience: customer-woodfine
bcsc_class: current-fact
language_protocol: PROSE-TOPIC
last_edited: 2026-07-11
editor: pointsav-engineering
short_description: "Three co-location archetypes — Retail Centres (PRO), Urban Fringe (VWH), and Commuter (PKS) — identifying distinct commercial clustering patterns across 17 countries in North America and Europe."
paired_with: site-selection/location-intelligence-archetypes.es.md
---

The Location Intelligence platform identifies retail and commercial gravity
through three co-location archetypes: Retail Centres (PRO), Urban Fringe
(VWH), and Commuter (PKS). Each archetype describes a distinct clustering
pattern that reflects a different type of commercial activity and a different
relationship to the surrounding urban geography.

The three-letter codes were ratified on 1 June 2026.

## The three archetypes

| Code | Name | Anchor type | Status |
|------|------|-------------|--------|
| **PRO** | Retail Centres | Grocery hypermarket with hardware and at least one of: price club, lifestyle, or electronics | Live — T1/T2/T3 co-location pipeline |
| **VWH** | Urban Fringe | Hardware + trade-supply ecosystem (MRO, tool rental, builders merchant, auto parts) | Live — production co-location pipeline across three tiers |
| **PKS** | Commuter | Regional transit anchor (airport, rail, bus) + park-and-ride + car rental/hotel enrichment | Live — production co-location pipeline across three tiers |

PRO is the base map product — the foundation of the site-selection dataset.
VWH and PKS are overlay archetypes that identify adjacent market structures
not captured by grocery-anchored clustering.

---

## PRO — Retail Centres

PRO clusters represent grocery-anchored commercial co-locations at three
scales. The pipeline groups anchor-category retail locations that fall within
a defined span distance, then assigns each group to one of three tiers based
on anchor composition.

### Tier definitions

**T1 — Regional:** A cluster containing a grocery hypermarket and a hardware
retailer, plus at least one of a price club, lifestyle retailer, or electronics
retailer. Alternatively: four or more anchor-category retailers in a tight
cluster, or three or more anchors in any tight cluster.

**T2 — District:** A cluster containing a grocery hypermarket and a hardware
retailer, within a wider district-level span.

**T3 — Local:** All remaining anchor pairs that do not qualify for T1 or T2.

### Current dataset

The current production dataset spans thousands of PRO clusters across all
three tiers, covering 17 display countries across North America and Europe.
Tier boundaries are periodically re-tuned as the underlying retail footprint
changes; the T2 district radius has been tightened in successive rebuilds
relative to earlier phases.

---

## VWH — Urban Fringe

VWH clusters identify concentrations of hardware and industrial-supply
retailers in the absence of grocery anchors. These sites occupy the urban
fringe — a band of distance beyond the immediate metro core but short of
standalone-market territory — and tend to cluster around highway interchanges
in areas with adjacent industrial landuse.

### Definition

A VWH candidate is a location where one or more hardware retailers are
present, no grocery hypermarket is within the cluster span, and the site
sits within the Urban Fringe metro-distance band. The typical built form is a
multi-storey warehouse or light-manufacturing building, distinct from the
one-storey big-box format of the retail park.

VWH locations serve trades contractors, light-manufacturing operators,
and just-in-time logistics tenants — not general retail consumers.

### Co-location signals

**Essential:**

| Signal | Rationale |
|--------|-----------|
| Highway interchange nearby | Truck ingress and egress |
| Sufficient population within a short drive | Manufacturing and logistics labour |
| Industrial landuse adjacent | Zoning compatibility |

**Significant:**

| Signal | Rationale |
|--------|-----------|
| Air cargo airport within reach | Electronics and components, rapid replenishment |
| Freight rail nearby | Just-in-time component delivery |
| Transit corridor nearby | Workforce access |

**Disqualifying:** Dense residential immediately adjacent; flood plain;
heritage conservation zone; location inside a PRO cluster.

### Production status

The VWH pipeline is production-grade. Hardware stores were profiled as
proxy anchors, and the trade-supply clustering was validated against
held-out hardware-anchor data, with an internally set acceptance threshold
for cluster quality that the production build clears.

The dataset spans thousands of clusters across the 17 display countries,
concentrated most heavily in the United States with meaningful coverage
across several other North American and European markets.

Clusters are distributed across the three tiers in the expected shape: a
small minority reach the Full Trade Hub tier, a larger share reach the
Established tier, and the majority sit in the Emerging/Thin tier. That
T3-heavy distribution is expected — a full trade hub combining MRO, tool
rental, builders merchant, and auto parts is a legitimately rare
combination.

A quality-control flag marks clusters that sit close enough to a grocery
hypermarket to be considered dual-use commercial parks — valid VWH
co-locations that also include grocery retail.

---

## PKS — Commuter

PKS clusters identify commercial concentrations near regional airports and
intercity train stations that sit in a Commuter belt beyond the immediate
metro core but short of standalone-market distance. The defining demand
pattern is park-and-fly or park-and-train travel: residents of a Regional
Market drive to a transit node, park, and travel to the Metro Market.

### Definition

A PKS candidate is a regional transit node — airport or intercity train
station — within the Commuter metro-distance band. Nodes closer than that
band are classified as suburban rather than regional; nodes beyond it are
considered standalone markets with a separate metro relationship.

The defining commercial signal at a PKS location is car rental. Auto parts,
fuel stations, quick-service restaurants, and convenience stores are
secondary signals.

### Co-location signals

**Essential:**

| Signal | Rationale |
|--------|-----------|
| Regional transit anchor nearby | Airport or intercity station with direct metro service |
| Metro isolation within the Commuter band | Defines the regional relationship |
| PRO T1 or T2 cluster nearby | Same population generates parking demand |
| Sufficient regional population | Minimum demand for multi-storey parking |

**Significant:**

| Signal | Rationale |
|--------|-----------|
| Car rental nearby | Arriving travellers require transport |
| Hotel cluster nearby | Business travel and multi-day parking |
| Second transit mode nearby | Multi-modal integration |

**Disqualifying:** Major hub within the immediate metro core; population
below a minimum viable threshold; no direct metro service.

### Production status

The PKS pipeline is production-grade. Park-and-ride records serve as the
primary geographic anchor — actual car-to-transit transition points
distributed independently of rail network geometry. Transit modes are
enrichment signals; car rental and hotel presence define commercial
maturity. Related transit-mode categories are grouped together before
tiering, to prevent related modes from inflating an apparent multi-modal
signal.

Clusters are distributed across three tiers. A Regional Hub tier combines
multi-modal access with a full commercial ecosystem. A Transit Interchange
tier combines transit with at least one commercial signal. A larger Transit
Node tier is where transit is present but commercial opportunity remains to
be proven out.

Commercial enrichment draws on major car rental and hotel chains active in
each market, ingested and reflected in the production build.

### Major hub filter

Airports adjacent to a major PRO retail cluster are excluded as likely major
commercial hubs. Major airports generate their own retail gravity and do not
exhibit the park-and-transit pattern. The filter correctly removes hubs such
as LAX, JFK, LHR, and CDG.

### Future enhancements

- Airport passenger volume data (CAPA or IATA) to replace the current
  adjacency-based hub proxy with a direct traffic-based classifier
- Parking operator directory: Q-Park, APCOA, NCP, Indigo/Vinci (EU); SP+ (US)

---

## Map integration

VWH and PKS appear as overlay layers under the **★ Regional Markets** section
in the layer control panel.

**VWH toggle** — displays orange dots at Urban Fringe candidate locations.
When active, cluster bubbles fade to reduce visual interference.

**PKS toggle** — displays teal dots at integrated candidates (near a PRO
T1/T2 cluster) and grey dots at standalone candidates. The same bubble
fade applies.

Both layers persist across view transitions — the fade state is maintained
when switching between the Retail View and the BentoBox market detail panel.

## See also

- [[co-location-methodology|Co-location Methodology]] — the anchor-composition scoring that drives PRO tier assignment
- [[co-location-ranking-system|Co-location Ranking System]] — the five-rank commercial density index that ranks PRO clusters
- [[about-regional-markets-system|Regional Markets Intelligence System]] — the 400-market ranking built on PRO cluster data
- [[atlas-top-400-north-america|Top 400 Regional Markets — North America]] — ranked list of suburban-regional PRO markets in NA
- [[atlas-top-400-europe|Top 400 Regional Markets — Europe]] — ranked list of suburban-regional PRO markets in EU
- [[od-catchment-methodology|O-D Catchment Methodology]] — how catchment zones are measured around each cluster centroid

## Data Sources

Map and location data © [OpenStreetMap contributors](https://www.openstreetmap.org/copyright) / [ODbL](https://opendatacommons.org/licenses/odbl/).
