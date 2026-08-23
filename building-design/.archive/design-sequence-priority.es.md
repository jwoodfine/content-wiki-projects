---
schema: foundry-doc-v1
title: "Prioridad de secuencia de diseño: plan de arrendamiento, luego servicios, luego estructura"
slug: design-sequence-priority
category: building-design
type: topic
content_type: topic
quality: complete
status: archived
archived: 2026-08-24
archived_reason: "Retirado -- el frontmatter ya marcaba bcsc_class: vendor-internal pero el archivo se publico de todas formas; datos internos reales de trabajo (medidas exactas, listas de tareas, citas a documentos internos, notas de flujo de trabajo del operador) no destinados a divulgacion publica. Revision de integridad Track-B, 2026-08-24."
superseded_by: none
audience: operator
bcsc_class: vendor-internal
language_protocol: TRANSLATE-ES
last_edited: 2026-07-15
editor: pointsav-engineering
short_description: "El orden de colaboración prescrito entre las disciplinas de diseño de un Sitio de Desarrollo — primero el plan de arrendamiento, luego los servicios del edificio, luego la revisión estructural — que mantiene coherentes las reglas de composición de placas de piso ya existentes."
paired_with: building-design/design-sequence-priority.md
cites: []
---

**La prioridad de secuencia de diseño** es el orden de colaboración prescrito entre las disciplinas de diseño de un Sitio de Desarrollo: el plan de arrendamiento — expresado mediante [[key-plans-and-tiles|Planos Clave y Tiles]] — se finaliza primero, los servicios del edificio le siguen, y la revisión estructural llega al final. La regla no introduce ingeniería nueva; nombra explícitamente una disciplina que ya gobierna la composición de placas de piso en [[bim-floor-plate-methodology|la metodología de placas de piso]], donde varias reglas de composición de tiles ya existentes solo cobran sentido una vez que el orden se hace explícito. El arrendamiento determina lo que una planta genera; los servicios y la estructura existen para entregar ese plan de arrendamiento sin degradarlo. Invertir el orden — diseñar la estructura o los servicios primero y ajustar el plan de arrendamiento a ellos — produce sistemáticamente espacio residual no arrendable, zonas climáticas desalineadas y retrabajo costoso en etapas tardías.

## Por qué el plan de arrendamiento va primero

El desempeño económico de un Sitio de Desarrollo lo determinan su área neta arrendable y la combinación de arrendatarios que puede alojar — ambas son propiedades del plan de arrendamiento, no de los sistemas mecánicos o estructurales del edificio. El Sistema de Placas de Piso Fijas restringe cada sitio a una de siete Placas de Piso catalogadas (Centros Profesionales; Oficina Suburbana; Retail Select en tamaño Pequeño/Mediano/Grande; Industrial Tecnológico en Mediano/Grande); un sitio que no puede alojar ninguna de las siete se descarta en lugar de rediseñarse a su medida. Esa decisión se toma en la etapa del plan de arrendamiento, antes de involucrar a un ingeniero de servicios o de estructura. La regla de composición FP-CORE en la metodología de placas de piso ya asume este orden: el núcleo del edificio se posiciona en relación con la disposición de los tiles — a al menos 18 m del extremo corto, dejando espacio para tiles de remate y tiles básicos a cada lado — lo cual requiere que la disposición de tiles exista primero. La ubicación del núcleo es una decisión derivada del plan de arrendamiento, no una decisión estructural independiente.

El colaborador de diseño externo contratado para cada Sitio de Desarrollo entra en esta secuencia después del plan de arrendamiento. Su función es desarrollar una adaptación específica del sitio sobre el prototipo fijo, y comentar el prototipo base durante la incorporación — comentando un prototipo que ya incorpora una disposición de tiles terminada, no proponiendo una desde cero.

## Los servicios siguen al arrendamiento

Los servicios del edificio se dimensionan según el plan de arrendamiento ya existente, no al revés. La zonificación climática a nivel de tile es el ejemplo más claro: cada tile tiene su propio termostato y zona climática ajustados al tamaño de ese tile, y los tiles especiales reciben zonas de control propio. Esto solo funciona si los límites de los tiles ya están fijados — un ingeniero de servicios que zonificara el HVAC antes de que exista la disposición de tiles estaría zonificando un espacio aún no definido, sin garantía de que esos límites sobrevivan al contacto con un plan de arrendamiento terminado. La regla de composición FP-SNAP opera igual: el ancho de los tiles especiales se ajusta al ancho del Plano Clave más cercano específicamente para preservar la continuidad de los muros divisorios, es decir, los servicios y los tiles adyacentes al núcleo se dimensionan contra la disposición de arrendamiento, no al revés.

Una política interna de dotación de baños, superpuesta al código de construcción jurisdiccional, sigue el mismo patrón. El número de baños se determina según la combinación de arrendatarios y el tráfico peatonal diario — los arrendamientos médicos, académicos y cívicos exigen cada uno un nivel de dotación distinto por encima de los mínimos del código. La combinación de arrendatarios es un resultado del plan de arrendamiento; el programa de baños que sirve a esa combinación no puede finalizarse antes de conocerla.

## La revisión estructural llega al final

La participación estructural en esta secuencia es reactiva, no generativa: verifica que el plan de arrendamiento y los servicios superpuestos a él sean físicamente construibles, y revisa la retícula estructural solo donde surge un conflicto. La regla de composición FP-CORNER lo establece directamente: cuando un tile de la familia pequeña cae en una esquina estructural, la retícula de columnas se revisa antes de finalizar el tile, y la posición del núcleo se ajusta si los tiles del lado corto entran en conflicto con ella. La estructura cede ante la disposición de tiles en la esquina, en lugar de que la disposición de tiles se rediseñe para ajustarse a una retícula de columnas preestablecida.

Una disciplina estructural relacionada extiende la misma lógica directamente a la economía del arrendamiento: la profundidad del tramo arrendable debe fijarla el requerimiento de espacio del arrendatario, no la luz de viga más económica disponible. Un ingeniero estructural que optimice la profundidad del tramo por economía de vigas antes de fijar el plan de arrendamiento arriesga fijar una profundidad más superficial o más profunda de lo que cualquier arrendatario realmente necesita — y la profundidad no arrendable que resulta de un tramo sobredimensionado no puede recuperarse durante la vida del arrendamiento. La economía estructural es una restricción real, pero se evalúa contra un plan de arrendamiento que ya existe, no se usa para fijar las dimensiones de ese plan.

## Qué ocurre cuando se viola el orden

Cada una de las reglas de composición anteriores codifica un modo de falla que aparece cuando la secuencia se ejecuta al revés. Una retícula estructural fijada antes del plan de arrendamiento produce esquinas de columnas que compiten con la geometría de los tiles, forzando la revisión FP-CORNER después del hecho en lugar de evitarla. Servicios dimensionados para una planta nocional en lugar de una disposición de tiles terminada producen zonas climáticas que cruzan los límites de los tiles, socavando la fijación de precios por autonomía del arrendatario de la que depende la zonificación climática a nivel de tile. Una dotación de baños fijada a los mínimos del código antes de conocer la combinación de arrendatarios desatiende los arrendamientos de alto tráfico y exige una adaptación posterior una vez firmada la combinación real. Y una profundidad de tramo fijada por economía de vigas antes de conocer los requerimientos del arrendatario produce profundidad estructural no arrendable e irrecuperable — el modo de falla más costoso de toda la secuencia, porque no puede corregirse sin reconstruir.

La prioridad de secuencia de diseño no es, por tanto, una conveniencia de programación. Es el orden que hace internamente coherentes las reglas de composición de tiles ya existentes — FP-CORE, FP-SNAP y FP-CORNER —: cada regla asume una capa previa terminada contra la cual diseñar, y cada una produce un paso de revisión o ajuste documentado precisamente en el punto donde una disciplina posterior se encuentra con una anterior.

## Véase también

- [[bim-floor-plate-methodology]]
- [[key-plans-and-tiles]]
- [[bim-design-philosophy]]
