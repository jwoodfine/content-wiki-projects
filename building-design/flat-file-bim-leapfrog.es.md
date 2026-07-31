---
schema: foundry-doc-v1
title: Salto tecnológico del BIM de archivo plano
slug: flat-file-bim-leapfrog
language: es
category: building-design
type: topic
content_type: topic
status: active
last_edited: 2026-07-31
short_description: "El Building Design System se construye sobre cinco restricciones arquitectónicas — almacenamiento de archivos planos, estándares abiertos, Rust y Tauri, funcionamiento sin conexión y licencia Apache 2.0 — permitiendo modelos de información de construcción supervivientes a la obsolescencia de proveedores. La propiedad anclada en activos, la capacidad sin conexión, la integración IoT y la convergencia de BIM con libros mayores de arrendamiento y financieros se derivan de la arquitectura en sí."
paired_with: building-design/flat-file-bim-leapfrog.md
---


El [[design-system-bim|Sistema de Diseño de Edificios]] de PointSav redefine la categoría de producto BIM mediante un enfoque de "archivo plano" que devuelve la soberanía del dato al propietario del activo. La pila de estándares abiertos — IFC 4.3 (ISO 16739-1:2024, publicado en abril de 2024), IDS 1.0 (buildingSMART, junio 2024) y BCF 3.0 — alcanzó madurez de producción en 2024 y proporciona la infraestructura que hace viable esta estrategia. Mientras que las grandes plataformas de software fuerzan un modelo de alquiler de datos en la nube, la arquitectura de la plataforma permite que el gemelo digital sea una propiedad permanente, transferible y legible durante décadas.

## La pila de estándares alcanzó madurez de producción en 2024

La base es que los estándares existen, especifican codificaciones de texto plano y forman parte de la ISO. IFC 4.3 se publicó formalmente como ISO 16739-1:2024 en abril de 2024, extendiendo IFC de los edificios a puentes, carreteras, ferrocarriles, puertos y vías navegables. La serialización canónica, IFC-SPF, es texto plano ISO 10303-21 — legible en cualquier editor de texto. IDS 1.0 se convirtió en el estándar oficial de buildingSMART el 1 de junio de 2024. BCF 3.0 es un ZIP de archivos de marcado XML más capturas PNG — al descomprimirlo, el árbol de directorios por tema es prosa comparable (diff-able) y compatible con git. CityJSON 2.0 es un estándar comunitario de la OGC, con CityJSONSeq utilizado a escala nacional por el conjunto de datos 3DBAG de TU Delft para más de 10 millones de edificios neerlandeses.

Lo que aún no está listo para producción importa igualmente. ifcJSON sigue siendo un borrador comunitario. IFC 5 está en fase alfa, con una serialización IFCX basada en JSON que toma prestada la composición al estilo USD de OpenUSD de Pixar; se esperan cambios disruptivos. La conclusión pragmática: canonizar sobre IFC-SPF hoy, reflejar a ifcJSON de forma oportunista, y diseñar el modelo de objetos de modo que una migración a IFC 5 / IFCX esté pensada como un cambio de serialización, no una reescritura.

## Qué significa "archivo plano"

Un directorio de archivos de texto plano y binarios estandarizados que un editor de texto ordinario o un visor SVG puede abrir sin un SDK propietario, décadas después de que el proveedor de software que lo produjo haya desaparecido.

| Formato | ISO / editor | Función |
|---|---|---|
| IFC-SPF (`.ifc`) | ISO 16739-1:2024 | Geometría y semántica autoritativas |
| IDS 1.0 | buildingSMART (junio 2024) | Contrato de validación |
| BCF 3.0 | buildingSMART | Historial de colaboración por tema |
| COBie vía ifccsv | NIST | Entrega de activos |
| Sidecars YAML por elemento | convención local | Datos Pset_*, sensores y órdenes de trabajo |
| Almacén de objetos direccionado por hash | convención local; inspirado en Speckle | DAG de Merkle versionado |
| glTF 2.0 | ISO/IEC 12113:2022 | Caché de visualización (regenerable) |
| SVG | ISO/IEC 14496-22:2019 | Dibujos 2D (regenerables) |
| CityJSONSeq | OGC | Portafolio / contexto urbano |

El archivo `.ifc` es el estado espacial y semántico autoritativo del edificio. Los sidecars llevan datos no geométricos (calificaciones, cantidades, lecturas de sensores, órdenes de trabajo, referencias de arrendamiento). La capa de almacén de objetos otorga a todo el archivo semánticas de versionado de grado git. Los derivados de visualización son cachés que se regeneran a voluntad desde la fuente autoritativa. Cualquier visor o herramienta de autoría BIM específico es reemplazable. El archivo es permanente.

## Pilares Arquitectónicos

La estrategia se basa en cinco restricciones que garantizan la independencia del proveedor:

1. **Archivos Planos:** Almacenamiento en formatos de texto legibles sin SDK propietario, accesibles con cualquier editor de texto décadas después de que el proveedor original haya desaparecido.
2. **Estándares Abiertos:** Uso estricto de ISO IFC 4.3, IDS 1.0 y BCF 3.0 como formatos autoritativos.
3. **Rust + Tauri:** Entorno de ejecución seguro, eficiente en memoria y de alto rendimiento.
4. **Primero fuera de línea (Offline-First):** Funcionalidad BIM total sin dependencia de conexión a internet.
5. **Licencia Apache 2.0:** Los archivos de datos de Objetos BIM se publican bajo Apache 2.0, aprobado por la OSI, compatible con la contratación pública (FAR 12.212) y con el uso comercial derivado.

## Capacidades Diferenciadoras

- **[[asset-anchored-bim-vault|BIM Anclado al Activo]]:** El gemelo digital se firma con el título de propiedad y se transfiere con la escritura. Los modelos de suscripción en plataformas en la nube generan un riesgo explícito: el vencimiento del contrato puede requerir un nuevo acuerdo de suscripción para acceder a los datos del proyecto. El archivo plano es propiedad permanente del activo, no un servicio de alquiler.
- **Operación sin Conexión:** Las plataformas BIM basadas en la nube requieren conexión a internet por diseño. El shell Rust + Tauri con un archivo IFC local preserva la funcionalidad BIM completa en sótanos, obras remotas, instalaciones de defensa con aislamiento de red (air-gap), entornos hospitalarios y zonas de conectividad limitada.
- **Supervivencia a la Obsolescencia:** Los edificios viven más de 50 años; los formatos de autoría BIM propietarios tienen ventanas de compatibilidad de tres a cinco años. El sustrato de archivo plano garantiza que los datos sean legibles décadas después de que el proveedor original haya desaparecido — una ventaja decisiva para propietarios de largo plazo, patrimonio cultural e infraestructura pública.
- **Integración IoT Soberana:** Los sensores inyectan datos directamente en sidecars YAML locales vía broker MQTT, sin que los datos abandonen las instalaciones del propietario. Esto elimina cargos por tokens basados en el número de sensores y cumple con el RGPD, HIPAA y normativas de residencia y control de exportación de datos.
- **Convergencia Legal, Financiera y Espacial:** La familia de aplicaciones de escritorio — `app-workplace-bim`, `app-workplace-proforma`, `app-workplace-memo` y `app-workplace-presentation` — tiene como objetivo reunir el edificio, el contrato de arrendamiento y el libro mayor financiero en un único archivo portátil (Totebox Archive): la primera arquitectura donde la identidad legal, financiera, espacial y operacional de un edificio son un único artefacto que viaja con el activo.

## Postura Regulatoria

El formato IFC-SPF + IDS 1.0 + BCF 3.0 + COBie cumple los requisitos de entrega en estándares abiertos exigidos por agencias federales de EE. UU. (GSA, USACE, VA, NAVFAC), estados miembros de la UE (Alemania, Italia, España, Dinamarca, Noruega, Países Bajos, Polonia), el Marco BIM del Reino Unido, Singapur CORENET X (obligatorio desde octubre de 2026) y Dubái (obligatorio desde enero de 2024). Véase [[open-bim-regulatory-acceptance|aceptación regulatoria del BIM abierto]] para el mapa completo.

La arquitectura offline-first es la única que satisface por diseño los requisitos ITAR de aislamiento de red para proyectos de defensa, la Ley de Datos de la UE, los requisitos técnicos de la HIPAA y el RGPD — sin depender de garantías contractuales de un proveedor de nube.

## Concesiones Deliberadas

El BIM de archivo plano presenta limitaciones reconocidas: la edición colaborativa simultánea en tiempo real es más lenta que los SaaS síncronos para talleres de diseño intensivos; la federación a escala urbana (más de un millón de edificios) requiere una arquitectura de transmisión distinta; las herramientas de autoría BIM generativa disponibles actualmente en el mercado son propietarias. Estas son concesiones deliberadas para priorizar una postura offline-first e independiente del proveedor, no carencias pendientes de corrección.

## Véase también

- worm-ledger-design
- service-fs-architecture
- sel4-microkernel-substrate
- sovereign-ai-routing
