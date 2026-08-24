---
schema: foundry-doc-v1
title: "Regiones de desarrollo"
slug: development-regions
category: rollout
index_group: regions-and-tracking
type: concept
content_type: topic
quality: complete
status: active
audience: customer-woodfine
bcsc_class: current-fact
language_protocol: TRANSLATE-ES
last_edited: 2026-07-03
editor: pointsav-engineering
short_description: "Zonas geográficas y jurisdiccionales que segmentan datos de mercado, contexto regulatorio y alcance de selección de sitios para la evaluación de coubicación y cumplimiento."
paired_with: development-regions.md
cites: []
---

Cada candidato de co-ubicación se evalúa dentro de una región de desarrollo declarada — un alcance geográfico y jurisdiccional delimitado que acota los datos de mercado, el contexto regulatorio y la selección de sitios. Dentro del alcance de cada región se aplican posturas de cumplimiento y se acumula inteligencia de mercado. Las regiones no son territorios de entrega; son límites analíticos y operativos que determinan cómo se toman las decisiones de desarrollo.

## Propósito

Un programa que opera en múltiples jurisdicciones no puede aplicar una única postura regulatoria de forma universal. Un despliegue canadiense que opera bajo obligaciones de divulgación continua de la NI 51-102 enfrenta requisitos diferentes a los de un despliegue que opera bajo regímenes equivalentes en EE. UU. o Europa.

Las regiones de desarrollo codifican esta especificidad jurisdiccional a nivel de planificación. Cuando se inicia un proceso de selección de sitio, se declara la región objetivo. La puntuación de co-ubicación y la revisión de la postura de cumplimiento se delimitan al alcance de esa región.

## Composición de una región

Cada región de desarrollo se define mediante tres componentes:

**Alcance jurisdiccional.** El conjunto de marcos legales y regulatorios aplicables dentro de la región. Para las regiones canadienses, esto incluye el regulador de valores provincial aplicable, el marco de divulgación continua NI 51-102, y las disposiciones relevantes para el manejo de datos.

**Límite geográfico.** La geografía física dentro de la cual se consideran las instalaciones y los sitios de co-ubicación. Los límites geográficos no siempre se alinean con los jurisdiccionales: un alcance regulatorio canadiense puede abarcar sitios en múltiples provincias, cada una con características de mercado distintas.

**Alcance de datos de mercado.** Las fuentes de datos e índices de mercado que alimentan el canal de inteligencia para la región. Los datos del mercado inmobiliario, los indicadores económicos y las señales demográficas están delimitados por región porque su contenido informativo está jurisdiccionalmente acotado. El [[about-regional-markets-system|sistema de clasificación de Mercados Regionales]] — incluidas las listas [[atlas-top-400-north-america|Top 400 Mercados Regionales]] — es el índice principal de este tipo: el alcance de datos de mercado de una región de desarrollo determina qué mercados clasificados entran en juego para la selección de sitios dentro de ella.

## Relación con la metodología de co-ubicación

Las definiciones de regiones de desarrollo son el marco dentro del cual opera la puntuación de selección de sitios. Cuando se inicia un proceso de selección de sitio, se especifica una región de desarrollo; la puntuación busca dentro del límite geográfico de esa región y devuelve una lista clasificada de candidatos delimitada a esa región.

## Véase también

- el programa de expansión país por país dentro del cual se toman las decisiones de despliegue regional
- [[about-regional-markets-system|Sistema de Inteligencia de Mercados Regionales]] — la metodología de clasificación detrás del alcance de datos de mercado
- [[atlas-top-400-north-america|Top 400 Mercados Regionales — América del Norte]]
- [[atlas-top-400-europe|Top 400 Mercados Regionales — Europa]]
