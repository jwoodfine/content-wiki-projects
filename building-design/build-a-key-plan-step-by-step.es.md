---
schema: foundry-doc-v1
title: "Construir un Key Plan, paso a paso"
slug: build-a-key-plan-step-by-step
category: building-design
type: guide
content_type: guide
quality: complete
status: pre-build
audience: operator
bcsc_class: vendor-internal
language_protocol: TRANSLATE-ES
last_edited: 2026-07-15
editor: pointsav-engineering
short_description: "Un recorrido procedimental por el método de Key Plan: desde la geometría de mobiliario y equipamiento hasta el dimensionamiento de zonas, el ensamblaje de Tiles y la combinación en Floor Plate."
paired_with: building-design/build-a-key-plan-step-by-step.md
cites: []
---

Esta guía describe el procedimiento para construir un Key Plan individual y combinarlo, junto con otros, en un [[bim-tile-system|Tile]] y finalmente en un Floor Plate. Es un procedimiento, no una introducción conceptual: para el vocabulario subyacente (qué es un Key Plan, por qué el sistema es geométrico y autosimilar, qué significa un Tile o un Floor Plate) consulte los Prerrequisitos indicados abajo en lugar de esperar que esta guía los repita.

Construir un único Key Plan a partir de un inventario de mobiliario, una vez que ese inventario está disponible, suele ser un ejercicio de una sola sesión. Agrupar Key Plans en un Tile y verificarlo contra las reglas de composición añade una segunda sesión. Ensamblar un Floor Plate completo —que requiere ejecutar el estudio comparativo de Tiles Alternativos en todas las categorías de inquilino de la planta— es un ejercicio más largo, medido en días y no en horas, porque depende de conciliar múltiples categorías de inquilino sobre una única retícula estructural compartida.

## Prerrequisitos

Antes de comenzar, es necesario comprender lo siguiente —esta guía asume estos conceptos en lugar de explicarlos—:

- [[key-plans-and-tiles|Key Plans y Tiles]] — el sistema geométrico, autosimilar y aperiódico que esta guía construye. Léalo primero si los términos "Key Plan," "Tile" o "aperiódico" no le resultan familiares.
- [[bim-floor-plate-methodology|Metodología de floor plate]] — las reglas de composición (FP-SUM, FP-ENDCAP, FP-CORE, FP-SNAP, FP-CLIMATE, FP-DOORS, FP-CORNER) que un Floor Plate terminado debe satisfacer. Esta guía hace referencia a esas reglas por su nombre; no las repite.
- [[bim-building-width-method|Calculadora de ancho de edificio]] — el método de tres zonas (Habitat / Magazine / Corridor) usado para dimensionar el ancho del edificio a partir de la profundidad del mobiliario. Esta guía utiliza la calculadora como un paso, pero no vuelve a derivar su fórmula ni sus cifras — consulte ese artículo directamente para la matemática de profundidad de zonas.
- [[bim-tile-system|Sistema de Tiles]] — el catálogo de las familias de Tile Pequeño, Mediano y Grande, y de los Tiles Especiales, hacia los que se dirige el resultado de esta guía.
- Un inventario de mobiliario y equipamiento para la categoría de inquilino que se está planificando — dimensiones reales de escritorios, estaciones de trabajo, mesas de tratamiento, mesones de laboratorio o equivalentes, no valores por defecto asumidos. El método solo funciona a partir de geometría medida.

## Pasos

**1. Confirme la categoría de inquilino.**
Identifique a qué categoría de ocupante profesional sirve el Key Plan — Oficina Privada, o un subtipo de Oficina Profesional (Médico, Empresarial, Laboratorio, Académico, Cívico), u Oficina Corporativa. La categoría determina qué conjunto de mobiliario y qué valores de profundidad de zona aplican; es la primera decisión porque todo lo que sigue depende de ella.

**2. Levante el inventario de mobiliario y equipamiento.**
Mida la huella física de la configuración principal de equipamiento para la categoría confirmada: la huella de la estación de trabajo o del área de tratamiento, la holgura de circulación requerida en cada lado, y cualquier adyacencia secundaria (archivo, almacenamiento o equipo fijo) que deba ubicarse dentro de la misma zona. Use dimensiones reales. Esta medición es el insumo geométrico para cada paso siguiente — el método no avanza a partir de cifras supuestas o redondeadas.

**3. Dimensione las tres zonas con la Calculadora de ancho de edificio.**
Procese el inventario de mobiliario a través de la Calculadora de ancho de edificio para establecer las profundidades de Zona 1 (Habitat), Zona 2 (Magazine) y Zona 3 (Corridor) para esta categoría de inquilino. Dos notas de trabajo que conviene retener de este paso, más allá de lo que cubre el artículo de la calculadora:

- La profundidad de la Zona 1 no queda fija una vez definida: puede intercambiarse contra la profundidad de la Zona 2, siempre que se preserven la disposición del mobiliario y las holguras de circulación. Un Magazine más ancho puede absorber un Habitat más estrecho, y viceversa.
- La profundidad mínima de la Zona 2 la determina el mayor entre dos requisitos: el de la sala de personal/conferencias o el del baño del inquilino. Cualquier profundidad adicional por encima de ese mínimo queda disponible para usos informales de diseño interior — el método mismo no la compromete a una función específica.

**4. Asigne la letra del Key Plan.**
Todo Key Plan dentro de la Clase de Desarrollo Profesional y Suburbana lleva un identificador de letra (de la A a la DD) vinculado a un programa o tipo de sala específico —Oficina Privada, un subtipo de Oficina Profesional, Oficina Corporativa, Salón de Inquilinos, Oficina del Administrador del Edificio, Sala de Correo, pasillos, baños, o un espacio de amenidad de Planta Principal (carga y descarga, reciclaje, sala de bicicletas, servicio de café/pan)—. Asigne la letra que corresponda al programa identificado en el Paso 1. Esta letra es la referencia permanente del Key Plan para cada paso de ensamblaje posterior.

**5. Verifique los mínimos de baños y salas compartidas contra el nivel del Key Plan.**
Si el Key Plan incluye un baño de inquilino, confirme que el número de artefactos corresponda a la configuración ya documentada en el artículo propio de esa categoría de inquilino — por ejemplo, Empresarial mantiene un conteo fijo de 2 cubículos en sus cinco opciones de configuración de baño, sin que ese número escale con el nivel del tile. No asuma que el número de artefactos escala por nivel Pequeña/Mediana/Grande a menos que el artículo propio de la categoría así lo indique. Esta es una de las dos restricciones (junto con la sala de personal/conferencias) que fija la profundidad mínima de la Zona 2 en el Paso 3 — verifíquelo aquí antes de continuar, ya que corregirlo más adelante implica volver a ejecutar el Paso 3.

**6. Agrupe los Key Plans en un Tile.**
Combine el Key Plan (o los Key Plans, en el caso de un Tile Compuesto) en un único Tile. Confirme la regla de un-Tile-una-zona-climática: todo Key Plan dentro de un Tile comparte un único control de HVAC/termostato, y ningún Tile puede quedar dividido entre dos Zonas Climáticas. Los inquilinos más pequeños suelen preferir Tiles más pequeños por esta razón — un Tile más pequeño significa que el inquilino no comparte el control climático con un vecino.

**7. Seleccione la familia de Tile que corresponda a la superficie ensamblada.**
Compare el total de Key Plans ensamblados contra la familia de Tile Pequeño, Mediano o Grande (véase [[bim-tile-system|Sistema de Tiles]] para el catálogo de familias). Los inquilinos más pequeños que buscan autonomía de zona climática eligen familias más pequeñas; los inquilinos más grandes, que priorizan espacio contiguo, aceptan una familia mayor a cambio de menos zonas.

**8. Trate por separado los Tiles de esquina y de remate (end-cap).**
Un Tile ubicado en una esquina del edificio o en una condición de remate no es simplemente un redimensionamiento de un Tile intermedio de la misma clase de tamaño — requiere su propio tratamiento de ubicación de puertas y de luz natural. Confirme que la variante de remate reciba luz natural en ambos ejes perpendiculares; una comparación documentada de disposiciones de remate de Oficina Profesional y Oficina Privada muestra que un remate sin luz natural en ambos ejes no alcanza el 100% de eficiencia en términos de arrendamiento. Si una condición de esquina también ubica un Tile de la familia Pequeña sobre una crujía estructural, márquelo para una revisión de la retícula estructural antes de finalizarlo — los Tiles Pequeños pueden entrar en conflicto con el módulo estructural en una esquina.

**9. Posicione los Tiles Especiales alrededor del Núcleo del Edificio.**
Los Tiles Especiales ocupan el área residual adyacente al Núcleo del Edificio. Colóquelos de manera que:

- Un inquilino que ocupe todo un lado corto del edificio conserve el control total de una Zona Climática.
- Ninguna puerta de un Tile Especial adyacente al núcleo quede directamente enfrentada a la apertura del ascensor.
- Cualquier desajuste entre la superficie agregada de los Key Plans ya ensamblados y la superficie propia del Tile Especial se concilie ajustando el Tile Especial, no dejando un vacío.

**10. Ensamble los Tiles, los Tiles Especiales y el Núcleo del Edificio en el Floor Plate.**
Sume los Tiles Básicos, los Tiles Compuestos, los Tiles Especiales y el Núcleo del Edificio. El total debe conciliar con el Área Neta Arrendable del Floor Plate (véase FP-SUM en la [[bim-floor-plate-methodology|metodología de floor plate]]) — esta guía no repite la banda de tolerancia de esa regla, solo señala que la verificación ocurre aquí, en el ensamblaje final, y no antes.

**11. Amplíe el Floor Plate añadiendo crujías, no estirando una existente.**
Si el Floor Plate ensamblado necesita ser mayor de lo que exige la mezcla de inquilinos, añada una crujía estructural adicional en posición escalonada (offset). No estire una crujía existente para ganar superficie — el método trata el estiramiento de crujías y la adición de crujías como operaciones distintas, y solo la segunda preserva la geometría aperiódica de Tiles establecida en los Pasos 6 a 9.

**12. Ejecute el estudio comparativo de Tiles Alternativos antes de finalizar.**
Antes de dar por definitiva cualquier combinación específica de Tiles, compárela contra las cuatro combinaciones base del estudio (Tiles A a D, que abarcan desde escala de Oficina Privada hasta Oficina Corporativa) más sus variantes de esquina y remate. El estudio existe para identificar qué combinación produce el conjunto de Tiles más eficiente y flexible para la mezcla de inquilinos de esa planta — una combinación elegida sin esta comparación no ha sido verificada contra las alternativas que el método está diseñado para ponderar.

## Verificación

Confirme lo siguiente antes de dar por completo un ensamblaje Key Plan → Tile → Floor Plate:

- La superficie agregada de Tiles Básicos + Tiles Compuestos + Tiles Especiales + el Núcleo del Edificio concilia con el Área Neta Arrendable (FP-SUM).
- Ninguna puerta de un Tile Especial adyacente al núcleo queda directamente enfrentada a la apertura del ascensor.
- Todo inquilino que ocupe un lado corto completo del edificio conserva el control de exactamente una Zona Climática — ningún control de HVAC de un inquilino queda dividido entre dos Tiles.
- El número de artefactos de baño corresponde a la configuración documentada en el artículo propio de esa categoría de inquilino (el número de artefactos no necesariamente escala por nivel Pequeña/Mediana/Grande — verifíquelo contra la fuente propia de la categoría en lugar de asumir un patrón de escalamiento).
- Todo Tile de remate recibe luz natural en ambos ejes perpendiculares.
- Las líneas de división (demising) caen sobre los límites de los Tiles, no sobre cortes ad hoc — esto es lo que permite recuperar el 100% de la eficiencia de arrendamiento cada vez que un inquilino desocupa el espacio ("eficiencia continua" o rolling efficiency).
- Todo Tile de la familia Pequeña ubicado en una esquina estructural ha pasado por una revisión de la retícula estructural.

**Una condición abierta que debe señalarse, no resolverse, en la verificación:** un inquilino puede arrendar un espacio que cruce el límite de un Tile siempre que las paredes divisorias sigan alineadas con los límites de los Tiles — pero al hacerlo pierde el control de Zona Climática de zona única. La metodología señala que esta condición permanece sin resolver por el diseño de Servicios del Edificio. No trate un arrendamiento que cruza límites como algo rutinario; remítalo a revisión de Servicios del Edificio en lugar de asumir que las reglas estándar de ensamblaje de Tiles lo cubren.

## Próximos pasos

- Consulte [[bim-floor-plate-tile-combinations|combinaciones de tiles de floor plate]] para ver ejemplos resueltos de ensamblajes terminados en cada clase de Floor Plate.
- Lea [[bim-zone-depths-per-use-type|profundidades de zona por tipo de uso]] si la categoría de inquilino del Paso 1 es una de aquellas cuyas cifras de Zona 1/Zona 2/Zona 3 aún figuran como pendientes en el artículo de la Calculadora de ancho de edificio.
- Si el Floor Plate en diseño mezcla categorías de inquilino con requisitos de ancho de edificio sustancialmente distintos (por ejemplo, un ancla Médica junto a un clúster de Oficina Privada), revise la guía de conciliación en [[bim-building-width-method|Calculadora de ancho de edificio]] antes de finalizar el Paso 10.
- Derive a Servicios del Edificio cualquier pregunta sobre arrendamiento que cruce límites de Tile surgida en la Verificación, antes de finalizar el contrato de arrendamiento — esta guía no resuelve esa condición abierta.
