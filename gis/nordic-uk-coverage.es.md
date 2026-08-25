---
schema: foundry-doc-v1
title: "Expansión de Cobertura en los Países Nórdicos y el Reino Unido"
slug: nordic-uk-coverage
category: gis
index_group: coverage-expansion
type: topic
content_type: topic
quality: complete
status: active
lang: es
audience: customer-woodfine
bcsc_class: current-fact
language_protocol: TRANSLATE-ES
last_edited: 2026-08-25
editor: pointsav-engineering
short_description: "Cómo Noruega, Suecia y el Reino Unido ingresaron al conjunto de datos de inteligencia de co-ubicación mediante tres promociones de cadenas al nivel Alfa en mayo de 2026."
paired_with: gis/nordic-uk-coverage.md
cites:
  - ni-51-102
  - osc-sn-51-721
---

El [[co-location-intelligence-overview|mapa de inteligencia de co-ubicación]] de Woodfine incorporó cobertura sustancial en Noruega, Suecia y el Reino Unido el 6 de mayo de 2026, mediante la promoción de tres cadenas de mejoras del hogar al nivel Alfa y la primera ingesta de datos de ubicación de Obs Bygg en Noruega. La lógica de calificación es la [[co-location-methodology|metodología de co-ubicación]] operacionalizada por el [[co-location-ranking-system|sistema de clasificación determinista]]; los mapeos de cadenas a familias se documentan en la [[retail-brand-family-taxonomy|taxonomía de familias de marcas minoristas]].

## Qué Cambió

**Nota sobre terminología (añadida 2026-08-24):** las etiquetas de nivel de este artículo — T2 Hub, T3, y la clasificación de cadenas Alfa/Genérica descrita a continuación — reflejan el sistema de puntuación basado en puntos vigente en la fecha del evento, 6 de mayo de 2026. Ese sistema fue retirado en toda la plataforma el 16 de mayo de 2026 y reemplazado por el sistema de niveles por compuertas actual (Regional, Distrital, Local, Marginal; véase el [[gis-cluster-scoring-glossary|glosario de puntuación de clústeres]]). Las cifras de cobertura a continuación — conteos de tiendas, conteos de clústeres y fechas — no se ven afectadas por ese cambio y permanecen precisas; solo el vocabulario de nivel que las describe es histórico.

En ese momento, el sistema de niveles de la plataforma clasificaba a los minoristas de mejoras del hogar y almacenes en dos grupos: cadenas Alfa, que por sí solas calificaban una co-ubicación como T2 Hub, y cadenas Genéricas, que solo producían el nivel de calificación más bajo. Tres cadenas mantenidas en el nivel Genérico fueron promovidas al nivel Alfa tras confirmar una cobertura de datos suficiente. (Las etiquetas orientadas al mapa siguen la jerarquía ICSC descrita en [[co-location-tier-nomenclature|nomenclatura de niveles]].)

**Bauhaus Sverige** (Suecia) — 40 ubicaciones. Bauhaus es la cadena dominante de grandes superficies de mejoras del hogar en Suecia. Su presencia nacional se superpone directamente con los corredores minoristas de IKEA. La promoción al nivel Alfa activó de inmediato el estado T2 en los nodos adyacentes a IKEA en Estocolmo, Gotemburgo, Uppsala y Malmö.

**B&Q** (Reino Unido) — 356 ubicaciones. B&Q es el principal minorista masivo de mejoras del hogar en Gran Bretaña, con grandes superficies en parques comerciales suburbanos y periféricos. La cadena se había mantenido en el nivel Genérico a la espera de una nueva ingesta desde OSM, que se completó con 356 ubicaciones verificadas. La promoción al nivel Alfa desbloqueó designaciones T2 y T3 en nodos de IKEA en el Gran Londres, las Midlands y Escocia.

**Obs Bygg** (Noruega) — 63 ubicaciones. Obs Bygg es el formato de bricolaje operado por Coop Norge, la mayor cooperativa minorista de Noruega. La cadena no había sido ingestada anteriormente por la escasa cobertura de etiquetas de marca en OpenStreetMap; una consulta de ingesta por prefijo de nombre resolvió 63 tiendas activas. Obs Coop, el formato de hipermercado del mismo grupo, actúa como ancla de clúster en Noruega — la primera vez que se puntúan clústeres noruegos en la plataforma.

## Cobertura Antes y Después

| Mercado | Clústeres T2 Antes | Clústeres T2 Después |
|---|---|---|
| Noruega | 0 | 66 |
| Suecia (radio de 1 km) | 0 | 4+ |
| Reino Unido (radio de 1 km) | 0 | 9+ |
| Total Europa (1 km) | 162 | 229 |

En ese momento, todos los nuevos clústeres noruegos llevaban la designación T2 Hub, lo que reflejaba la combinación de Obs Coop (ancla) y Obs Bygg (ferretería alfa) dentro de un radio de 1 km — el patrón de co-tenencia característico del formato Coop Norge. Bajo el sistema de niveles actual, la misma composición Obs Coop / Obs Bygg alimenta la compuerta de composición para Distrital; el nivel real que lleva un clúster hoy también depende del rango de captación y la presencia cívica, que no se reafirman aquí.

## Relevancia

El formato de parque comercial noruego es estructuralmente distinto de los patrones de América del Norte o Europa Central. La co-tenencia Obs Coop / Obs Bygg es un estándar nacional: Coop Norge co-ubica deliberadamente sus formatos de hipermercado y bricolaje para anclar corredores comerciales en ciudades noruegas de tamaño medio. Los 66 nuevos clústeres T2 representan el primer mapa sistemático de este formato en la plataforma.

La promoción de B&Q resuelve la brecha de datos más significativa del conjunto de datos del Reino Unido. Con 356 ubicaciones verificadas, el conjunto de clústeres del Reino Unido refleja ahora la distribución real de los parques comerciales adyacentes a IKEA.

## Véase También

- [[atlas-co-location-index-nordics]] — índice clasificado de sitios de convergencia comercial en los países nórdicos
- [[co-location-ranking-system]] — el modelo de clasificación de anclas nominadas actual
- [[co-location-methodology]] — el modelo de puntuación de geometría lineal en el que se basan todos los índices
- [[co-location-tier-system]] — el sistema de niveles de co-ubicación, incluida la aplicación europea
