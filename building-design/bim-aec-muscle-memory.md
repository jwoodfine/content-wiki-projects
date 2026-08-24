---
schema: foundry-doc-v1
title: "AEC muscle memory and interface patterns"
slug: bim-aec-muscle-memory
category: building-design
type: topic
content_type: topic
status: active
audience: customer-woodfine
bcsc_class: current-fact
language_protocol: PROSE-TOPIC
last_edited: 2026-08-24
editor: pointsav-engineering
short_description: "The Building Design System adopts established interface patterns from industry-standard tools to ensure zero learning curve for AEC practitioners, while enabling facility management workflows through work-order linking, lease integration, and sensor overlays."
paired_with: building-design/bim-aec-muscle-memory.es.md
cites: [ifc-4-3, uniclass-2015, bsdd-v1]
---

The Building Design System is planned to adopt established interface vocabularies from industry-standard tools (Revit, ArchiCAD, BricsCAD, and Bonsai) to ensure a zero-learning curve for AEC practitioners. By mirroring universal navigation and layout conventions, the platform is intended to let users focus on strategic innovations — such as the flat-file vault and city-code-as-composable-geometry — rather than basic tool interaction.

This interface (SpatialTree/Left Rail, PropertiesPanel/Right Rail, Toolbar, StatusBar, NavCube, and the other components described below) is a planned, conceptual design — none of it has been implemented in canonical code yet. `app-workplace-bim` and `app-console-bim` currently hold documentation only, and `moonshot-bim-engine`, the crate that would implement BIM rendering, remains a structural placeholder. Same status as the interface conventions described in [[aec-interface-conventions]].

## Planned Universal AEC Interface Conventions

The platform is intended to implement the following industry-standard layout patterns:

| Convention | Standard Location | Building Design System Component |
| :--- | :--- | :--- |
| **Spatial Tree** | Left Rail | `SpatialTree` |
| **Properties Panel** | Right Rail | `PropertiesPanel` |
| **Toolbar** | Top | `Toolbar` |
| **Status Bar** | Bottom | `StatusBar` |
| **NavCube** | Top-Right Viewport | `Viewport3D__navcube` |

### Key Navigation Standards (planned)
* **Storey-Level Expansion:** The planned `SpatialTree` is intended to default to storey-level nodes. Expanding directly to individual spaces would be avoided to minimize visual noise and align with professional mental models.
* **Non-Modal Properties:** The planned `PropertiesPanel` is intended to operate as a selection-sensitive sidebar that updates in real-time, avoiding disruptive popup modals.
* **Semantic Grouping:** Property sets (Pset_*) and quantities (Qto_*) are intended to be grouped into named, collapsible sections for rapid data retrieval.

## Strategic Divergence from Generic Modeling (planned)

While the platform is designed to respect professional conventions, it is intended to deliberately avoid artifacts of general-purpose 3D modeling software (e.g., Blender-host artifacts in Bonsai):

1. **Dedicated Spatial Tree:** The platform is intended to use a purpose-built `SpatialTree` widget rather than a generic scene-graph outliner, enabling features like search-by-space-name and floor-plan thumbnails.
2. **Standardized Keymaps:** Navigation is intended to use the standard 1–6 number row for view switching (top, bottom, front, back, left, right), accommodating the lack of numpads on modern laptops.
3. **Removal of Modal Editing:** The platform is intended to eliminate complex "mode-switching" (e.g., Object vs. Edit mode) common in general 3D software, providing a streamlined authoring experience.

## Addressing the FM Operator Persona

Existing BIM tools predominantly target designers. The Building Design System is intended to address the Facility Management (FM) and Property Manager personas through three planned unique workflows:

* **Work-Order Linking:** Attaching maintenance status directly to IFC elements via YAML sidecars.
* **Lease Integration:** Linking `IfcSpace` entities to lease records in the bookkeeping vault.
* **Sensor Overlays:** Displaying real-time MQTT-backed sensor readings directly in the `Viewport3D`.

These capabilities are planned for the v0.0.2 release and represent the convergence of spatial and operational data.

## See also

- [[bim-design-philosophy]]
- [[bim-objects-substrate]]
- [[flat-file-bim-leapfrog]]
