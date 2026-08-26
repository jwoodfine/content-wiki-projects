---
schema: foundry-doc-v1
title: "Objetos BIM — Sustrato"
slug: bim-objects-substrate
language: es
category: building-design
index_group: bim-objects-and-the-digital-record
type: topic
content_type: topic
status: archived
archived: 2026-08-26
archived_reason: "Contenido de arquitectura de software/plataforma de PointSav ubicado por error en un wiki inmobiliario. Palabras del operador: el wiki de proyectos 'no es para software ni para PointSav, es para bienes raíces' -- si el contenido necesita un enlace a documentation.pointsav.com, hay algo mal en el contenido; debe reescribirse para encajar en corporate o projects, o trasladarse. Este artículo describía la taxonomía de categorías primitivas de Objeto BIM -- una definición de esquema de datos de plataforma, no contenido inmobiliario de Woodfine. Consolidado (junto con bim-objects-three-layers y bim-objects-what-they-are) en media-knowledge-documentation substrate/bim-object-specification (2026-08-26) -- tres facetas estrechamente ligadas de un mismo concepto, antes divididas en tres artículos breves."
superseded_by: none
last_edited: 2026-08-24
editor: pointsav-engineering
short_description: "Los Objetos BIM se organizan en un conjunto pequeño y fijo de categorías primitivas — elementos espaciales, elementos físicos, materiales, sistemas, umbrales de desempeño y más — cada una anclada a normas abiertas de la industria (IFC, Uniclass, bSDD) en lugar de un esquema propietario, de modo que una especificación se mantiene portátil y verificable entre herramientas y proveedores."
cites: [ifc-4-3, uniclass-2015, bsdd-v1]
paired_with: building-design/bim-objects-substrate.md
aliases:
  - bim-token-taxonomy
---

Cada [[bim-objects-what-they-are|Objeto BIM]] del [[design-system-bim|Sistema de Diseño de la Construcción]] pertenece a una de un conjunto pequeño y fijo de categorías primitivas. Entre ellas: elementos espaciales como sitios y plantas, elementos físicos como muros y puertas, materiales, conjuntos constructivos, sistemas del edificio, umbrales de desempeño, requisitos de zona climática y códigos de identidad. Agrupar los objetos de este modo significa que la categoría le dice a un profesional qué tipo de cosa describe un objeto, antes de que abra su especificación completa.

## Anclado a normas abiertas, no a un esquema propietario

Cada categoría se ancla a las mismas normas abiertas ya utilizadas en toda la industria AEC. La jerarquía de entidades IFC define qué es un elemento; Uniclass 2015 define cómo se clasifica; el Diccionario de Datos de buildingSMART (bSDD) aporta una definición estable e independiente de la herramienta. Anclarse a normas abiertas en lugar de a un esquema propietario significa que el significado de un objeto no depende de que una herramienta de autoría BIM en particular siga en el mercado. La especificación permanece legible y verificable durante toda la vida del edificio, sin importar cuántos proveedores de software vayan y vengan.

## Dónde vive la especificación

El catálogo completo de categorías, los mapeos a IFC y Conjuntos de Propiedades, y el formato de entrega detrás de este sustrato se mantienen directamente en [bim.woodfinegroup.com](https://bim.woodfinegroup.com).

## Véase también

- [[bim-objects-what-they-are]] — la tesis de pre-restricción y cómo los Objetos BIM difieren de los conjuntos de propiedades IFC
- [[bim-objects-three-layers]] — las capas de Especificación, Regulación y Zona Climática que lleva cada objeto
- [[design-system-bim]] — el Sistema de Diseño de la Construcción para el entorno construido
