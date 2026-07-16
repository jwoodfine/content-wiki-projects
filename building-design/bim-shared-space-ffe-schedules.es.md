---
schema: foundry-doc-v1
title: "Programas de mobiliario y equipamiento para espacios compartidos del núcleo del edificio"
slug: bim-shared-space-ffe-schedules
short_description: "Programas de Mobiliario, Instalaciones y Equipamiento (FFE) para los cinco componentes de espacio compartido de todo el edificio — Carga y Reciclaje, Núcleo del Edificio en Pisos Superiores, Baño Público del Vestíbulo, Estructura Auxiliar, y Oficina del Administrador del Edificio más Sala de Correo — y cómo el coeficiente de Disponibilidad por Tesela vincula la carga de mobiliario de cada programa con el tamaño de la Tesela."
category: building-design
type: topic
content_type: topic
quality: complete
status: pre-build
audience: operator
bcsc_class: vendor-internal
language_protocol: TRANSLATE-ES
last_edited: 2026-07-15
editor: pointsav-engineering
paired_with: building-design/bim-shared-space-ffe-schedules.md
cites: []
---

Los **Programas de FFE para Espacios Compartidos del Núcleo del Edificio** son los cinco programas de Mobiliario, Instalaciones y Equipamiento (FFE) del libro de trabajo de Plantas Clave que amueblan la infraestructura compartida de todo el edificio, a diferencia de una sola suite de arrendatario: Carga y Reciclaje, Núcleo del Edificio en Pisos Superiores, Baño Público del Vestíbulo, Estructura Auxiliar, y Oficina del Administrador del Edificio + Sala de Correo. Mientras que el [[bim-key-plans-index|índice de Plantas Clave]] cataloga estos espacios por Clase de Desarrollo, Tipología y código de índice, este artículo inventaría el contenido de mobiliario e instalaciones que los llena y explica cómo el coeficiente de Disponibilidad por Tesela del libro de trabajo vincula la carga de mobiliario de cada programa con la [[bim-tile-system|Tesela]] que la aloja. De los trece programas de FFE por espacio del libro de trabajo, estos cinco son el conjunto de todo el edificio; los ocho restantes — Negocio, Académico, Médico, Laboratorios, Cívico y Oficina Privada — son específicos de arrendatario y se catalogan por separado.

## Carga y Reciclaje

El programa de Carga y Reciclaje amuebla la función de carga de mercancías y manejo de residuos del edificio: puertas del muelle de carga, bancos de contenedores de basura y reciclaje clasificados por flujo, y el Cuarto de Bicicletas adyacente. En el [[bim-key-plans-index|índice de Plantas Clave]], estas tres funciones corresponden a tres entradas de índice separadas del Centro Profesional — Carga (X-1), Reciclaje (Y-1) y Cuarto de Bicicletas (Z-1) —, cada una con su propia fila de índice, aunque el libro de trabajo de FFE las agrupa en un único programa amueblado. La clase Oficina Suburbana repite el mismo vocabulario con el sufijo "-2".

## Núcleo del Edificio en Pisos Superiores

El programa de Núcleo del Edificio en Pisos Superiores amuebla el eje de circulación vertical y sistemas del edificio que se repite en cada piso sobre el nivel de acceso: el vestíbulo del ascensor, la escalera de servicio, un baño de piso y el cuarto de medidores. Las entradas Vestíbulo del Ascensor (S-1) y Baño de Arrendatario (U-1) en el índice de Plantas Clave nombran los componentes adyacentes al área arrendable; el Cuarto de Medidores (V-1) se indexa por separado en la clase General (Índice 25) como Tesela Especial, lo que refleja que es un elemento de área residual y no una Planta Clave arrendable. Este programa es el que está más directamente vinculado a la geometría de Teselas: el vestíbulo del ascensor y su antesala frontal se dimensionan según la Tesela Especial SP-C del [[bim-tile-system|sistema de teselas]] (aproximadamente 4.700 SF), mientras que el cuarto de medidores y las áreas de relleno adyacentes al núcleo recurren a las clases más pequeñas de Tesela Especial SP-A y SP-B, en lugar de las familias regulares de teselas de arrendatario Pequeña/Media/Grande.

## Baño Público del Vestíbulo

El programa de Baño Público del Vestíbulo amuebla el baño de planta baja que atiende a los visitantes del edificio y al tránsito del vestíbulo, distinto del Baño de Arrendatario por piso (U-1) cubierto bajo Núcleo del Edificio en Pisos Superiores. En el índice de Plantas Clave esto corresponde a la entrada Baños Públicos (DD-1), uno de los trece códigos de amenidad del Centro Profesional (Índice 26–38). El número de instalaciones escala con el volumen de tránsito del vestíbulo, no con la cantidad de personal de los arrendatarios, razón por la cual el libro de trabajo lo trata como un programa independiente en lugar de integrarlo al recuento de baños por piso.

## Estructura Auxiliar

El programa de Estructura Auxiliar amuebla la infraestructura exterior y de trastienda del predio que sostiene al edificio pero queda fuera de su envolvente arrendable: el recinto de basura, las plataformas del transformador y una caseta de jardinería. Ninguno de estos tres componentes tiene actualmente una entrada distinta en el [[bim-key-plans-index|Directorio de Plantas Clave]] — la clase Paisajismo del Directorio (Índice 59–62) cubre las Bioswales y la Galería de Irrigación, un alcance relacionado pero distinto de paisajismo del predio. Estructura Auxiliar es, por tanto, el único programa de FFE del núcleo del edificio sin un código de índice de Planta Clave correspondiente uno a uno; cerrar esa brecha es un pendiente del Directorio, no una deficiencia de este programa.

## Oficina del Administrador del Edificio + Sala de Correo

El programa de Oficina del Administrador del Edificio + Sala de Correo amuebla al personal administrativo y logístico interno del edificio: conjuntos de mobiliario de gerencia y de asistencia para la Oficina del Administrador del Edificio, un conjunto para el supervisor de la Sala de Correo, y un conjunto de vigilancia nocturna para la cobertura fuera de horario. El índice de Plantas Clave registra las entradas Administrador del Edificio (O-1) y Sala de Correo (P-1) como códigos separados del Centro Profesional; el libro de trabajo de FFE las combina en un único programa amueblado porque ambas funciones suelen compartir una misma suite de trastienda. Los códigos Sala de Descanso de Arrendatarios (N-1) y Atrio del Vestíbulo (EE-1) están adyacentes a este par en el índice, pero se amueblan bajo un programa distinto; los Casilleros del Personal del Edificio (BB-1) y el Banco de Trabajo (AA-1) son los equivalentes para el personal de mantenimiento y también quedan fuera del alcance de este programa.

## Disponibilidad por Tesela — el coeficiente de dimensionamiento

Disponibilidad por Tesela es el coeficiente metodológico que el libro de trabajo registra en cada programa de FFE por espacio, tanto de arrendatario como del núcleo del edificio: la fracción del área de piso de una Tesela que queda sin asignar una vez colocado el mobiliario de ese programa. En los programas de nivel de arrendatario ya publicados, el patrón es legible — Negocio, Académico y Cívico corren 0,2 / 0,6 / 0,2 en Pequeña / Media / Grande; Médico y Laboratorios corren 0,4 / 0,4 / 0,2; Oficina Privada, el programa más austero, corre 0,8 / 0,1 / 0,1. Una cifra de Disponibilidad más baja indica un nivel más denso en mobiliario en relación con su huella de Tesela, y el coeficiente es lo que permite al [[bim-tile-system|sistema de teselas]] validar que una disposición de mobiliario propuesta realmente cabe en la Tesela que se le asigna, en lugar de aproximarla únicamente por superficie.

Los programas del núcleo del edificio de este artículo se ubican en Teselas Especiales (SP-A, SP-B, SP-C) en lugar de las familias regulares Pequeña/Media/Grande que describen los coeficientes de nivel de arrendatario anteriores, y el libro de trabajo fuente no registra valores de Disponibilidad completados para ninguno de los cinco programas del núcleo del edificio en particular. Confirmar la Disponibilidad por programa para Carga y Reciclaje, Núcleo del Edificio en Pisos Superiores, Baño Público del Vestíbulo, Estructura Auxiliar, y Oficina del Administrador del Edificio + Sala de Correo es un pendiente frente al libro de trabajo de Plantas Clave, aún no resuelto por este ejercicio de extracción.

## Véase también

- [[bim-key-plans-index]]
- [[bim-tile-system]]
- [[bim-zone-depths-per-use-type]]
