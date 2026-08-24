---
schema: foundry-doc-v1
title: "AEC interface conventions"
slug: aec-interface-conventions
language: en
category: building-design
type: topic
content_type: topic
status: active
last_edited: 2026-08-24
editor: pointsav-engineering
short_description: "The four universal interface conventions — spatial tree, properties panel, 3D viewport, and view navigator — that all BIM authoring tools implement, providing shared vocabulary for consistent cross-tool coordination surfaces."
cites: [ifc-4-3]
paired_with: building-design/aec-interface-conventions.es.md
---

Every major BIM authoring platform ships with four interface conventions that an architect or engineer learns once and carries across products: a hierarchy tree for the spatial structure, a properties panel for element attributes, a 3D viewport, and a saved-view navigator. These conventions exist because the underlying data model (the IFC entity hierarchy) is the same regardless of which tool authors it. The [[design-system-bim|Building Design System]]'s planned universal interface components are intended to be built on this shared vocabulary.

These are planned, conceptual interface components — none has been implemented yet. `app-workplace-bim` and `app-console-bim` currently hold documentation only; `moonshot-bim-engine`, the crate that would implement BIM rendering, is a structural placeholder. The descriptions below state the intended design, not a shipped product.

## The Four Universal Conventions

### Spatial tree

Every BIM authoring tool displays the spatial structure of a building as a hierarchical tree: Site contains Building, Building contains Storey, Storey contains Space, Space contains Elements. This corresponds directly to the `IfcSpatialStructureElement` hierarchy in IFC 4.3. The Building Design System's planned `SpatialTree` component is intended to render this hierarchy with consistent expand/collapse behaviour, selection propagation to the Viewport3D, and IFC GUID display on hover. An operator who has used any of the major authoring tools would be able to navigate a `SpatialTree` without reading documentation.

### Properties panel

When an element is selected, a properties panel shows the element's IFC class name, its globally unique identifier (IFC GUID), and all attached Property Set values. The Building Design System's planned `PropertiesPanel` component is intended to render the same data with a mode-prop variant: the `view` mode shows all Pset values flat; the `edit` mode shows only the values the current role is authorised to modify. A BIM operator would find their familiar Pset vocabulary — `Pset_WallCommon.FireRating`, `Pset_SpaceOccupancyRequirements.OccupancyNumber`, `Pset_DoorCommon.FireExit` — in the same position as in their authoring tool.

### 3D viewport

The principal interface surface of every BIM tool is a perspective or orthographic 3D viewport. Camera controls (orbit, pan, zoom) use industry-standard mouse bindings: middle-button orbit, scroll zoom, shift-scroll pan. Section cuts are applied as clipping planes. The Building Design System's planned `Viewport3D` component is intended to embed the xeokit-sdk or @thatopen/web-ifc viewer — both open-source — with these standard camera controls. An IFC file loaded into the viewport would render correctly because both viewers implement the IFC 4.3 geometry pipeline natively, without round-tripping through a proprietary format.

### View navigator

Named saved views — floor-plan views, section cuts, elevation views, 3D perspectives framed on a specific storey — are how BIM operators communicate intent without sending full model files. The Building Design System's planned `ViewNavigator` component is intended to render saved views as labelled tabs, with a tab selection loading the camera state and, optionally, the IFC storey-filter for that view.

## Ten Planned Universal Interface Components

The [[design-system-bim|Building Design System]] is planned to define ten interface components intended to appear on every surface — whether the field client, the facility management console, or any future surface that consumes the Building Design System. None of the ten exists in canonical code yet.

| Component | Role |
|---|---|
| `SpatialTree` | Spatial hierarchy navigation (Site → Building → Storey → Space) |
| `PropertiesPanel` | IFC Pset viewer and editor (mode-prop variant) |
| `Viewport3D` | 3D model viewport (xeokit / @thatopen embed) |
| `ViewNavigator` | Named saved views as labelled tabs |
| `IssueTracker` | BCF 3.0 topic list with status and assignee filters |
| `ElementSearch` | IFC GUID or Pset-value search across the loaded model |
| `ClashReview` | Clash detection result list with viewport highlight |
| `HistoryTimeline` | Git commit history rendered as model-state timeline |
| `ExportPanel` | COBie export, IDS validation run, BCF ZIP download |
| `StatusBar` | Model load progress, validation counts, last-sync timestamp |

Four planned surface-unique components — `GuidSearch` and `AuditLog` for the facility management console, and two field-client components — are intended to extend the universal set without replacing it. An operator who learns the ten universal components would have a working mental model of every PointSav BIM surface before opening it.

## Why Shared Vocabulary Matters

BIM project teams frequently work across multiple authoring tools in a single project. The structural engineer's model, the architect's model, and the MEP engineer's model all export IFC-SPF. Coordination happens in a common viewer where no one is in their native authoring environment.

A shared interface vocabulary means that a coordination viewer built to this convention would not introduce a new learning surface on top of the authoring tools. An architect opening a building model in a Building Design System viewer would find the same tree, the same properties panel, and the same viewport controls they use in their authoring tool — the tool invisible, the model visible.

## Relationship to the Design System Substrate

The [[design-system-bim|Building Design System]] is planned as a BIM-semantic extension of the Carbon Design System baseline. Carbon provides the foundational UI primitives — buttons, inputs, data tables, colour tokens, typography scale. The Building Design System is intended to add the AEC-semantic layer on top: the ten universal interface components and the eight [[bim-objects-what-they-are|BIM Object]] primitive categories.

A designer who contributes to the Carbon-based platform design surface would use the same token and component authoring workflow to contribute a new BIM component to the [[bim-objects-substrate|BIM Object catalog]]. The substrate is the same; the semantic domain is different.
