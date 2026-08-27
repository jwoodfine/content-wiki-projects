---
schema: foundry-doc-v1
title: "Nomenclatura de Niveles de Co-localización"
slug: co-location-tier-nomenclature
category: site-selection
index_group: anchors-and-tenants
type: topic
content_type: topic
quality: complete
status: active
audience: customer-woodfine
bcsc_class: current-fact
language_protocol: TRANSLATE-ES
last_edited: 2026-08-26
editor: pointsav-engineering
short_description: "Las cuatro etiquetas de nivel — Regional, Distrital, Local, Marginal — visibles en el mapa de co-localización toman su nombre de la jerarquía de propiedades comerciales del Consejo Internacional de Centros Comerciales (ICSC), aunque solo \"Regional\" es un término ICSC genuino; Distrital, Local y Marginal son nombres propios de la plataforma. Introducidas junto con el sistema actual de puntuación por compuertas predicativas en mayo de 2026."
paired_with: site-selection/co-location-tier-nomenclature.md
cites:
  - ni-51-102
  - osc-sn-51-721
---

El [[co-location-methodology|índice de co-localización]] asigna cada clúster a uno de cuatro niveles en función de la composición categórica de sus [[co-location-anchors|anclas]] y tiendas secundarias, y de la posición del clúster dentro de la captación nacional de población. Las etiquetas visibles en el mapa — **Regional**, **Distrital**, **Local**, **Marginal** — toman su nombre de la jerarquía de propiedades del Consejo Internacional de Centros Comerciales (ICSC), utilizada por promotores inmobiliarios, planificadores y analistas de retail en los mercados de [[co-location-tier-system|América del Norte y Europa]] que cubre la plataforma. Las compuertas de calificación se definen en la [[catchment-ranking-methodology-v3|metodología V3 de clasificación de captación]] y la lógica de puntuación subyacente en el [[co-location-ranking-system|sistema de clasificación de co-ubicación]].

## Qué significa cada nivel

| Nivel | Nombre | Descripción |
|---|---|---|
| 1 | **Regional** | Un nodo de co-localización de importancia nacional. Contiene tanto un ancla de tipo hipermercado como un club de almacén o ancla de estilo de vida, se encuentra en el decil superior de su país por captación de población primaria y tiene un hospital clasificado como regional dentro del anillo cívico. El nivel más alto. |
| 2 | **Distrital** | Un nodo de área comercial subregional. Contiene un hipermercado y un ancla de ferretería o almacén, está en el cuartil superior de su país por captación de población primaria y tiene acceso hospitalario dentro del anillo cívico. |
| 3 | **Local** | Un hub de ferretería o mayoreo con apoyo cívico a nivel comunitario. Contiene al menos un ancla de tipo ferretería o almacén, está en la mitad superior de su país por captación de población primaria y tiene algún hospital dentro del anillo cívico. |
| 4 | **Marginal** | Por debajo del umbral en una o más compuertas requeridas. Un clúster comercial con co-tenencia minorista pero con captación insuficiente, composición inadecuada o apoyo cívico insuficiente para calificar para Local o superior. |

## Descriptores de composición

Cada clúster lleva un descriptor de composición que se muestra debajo de la insignia de nivel. El descriptor nombra las clases de ancla presentes, separadas por "+": por ejemplo, "Hipermercado + Ferretería + Almacén" o "Estilo de Vida + Hipermercado". Las cuatro clases de ancla son: Hipermercado (tiendas de mercancías generales: Walmart, Target, Mercadona, Tesco, Sainsbury's), Estilo de Vida (hogar y decoración a gran escala: IKEA), Ferretería (mejoras para el hogar: Home Depot, Lowe's, Leroy Merlin) y Almacén (clubes de almacén por membresía: Costco, Sam's Club, Makro). El mapeo completo de cadenas a familias se documenta en la [[retail-brand-family-taxonomy|taxonomía de familias de marcas minoristas]].

## Historia de la nomenclatura

Las etiquetas de nivel han sido renombradas dos veces desde el lanzamiento de la plataforma.

**Primer renombramiento (mayo de 2026):** Las etiquetas numéricas originales (T3 Complemento Total, T2 Ancla Minorista, T0 Nodo Comercial, entre otras) fueron reemplazadas por sustantivos en lenguaje sencillo: Prime, Strong (Retail), Strong (Bulk), Strong (Hub), Core (Hyper), Core (Hardware), Core (Wholesale), Emerging. Esto resolvió dos problemas de legibilidad: la ambigüedad del "+" en los descriptores compuestos y el esfuerzo cognitivo de mapear un número de nivel a un rango de calidad.

**Segundo renombramiento (mayo de 2026):** Las etiquetas del primer renombramiento fueron reemplazadas por la jerarquía ICSC: Regional, Distrital, Local, Marginal. La motivación fue la alineación con una nomenclatura internacionalmente reconocida que lleva significado sin requerir contexto específico de la plataforma.

Los nombres de la plataforma toman como referencia la jerarquía ICSC de centros comerciales, pero no son idénticos a ella. La jerarquía ICSC real es Neighborhood/Community/Regional/Super Regional; solo "Regional" es un término ICSC genuino. "Distrital", "Local" y "Marginal" son nombres propios de la plataforma, no términos ICSC.

## Lectura de los colores de nivel en el mapa

Cuando un usuario selecciona un clúster en el mapa, el nombre del nivel se muestra como una insignia de gran tamaño. Debajo de la insignia, un descriptor de composición en tono apagado nombra las clases de ancla presentes.

El color de la insignia codifica la jerarquía: azul marino oscuro para Regional, índigo para Distrital, pizarra para Local, gris claro para Marginal.

## Véase también

- [[co-location-methodology]]
- [[catchment-ranking-methodology-v3]]
- [[retail-brand-family-taxonomy]]
