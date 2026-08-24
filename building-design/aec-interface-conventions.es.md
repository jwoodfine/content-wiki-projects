---
schema: foundry-doc-v1
title: "Convenciones de interfaz AEC"
slug: aec-interface-conventions
language: es
category: building-design
type: topic
content_type: topic
status: active
last_edited: 2026-08-24
editor: pointsav-engineering
short_description: "Las cuatro convenciones universales de interfaz — árbol espacial, panel de propiedades, visor 3D y navegador de vistas — que todas las herramientas de autoría BIM implementan, proporcionando vocabulario compartido para superficies de coordinación transversales consistentes."
cites: [ifc-4-3]
paired_with: building-design/aec-interface-conventions.md
---

Cada plataforma importante de autoría BIM incluye cuatro convenciones de interfaz que un arquitecto o ingeniero aprende una vez y aplica en todos los productos: un árbol de jerarquía para la estructura espacial, un panel de propiedades para los atributos de los elementos, un viewport 3D y un navegador de vistas guardadas. Estas convenciones existen porque el modelo de datos subyacente (la jerarquía de entidades IFC) es el mismo independientemente de la herramienta que lo autorice. Los componentes de interfaz universal previstos del [[design-system-bim|Sistema de Diseño de la Construcción]] están concebidos para construirse sobre este vocabulario compartido.

Estos son componentes de interfaz planificados y conceptuales — ninguno se ha implementado todavía. `app-workplace-bim` y `app-console-bim` contienen actualmente solo documentación; `moonshot-bim-engine`, el crate que implementaría el renderizado BIM, es un marcador de posición estructural. Las descripciones siguientes exponen el diseño previsto, no un producto ya entregado.

## Las Cuatro Convenciones Universales

### Árbol espacial

Toda herramienta de autoría BIM muestra la estructura espacial de un edificio como un árbol jerárquico: Sitio contiene Edificio, Edificio contiene Planta, Planta contiene Espacio, Espacio contiene Elementos. Esto corresponde directamente a la jerarquía `IfcSpatialStructureElement` en IFC 4.3. El componente `SpatialTree` previsto del Sistema de Diseño de la Construcción está concebido para renderizar esta jerarquía con comportamiento consistente de expansión/colapso, propagación de selección al Viewport3D y visualización del GUID IFC al pasar el cursor.

### Panel de propiedades

Cuando se selecciona un elemento, un panel de propiedades muestra el nombre de la clase IFC del elemento, su identificador globalmente único (GUID IFC) y todos los valores de Conjunto de Propiedades adjuntos. El componente `PropertiesPanel` previsto del Sistema de Diseño de la Construcción está concebido para renderizar los mismos datos con una variante de prop de modo: el modo `view` muestra todos los valores Pset de forma plana; el modo `edit` muestra solo los valores que el rol actual está autorizado a modificar.

### Viewport 3D

La superficie de interfaz principal de toda herramienta BIM es un viewport 3D de perspectiva u ortográfico. Los controles de cámara (órbita, panorámica, zoom) usan controles de ratón estándar de la industria. El componente `Viewport3D` previsto del Sistema de Diseño de la Construcción está concebido para incorporar el visor xeokit-sdk o @thatopen/web-ifc con estos controles de cámara estándar.

### Navegador de vistas

El componente `ViewNavigator` previsto del Sistema de Diseño de la Construcción está concebido para renderizar las vistas guardadas como pestañas etiquetadas: `Planta L1`, `Sección A-A`, `Alzado Norte`. Al seleccionar una pestaña se cargaría el estado de la cámara y, opcionalmente, el filtro de planta IFC para esa vista.

## Diez Componentes de Interfaz Universal Previstos

El [[design-system-bim|Sistema de Diseño de la Construcción]] está previsto para definir diez componentes de interfaz que aparecerían en cada superficie — ya sea el cliente de campo, la consola de gestión de instalaciones o cualquier superficie futura que consuma el Sistema de Diseño de la Construcción. Ninguno de los diez existe todavía en el código canónico.

| Componente | Función |
|---|---|
| `SpatialTree` | Navegación de jerarquía espacial (Sitio → Edificio → Planta → Espacio) |
| `PropertiesPanel` | Visualizador y editor de Psets IFC (variante de prop de modo) |
| `Viewport3D` | Viewport del modelo 3D (incorporación xeokit / @thatopen) |
| `ViewNavigator` | Vistas guardadas con nombre como pestañas etiquetadas |
| `IssueTracker` | Lista de temas BCF 3.0 con filtros de estado y asignado |
| `ElementSearch` | Búsqueda de GUID IFC o valor Pset en todo el modelo cargado |
| `ClashReview` | Lista de resultados de detección de colisiones con resaltado en el viewport |
| `HistoryTimeline` | Historial de confirmaciones Git renderizado como línea de tiempo de estados del modelo |
| `ExportPanel` | Exportación COBie, ejecución de validación IDS, descarga BCF ZIP |
| `StatusBar` | Progreso de carga del modelo, recuentos de validación, marca de tiempo de última sincronización |

## Por qué Importa el Vocabulario Compartido

Los equipos de proyectos BIM frecuentemente trabajan con múltiples herramientas de autoría en un solo proyecto. Los modelos del ingeniero estructural, del arquitecto y del ingeniero MEP exportan IFC-SPF. La coordinación ocurre en un visor común donde nadie está en su entorno de autoría nativo.

Un vocabulario de interfaz compartido significa que un visor de coordinación construido según esta convención no introduciría una nueva curva de aprendizaje además de las herramientas de autoría.

## Relación con el Sustrato del Sistema de Diseño

El [[design-system-bim|Sistema de Diseño de la Construcción]] está previsto como una extensión semántica AEC de la línea base del Sistema de Diseño Carbon. Carbon proporciona los primitivos de interfaz de usuario fundamentales. El Sistema de Diseño de la Construcción está concebido para agregar la capa semántica AEC encima: los diez componentes de interfaz universal y las ocho categorías de [[bim-objects-what-they-are|Objetos BIM]] primitivos.
