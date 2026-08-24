---
schema: foundry-doc-v1
title: "Zonificación climática a nivel de módulo"
slug: tile-level-climate-zoning
category: building-design
type: topic
content_type: topic
quality: pre-build
status: active
audience: customer-woodfine
bcsc_class: current-fact
language_protocol: TRANSLATE-ES
last_edited: 2026-08-24
editor: pointsav-engineering
short_description: "El estándar de granularidad de servicios del edificio de Woodfine: cada Módulo tiene su propio termostato, con Módulos Especiales que reciben una zona climática autocontrolada, en lugar de zonificar a nivel de espacio arrendable individual o de piso completo."
paired_with: building-design/tile-level-climate-zoning.md
---

Woodfine dimensiona el control climático según el [[key-plans-and-tiles|Módulo]], no según el espacio arrendable individual ni según el piso completo: cada Módulo tiene su propio termostato, y cada Plano Maestro que comparte ese Módulo comparte también su termostato. La granularidad se fija una vez que el Módulo está definido. Por eso [[design-sequence-priority|Servicios del Edificio se superpone solo después del Plan de Arrendamiento]]: una zona climática a nivel de Módulo solo puede trazarse correctamente una vez que los Módulos mismos son conocidos.

## Por qué el Módulo es la unidad correcta

Un [[key-plans-and-tiles|Módulo]] ya es la unidad de espacio arrendable geométricamente completa más pequeña contra la que arrienda Woodfine, dimensionada según la geometría de equipo y circulación de un uso profesional específico. Hacer coincidir la zona climática con esa misma unidad significa que un Colaborador de Servicios del Edificio zonifica contra un límite que ya existe en la geometría de arrendamiento, en lugar de inventar un límite de zonificación separado que luego habría que conciliar con ella. Los Módulos Especiales son el único caso dimensionado de otra manera — configuraciones más grandes construidas para espacios arrendables que ocupan hasta tres cuartas partes de un piso alrededor de los Vestíbulos de Ascensores. Dado que un Módulo Especial es lo bastante grande para funcionar como su propio espacio arrendable, recibe una zona climática autocontrolada en lugar de compartir la zona de tamaño estándar de Módulo.

## Qué reemplaza

El estándar reemplaza el control ambiental a nivel de espacio arrendable individual como opción predeterminada de Woodfine. El control a nivel de inquilino suena como una mejor comodidad, y Woodfine lo puso a prueba. Un amplio grupo de Colaboradores de Servicios del Edificio que trabajan en Canadá, Estados Unidos, el Reino Unido y Europa continental reportó de manera independiente el mismo hallazgo. Los sistemas construidos para dar control individual a los inquilinos generaron problemas significativos de mantenimiento y confiabilidad, y las fallas de servicio resultantes crearon una insatisfacción real entre los inquilinos y sus Usuarios. El control ambiental propio de Woodfine se administra en cambio de forma centralizada, como parte de la administración de la propiedad. La premisa es que un sistema optimizado centralmente supera a un mosaico de sistemas administrados individualmente, y es lo que los inquilinos de un edificio Clase A deberían esperar por defecto.

## Dónde un inquilino todavía puede obtener más control

El comportamiento predeterminado no es absoluto. Un inquilino que arrienda una Corporate Office completa — aproximadamente del tamaño de un Módulo completo, un octavo de piso como mínimo — alcanza la escala en la que el control ambiental individual se vuelve práctico de ofrecer. Un inquilino que desea distribución más allá de eso puede instalar y pagar sus propios sistemas de mayor gama, siempre que la instalación no interfiera con los sistemas compartidos del edificio. Un inquilino más pequeño que comparte un Módulo con otros espacios arrendables no tiene esa opción y en su lugar escala un problema climático a través del canal de servicio para inquilinos del edificio o directamente con el administrador del edificio en el sitio.

## Consecuencia para la experiencia del inquilino y el costo de mantenimiento

El límite de zonificación se fija en el Módulo en lugar de negociarse espacio por espacio. Por eso el estándar evita la falla específica que Woodfine identificó en los sistemas de control individual: un servicio poco confiable que genera llamadas de mantenimiento repetidas y una frustración creciente de los inquilinos. Dimensionar la zona según el Módulo también significa que el estándar viaja sin cambios junto con la [[fixed-floor-plates|Placa de Piso Fija]] a cada despliegue de la misma clase de prototipo, en lugar de rediseñarse edificio por edificio.

## Véase también

- [[key-plans-and-tiles]] — la unidad de Módulo contra la que zonifica este estándar
- [[design-sequence-priority]] — por qué la zonificación climática se fija solo después del Plan de Arrendamiento
- [[fixed-floor-plates]] — la disciplina de placa de piso con la que viaja este estándar
- [[geometry-of-sustainability]] — el enfoque basado en estándares regulatorios para el desempeño operativo a nivel de edificio
