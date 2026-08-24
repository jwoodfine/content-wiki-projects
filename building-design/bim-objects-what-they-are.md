---
schema: foundry-doc-v1
title: "BIM objects — what they are"
slug: bim-objects-what-they-are
language: en
category: building-design
index_group: bim-objects-and-the-digital-record
type: topic
content_type: topic
status: active
last_edited: 2026-08-24
editor: pointsav-engineering
short_description: "A BIM Object is Woodfine's term for a reusable building-element specification that carries its applicable code and performance requirements with it, so non-compliant configurations are caught at design time rather than at inspection."
cites: [ifc-4-3]
paired_with: building-design/bim-objects-what-they-are.es.md
aliases:
  - bim-token-what-it-is
---

Building Information Modelling produces detailed digital representations of a structure, but a standard BIM model does not by itself prevent code violations — a model can be geometrically complete and still fail a jurisdiction's requirements, discovered only when a compliance check runs after the fact. A **BIM Object** is Woodfine's term for a building-element specification designed to carry its applicable code and performance requirements with it from the moment it's placed, so a violation is caught in the design itself rather than at a later inspection. See [[bim-design-philosophy]] for why this approach matters for a building's compliance risk and long-term value.

## What distinguishes a BIM Object

A BIM Object differs from the building blocks it might be mistaken for. It is not a raw IFC entity type (which defines a data shape but carries no jurisdiction-specific requirements). It is not a proprietary, vendor-locked model-authoring format. It is not after-the-fact facility-management data captured once a model is complete. It combines three things at once: what the element is, what regulatory requirements it must satisfy in its jurisdiction, and what performance requirements it must meet for its climate zone — bundled into one reusable specification unit rather than checked separately after design.

## Where the specification lives

The full data model — the object schema, the three-layer composition structure, the file format, and the implementation detail behind how this actually works — is maintained directly at [bim.woodfinegroup.com](https://bim.woodfinegroup.com).

## See also

- [[bim-design-philosophy]] — why this pre-constraining approach matters, and what it replaces
- [[bim-objects-three-layers]] — the three-layer structure a BIM Object carries
- [[design-system-bim]] — the broader Building Design System this fits within
