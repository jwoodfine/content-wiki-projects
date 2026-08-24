---
schema: foundry-doc-v1
title: "BIM abierto y aceptación regulatoria"
slug: open-bim-regulatory-acceptance
language: es
category: building-design
type: topic
content_type: topic
status: active
last_edited: 2026-08-24
editor: pointsav-engineering
short_description: "El modelado de información de construcción es obligatorio en la mayoría de las economías del G7 para contratación pública, con estándares abiertos — IFC 4.3, IDS 1.0, COBie — como requisito de entrega en lugar de formatos propietarios. Las plataformas BIM sin conexión y autohospedadas son el único tipo de arquitectura que satisface de forma nativa los requisitos de datos soberanos impuestos por ITAR, GDPR, HIPAA y marcos regulatorios equivalentes."
cites: [ifc-4-3, iso-19650, ids-1-0]
paired_with: building-design/open-bim-regulatory-acceptance.md
---

El Modelado de Información para la Construcción ya no es opcional en la contratación pública para la mayoría de las economías del G7. El gobierno federal de los Estados Unidos ha requerido entregables BIM en formato IFC para proyectos importantes de infraestructura y edificación desde 2007. La Unión Europea ha incorporado requisitos BIM en las directivas de contratación pública aplicadas en los estados miembros. El Reino Unido, Singapur, Noruega, Dinamarca, los Países Bajos y Australia han emitido mandatos nacionales o requisitos de política equivalentes. El panorama regulatorio para el BIM Abierto está definido. La pregunta abierta es qué plataformas pueden cumplir los requisitos de soberanía de datos adjuntos a estos mandatos. Véase [[flat-file-bim-leapfrog|el salto del BIM de archivo plano]] y [[asset-anchored-bim-vault|la bóveda BIM anclada al activo]].

## Definición de BIM Abierto

El BIM Abierto, según la definición de buildingSMART International, denota un enfoque de flujo de trabajo e intercambio de datos donde:

1. Los datos del modelo se almacenan e intercambian en formatos abiertos neutros respecto al proveedor, principalmente IFC (ISO 16739-1:2024).
2. Las definiciones de clasificación y propiedad referencian diccionarios abiertos, principalmente bSDD.
3. Las especificaciones de restricciones se expresan en lenguajes de restricción abiertos, principalmente IDS 1.0.
4. Los datos de entrega se formatean según estándares abiertos de gestión de instalaciones, principalmente COBie.

## Mandatos Federales de los Estados Unidos

**Administración de Servicios Generales (GSA).** El Programa Nacional de BIM 3D-4D de la GSA requiere datos espaciales y de programa en formato IFC para proyectos por encima de umbrales definidos. Se requieren entregables COBie para la transferencia.

**Cuerpo de Ingenieros del Ejército de los EE. UU. (USACE).** El Plan de Acción BIM del USACE exige BIM para proyectos de construcción militar (MILCON) y obras civiles por encima de 5 millones de dólares.

**Departamento de Asuntos de Veteranos (VA) y Comando de Ingeniería de Instalaciones Navales (NAVFAC).** Ambas agencias han publicado normas BIM que requieren exportaciones IFC en hitos de diseño.

**Compatibilidad con el Reglamento Federal de Adquisiciones (FAR).** Apache 2.0 (la licencia bajo la cual se publican los archivos de datos de Objetos BIM) es una licencia de código abierto aprobada por la OSI. Las disposiciones de la Parte 27 del FAR para software de código abierto no prohíben datos con licencia Apache 2.0 en contratos federales, y sus términos permisivos no generan complicaciones de copyleft en la contratación gubernamental.

## Unión Europea

La Directiva de Contratación Pública de la UE de 2014 (Directiva 2014/24/UE) permite explícitamente a los estados miembros requerir herramientas BIM electrónicas para contratos de construcción financiados con fondos públicos.

**Alemania.** El Ministerio Federal de Asuntos Digitales y Transporte (BMDV) emitió una hoja de ruta BIM con objetivos para la infraestructura federal de transporte establecidos para 2020 (fase de diseño) y 2025 (ciclo de vida completo).

**Italia.** El mandato BIM de Italia se origina en el Decreto Ministerial 560/2017, que introdujo por fases el uso obligatorio de BIM en obras públicas según el valor del proyecto a partir de enero de 2019, alcanzando todas las obras públicas para 2025. El Código de Contratos Públicos de 2023 (Decreto Legislativo 36/2023) continúa este requisito de digitalización bajo el marco de contratación vigente.

**España.** El Plan de Impulso de la Contratación Pública de Edificación BIM (PPRE 2022-2026) establece un mandato progresivo que apunta a la implementación completa en todas las obras públicas para 2026.

**Dinamarca.** Dinamarca ha requerido BIM en proyectos de edificación financiados por el Estado por encima de DKK 5 millones desde 2013.

**Noruega.** Statsbygg ha requerido entregables de BIM Abierto desde 2016. El Manual BIM de Statsbygg especifica IFC 4.x y requisitos de LOD por fase de proyecto.

**Países Bajos.** Rijkswaterstaat y ProRail operan programas de requisitos BIM que especifican entregables IFC y datos de transferencia COBie para proyectos de infraestructura de gran envergadura.

**Reino Unido.** El mandato de BIM Nivel 2 del Gobierno del Reino Unido para proyectos del sector público contratados centralmente ha estado vigente desde 2016. BS EN ISO 19650 fue adoptada como norma nacional del Reino Unido en 2019.

## Certificación buildingSMART

buildingSMART International opera un programa de certificación de software para implementaciones de importación/exportación IFC. Se prevé que la plataforma BIM de PointSav obtenga la certificación buildingSMART para sus implementaciones de exportación e importación IFC. La Vista de Referencia IFC 4.3 y la Vista de Transferencia de Diseño son las dos certificaciones objetivo para herramientas de autoría; la plataforma de Objetos BIM apunta a la certificación frente a la especificación de intercambio de Conjuntos de Propiedades.

## Arquitectura Soberana de Datos como Requisito de Contratación

**ITAR (Reglamento sobre el Tráfico Internacional de Armas).** Los proyectos de construcción de defensa que involucran datos sensibles de instalaciones están sujetos a ITAR y EAR. Una plataforma de primer uso sin conexión, autohospedada, que nunca transmite datos del modelo fuera de la red de la instalación, es la única arquitectura que satisface los requisitos ITAR sin autorización de nube comercial.

**RGPD (Reglamento General de Protección de Datos).** Los datos de ocupación de edificios, datos de sensores y registros de gestión de instalaciones asociados con gemelos digitales BIM pueden contener datos personales. Una plataforma BIM autohospedada que procesa datos dentro de la jurisdicción de la UE elimina la pregunta de transferencia.

**HIPAA.** La construcción de instalaciones sanitarias genera datos BIM asociados con el flujo de pacientes y la programación del espacio clínico. Una plataforma autohospedada con controles de acceso alineados con la postura de seguridad de la instalación satisface estos requisitos.

## ISO 19650 y el Entorno de Datos Común

Un repositorio git satisface los requisitos del EDC de ISO 19650:

| Concepto ISO 19650 | Implementación Git |
|---|---|
| Contenedor de información | Archivo IFC o sidecar YAML |
| UID del contenedor | Hash de objeto Git o GUID IFC |
| Estado | Nombre de rama (`work-in-progress`, `shared`, `published`) |
| Revisión | Hash de confirmación Git |
| Clasificación | Ruta de directorio + encabezado YAML |
| Historial de cambios | `git log --follow <filename>` |
| Estados de flujo de trabajo del EDC | Flujo de fusión de ramas Git / solicitudes de extracción (pull request) |

Un proyecto BIM gestionado a través de una bóveda de objetos y un repositorio de modelos alojados en git opera dentro de un EDC conforme a ISO 19650, sin necesidad de una plataforma construida a medida.

## Licencia Apache 2.0 y Ventaja en Contratación

Los archivos de datos de Objetos BIM se publican bajo Apache 2.0. Esta licencia tiene tres propiedades relevantes para la contratación pública.

**Aprobada por la OSI.** Apache 2.0 figura en la lista de licencias aprobadas de la Open Source Initiative (OSI).

**Compatible con el FAR.** Los términos permisivos de Apache 2.0 no generan complicaciones de copyleft en la contratación federal, y la cláusula de concesión de patentes aporta protección adicional para el uso gubernamental.

**Compatibilidad amplia.** Apache 2.0 es compatible con GPL-3.0, LGPL, MIT y EUPL-1.2 — lo que permite combinarla con componentes bajo una variedad de licencias de código abierto sin análisis de cumplimiento adicional.

## Preguntas Abiertas

**Cronograma de certificación buildingSMART.** El servicio de certificación IFC 4.3 no aceptaba envíos para todos los tipos de vista a la fecha de esta investigación. El cronograma de certificación para la plataforma BIM de PointSav no está fijado. Esto afecta cómo puede representarse la plataforma en respuestas de contratación que exigen conformidad IFC certificada.

**Mapeo de instalaciones ITAR.** La lista de tipos específicos de instalaciones donde aplican las restricciones ITAR a los datos BIM no está enumerada públicamente por el Gobierno de los EE. UU. Se requiere revisión legal antes de representar la plataforma como certificada para construcción restringida por ITAR. La arquitectura sin conexión desde el diseño es un hecho técnico que puede afirmarse; cualquier declaración de conformidad ITAR requiere revisión de asesoría legal.
