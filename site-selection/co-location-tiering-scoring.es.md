---
schema: foundry-doc-v1
title: "Niveles y puntuación de co-ubicación"
slug: co-location-tiering-scoring
category: site-selection
type: topic
content_type: topic
quality: complete
status: active
audience: customer-woodfine
bcsc_class: current-fact
language_protocol: TRANSLATE-ES
last_edited: 2026-07-31
editor: pointsav-engineering
short_description: "Puntuación por niveles de clústeres de co-localización — qué miden los niveles T1–T3 de composición, los parámetros DBSCAN que forman clústeres y qué no afirman."
paired_with: site-selection/co-location-tiering-scoring.md
cites: []
---

Este artículo describe una metodología de niveles composicionales — fundamentada en la investigación de agrupación basada en DBSCAN documentada en [[geometric-site-selection-national-tenancy]] — que asigna a cada clúster de co-ubicación uno de tres niveles — T1, T2 o T3 — sobre la base de la composición de categorías de minoristas. Representados como puntos de colores, los niveles se gradúan de T1 (co-ubicación más profunda) a T3 (co-ubicación calificada más superficial). Comprender con precisión qué miden estos niveles — y qué no — es necesario para leer correctamente un resultado de clúster composicional.

Las etiquetas de nivel que se muestran actualmente en el mapa de inteligencia de ubicación de Woodfine son el sistema de cuatro niveles — Regional, Distrital, Local, Marginal — descrito en [[co-location-tier-nomenclature]]. El modelo composicional T1/T2/T3 documentado en este artículo es un enfoque de clasificación distinto y relacionado; los dos no deben leerse como intercambiables.

## Qué miden los niveles

La variable que impulsa el nivel es la **composición de categorías de minoristas**: el conteo y la combinación de categorías de ancla distintas co-presentes dentro de un solo clúster espacial. El nivel es, por tanto, una clasificación composicional ordinal.

Los niveles miden la composición. No miden la fortaleza del área de atracción, el potencial de ventas, la población alcanzada ni el gasto capturado. La composición no implica demanda: un clúster T1 tiene más diversidad de anclas que un clúster T3, pero no se sigue que tenga más personas, más gasto o mejor accesibilidad en su área de atracción.

El etiquetado en el mapa dice "profundidad de co-ubicación (conteo de anclas)" en lugar de "niveles de calidad", y la definición en lenguaje sencillo de cada nivel está vinculada a la composición:

- **T1** — mayor profundidad de co-ubicación (más categorías de ancla co-presentes)
- **T2** — profundidad de co-ubicación intermedia
- **T3** — co-ubicación calificada más superficial

## Cómo se forman los clústeres: parámetros DBSCAN

Los clústeres se producen mediante agrupación espacial de ubicaciones de minoristas ancla usando **DBSCAN** (agrupación espacial basada en densidad), seguido de un pase de deduplicación. DBSCAN se rige por tres parámetros publicados en el modal de Metodología:

- **eps** — el radio de vecindad que define si dos puntos ancla son accesibles por densidad.
- **minPts** — el número mínimo de puntos necesarios para iniciar un clúster.
- **Umbral de IoU** — el corte de intersección sobre unión utilizado para deduplicar clústeres candidatos superpuestos.

Un límite duro en el alcance del clúster (diámetro máximo por pares) se aplica uniformemente; un ajuste más amplio no se utiliza porque fusiona aglomeraciones distintas. Los clústeres cuyo alcance queda muy por debajo de ese límite llevan una bandera de calidad interna que indica una mayor compacidad espacial.

### Sensibilidad: el conteo de clústeres es una salida del modelo

DBSCAN es un procedimiento **descriptivo**. El número de clústeres que devuelve el algoritmo es una función de eps, minPts y el umbral de IoU, y se mueve materialmente cuando estos varían dentro de rangos razonables. Los barridos de parámetros realizados durante el desarrollo demuestran esto directamente: en el rango razonable probado, el conteo de clústeres norteamericanos varía en más del doble dependiendo de la configuración, sin ningún cambio en los datos minoristas subyacentes. Un conteo titular de clústeres es, por tanto, una salida del modelo bajo una parametrización elegida, no un conteo preciso de un fenómeno objetivo.

## El puntaje de fortaleza planeado

El nivel de composición responde "¿qué combinación de minoristas hay aquí?" Un **puntaje de fortaleza** por clúster separado — planeado, aún no construido — está destinado a responder "¿cuánto mercado comanda esta ubicación?" Las dos dimensiones se informan una al lado de la otra una vez que el cuadro de mando esté conectado; nunca se colapsan en un solo color o un solo número.

### Principios de diseño

El puntaje de fortaleza previsto es explicable, no opaco. Es una combinación transparente de factores nombrados, cada uno de los cuales puede mostrarse en el cuadro de mando del clúster con su propio valor y su contribución al total. Sin ponderaciones de aprendizaje automático ni términos de interacción ocultos. Un revisor debe poder reconstruir el puntaje a partir de los factores mostrados.

### Conjunto de variables propuesto

Tres cantidades del lado de la demanda que las capas de datos ya admiten:

1. **Población alcanzada** — población de la cuenca e hogares, del ráster dasymétreo WorldPop 2026 agregado a la resolución 7 de H3.
2. **Gasto capturado** — gasto minorista anual estimado en la cuenca, derivado de la población y proxies de gasto per cápita (BLS, StatCan, Eurostat). Lleva las advertencias de estimación documentadas en [[spend-population-provenance]].
3. **Accesibilidad** — qué tan accesible es la cuenca, expresada a través de la demanda de origen-destino observada donde está disponible y una reserva de banda de distancia en otro lugar.

### Ponderaciones: una cuestión abierta

Cómo se combinan estos tres factores en un solo número es una cuestión abierta que este artículo deliberadamente no resuelve. Hasta que se ratifique la ponderación, el cuadro de mando muestra los valores de los factores individualmente para que cualquier compuesto mostrado siempre sea descomponible.

### Qué está destinado a mostrar el cuadro de mando

Para cada clúster seleccionado, el panel de detalle planeado presenta, como mínimo:

- El nivel de composición y su definición en lenguaje sencillo.
- La población e informe de hogares de la cuenca, con la vigencia y la base dasymétrica indicadas.
- El gasto anual estimado, explícitamente enmarcado como una estimación modelada.
- La lista de cadenas co-ubicadas que impulsan la composición.
- El puntaje de fortaleza (cuando esté construido) con sus principales factores y la contribución de cada uno, y la bandera `demand_basis`.

## Qué cambia respecto a la presentación anterior

| Dimensión | Anterior | Actual |
|---|---|---|
| Etiqueta de nivel | "NIVELES DE CALIDAD" | "Profundidad de co-ubicación (conteo de anclas)" — solo composición |
| Qué mide un nivel | Ambiguo | Explícitamente composición (conteo y combinación de categorías de ancla), ordinal |
| Apoyo a la decisión | Solo insignia de nivel y anillos | Cuadro de mando planeado: población, gasto, cadenas co-ubicadas, puntaje de fortaleza explicable con factores nombrados |
| Puntaje de fortaleza | Conflado con el nivel | Planeado como dimensión separada, del lado de la demanda, descomponible |
| Parámetros DBSCAN | No publicados | eps, minPts, IoU y el límite de alcance publicados en el modal de Metodología y aquí |
| Conteo de clústeres | Declarado como cifra precisa | Salida del modelo bajo una parametrización; sensibilidad a la elección de parámetros divulgada |

## Véase también

- [[trade-area-methodology]] — derivación de la cuenca y la migración desde bandas de distancia hacia áreas de atracción observadas
- [[spend-population-provenance]] — la cadena de estimación para el factor de gasto en el puntaje de fortaleza
- el resumen a nivel de asentamiento y el criterio de selección Top-400
- la capa de orquestación que produce los clústeres por niveles
- la agrupación minorista ascendente que alimenta el índice de co-ubicación
