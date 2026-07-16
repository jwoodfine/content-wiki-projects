---
schema: foundry-doc-v1
title: "TOP600 North America — Regional Market index"
slug: atlas-top-600-north-america
category: markets
type: topic
content_type: topic
quality: stub
status: active
audience: customer-woodfine
bcsc_class: current-fact
language_protocol: PROSE-TOPIC
keynote: false
last_edited: 2026-07-11
editor: woodfine-editorial
short_description: "Index of up to 600 regional commercial real estate markets across North America screened for co-location viability."
paired_with: markets/atlas-top-600-north-america.es.md
---

The **TOP600 North America** index identifies up to 600 regional commercial real estate markets
across the United States, Canada, and Mexico meeting the population, income, and retail
infrastructure thresholds established by the [[about-regional-markets-system|co-location regional market]]
framework. The index provides the geographic foundation for direct-hold site selection and
market monitoring, prioritising cities and metropolitan areas outside major-metro central
business districts where co-location professional centre deployments are viable.

## Scope and classification

A regional market qualifies for inclusion when it meets three primary screens:

**Population range.** The metropolitan or census agglomeration population is typically between
50,000 and 500,000. This range captures markets large enough to sustain national retail
infrastructure and professional demand, while remaining below the legacy-office-oversupply
dynamics that characterise major-metro central business districts.

**Disposable income signal.** Household disposable income is sufficient to sustain at minimum
two national anchors — one warehouse club format and one home-improvement or general
merchandise superstore. National retailer site-selection is treated as an independent
corroboration of local income and demand conditions.

**Power centre investment.** Confirmed power centre development within the market boundary
provides physical infrastructure compatible with professional centre co-location. Markets with
no power centre investment are deferred.

Markets meeting all three screens are scored using the [[co-location-ranking-system|co-location ranking system]]
and assigned a rank within the North American index.

## Geographic coverage

The index covers markets across:

- **United States** — the largest market count, spanning all major census regions
- **Canada** — markets concentrated in Ontario, Alberta, British Columbia, and Quebec, with secondary representation in the Atlantic and Prairie provinces
- **Mexico** — targeted coverage of OECD-income-level metropolitan markets in the central and western regions

Country-level sub-indexes provide ranked market tables for each jurisdiction.

**Flag, not resolved (2026-07-16):** a fresh handoff from Command describes project-gis's
live `score-regional-markets.py` tool outputting to a file literally named `rm-top600.json`,
with `top400` as a filtered tier within it and a separate "buffer" tier (NA 20, EU 63)
below the published cutoff — suggesting a live, real TOP600-named system exists at the tool
level, not the dead/abandoned scaffolding an earlier reading of this stub article alone
suggested. Whether that live tiering (top400 + buffer) is the same methodology this stub
describes (population 50,000–500,000, disposable-income + power-centre screens) or a
different, complementary one is not yet reconciled — needs the actual seed-data file
(referenced in the Command handoff but not yet landed) before this article is rewritten or
marked superseded either way.

## Relationship to the global market framework

The TOP600 North America index is one component of a planned global market framework
targeting coverage of up to 600 regional markets per major continent or economic zone. The
complementary [[atlas-top-600-europe|TOP600 Europe]] index applies equivalent screens to European
markets. Together these two indexes represent the primary geographic scope of planned
direct-hold deployment activity.

## Country sub-indexes

| Country | Sub-index article |
|---|---|
| Canada | [[atlas-canada|Canada — Regional Market Index]] |
| United States | [[atlas-united-states|United States — Regional Market Index]] |
| Mexico | Planned |

## See also

- [[about-regional-markets-system]] — the co-location framework that defines market selection criteria
- [[atlas-top-600-europe]] — the complementary European regional market index
