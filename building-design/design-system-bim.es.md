---
schema: foundry-doc-v1
title: "Sistema de diseño de la construcción"
slug: design-system-bim
language: es
category: building-design
index_group: design-philosophy-and-system
type: topic
content_type: topic
status: active
last_edited: 2026-08-24
editor: pointsav-engineering
short_description: "Una plataforma de sistema de diseño prevista para el entorno construido — la capa de coordinación que hoy falta y que permitiría a superficies de autoría BIM independientes trabajar desde un vocabulario de especificación compartido, del mismo modo en que un sistema de diseño de software mantiene consistentes a equipos de producto independientes."
cites: [ifc-4-3, uniclass-2015, bsdd-v1]
paired_with: building-design/design-system-bim.md
---

Los grandes sistemas de diseño de software resuelven un problema de coordinación a escala: cuando equipos independientes construyen interfaces en paralelo, la consistencia se rompe a menos que las decisiones de diseño estén codificadas en una capa compartida que cada superficie consulta por referencia. No ha existido un equivalente para el entorno construido. La producción de Modelado de Información de Construcción (BIM) se coordina mediante normas compartidas (IFC, Uniclass, bSDD) y herramientas de autoría compartidas. Pero no ha existido una capa de especificación común: ninguna biblioteca canónica y legible por máquina de especificaciones de elementos constructivos que las superficies de autoría independientes consulten por referencia. El Sistema de Diseño de la Construcción está concebido para llenar ese vacío.

## Por qué el espacio ha estado vacío

Tres factores estructurales lo han mantenido vacío. Las herramientas de autoría BIM propietarias han almacenado históricamente las especificaciones de elementos en formatos bloqueados a una sola herramienta, no diseñados para llevar datos normativos entre herramientas. IFC es un formato de intercambio neutral — expresa lo que contiene un modelo, no lo que exige una especificación — por lo que nunca fue diseñado para ser, por sí solo, un sistema de diseño. Y la pila más amplia de normas del entorno construido evolucionó en paralelo entre jurisdicciones, sin que ninguna norma ofreciera una capa de especificación composable que uniera a las demás.

## De qué está compuesto

El Sistema de Diseño de la Construcción se organiza en dos capas. La primera es una biblioteca de [[bim-objects-substrate|categorías primitivas de Objetos BIM]] — las unidades de especificación para elementos espaciales, elementos físicos, materiales, sistemas y más. La segunda es un conjunto de [[aec-interface-conventions|componentes de interfaz compartidos]] sobre los que puede construir cualquier superficie con capacidad BIM. Juntas están pensadas para dar a las superficies de autoría independientes un vocabulario común. Un profesional que se mueve entre ellas no tendría así que aprender una nueva interfaz cada vez.

## Un archivo propio, no un servicio alojado

El Sistema de Diseño de la Construcción no está previsto como un servicio alojado — es un conjunto de archivos en un repositorio git que una organización clona y extiende con sus propios datos jurisdiccionales y específicos del sitio. Es el mismo modelo de soberanía que sustenta de forma más amplia el archivo BIM de archivo plano de Woodfine. No es necesario que nada regrese a un proveedor central para que una organización siga usando su propia copia.

## Dónde vive la especificación

El catálogo completo de categorías de objetos, la biblioteca de componentes de interfaz y el estado actual de implementación se mantienen directamente en [bim.woodfinegroup.com](https://bim.woodfinegroup.com).

## Véase también

- [[bim-objects-what-they-are]]
- [[bim-objects-three-layers]]
- [[bim-objects-substrate]]
