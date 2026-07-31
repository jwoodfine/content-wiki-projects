---
schema: foundry-doc-v1
title: "Sistema de diseño de la construcción"
slug: design-system-bim
language: es
category: building-design
type: topic
content_type: topic
status: active
last_edited: 2026-07-31
editor: pointsav-engineering
short_description: "Una plataforma de sistema de diseño para el entorno construido organizada en ocho categorías primitivas de BIM Objects y diez componentes universales de interfaz AEC, proporcionando vocabulario de especificación compartido para que superficies de autoría independientes se coordinen sin introducir nuevas superficies de aprendizaje."
cites: [ifc-4-3, uniclass-2015, bsdd-v1, ids-1-0, dtcg-w3c]
paired_with: building-design/design-system-bim.md
---

Los grandes sistemas de diseño de software resuelven un problema de coordinación a escala: cuando equipos independientes crean superficies de interfaz de forma paralela, la consistencia se rompe a menos que las decisiones de diseño estén codificadas en una capa compartida de tokens, recetas de componentes y patrones de interacción que todas las superficies deben consumir. No existe un sistema equivalente para el entorno construido. La producción BIM se coordina a través de normas compartidas (IFC, Uniclass, bSDD) y herramientas de autoría compartidas, pero no existe una capa de Objetos BIM común — ninguna biblioteca canónica y legible por máquina de especificaciones de elementos del entorno construido que las superficies de autoría consuman por referencia. Una investigación encargada en abril de 2026 analizó el estado del arte disponible y encontró ese espacio vacío. El Sistema de Diseño de la Construcción está concebido para llenarlo. Se compone de ocho [[bim-objects-substrate|categorías primitivas de Objetos BIM]] y diez [[aec-interface-conventions|componentes universales de interfaz AEC]].

## Por qué el espacio está vacío

Tres factores estructurales mantuvieron vacío ese espacio.

**Dominio de herramientas de autoría propietarias.** Las herramientas BIM dominantes han almacenado históricamente las especificaciones de elementos en formatos de objetos propietarios. Estos formatos contienen geometría, comportamiento paramétrico y algunos metadatos, pero están bloqueados por formato, no son interoperables entre herramientas y no están diseñados para llevar datos normativos. Sirven como biblioteca de elementos para una sola herramienta, no como capa de especificación compartida entre herramientas.

**IFC como formato de intercambio, no de especificación.** IFC 4.3 (ISO 16739-1:2024) es un formato de intercambio neutro — expresa lo que contiene un modelo, no lo que requiere una especificación de token. El mecanismo de conjuntos de propiedades IFC proporciona plantillas para valores de propiedad pero no lleva lógica de aplicación, jerarquía de restricciones ni mapeo jurisdiccional.

**Fragmentación de normas.** La pila de normas del entorno construido — IFC, Uniclass, Omniclass, MasterFormat, CoClass, NBS, bSDD — evolucionó en paralelo entre jurisdicciones. Ninguna proporciona una capa de especificación composable análoga al DTCG.

El Sistema de Diseño de la Construcción usa cada una de estas normas en su función adecuada: IFC como jerarquía de tipos de entidad, Uniclass 2015 como base de clasificación, bSDD como identidad semántica e IDS 1.0 como expresión de restricciones. DTCG proporciona el formato contenedor y el mecanismo de alias.

## Las ocho categorías de Objetos BIM primitivos

La capa de Objetos BIM está organizada en ocho categorías de primitivos, cada una correspondiente a un grupo de tipos de entidades IFC 4.3:

1. **Espacial** — jerarquía `IfcSpatialElement`: sitio, edificio, planta, espacio, zona.
2. **Elementos** — jerarquía `IfcBuiltElement`: muros, losas, vigas, columnas, puertas, ventanas, escaleras, rampas. Los Objetos BIM de elementos llevan la especificación completa de tres capas porque son los objetos primarios de restricción normativa.
3. **Sistemas** — jerarquía `IfcDistributionElement`: mecánico, eléctrico, fontanería, protección contra incendios, HVAC.
4. **Materiales** — especificaciones `IfcMaterial` e `IfcMaterialLayer`, incluyendo conductividad térmica, grado estructural y clasificación de reacción al fuego.
5. **Conjuntos** — composiciones `IfcElementAssembly`: un Objeto BIM de conjunto de muro cortina referencia sus Objetos BIM de componentes mediante el mecanismo de alias DTCG.
6. **Rendimiento** — plantillas `IfcPropertySet` para especificaciones de rendimiento transversales: puentes térmicos, permeabilidad al aire, índices de aislamiento acústico.
7. **Identidad y Códigos** — tablas de mapeo entre identificadores de Objetos BIM y sistemas de clasificación externos: Uniclass 2015, Omniclass Tabla 23, referencias de sección NBS, Masterformat 2018.
8. **Zonas climáticas** — tablas de parámetros de rendimiento por identificador de zona climática (ASHRAE 90.1, NBC canadiense, EN ISO 52000).

## El nivel de componentes de interfaz AEC

Por encima de la capa de [[bim-objects-substrate|Objetos BIM primitivos]], el Sistema de
Diseño de la Construcción define un conjunto de [[aec-interface-conventions|componentes
universales de interfaz AEC]] — patrones de interfaz comunes a cualquier superficie de
autoría con capacidad BIM, independientemente del tipo de programa específico.

La investigación identificó diez componentes universales que aparecen en todo contexto de
autoría BIM:

1. **Árbol espacial BIM** — Presentación jerárquica de `IfcSite → IfcBuilding →
   IfcBuildingStorey → IfcSpace`. El árbol de navegación canónico para la contención espacial.
2. **Panel de propiedades BIM** — Presentación estructurada de las propiedades del elemento:
   tipo IFC, conjuntos de propiedades aplicables, valores de propiedad actuales, referencia
   Uniclass, enlace URI bSDD y resumen de superposición normativa.
3. **Vista 3D BIM** — Renderizador WebGL de doble precisión para geometría IFC. Usa
   xeokit-sdk para renderizado de doble precisión (requerido para exactitud de coordenadas en
   sitios grandes).
4. **Navegador de vistas BIM** — Controles de vista ortográfica: planta, sección, elevación.
   Control de plano de sección y sincronización de vistas para diseños multi-vista.
5. **Búsqueda de GUID BIM** — Superficie de búsqueda de `IfcGlobalId`.
6. **Registro de auditoría BIM** — Registro cronológico de cambios del modelo frente a la
   conformidad de la especificación de Objetos BIM.
7. **Navegador de normativa BIM** — Explorador de jurisdicciones y normas. Muestra las
   superposiciones normativas registradas con filtro por jurisdicción, tipo de elemento y
   fecha de vigencia.
8. **Tarjeta de catálogo de Objeto BIM** — La tarjeta de cuadrícula para una categoría de
   Objeto BIM en la página índice del catálogo.
9. **Pestaña de detalle de Objeto BIM** — La vista de detalle con pestañas para una sola
   categoría de Objeto BIM: pestaña de Especificación, pestaña de Normativa, pestaña de Zona
   Climática.
10. **Tarjeta de superposición de código BIM** — Unidad de presentación para una sola
    superposición normativa registrada: nombre de jurisdicción, identificador de la norma,
    resumen de restricciones, enlace al archivo IDS, fecha de vigencia.

Tres de estos componentes (Árbol Espacial, Panel de Propiedades, Vista 3D) están
implementados en v0.0.1. Los siete restantes están previstos para v0.0.2 y v0.0.3.

## Extensiones específicas de superficie

Más allá de los componentes universales, cada tipo de programa del entorno construido tiene
un conjunto distinto de requisitos de interfaz. Tres tipos de programa están en alcance en
v0.0.1:

**app-orchestration-bim** — La superficie web del catálogo de Objetos BIM. Muestra el
catálogo completo, las superposiciones normativas y la referencia de normas. Solo lectura;
sirve a diseñadores, reguladores y consumidores automatizados.

**app-workplace-bim** — El banco de trabajo de autoría BIM. Aplicación de escritorio Tauri
2.x que incorpora xeokit para renderizado 3D e IfcOpenShell (vía sidecar) para el análisis de
archivos IFC. Licenciada bajo AGPL-3.0 debido a la licencia del componente xeokit.

**app-console-bim** — La consola administrativa para la gestión de la bóveda de Objetos BIM.
Aplicación Axum exclusivamente web. Superficie de lectura para la exploración de objetos;
superficie de escritura (prevista para v0.1.x) para la autoría de Objetos BIM mediante el
modelo CMS de cuatro zonas.

## Uniclass 2015 como piso de clasificación

Todos los Objetos BIM usan Uniclass 2015 como piso de clasificación. Uniclass 2015 es la
norma de clasificación abierta mantenida en el Reino Unido que ofrece una referencia
estructurada para elementos, sistemas, productos y actividades del entorno construido. Es
mantenida por NBS y se publica bajo términos de licencia abierta.

Uniclass 2015 fue seleccionada sobre otros sistemas de clasificación abiertos comparables
porque es la más mantenida de manera consistente, se corresponde bien con los tipos de
entidad IFC 4.3 en el nivel de detalle apropiado para la especificación de objetos, y es
neutral respecto a la jurisdicción a pesar de su origen británico.

La bóveda de Objetos BIM incluye la tabla completa de Uniclass 2015 como un archivo DTCG
separado (`identity-codes.dtcg.json`), lo que permite que los Objetos BIM referencien los
códigos de clasificación por alias en lugar de duplicar el texto de la clasificación.

## El modelo de bóveda soberana

El Sistema de Diseño de la Construcción no es un servicio alojado externamente. Es un conjunto de archivos JSON en un repositorio git — la [[asset-anchored-bim-vault|bóveda de Objetos BIM]]. Las organizaciones que operan la plataforma clonan el repositorio de la bóveda, lo extienden con sus propias superposiciones normativas y datos de zona climática, y configuran su instancia local de `app-orchestration-bim` para leer desde su copia local.

La capa de proveedor (`pointsav-design-system`) mantiene los Objetos BIM primitivos universales, las recetas de componentes y los archivos de investigación. Las bóvedas de capa de cliente extienden la capa del proveedor con adiciones jurisdiccionales y específicas de programa. Las instancias de despliegue leen desde la bóveda del cliente. Ningún dato fluye hacia arriba: proveedor → cliente → despliegue únicamente.

## Véase también

- [[bim-objects-what-they-are]]
- [[bim-objects-three-layers]]
- [[bim-objects-substrate]]
- [[flat-file-bim-leapfrog]]
