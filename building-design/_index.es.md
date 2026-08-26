---
schema: foundry-doc-v1
title: "Diseño de Edificios"
slug: building-design-index
category: building-design
type: topic
content_type: topic
quality: complete
short_description: "El sistema de diseño: edificios diseñados desde el inquilino hacia afuera, placas de piso fijas, el núcleo desplazado, planos clave y módulos, estándares de medición y práctica BIM."
index_type: thematic
index_scope: building-design
status: active
bcsc_class: current-fact
language_protocol: TRANSLATE-ES
last_edited: 2026-08-26
editor: pointsav-engineering
paired_with: building-design/_index.md
---

Diseño de Edificios abarca el sistema de diseño detrás de cada edificio Woodfine: una geometría de arrendamiento fija, una práctica BIM de estándares abiertos, y las disciplinas de sitio y edificio que convierten esa geometría en una propiedad construible y sostenible.

<!-- START-HERE-HIGHLIGHT: engine reads this block to render the single "start here" card (reuses the existing cluster-card--start-here component). Do not add more than one. -->

**Comience aquí:** [[bim-design-philosophy|Filosofía de Diseño BIM]]

<!-- END-START-HERE-HIGHLIGHT -->

## Filosofía y Sistema de Diseño

[[bim-design-philosophy|Filosofía de Diseño BIM]] establece el compromiso central: los edificios se diseñan para cumplir con el código jurisdiccional en la etapa de diseño, no para verificarse después. [[design-system-bim|El Sistema de Diseño de la Construcción]] expone la capa de coordinación prevista que permitiría a superficies de autoría BIM independientes trabajar desde un vocabulario de especificación compartido. [[bim-market-context|Contexto del Mercado BIM]] y [[open-bim-regulatory-acceptance|BIM Abierto y Aceptación Regulatoria]] cubren los mandatos gubernamentales que ya empujan a la industria AEC hacia esos mismos estándares abiertos. [[aec-interface-conventions|Las Convenciones de Interfaz AEC]], [[bim-aec-muscle-memory|la Memoria Muscular AEC]] y [[property-manager-bim-gap|la Brecha BIM del Administrador de Propiedades]] cubren las convenciones de interfaz que toman prestadas las herramientas previstas y el problema de entrega — modelos que la mayoría de los gerentes de instalaciones nunca llegan a usar — que esta práctica está diseñada para cerrar.

<!-- AUTO-GENERATED MEMBERSHIP: DO NOT EDIT BELOW — regenerate from index_group: design-philosophy-and-system -->
- [[bim-design-philosophy]] — Los edificios de Woodfine se diseñan para cumplir con los códigos jurisdiccionales en la etapa de diseño, en lugar de verificarse después del hecho — una consecuencia de construir sobre estándares abiertos y portátiles desde el principio.
- [[design-system-bim]] — Una plataforma de sistema de diseño prevista para el entorno construido — la capa de coordinación que hoy falta y que permitiría a superficies de autoría BIM independientes trabajar desde un vocabulario de especificación compartido, del mismo modo en que un sistema de diseño de software mantiene consistentes a equipos de producto independientes.
- [[bim-market-context]] — Los mandatos gubernamentales de BIM en el Reino Unido, la UE y otras jurisdicciones exigen formatos de datos abiertos y neutrales respecto al proveedor; los edificios de Woodfine se diseñan y especifican conforme a esos estándares abiertos desde el principio.
- [[open-bim-regulatory-acceptance]] — El Modelado de Información para la Construcción es obligatorio en la mayoría de las economías del G7 para la contratación pública, con estándares abiertos y neutrales respecto al proveedor como requisito de entrega en lugar de formatos propietarios.
- [[aec-interface-conventions]] — Las herramientas de autoría BIM del sector comparten un vocabulario de interfaz común — jerarquía espacial, panel de propiedades, visor 3D y vistas guardadas — porque se construyen sobre el mismo modelo de datos IFC subyacente, lo que le da a la capa de interfaz prevista de PointSav una base compartida sobre la cual construir en lugar de inventar una nueva.
- [[bim-aec-muscle-memory]] — El Sistema de Diseño de la Construcción está previsto para adoptar patrones de interfaz ya familiares de las herramientas estándar de la industria AEC, de modo que los profesionales lleguen sin curva de aprendizaje, y para extender esa misma interfaz familiar a los flujos de gestión de instalaciones — vinculando mantenimiento, arrendamientos y datos de sensores en vivo al modelo del edificio.
- [[property-manager-bim-gap]] — Una parte sustancial de los gerentes de instalaciones no utiliza activamente los modelos BIM entregados en la entrega del proyecto, debido al costo del software, los requisitos de capacitación y la opacidad del formato de archivo — una brecha que los registros de construcción de Woodfine están diseñados para cerrar.
<!-- END AUTO-GENERATED -->

## Objetos BIM y el Registro Digital

[[bim-objects-what-they-are|Los Objetos BIM]] son el término de Woodfine para una especificación reutilizable de un elemento de construcción que lleva consigo sus propios requisitos de código y desempeño. [[bim-objects-substrate|Objetos BIM — Sustrato]] y [[bim-objects-three-layers|Objetos BIM — Tres Capas]] cubren las categorías primitivas fijas en que se organizan los objetos y las tres capas de información — qué es, qué exige la jurisdicción, qué exige el clima — que lleva cada objeto a la vez. [[asset-anchored-bim-vault|La Bóveda BIM Anclada al Activo]] y [[3d-asset-tokens|el Token de Activo Tridimensional]] cubren cómo se almacena y versiona el propio registro digital de un edificio.

<!-- AUTO-GENERATED MEMBERSHIP: DO NOT EDIT BELOW — regenerate from index_group: bim-objects-and-the-digital-record -->
- [[bim-objects-what-they-are]] — Un Objeto BIM es el término de Woodfine para una especificación reutilizable de un elemento de construcción que lleva consigo sus requisitos de código y desempeño aplicables, de modo que las configuraciones no conformes se detectan en la etapa de diseño en lugar de en la inspección.
- [[bim-objects-substrate]] — Los Objetos BIM se organizan en un conjunto pequeño y fijo de categorías primitivas — elementos espaciales, elementos físicos, materiales, sistemas, umbrales de desempeño y más — cada una anclada a normas abiertas de la industria (IFC, Uniclass, bSDD) en lugar de un esquema propietario, de modo que una especificación se mantiene portátil y verificable entre herramientas y proveedores.
- [[bim-objects-three-layers]] — Un Objeto BIM lleva tres capas de información a la vez — qué es, qué exige su jurisdicción y qué exige su clima — y prevalece la más estricta de las dos capas de requisitos cuando ambas se aplican a la misma propiedad.
- [[asset-anchored-bim-vault]] — El registro digital autoritario de un edificio estructurado como archivos de texto plano y binarios estandarizados en un directorio versionado con git, calificando como un Entorno de Datos Común conforme a ISO 19650 que viaja con la escritura de propiedad.
- [[3d-asset-tokens]] — La unidad de datos almacenados en el archivo, que combina una carga útil binaria inmutable, un esqueleto de metadatos legible por máquina y una conexión gráfica taxonómica dinámica que codifica la procedencia y el contexto.
<!-- END AUTO-GENERATED -->

## La Geometría de Arrendamiento

[[fixed-floor-plates|Las Placas de Piso Fijas]] y [[key-plans-and-tiles|los Planos Maestros y Módulos]] establecen la base estructural estandarizada y el sistema de planificación espacial autosimilar del que deriva cada edificio Woodfine. [[boma-standard|El Estándar BOMA]] es la base de medición compartida para toda área de arrendamiento y comparación de edificios. [[asset-architecture-standard|El Estándar de Arquitectura de Activos]] fija los requisitos estructurales uniformes — construcción de concreto y acero, dimensionamiento previo a la adquisición — aplicados en toda la cartera.

<!-- AUTO-GENERATED MEMBERSHIP: DO NOT EDIT BELOW — regenerate from index_group: the-leasing-geometry -->
- [[fixed-floor-plates]] — La base estructural estandarizada e inmutable utilizada en todos los edificios Woodfine, derivada de la geometría optimizada de los equipos para permitir una construcción repetible y un rendimiento espacial predecible.
- [[key-plans-and-tiles]] — Un sistema de planificación espacial geométrico y autosimilar derivado de la geometría de equipos y circulación de los inquilinos, utilizado para determinar las dimensiones de las placas de piso fijas.
- [[boma-standard]] — El estándar de medición de área de piso de la Building Owners and Managers Association, base de medición común para las áreas de arrendamiento y comparaciones de edificios de Woodfine.
- [[asset-architecture-standard]] — Requisitos estructurales uniformes para los desarrollos Woodfine: construcción de concreto y acero, dimensionamiento previo a la adquisición y configuración estandarizada en toda la cartera.
<!-- END AUTO-GENERATED -->

## Disciplinas de Sitio y Edificio

[[design-sequence-priority|La Prioridad de Secuencia de Diseño]] fija el orden de colaboración detrás de cada paquete de diseño: primero el Plan de Arrendamiento, luego Servicios del Edificio, y por último Estructural. [[four-to-one-parking-ratio|La Relación de Estacionamiento 4:1]] y [[water-management-system|el Sistema de Gestión del Agua]] se aplican a nivel de sitio. [[common-building-code|El Código de Construcción Común]], la [[tile-level-climate-zoning|zonificación climática a nivel de módulo]] y la [[structural-bay-depth-discipline|disciplina de profundidad del vano estructural]] se aplican a nivel de edificio y espacio arrendable. [[geometry-of-sustainability|Geometría de la Sostenibilidad]] y [[dual-mandate-building-certifications|las Certificaciones de Edificio de Doble Mandato]] cubren la ingeniería de costos operativos y la estrategia de certificación BREEAM/WELL que se derivan de ella.

<!-- AUTO-GENERATED MEMBERSHIP: DO NOT EDIT BELOW — regenerate from index_group: site-and-building-disciplines -->
- [[design-sequence-priority]] — El orden fijo de colaboración detrás de cada paquete de diseño de Woodfine: primero el Plan de Arrendamiento, luego Servicios del Edificio, y por último Estructural — cada disciplina diseñando sobre una capa previa ya completada en lugar de negociar en paralelo.
- [[four-to-one-parking-ratio]] — El estándar de estacionamiento de cuatro cajones por cada 1.000 pies cuadrados de área arrendable neta que Woodfine aplica en los Mercados Regionales, donde el automóvil privado es la única forma práctica en que los clientes de un inquilino llegan al edificio.
- [[water-management-system]] — Un mecanismo de conservación de agua para el día a día — almacenamiento en cisterna y galería de irrigación, un sistema de plomería de aguas grises, pavimento permeable y biozanjas — que hace que el paisajismo de un Sitio de Desarrollo sea autosuficiente en lugar de depender de la infraestructura pluvial municipal.
- [[common-building-code]] — El estándar interno de provisión de baños de Woodfine, superpuesto al código de construcción jurisdiccional y determinado por la Combinación de Inquilinos y el tráfico peatonal diario, no solo por los mínimos de código.
- [[tile-level-climate-zoning]] — El estándar de granularidad de servicios del edificio de Woodfine: cada Módulo tiene su propio termostato, con Módulos Especiales que reciben una zona climática autocontrolada, en lugar de zonificar a nivel de espacio arrendable individual o de piso completo.
- [[structural-bay-depth-discipline]] — Una disciplina de la cuadrícula estructural que exige fijar la profundidad del vano de un espacio arrendable según las necesidades del inquilino, no según el vano de viga más económico disponible, dado que la profundidad no arrendable de un vano sobredimensionado nunca se recupera durante la vida del contrato de arrendamiento.
- [[geometry-of-sustainability]] — Disciplina de ingeniería que aplica normas europeas, suizas y alemanas de iluminación, aire y circulación a la Planta Fija, para mejorar la eficiencia de los costos operativos del edificio.
- [[dual-mandate-building-certifications]] — Estrategia de arrendamiento que certifica cada Woodfine Building bajo los estándares BREEAM y WELL, dirigida a Arrendatarios Nacionales que dejan oficinas heredadas obsoletas.
<!-- END AUTO-GENERATED -->

## Véase también

- [[buildings-index|Edificios]]
- [[site-selection-index|Selección de Sitios]]
