---
schema: foundry-doc-v1
title: "Token de activo tridimensional"
slug: 3d-asset-tokens
category: building-design
type: topic
content_type: topic
status: stub
audience: customer-woodfine
bcsc_class: current-fact
language_protocol: TRANSLATE-ES
last_edited: 2026-08-24
editor: pointsav-engineering
short_description: "La unidad de datos almacenados en el archivo, que combina una carga útil binaria inmutable, un esqueleto de metadatos legible por máquina y una conexión gráfica taxonómica dinámica que codifica la procedencia y el contexto."
paired_with: building-design/3d-asset-tokens.md
cites: []
---

Un token de activo tridimensional es la unidad de datos almacenados del archivo, que combina una carga binaria inmutable, un esqueleto de metadatos legible por máquina y una conexión al grafo taxonómico activo que codifica la procedencia y el contexto.

## Estructura

Cada token tiene tres componentes: una carga útil binaria de escritura única y dirección por contenido; un esqueleto de metadatos con campos validados por esquema que describen el tipo de contenido, la procedencia y la propiedad; y una conexión al grafo que vincula el token a su posición en la jerarquía taxonómica mantenida por el servicio de grafo de conocimiento.

Los tres componentes — carga útil, metadatos y posición en el grafo — se escriben juntos como un registro atómico único. Ningún componente existe de forma aislada dentro del archivo.

## Véase también

- [[asset-anchored-bim-vault]] — el archivo de archivos planos con direccionamiento por hash que almacena los tokens de activo tridimensional
