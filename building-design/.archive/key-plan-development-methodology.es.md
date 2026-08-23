---
schema: foundry-doc-v1
title: "Metodología de desarrollo del Key Plan"
slug: key-plan-development-methodology
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
last_edited: 2026-08-03
editor: pointsav-engineering
short_description: "Cómo se desarrolla un Key Plan individual a partir de la geometría de mobiliario y equipamiento, y cómo se combina con otros en un Tile y en un Floor Plate — categoría de inquilino y dimensionamiento de zonas, el esquema de identificador de letra, mínimos de baño, selección de familia de Tile, tratamiento de esquina y remate, Tiles Especiales, y el estudio comparativo de Tiles Alternativos."
aliases:
  - build-a-key-plan-step-by-step
paired_with: building-design/key-plan-development-methodology.md
cites: []
---

El desarrollo del Key Plan es el proceso que convierte el inventario de mobiliario y equipamiento de un inquilino en un [[bim-tile-system|Tile]] ensamblado y, combinado con los demás Tiles de una planta, en un Floor Plate. Se ubica un nivel por debajo de la [[bim-floor-plate-methodology|metodología de floor plate]], cuyas reglas de composición FP-* (FP-SUM, FP-ENDCAP, FP-CORE, FP-SNAP, FP-CLIMATE, FP-DOORS, FP-CORNER) rigen lo que debe satisfacer un Floor Plate terminado — este artículo cubre cómo se construye y se lleva un Key Plan individual a través de la composición hacia ese fin, no las reglas de composición en sí. Asume el vocabulario expuesto en [[key-plans-and-tiles|Key Plans y Tiles]] —qué es un Key Plan, un Tile o un Floor Plate, y por qué el sistema es geométrico, autosimilar y aperiódico— y utiliza el método de tres zonas de la [[bim-building-width-method|Calculadora de ancho de edificio]] como una etapa de la secuencia, sin volver a derivar su fórmula ni sus cifras.

Las tres etapas difieren en escala. Desarrollar un único Key Plan a partir de un inventario de mobiliario, una vez que ese inventario está disponible, suele ser un ejercicio de una sola sesión. Agrupar Key Plans en un Tile y verificarlo contra las reglas de composición añade una segunda sesión. Ensamblar un Floor Plate completo —que requiere ejecutar el estudio comparativo de Tiles Alternativos en todas las categorías de inquilino de la planta— es un ejercicio más largo, medido en días y no en horas, porque depende de conciliar múltiples categorías de inquilino sobre una única retícula estructural compartida.

## La categoría de inquilino y la geometría de mobiliario como punto de partida

Todo Key Plan parte de la categoría de ocupante profesional a la que sirve —Oficina Privada, un subtipo de Oficina Profesional (Médico, Empresarial, Laboratorio, Académico, Cívico), u Oficina Corporativa. Esta categoría se confirma primero porque determina qué conjunto de mobiliario y qué valores de profundidad de zona aplican; todo lo que sigue depende de ella. A partir de ahí, el método requiere la huella física de la configuración principal de equipamiento para esa categoría —la huella de la estación de trabajo o del área de tratamiento, la holgura de circulación requerida en cada lado, y cualquier adyacencia secundaria (archivo, almacenamiento o equipo fijo) que deba ubicarse dentro de la misma zona. Esta huella debe provenir de dimensiones reales medidas de escritorios, estaciones de trabajo, mesas de tratamiento, mesones de laboratorio o equivalentes. El método no avanza a partir de cifras supuestas o redondeadas — el inventario de mobiliario es el insumo geométrico del que se derivan todas las etapas posteriores.

## Dimensionamiento de las tres zonas

El inventario de mobiliario se procesa a través de la [[bim-building-width-method|Calculadora de ancho de edificio]] para establecer las profundidades de Zona 1 (Habitat), Zona 2 (Magazine) y Zona 3 (Corridor) para la categoría de inquilino en cuestión. Dos propiedades de este dimensionamiento conviene retener, más allá de lo que cubre el propio artículo de la calculadora:

- La profundidad de la Zona 1 no queda fija una vez definida: puede intercambiarse contra la profundidad de la Zona 2, siempre que se preserven la disposición del mobiliario y las holguras de circulación. Un Magazine más ancho puede absorber un Habitat más estrecho, y viceversa.
- La profundidad mínima de la Zona 2 la determina el mayor entre dos requisitos: el de la sala de personal/conferencias o el del baño del inquilino (véase más abajo). Cualquier profundidad adicional por encima de ese mínimo queda disponible para usos informales de diseño interior — el método mismo no la compromete a una función específica.

## El identificador de letra del Key Plan

Todo Key Plan dentro de la Clase de Desarrollo Profesional y Suburbana lleva un identificador de letra (de la A a la DD) vinculado a un programa o tipo de sala específico —Oficina Privada, un subtipo de Oficina Profesional, Oficina Corporativa, Salón de Inquilinos, Oficina del Administrador del Edificio, Sala de Correo, pasillos, baños, o un espacio de amenidad de Planta Principal (carga y descarga, reciclaje, sala de bicicletas, servicio de café/pan). La letra asignada corresponde al programa identificado por la categoría de inquilino anterior, y funciona como la referencia permanente del Key Plan a lo largo de cada etapa posterior de ensamblaje.

## Mínimos de baños y salas compartidas

Cuando un Key Plan incluye un baño de inquilino, el número de artefactos sigue la configuración ya documentada en el artículo propio de esa categoría de inquilino, en lugar de una regla general — Empresarial, por ejemplo, mantiene un conteo fijo de 2 cubículos en sus cinco opciones de configuración de baño, un conteo que no escala con el nivel del Tile. No debe asumirse que el número de artefactos escala por nivel Pequeña/Mediana/Grande a menos que el artículo propio de la categoría así lo indique. Este requisito de baño es una de las dos restricciones —junto con la sala de personal/conferencias— que fija la profundidad mínima de la Zona 2 más arriba; un error aquí resulta costoso precisamente porque obliga a repetir la etapa de dimensionamiento de zonas.

## Agrupación de Key Plans en un Tile

Los Key Plans se combinan —un único Key Plan, o varios para un Tile Compuesto— en un Tile bajo la regla de un-Tile-una-zona-climática: todo Key Plan dentro de un Tile comparte un único control de HVAC/termostato, y ningún Tile puede quedar dividido entre dos Zonas Climáticas. Por esto los inquilinos más pequeños suelen preferir Tiles más pequeños — un Tile más pequeño significa que el inquilino no comparte el control climático con un vecino. El total de Key Plans ensamblados se compara luego contra la familia de [[bim-tile-system|Tile]] Pequeña, Mediana o Grande: los inquilinos más pequeños que buscan autonomía de zona climática eligen familias más pequeñas, mientras que los inquilinos más grandes, con espacio contiguo, aceptan una familia mayor a cambio de menos zonas.

## Tiles de esquina y de remate

Un Tile ubicado en una esquina del edificio o en una condición de remate no es simplemente un redimensionamiento de un Tile intermedio de la misma clase de tamaño — lleva su propio tratamiento de ubicación de puertas y de luz natural. La variante de remate necesita luz natural en ambos ejes perpendiculares; una comparación documentada de disposiciones de remate de Oficina Profesional y Oficina Privada muestra que un remate sin luz natural en ambos ejes no alcanza el 100% de eficiencia en términos de arrendamiento. Cuando una condición de esquina también ubica un Tile de la familia Pequeña sobre una crujía estructural, esto se señala para una revisión de la retícula estructural antes de finalizarlo, ya que los Tiles Pequeños pueden entrar en conflicto con el módulo estructural en una esquina.

## Tiles Especiales y el Núcleo del Edificio

Los Tiles Especiales ocupan el área residual adyacente al Núcleo del Edificio, colocados de manera que un inquilino que ocupe todo un lado corto del edificio conserve el control total de una Zona Climática, ninguna puerta de un Tile Especial adyacente al núcleo quede directamente enfrentada a la apertura del ascensor, y cualquier desajuste entre la superficie agregada de los Key Plans ya ensamblados y la superficie propia del Tile Especial se concilie ajustando el Tile Especial en lugar de dejar un vacío.

## Ensamblaje del Floor Plate

Los Tiles Básicos, los Tiles Compuestos, los Tiles Especiales y el Núcleo del Edificio suman el Floor Plate, y este total se verifica contra el Área Neta Arrendable del Floor Plate en esta etapa de ensamblaje final —la banda de tolerancia de FP-SUM pertenece a la [[bim-floor-plate-methodology|metodología de floor plate]], no a este artículo. Se espera que las líneas de división (demising) caigan sobre los límites de los Tiles y no sobre cortes ad hoc, lo cual es lo que permite recuperar el 100% de la eficiencia de arrendamiento cada vez que un inquilino desocupa el espacio — una propiedad conocida como eficiencia continua (rolling efficiency).

Cuando un Floor Plate ensamblado necesita ser mayor de lo que exige la mezcla de inquilinos, el método añade una crujía estructural adicional en posición escalonada (offset) en lugar de estirar una existente. El estiramiento de crujías y la adición de crujías se tratan como operaciones distintas, y solo la adición de crujías preserva la geometría aperiódica de Tiles establecida en la agrupación de Tiles y la colocación de Tiles Especiales descritas arriba.

## El estudio comparativo de Tiles Alternativos

Antes de dar por definitiva cualquier combinación específica de Tiles, se la compara contra las cuatro combinaciones base del estudio (Tiles A a D, que abarcan desde escala de Oficina Privada hasta Oficina Corporativa) más sus variantes de esquina y remate. El estudio existe para identificar qué combinación produce el conjunto de Tiles más eficiente y flexible para la mezcla de inquilinos de una planta determinada — una combinación elegida sin esta comparación no ha sido verificada contra las alternativas que el método está diseñado para ponderar.

## Una condición sin resolver: el arrendamiento que cruza límites

Un inquilino puede arrendar un espacio que cruce el límite de un Tile, siempre que las paredes divisorias sigan alineadas con los límites de los Tiles — pero al hacerlo pierde el control de Zona Climática única. Esta condición permanece actualmente sin resolver por el diseño de Servicios del Edificio, y se trata como una excepción que debe remitirse a revisión de Servicios del Edificio, no como una variante ya cubierta por las reglas estándar de ensamblaje de Tiles.

## Véase también

- [[key-plans-and-tiles]]
- [[bim-floor-plate-methodology]]
- [[bim-building-width-method]]
- [[bim-zone-depths-per-use-type]]
- [[bim-floor-plate-tile-combinations]]
- [[bim-tile-system]]
