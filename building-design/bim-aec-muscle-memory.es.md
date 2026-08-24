---
schema: foundry-doc-v1
title: "Memoria muscular AEC y patrones de interfaz"
slug: bim-aec-muscle-memory
category: building-design
type: topic
content_type: topic
status: active
audience: customer-woodfine
bcsc_class: current-fact
language_protocol: TRANSLATE-ES
last_edited: 2026-08-24
editor: pointsav-engineering
short_description: "El Building Design System adopta patrones de interfaz establecidos de herramientas estándar de la industria AEC para garantizar curva de aprendizaje cero para profesionales de AEC, mientras habilita flujos de gestión de instalaciones a través de vinculación de órdenes de trabajo, integración de arrendamientos y superposiciones de sensores."
paired_with: building-design/bim-aec-muscle-memory.md
cites: [ifc-4-3, uniclass-2015, bsdd-v1]
---

El Sistema de Diseño de Edificios está previsto para adoptar el vocabulario de interfaz universal de la industria (Revit, ArchiCAD, BricsCAD y Bonsai) para garantizar que los profesionales del sector AEC (Arquitectura, Ingeniería y Construcción) no tengan curva de aprendizaje. Al respetar las convenciones establecidas, la plataforma está concebida para permitir que los usuarios se concentren en las innovaciones estratégicas — como el almacén de archivos planos — en lugar de en la interacción básica con herramientas.

Esta interfaz (SpatialTree/Riel Izquierdo, PropertiesPanel/Riel Derecho, Toolbar, StatusBar, NavCube y los demás componentes descritos abajo) es un diseño planificado y conceptual — nada de esto se ha implementado todavía en el código canónico. `app-workplace-bim` y `app-console-bim` contienen actualmente solo documentación, y `moonshot-bim-engine`, el crate que implementaría el renderizado BIM, sigue siendo un marcador de posición estructural.

## Convenciones Universales de Interfaz AEC Previstas

La plataforma está prevista para implementar los siguientes patrones de diseño estándar de la industria:

| Convención | Ubicación estándar | Componente del Building Design System |
| :--- | :--- | :--- |
| **Árbol Espacial** | Riel izquierdo | `SpatialTree` |
| **Panel de Propiedades** | Riel derecho | `PropertiesPanel` |
| **Barra de Herramientas** | Superior | `Toolbar` |
| **Barra de Estado** | Inferior | `StatusBar` |
| **Cubo de Navegación (NavCube)** | Esquina superior derecha del visor | `Viewport3D__navcube` |

### Estándares Clave de Navegación (previstos)
* **Expansión a Nivel de Planta:** El `SpatialTree` previsto está concebido para desplegarse por defecto a nivel de planta, evitando la expansión directa a espacios individuales para minimizar el ruido visual y alinearse con los modelos mentales profesionales.
* **Propiedades No Modales:** El `PropertiesPanel` previsto está concebido para funcionar como una barra lateral sensible a la selección que se actualiza en tiempo real, evitando ventanas emergentes modales disruptivas.
* **Agrupación Semántica:** Los conjuntos de propiedades (Pset_*) y cantidades (Qto_*) están previstos para agruparse en secciones nombradas y colapsables para una recuperación rápida de datos.

## Divergencia Estratégica de la Modelación Genérica (prevista)

Si bien la plataforma está diseñada para respetar las convenciones profesionales, está concebida para evitar deliberadamente los artefactos propios del software de modelado 3D de propósito general (por ejemplo, artefactos heredados de Blender en Bonsai):

1. **Árbol Espacial Dedicado:** La plataforma está prevista para utilizar un widget `SpatialTree` diseñado a medida en lugar de un esquema genérico de grafo de escena, habilitando funciones como la búsqueda por nombre de espacio y miniaturas de plano de planta.
2. **Mapas de Teclas Estandarizados:** La navegación está prevista para utilizar la fila numérica estándar 1–6 para cambiar de vista (superior, inferior, frontal, posterior, izquierda, derecha), adaptándose a la ausencia de teclado numérico en los portátiles modernos.
3. **Eliminación de la Edición Modal:** La plataforma está prevista para eliminar el complejo "cambio de modo" (por ejemplo, modo Objeto frente a modo Edición) habitual en el software 3D genérico, ofreciendo una experiencia de autoría simplificada.

## Enfoque en el Gestor de Activos (Property Manager)

A diferencia de las herramientas tradicionales enfocadas solo en el diseño, la plataforma está diseñada para el operador de instalaciones:
- **Vínculos de Órdenes de Trabajo:** Conexión de estados de mantenimiento directamente con los elementos BIM.
- **Integración de Arrendamientos:** Vinculación de espacios (`IfcSpace`) con registros financieros en el sistema de contenido.
- **Superposición de Sensores:** Visualización de datos IoT en tiempo real sobre el modelo 3D.

Estas capacidades, previstas para la versión v0.0.2, transforman el BIM de una herramienta de dibujo en un sustrato operativo para la gestión de inmuebles.

## Véase también

- [[bim-design-philosophy]]
- [[bim-objects-substrate]]
- [[flat-file-bim-leapfrog]]
