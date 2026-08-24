---
schema: foundry-doc-v1
title: "Three-dimensional asset token"
slug: 3d-asset-tokens
category: building-design
type: topic
content_type: topic
status: stub
audience: customer-woodfine
bcsc_class: current-fact
language_protocol: PROSE-TOPIC
last_edited: 2026-08-24
editor: pointsav-engineering
short_description: "The archive's unit of stored data, combining an immutable binary payload, machine-readable metadata skeleton, and live taxonomic graph connection encoding provenance and context."
paired_with: building-design/3d-asset-tokens.es.md
cites: []
---

A three-dimensional asset token is the archive's unit of stored data, combining an immutable binary payload, a machine-readable metadata skeleton, and a live taxonomic graph connection that encodes provenance and context.

## Structure

Each token has three components: a binary payload that is content-addressable and write-once; a metadata skeleton carrying schema-validated fields describing the content's type, provenance, and ownership; and a graph connection linking the token to its position in the taxonomic hierarchy maintained by the knowledge graph service.

The three dimensions — payload, metadata, and graph position — are written together as a single atomic record. No component exists in isolation within the archive.

## See also

- [[asset-anchored-bim-vault]] — the flat-file, hash-addressed archive that holds three-dimensional asset tokens
