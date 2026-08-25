---
schema: foundry-doc-v1
title: "Sistema de clasificación de co-ubicación minorista"
slug: co-location-ranking-system
category: site-selection
index_group: scoring-and-clustering
type: topic
content_type: topic
quality: complete
status: active
audience: customer-woodfine
bcsc_class: current-fact
language_protocol: TRANSLATE-ES
last_edited: 2026-08-25
editor: editorial
es_status: complete
short_description: "La mecánica determinista detrás de la clasificación de clústeres en la plataforma de co-ubicación — ejes de percentil relativos al país, la prueba de superposición entre clústeres vecinos y el orden de desempate aplicado dentro de un nivel."
paired_with: site-selection/co-location-ranking-system.md
---

La [[co-location-methodology|metodología de co-ubicación]] de Woodfine asigna el nivel de cada clúster mediante compuertas predicativas binarias, no mediante una puntuación compuesta — ningún clúster obtiene un nivel acumulando puntos hacia un umbral. Este artículo cubre la mecánica detrás de esas compuertas: cómo se mide la posición de captación de un clúster frente a sus pares nacionales, cómo se comparan los clústeres competidores por superposición, y cómo se ordenan los clústeres una vez clasificados. Las definiciones de las compuertas — qué combinación de pruebas requiere cada nivel — se detallan en la [[catchment-ranking-methodology-v3|metodología V3 de clasificación de captación]]; las etiquetas de nivel se describen en la [[co-location-tier-nomenclature|nomenclatura de niveles]].

## Ejes de percentil relativos al país

El nivel de un clúster depende de su posición frente a todos los demás clústeres de su propio país, no frente a un umbral global fijo. Cada clúster se clasifica frente a sus pares nacionales en ocho medidas: población de captación primaria y secundaria, y gasto primario y secundario en las categorías de alimentación, ferretería y venta al por mayor. El percentil de un clúster en cada eje es su rango dividido por el total de clústeres del país — un clúster en el 10% superior por población primaria lleva un percentil de 0,10 en ese eje.

Dos zonas de captación alimentan los ejes de población y gasto: una zona primaria dentro de 35 km del clúster y una zona secundaria entre 35 km y 150 km, según la [[od-catchment-methodology|metodología de captación O-D]]. Las estimaciones de gasto se basan en encuestas nacionales de gasto de los hogares aplicadas a la misma cuadrícula de población. Clasificar dentro de cada país, en lugar de contra un único umbral global, preserva la estructura de un mercado más pequeño frente a uno más grande.

Estos umbrales son intencionalmente amplios. El sistema está diseñado para separar los clústeres de importancia nacional de los nodos locales, no para clasificar con precisión los clústeres entre sí dentro de un mismo nivel.

## La prueba de superposición

Un clúster solo se acredita para su nivel cuando no está dominado por un vecino más fuerte cercano. La superposición entre dos clústeres se mide como la intersección sobre unión (IoU) de dos discos de radio igual, cada uno de 3,0 km, centrados en las anclas de los clústeres — el área compartida entre los discos, en relación con su área combinada. A medida que dos centroides de clúster se alejan, el IoU tiende a cero y los clústeres se consideran espacialmente independientes. Un clúster cuyo disco se superpone sustancialmente con el de un clúster más fuerte se mantiene por debajo del nivel que su composición y captación alcanzarían por sí solas. Regional lleva el límite de superposición más estricto de todos los niveles, según las [[catchment-ranking-methodology-v3|definiciones de compuertas]].

## Orden dentro de un nivel

Los clústeres que comparten nivel y país se ordenan por tres criterios, aplicados en secuencia: recuento de tiendas dentro de 3,0 km, luego población de captación primaria, ambos de mayor a menor. El identificador del clúster resuelve cualquier empate restante, garantizando un orden determinista.

## Procedencia

- **Verificación:** La mecánica de clasificación se confirmó contra la metodología de puntuación V3 de la plataforma SIG.

## Fuentes de datos

Datos de mapa y localización © [colaboradores de OpenStreetMap](https://www.openstreetmap.org/copyright) / [ODbL](https://opendatacommons.org/licenses/odbl/).

## Ver también

- [[co-location-methodology]]
- [[co-location-intelligence-overview]]
- [[catchment-ranking-methodology-v3]]

## Referencias

- [Gran superficie](https://es.wikipedia.org/wiki/Gran_superficie) — Wikipedia, consultado 2026-06-14
- [DBSCAN](https://es.wikipedia.org/wiki/DBSCAN) — Wikipedia, consultado 2026-06-14

---

*Copyright © 2026 Woodfine Capital Projects Inc. Licenciado bajo [Creative Commons Atribución-SinDerivadas 4.0 Internacional](https://creativecommons.org/licenses/by-nd/4.0/).*
