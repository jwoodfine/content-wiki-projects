---
schema: foundry-doc-v1
title: "Umbral de Deduplicación de Clústeres"
slug: cluster-deduplication-threshold
category: site-selection
type: topic
content_type: topic
quality: complete
status: active
audience: customer-woodfine
bcsc_class: current-fact
language_protocol: TRANSLATE-ES
last_edited: 2026-05-25
editor: pointsav-engineering
short_description: "El proceso de deduplicación del índice de co-localización elimina los clústeres superpuestos que representan la misma zona comercial utilizando un umbral de proximidad fijo y estrecho, conservando el clúster con mayor recuento de operadores secundarios. Un umbral previo, sustancialmente más amplio, suprimía nodos comerciales legítimamente distintos en corredores suburbanos de alta densidad."
paired_with: site-selection/cluster-deduplication-threshold.md
cites:
  - ni-51-102
  - osc-sn-51-721
---

El proceso de deduplicación del [[co-location-methodology|índice de co-localización]] elimina los clústeres superpuestos que representan la misma zona comercial. Cuando dos [[co-location-anchors|anclas]] ocupan la misma zona comercial, el resultado son dos clústeres superpuestos que representan la misma área de captación. El paso de deduplicación resuelve esa redundancia. Los insumos de área comercial al [[co-location-ranking-system|sistema de clasificación]] se agregan después de la ejecución de la deduplicación.

## El problema del estacionamiento compartido

Las grandes zonas comerciales frecuentemente albergan dos o más tiendas de categoría ancla a pocos metros de distancia entre sí. Un Home Depot y un Costco que comparten un estacionamiento en los suburbios de Edmonton, por ejemplo, se ubican a aproximadamente 20 metros de distancia. Sin deduplicación, ambas tiendas generan clústeres con geometría de captación, co-inquilinos y puntuaciones casi idénticos. El mapa muestra dos anillos concéntricos que cubren la misma zona — ninguno incorrecto de forma aislada, pero juntos inducen a error sobre el número de nodos comerciales distintos en ese corredor.

## Selección del umbral

El paso de deduplicación elimina cualquier clúster cuya tienda ancla se encuentre dentro de un radio fijo y estrecho respecto a un ancla de mayor rango ya confirmada para su retención. El radio es lo bastante estrecho para que sólo se colapsen las tiendas que genuinamente comparten un único estacionamiento o complejo de edificios. Las anclas en centros comerciales adyacentes separados por una calle de servicio se tratan como nodos distintos y se conservan.

Una implementación anterior utilizaba un umbral sustancialmente más amplio. La revisión de campo del área metropolitana de Edmonton identificó casos en los que nodos comerciales legítimos y operados de forma independiente eran suprimidos sin notificación: un nodo anclado en Walmart y un nodo anclado en Home Depot en bloques comerciales vecinos, que atendían a captaciones residenciales diferentes, eran tratados como duplicados y uno era eliminado. Ese umbral más amplio resultó demasiado tosco para los corredores suburbanos densos, y se ajustó en consecuencia.

## Selección del superviviente

Cuando dos anclas se encuentran dentro de la distancia umbral, el clúster retenido es el que tiene el mayor recuento de co-inquilinos dentro del radio de captación de 3 km. Los empates se resuelven con el recuento a 1 km. Esto garantiza que el clúster que representa la zona comercial más completa — más tiendas, mayor atractivo multipropósito — sea el que sobrevive, independientemente de qué ancla fue procesada primero.

## Efecto en el proceso

Tras aplicar el umbral ajustado, la deduplicación elimina una proporción significativa de clústeres candidatos por ser duplicados de la misma zona en una ejecución representativa del proceso. La reducción se concentra en los corredores comerciales de alta densidad donde múltiples formatos de ancla se co-localizan en proximidad estrecha. Los recuentos de producción actuales se publican en [[about-regional-markets-system|Regional Markets Intelligence System]].

## Véase también

- [[co-location-methodology]]
- [[atlas-tier-index-north-america]]
