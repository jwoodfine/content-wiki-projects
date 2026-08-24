---
schema: foundry-doc-v1
title: "Filosofía de diseño BIM"
slug: bim-design-philosophy
category: building-design
type: topic
content_type: topic
status: active
audience: customer-woodfine
bcsc_class: current-fact
language_protocol: TRANSLATE-ES
last_edited: 2026-08-24
editor: pointsav-engineering
short_description: "Extensión AEC anclada a IFC 4.3 que traduce almacenamiento en archivos planos, estándares abiertos y ejecución offline-first en herramientas BIM profesionales."
paired_with: building-design/bim-design-philosophy.md
cites: [ifc-4-3, uniclass-2015, bsdd-v1]
---

El Sistema de Diseño de Edificios está diseñado para ser la contraparte AEC del sustrato de diseño de la plataforma. Se basa en una postura estructural: los compromisos de PointSav — almacenamiento en archivos planos, estándares abiertos, ejecución fuera de línea y seguridad seL4 — no son preferencias estéticas, sino las ventajas concebidas para superar las debilidades del software en la nube tradicional.

## Puntos clave

- El sistema de diseño está pensado para anclarse a la jerarquía de entidades IFC 4.3 y utilizar una pila de estándares abiertos basada en texto (IFC-SPF, BCF 3.0, IDS 1.0, COBie). Los datos estructurados con estos estándares permanecen accesibles durante 50 o más años y sobreviven a los proveedores de software específicos que los generan.
- El BIM Anclado al Activo está diseñado para ser el diferenciador estructural: el gemelo digital está concebido como un artefacto legal firmado con el título de propiedad. Está diseñado para moverse con la escritura del inmueble en lugar de estar vinculado al modelo de inquilino de un proveedor — de modo que los datos sobrevivirían a cambios de plataforma o fallos del proveedor sin necesidad de migración.
- El cumplimiento normativo de construcción primero está pensado para desplazar el enfoque de "verificar después del diseño" a "cumplir por construcción". Está previsto que las ciudades publiquen códigos como tokens de diseño componibles (diccionarios bSDD + restricciones IDS 1.0), y que los diseñadores ensamblen modelos dentro de envolventes pre-restringidas donde las infracciones se vuelvan geométricamente imposibles antes de producirse.
- La capacidad fuera de línea está concebida como estructural, no como una opción configurable. Está previsto que la funcionalidad BIM completa se mantenga en sótanos, instalaciones con aislamiento de red y sitios remotos. Esta propiedad estructural está pensada para distinguir la plataforma de las herramientas BIM solo en la nube que requieren conexión persistente para funcionar.

## Diferenciadores Estratégicos

La filosofía de la plataforma se centra en cinco capacidades únicas:
1. **BIM Anclado al Activo:** El gemelo digital está diseñado para ser un activo legal que viaje con la escritura del edificio.
2. **Capacidad fuera de línea:** Funcionalidad total prevista para entornos sin internet o de alta seguridad.
3. **Supervivencia a la Obsolescencia:** Datos diseñados para permanecer legibles durante 50 años mediante el uso de estándares ISO abiertos.
4. **Integración IoT Local:** Datos de sensores diseñados para procesarse localmente sin cargos por uso de nube.
5. **Convergencia de Datos:** Unificación prevista de la identidad espacial, legal y financiera en un único archivo portátil del edificio.

## El Salto del Código Componible

La plataforma está diseñada para proponer un modelo donde las normativas urbanísticas se publicarían como "tokens de diseño" (IDS 1.0). El diseñador trabajaría dentro de envolventes ya validadas, haciendo que los errores de cumplimiento sean geométricamente imposibles desde el primer trazo. Este enfoque de "cumplimiento por construcción" está concebido como el núcleo de la ventaja tecnológica de PointSav.

## Véase también

- [[bim-aec-muscle-memory]]
- [[bim-objects-substrate]]
- Salto BIM en archivos planos
