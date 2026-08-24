---
schema: foundry-doc-v1
title: "GIS cluster scoring glossary"
slug: gis-cluster-scoring-glossary
category: reference
index_group: glossaries
type: topic
content_type: topic
quality: complete
short_description: "Glossary of the anchor taxonomy, tier definitions (Regional, District, Local, Fringe), predicate gates, and radius convention used in the Woodfine geographic co-location scoring system."
status: stable
bcsc_class: current-fact
last_edited: 2026-08-24
editor: pointsav-engineering
language_protocol: PROSE-TOPIC
source_refs:
  - "bfe6fb6bbb557fd15bdb7ffd53bce60e527911eb7658c906df5b69813bdb8747"
  - "42cddb0e1bbd6516c578dbfe4a48f5ff2fd084529ef9adeaf09612c3bd36a5e1"
paired_with: gis-cluster-scoring-glossary.es.md
cites: []
---

These terms appear in co-location dataset reports, GIS coverage communications, and site selection materials prepared for review by the Independent Directors of the General Partner. This glossary defines the terminology of MCorp's [[geographic-co-location-methodology|geographic co-location scoring system]]: the anchor taxonomy, the four-tier classification, the predicate gates that assign each tier, and the radius convention behind the non-overlap gate.

## Anchor taxonomy

Every scored cluster forms around a store from one of four anchor classes. **Hypermarket** anchors are general-merchandise chains such as Walmart, Target, Mercadona, and Tesco. **Lifestyle** anchors are large-format home-and-furnishings retailers; IKEA is the only chain in this class. **Hardware** anchors are home-improvement chains such as Home Depot, Lowe's, and Leroy Merlin. **Warehouse** anchors are membership warehouse clubs such as Costco, Sam's Club, and Makro. A cluster's composition — which anchor classes co-locate at one node — is the first input to tier assignment. The full chain-to-family mapping is documented in the [[retail-brand-family-taxonomy|retail brand family taxonomy]].

## Tier definitions

The current scoring system assigns each cluster to one of four tiers, following the retail property hierarchy used by the International Council of Shopping Centres: **Regional**, **District**, **Local**, and **Fringe**. Regional is the highest tier; Fringe holds any cluster that clears none of the qualifying gates. This tier system replaced an interim points-based scale on 2026-05-16 — the earlier scale, and the T1/T2/T3 numeric labels attached to it, is retired and does not describe any current cluster. See [[co-location-tier-nomenclature|the tier nomenclature]] for the full naming history.

## Predicate gates

A cluster earns a tier by clearing every required gate for that tier, not by accumulating points toward a threshold. Four gate families apply: **composition** (which anchor classes are present), **catchment rank** (the cluster's population percentile within its own country), **civic** (a hospital of the required classification within the surrounding ring), and **non-overlap** (the cluster is not dominated by a stronger cluster nearby, measured by the radius convention below). The full gate tables are published at gis.woodfinegroup.com; this glossary defines the concepts, not the pass/fail thresholds.

## Radius convention

Clusters are compared for overlap using a fixed 3.0 km radius disk centred on each cluster. Two clusters compete for the same node when the overlap between their disks — measured as intersection over union — exceeds the non-overlap gate's limit; the weaker cluster is then held below the tier its composition would otherwise earn. This single radius convention replaced an earlier scheme of separate 1.0 km and 5.0 km proximity thresholds; the earlier scheme does not apply to any current tier.

## Dataset output metrics

**Composition descriptor** — The anchor classes present at a cluster, shown as a plain-language label such as "Hypermarket + Hardware + Warehouse." **Catchment rank** — A cluster's percentile position by population within its own country; a cluster in the top 10% nationally clears the strictest catchment gate. **Scored cluster** — Any geo-located node that has been evaluated against the anchor taxonomy and assigned a tier. The term appears in GIS coverage reports to describe the total count of evaluated nodes in a given geography.
