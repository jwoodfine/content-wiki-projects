---
schema: foundry-doc-v1
title: "Metodología de Clasificación de Captación por Predicados Puros (V3)"
slug: catchment-ranking-methodology-v3
category: site-selection
index_group: scoring-and-clustering
type: topic
content_type: topic
quality: complete
status: active
audience: customer-woodfine
bcsc_class: current-fact
language_protocol: TRANSLATE-ES
last_edited: 2026-08-26
editor: pointsav-engineering
short_description: "La metodología V3 asigna cada clúster de co-localización a uno de cuatro niveles mediante compuertas de predicado binarias — composición, rango de captación nacional, clasificación cívica e independencia espacial — sustituyendo el sistema previo de puntuación compuesta (mayo de 2026)."
paired_with: site-selection/catchment-ranking-methodology-v3.md
cites:
  - osm-odbl
  - overture-maps-cdla-2-0
  - ni-51-102
  - osc-sn-51-721
---

El sistema de niveles de [[co-location-methodology|co-localización]] asigna cada clúster a uno de cuatro niveles — Regional, Distrital, Local o Marginal (etiquetados según la [[co-location-tier-nomenclature|nomenclatura de niveles]]) — mediante compuertas de predicado binarias en lugar de una puntuación compuesta. Un clúster debe superar todas las compuertas del conjunto correspondiente a un nivel para calificar para ese nivel; los resultados parciales no se acumulan. Esta metodología describe la implementación actual, introducida en mayo de 2026. Complementa el [[co-location-ranking-system|sistema de clasificación determinista]] y toma sus insumos de área comercial de la [[od-catchment-methodology|metodología de bandas de distancia]] y de las [[trade-area-data-sources|fuentes de datos de áreas comerciales]].

## Por qué las compuertas de predicado reemplazan las puntuaciones compuestas

El sistema V2 anterior asignaba niveles sumando una puntuación base, un bono por recuento, un bono por diversidad, un término de profundidad cívica y una penalización por superposición. La puntuación resultante era internamente coherente, pero difícil de explicar: un clúster podía alcanzar el Nivel 2 mediante un bono por diversidad elevado, aun cuando le faltara la captación de población y la infraestructura cívica que el nivel pretendía señalar.

Las compuertas binarias hacen que los criterios de calificación sean explícitos e individualmente verificables. Un clúster Regional debe tener alcance poblacional a escala nacional, una composición de ancla específica, acceso hospitalario regional e independencia espacial respecto a clústeres más fuertes. Ninguno de estos requisitos se satisface mediante un indicador sustituto.

## Rangos de captación de población

La captación de población se calcula mediante una cuadrícula geográfica de resolución fija sobre distancia en línea recta, según la [[od-catchment-methodology|metodología de bandas de distancia]]. Se definen dos zonas para cada clúster:

- **Zona primaria**: todas las celdas de la cuadrícula dentro de 35 km del ancla del clúster
- **Zona secundaria**: todas las celdas de la cuadrícula entre 35 km y 150 km del ancla del clúster

Los totales de población provienen de los datos de población en cuadrícula WorldPop 2026, agregados a la misma cuadrícula usada para el análisis de captación (véase [[trade-area-data-sources|fuentes de datos de áreas comerciales]]). Los clústeres se clasifican dentro de su país ISO en ocho ejes: población primaria, población secundaria, gasto primario en víveres, gasto secundario en víveres, gasto primario en ferretería, gasto secundario en ferretería, gasto primario en mayoreo y gasto secundario en mayoreo.

El rango se expresa como una fracción percentil dentro del país del clúster: un valor más bajo indica un mayor alcance relativo. Esto permite comparar países con recuentos totales de clústeres muy distintos en una escala común.

## Definición de las compuertas de nivel

### Nivel 1 — Regional

Un clúster califica como Regional si se cumplen las cinco condiciones siguientes:

1. **Composición**: El clúster contiene un ancla de tipo Almacén (Costco, Sam's Club, Makro o equivalente) y un ancla de tipo Hipermercado (Walmart, Target, Mercadona, Tesco, Sainsbury's o equivalente); o contiene un ancla de tipo Estilo de Vida (IKEA) y un ancla de tipo Hipermercado.
2. **Captación primaria**: El rango de población primaria del clúster dentro de su país debe estar entre los más altos del país — la barra de captación primaria más exigente de todos los niveles.
3. **Captación secundaria**: El rango de población secundaria del clúster dentro de su país también debe estar muy por encima de la mediana del país, aunque esta barra es más laxa que la de captación primaria.
4. **Cívico — hospital regional**: Al menos un hospital clasificado como "regional" está presente dentro de un anillo cívico de proximidad definido alrededor del ancla del clúster.
5. **Independencia espacial**: La superposición entre el disco de área comercial de este clúster y el disco equivalente de cualquier clúster del mismo país con mayor rango de población primaria debe mantenerse baja — Regional exige la barra de independencia más estricta de todos los niveles.

### Nivel 2 — Distrital

Un clúster califica como Distrital si se cumplen las cinco condiciones siguientes:

1. **Composición**: El clúster contiene un ancla de tipo Hipermercado y un ancla de tipo Ferretería (Home Depot, Lowe's, Leroy Merlin o equivalente) o un ancla de tipo Almacén.
2. **Captación primaria**: El rango de población primaria del clúster dentro de su país debe superar una barra sustancialmente más baja que la de Regional, aunque sigue estando muy por encima de la mediana del país.
3. **Alcance de gasto**: El rango del clúster dentro de su país en al menos uno de los ejes — gasto en víveres, ferretería o mayoreo — también debe superar esa misma barra.
4. **Cívico — hospital presente**: Al menos un hospital clasificado como "regional" o "distrital" está presente dentro del anillo cívico de proximidad.
5. **Independencia espacial**: Se permite que la superposición entre el disco de área comercial de este clúster y el disco equivalente de cualquier clúster Regional del mismo país sea algo mayor que el límite del nivel Regional, aunque sigue estando acotada.

### Nivel 3 — Local

Un clúster califica como Local si se cumplen las tres condiciones siguientes:

1. **Composición**: El clúster contiene un ancla de tipo Ferretería o Almacén.
2. **Captación primaria**: El rango de población primaria del clúster dentro de su país debe estar en la mediana del país o por encima de ella.
3. **Cívico — cualquier hospital**: Al menos un hospital de cualquier clasificación está presente dentro del anillo cívico de proximidad.

### Nivel 4 — Marginal

Un clúster que no califica para los niveles Regional, Distrital o Local se clasifica como Marginal. Un clúster Marginal puede contener co-tenencia comercial significativa; la clasificación indica que uno o más requisitos necesarios para Local o superior no se cumplieron.

## Medición de la superposición

La compuerta de independencia espacial mide la superposición entre los discos de área comercial de dos clústeres, cada uno trazado con un radio fijo constante en todos los niveles, mediante un cálculo geométrico estándar de intersección sobre unión (IoU) — el área compartida por ambos discos, en relación con su área combinada. Dos clústeres cuyos centroides están lo bastante separados como para que sus discos ya no se superpongan se consideran totalmente independientes (IoU = 0); a medida que los discos se superponen más, el IoU aumenta, y el nivel del clúster más débil se limita en consecuencia.

## Resumen de umbrales

Las barras de captación y de gasto se vuelven más exigentes al pasar de Local a Regional, y el margen de independencia espacial se estrecha en consecuencia — los clústeres Regional enfrentan tanto la barra de captación más alta como el límite de superposición más estricto, mientras que los clústeres Local enfrentan la barra de captación más baja y ninguna compuerta explícita de superposición. El radio del anillo cívico y el radio del disco de independencia espacial se mantienen cada uno constante en todos los niveles.

## Referencias

*Los datos de ubicación de hospitales, universidades y minoristas usados para derivar los radios de captación de clústeres provienen de colaboradores de OpenStreetMap y están licenciados bajo la Licencia de Base de Datos Abierta (ODbL). Datos de OpenStreetMap © colaboradores de OpenStreetMap.*

## Véase también

- [[co-location-tier-nomenclature]]
- [[co-location-methodology]]
- [[co-location-ranking-system]]
