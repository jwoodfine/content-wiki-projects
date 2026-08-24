---
schema: foundry-doc-v1
title: "Convenciones de interfaz AEC"
slug: aec-interface-conventions
language: es
category: building-design
type: topic
content_type: topic
status: active
last_edited: 2026-08-24
editor: pointsav-engineering
short_description: "Las herramientas de autoría BIM del sector comparten un vocabulario de interfaz común — jerarquía espacial, panel de propiedades, visor 3D y vistas guardadas — porque se construyen sobre el mismo modelo de datos IFC subyacente, lo que le da a la capa de interfaz prevista de PointSav una base compartida sobre la cual construir en lugar de inventar una nueva."
cites: [ifc-4-3]
paired_with: building-design/aec-interface-conventions.md
---

Cada plataforma importante de autoría BIM incluye las mismas cuatro convenciones de interfaz: un árbol de jerarquía para la estructura espacial, un panel de propiedades para los atributos de los elementos, un visor 3D y un navegador de vistas guardadas. Estas convenciones existen porque el modelo de datos subyacente — la jerarquía de entidades IFC — es el mismo sin importar qué herramienta lo autoriza. Un arquitecto o ingeniero que aprendió este vocabulario en una herramienta de autoría ya lo conoce en la siguiente.

## Por qué importa un vocabulario compartido

Los equipos de proyectos BIM trabajan habitualmente con varias herramientas de autoría en un mismo proyecto. El modelo del ingeniero estructural, el del arquitecto y el del ingeniero de instalaciones (MEP) se exportan al mismo formato abierto, y la coordinación ocurre en un visor común donde nadie está en su entorno de autoría nativo. Una superficie de coordinación construida sobre este vocabulario compartido no añade una nueva curva de aprendizaje sobre las herramientas que los profesionales ya usan.

## La capa de interfaz prevista del Sistema de Diseño de la Construcción

El [[design-system-bim|Sistema de Diseño de la Construcción]] está previsto para construir sus propios componentes de interfaz sobre este mismo vocabulario compartido. Un profesional que se mueve entre su herramienta de autoría y cualquier superficie BIM de PointSav encontraría así el mismo árbol, el mismo panel de propiedades y los mismos controles de visor. Esta capa todavía no existe en el código canónico.

## Dónde vive la especificación

El catálogo completo de componentes y el detalle de implementación detrás de esta capa de interfaz se mantienen directamente en [bim.woodfinegroup.com](https://bim.woodfinegroup.com).

## Véase también

- [[design-system-bim]] — el Sistema de Diseño de la Construcción del cual esta capa de interfaz forma parte
- [[bim-aec-muscle-memory]] — cómo este vocabulario compartido se extiende a los flujos de gestión de instalaciones
- [[bim-objects-what-they-are]] — el modelo de objetos subyacente que expone esta interfaz
