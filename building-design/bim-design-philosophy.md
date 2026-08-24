---
schema: foundry-doc-v1
title: "BIM design philosophy"
slug: bim-design-philosophy
category: building-design
type: topic
content_type: topic
status: active
audience: customer-woodfine
bcsc_class: current-fact
language_protocol: PROSE-TOPIC
last_edited: 2026-08-24
editor: pointsav-engineering
short_description: "AEC-specific design extension anchored to IFC 4.3, translating flat-file storage, open standards, and offline-first execution into a professional BIM toolset."
paired_with: building-design/bim-design-philosophy.es.md
cites: [ifc-4-3, uniclass-2015, bsdd-v1]
---

The Building Design System is designed to serve as the AEC-specific extension of the platform's design substrate, analogous to the relationship between IBM Carbon and specialized industry modules. It is intended to be anchored to the IFC 4.3 entity hierarchy and prioritized for high-fidelity operational environments. The system is designed to translate the platform's core commitments — flat-file storage, open standards, and offline-first execution — into a professional toolset intended to address the structural weaknesses of legacy cloud-only BIM. The seL4 security foundation is intended to provide the hardware-attested isolation that defence and healthcare clients require.

## Key Takeaways

- The design system is intended to be anchored to the IFC 4.3 entity hierarchy and to use a text-based open-standard stack (IFC-SPF, BCF 3.0, IDS 1.0, COBie). Data structured to these standards remains accessible for 50+ years and outlasts the specific software vendors that generate it.
- Asset-Anchored BIM is designed to be the structural differentiator: the digital twin is intended to be a legal artifact signed with the land title. It is designed to move with the property deed rather than being held in a vendor's tenant model — the data would survive platform changes or vendor failure without requiring a migration.
- Compositional-first regulatory compliance is intended to shift the model from "check-after-design" to "compliant-by-construction". Cities are intended to publish codes as composable design tokens (bSDD dictionaries + IDS 1.0 constraints), and designers would assemble models within pre-constrained envelopes where violations become geometrically impossible before they occur.
- Offline capability is designed to be structural, not a feature flag. Full BIM functionality is intended to be maintained in basements, air-gapped facilities, and remote sites. This structural property is designed to separate the platform from cloud-only BIM tools that require a persistent connection to function.

## Structural Differentiators

The platform's design philosophy is predicated on five capabilities that are structurally incompatible with multi-tenant SaaS models:

1. **Asset-Anchored BIM:** The digital twin is intended to be a legal artifact signed with the land title, designed to move with the property deed rather than being tied to a vendor's tenant model.
2. **Offline-Capable Operations:** Full BIM functionality is intended to be maintained in basements, air-gapped facilities, and remote sites where internet access is unavailable.
3. **Vendor-Obsolescence Survival:** By design, the text-based open-standard stack (IFC-SPF, BCF 3.0, IDS 1.0, COBie) is intended to keep data accessible for 50+ years, outlasting specific software vendors.
4. **Local IoT Integration:** Sensor data is designed to be ingested via local brokers into YAML sidecars, intended to ensure data residency and eliminate usage-based token charges.
5. **Legal-Financial Convergence:** The building archive is designed to unify the building's spatial, operational, and financial identities into a single portable artifact.

## Compositional-First Regulatory Compliance

The platform is designed to introduce a "compositional-first" approach to building codes and jurisdictional rules. Instead of post-design validation, cities are intended to publish codes as composable design tokens (bSDD dictionaries + IDS 1.0 constraints). Designers would then assemble models within pre-constrained envelopes where violations become geometrically impossible by construction.

This shift from "check-after-design" to "compliant-by-construction" represents a significant leapfrog in AEC technology.

## Integration with the Design Substrate

The BIM-SEMANTIC layer is designed to sit atop the platform's broader design-token substrate. While the baseline design-token and DTCG vault standards are shared across the platform, the Building Design System is intended to manage the BIM-specific extensions:
* 8 BIM token categories anchored to IFC 4.3.
* 18 specialized component recipes.
* Uniclass 2015 as the universal classification floor.

This architecture is intended to keep BIM components consistent with the broader platform design language while meeting the rigorous semantic requirements of ISO-standardized building data.

## See also

- [[bim-aec-muscle-memory]]
- [[bim-objects-substrate]]
- Flat-file BIM leapfrog
