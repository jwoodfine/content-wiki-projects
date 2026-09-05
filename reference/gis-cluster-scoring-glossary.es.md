---
schema: foundry-doc-v1
title: "Glosario de Puntuación de Clústeres GIS"
slug: gis-cluster-scoring-glossary
category: reference
index_group: glossaries
type: topic
content_type: topic
quality: complete
short_description: "Glosario de la taxonomía de anclas, las definiciones de nivel (Regional, Distrital, Local, Marginal), las compuertas de calificación y la convención de radio del sistema de puntuación de co-ubicación geográfica de Woodfine."
status: stable
bcsc_class: current-fact
last_edited: 2026-09-04
editor: pointsav-engineering
language_protocol: TRANSLATE-ES
source_refs:
  - "bfe6fb6bbb557fd15bdb7ffd53bce60e527911eb7658c906df5b69813bdb8747"
  - "42cddb0e1bbd6516c578dbfe4a48f5ff2fd084529ef9adeaf09612c3bd36a5e1"
paired_with: gis-cluster-scoring-glossary.md
cites: []
---

Estos términos aparecen en los informes del conjunto de datos de co-ubicación, las comunicaciones de cobertura GIS y los materiales de selección de sitios preparados para revisión por los Directores Independientes del Socio General. Este glosario define la terminología del [[geographic-co-location-methodology|sistema de puntuación de co-ubicación geográfica]] de Woodfine: la taxonomía de anclas, la clasificación de cuatro niveles, las compuertas de calificación que asignan cada nivel y la convención de radio detrás de la compuerta de no-superposición.

## Taxonomía de anclas

Cada clúster puntuado se forma alrededor de una tienda de una de cuatro clases de ancla. Las anclas de **Hipermercado** son cadenas de mercancía general como Walmart Supercenter, Target y Carrefour Hypermarket. Las anclas de **Estilo de Vida** son minoristas de hogar y decoración a gran formato; IKEA es la única cadena en esta clase. Las anclas de **Ferretería** son cadenas de mejoras para el hogar como Home Depot, Lowe's y Leroy Merlin. Las anclas de **Almacén** son clubes de almacén por membresía como Costco, Sam's Club y Makro. La composición de un clúster — qué clases de ancla se co-ubican en un nodo — es el primer insumo para la asignación de nivel. El mapeo completo de cadenas a familias se documenta en la [[retail-brand-family-taxonomy|taxonomía de familias de marcas minoristas]].

## Definiciones de nivel

El sistema de puntuación actual asigna cada clúster a uno de cuatro niveles, siguiendo la jerarquía de propiedades comerciales del Consejo Internacional de Centros Comerciales: **Regional**, **Distrital**, **Local** y **Marginal**. Regional es el nivel más alto; Marginal agrupa cualquier clúster que no supere ninguna de las compuertas calificantes. Este sistema de niveles reemplazó una escala intermedia basada en puntos el 16 de mayo de 2026 — esa escala anterior, junto con las etiquetas numéricas T1/T2/T3 que llevaba, quedó retirada y no describe ningún clúster actual. Véase [[co-location-tier-nomenclature|la nomenclatura de niveles]] para el historial completo de nombres.

## Compuertas de calificación

Un clúster obtiene un nivel al superar todas las compuertas requeridas para ese nivel, no al acumular puntos hacia un umbral. Se aplican cuatro familias de compuertas: **composición** (qué clases de ancla están presentes), **rango de captación** (el percentil de población del clúster dentro de su propio país), **cívica** (un hospital de la clasificación requerida dentro del anillo circundante) y **no-superposición** (el clúster no está dominado por un clúster más fuerte cercano, medido mediante la convención de radio a continuación). Las tablas completas de compuertas se publican en gis.woodfinegroup.com; este glosario define los conceptos, no los umbrales de aprobación.

## Convención de radio

Los clústeres se comparan por superposición usando un disco de radio fijo centrado en cada clúster. Dos clústeres compiten por el mismo nodo cuando la superposición entre sus discos supera el límite de la compuerta de no-superposición; el clúster más débil queda entonces por debajo del nivel que su composición habría obtenido de otro modo. Esta convención de radio única reemplazó un esquema anterior de umbrales de proximidad separados y más amplios; ese esquema anterior no se aplica a ningún nivel actual. El radio exacto es un parámetro de la plataforma, publicado en gis.woodfinegroup.com y no se reproduce aquí.

## Métricas de salida del conjunto de datos

**Descriptor de composición** — Las clases de ancla presentes en un clúster, mostradas como una etiqueta en lenguaje sencillo como "Hipermercado + Ferretería + Almacén." **Rango de captación** — La posición percentil de un clúster por población dentro de su propio país; un clúster que figura entre los más altos a nivel nacional supera la compuerta de captación más estricta. **Clúster puntuado** — Cualquier nodo geo-localizado que ha sido evaluado contra la taxonomía de anclas y al que se le ha asignado un nivel. El término aparece en los informes de cobertura GIS para describir el conteo total de nodos evaluados en una geografía dada.
