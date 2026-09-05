---
schema: foundry-doc-v1
title: "Umbral de Deduplicación de Clústeres"
slug: cluster-deduplication-threshold
category: site-selection
index_group: site-scoring-and-trade-areas
type: topic
content_type: topic
quality: complete
status: active
audience: customer-woodfine
bcsc_class: current-fact
language_protocol: TRANSLATE-ES
last_edited: 2026-09-04
editor: pointsav-engineering
short_description: "El proceso de deduplicación del índice de co-localización elimina los clústeres superpuestos que representan la misma zona comercial utilizando un umbral de proximidad fijo y estrecho, conservando el clúster con mayor recuento de operadores secundarios."
paired_with: site-selection/cluster-deduplication-threshold.md
cites:
  - ni-51-102
  - osc-sn-51-721
---

El flujo del [[co-location-methodology|índice de co-localización]] genera un clúster por cada tienda [[co-location-anchors|ancla]] — cada hipermercado, minorista de ferretería y club de almacén calificado genera un clúster candidato centrado en las coordenadas de esa tienda, conforme a las reglas de [[co-location-cluster-formation|formación de clústeres]]. Cuando dos anclas ocupan la misma zona comercial, el resultado son dos clústeres superpuestos que representan la misma área de captación. El paso de deduplicación resuelve esa redundancia. Los insumos de área comercial al [[co-location-ranking-system|sistema de clasificación]] se agregan después de la ejecución de la deduplicación.

## El problema del estacionamiento compartido

Las grandes zonas comerciales frecuentemente albergan dos o más tiendas de categoría ancla a pocos metros de distancia entre sí — una tienda de mejoras del hogar y un club de almacén que comparten un mismo estacionamiento es el caso habitual. Sin deduplicación, ambas tiendas generan clústeres con geometría de captación, co-inquilinos y puntuaciones casi idénticos. El mapa muestra dos anillos concéntricos que cubren la misma zona — ninguno incorrecto de forma aislada, pero juntos inducen a error sobre el número de nodos comerciales distintos en ese corredor.

## Selección del umbral

El paso de deduplicación elimina cualquier clúster cuya tienda ancla se encuentre dentro de un radio fijo y estrecho respecto a un ancla de mayor rango ya confirmada para su retención. El radio es lo bastante estrecho para que sólo se colapsen las tiendas que genuinamente comparten un único estacionamiento o complejo de edificios. Las anclas en centros comerciales adyacentes separados por una calle de servicio se tratan como nodos distintos y se conservan.

La calibración es deliberadamente conservadora en esa dirección. Un umbral demasiado amplio colapsa en un solo nodo bloques comerciales operados de forma independiente — bloques que atienden captaciones residenciales diferentes — y subestima el número de sitios distintos en un corredor. Suprimir un nodo legítimo es el más dañino de los dos errores, porque retira un sitio de la consideración sin dejar constancia de que algo fue retirado.

## Selección del superviviente

Cuando dos anclas se encuentran dentro de la distancia umbral, el clúster retenido es el que tiene el mayor recuento de co-inquilinos dentro de su área de captación. Cuando ese recuento empata, el desempate recae en el recuento de co-inquilinos dentro de un radio interior más estrecho. Esto garantiza que el clúster que representa la zona comercial más completa — más tiendas, mayor atractivo multipropósito — sea el que sobrevive, independientemente de qué ancla fue procesada primero.

## Efecto en el proceso

La deduplicación elimina una proporción significativa de clústeres candidatos por ser duplicados de la misma zona en una ejecución representativa del proceso. La reducción se concentra en los corredores comerciales de alta densidad donde múltiples formatos de ancla se co-localizan en proximidad estrecha. La distribución por niveles y las clasificaciones nacionales se asignan después de la ejecución de la deduplicación, por lo que los recuentos publicados reflejan únicamente zonas deduplicadas. Los recuentos de producción actuales se publican en [[about-regional-markets-system|Regional Markets Intelligence System]].

## Véase también

- [[co-location-methodology]]
- [[co-location-tier-system]]
