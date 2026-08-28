---
schema: foundry-doc-v1
title: "Prioridad de secuencia de diseño"
slug: design-sequence-priority
category: building-design
index_group: site-and-building-standards
type: topic
content_type: topic
quality: pre-build
status: active
audience: customer-woodfine
bcsc_class: current-fact
language_protocol: TRANSLATE-ES
last_edited: 2026-08-24
editor: pointsav-engineering
short_description: "El orden fijo de colaboración detrás de cada paquete de diseño de Woodfine: primero el Plan de Arrendamiento, luego Servicios del Edificio, y por último Estructural — cada disciplina diseñando sobre una capa previa ya completada en lugar de negociar en paralelo."
paired_with: building-design/design-sequence-priority.md
---

Woodfine secuencia a sus colaboradores de diseño en un orden fijo: primero el Plan de Arrendamiento, luego Servicios del Edificio, y por último Estructural. Cada disciplina diseña así sobre una capa previa ya completada, en lugar de negociar en paralelo con las demás. El orden no es una conveniencia de calendario; es el mecanismo que Woodfine utiliza para evitar que una sola disciplina rediseñe el edificio en función de su propia conveniencia una vez que la construcción ya está comprometida.

## El orden de tres pasos

[[key-plans-and-tiles|Planos Maestros y Módulos]] van primero porque son el Plan de Arrendamiento — los espacios disponibles que un edificio Woodfine está construido para vender. Una vez fijados los Planos Maestros y Módulos, Servicios del Edificio se superpone sobre ellos, dimensionando la distribución y las zonas de servicio para espacios ya conocidos en lugar de para una placa de piso que aún podría cambiar. Estructural va al final. Solo una vez que Servicios del Edificio se ha superpuesto sobre los Planos Maestros y Módulos puede un Colaborador Estructural identificar qué sistema estructural — concreto, acero, madera o híbrido — se ajusta realmente a la Combinación de Inquilinos y al dimensionamiento de espacios resultante.

## Qué reemplaza

El orden reemplaza una práctica anterior de involucrar a Estructural o a Servicios del Edificio antes de fijar el Plan de Arrendamiento. Esa práctica cedía ante la disciplina que estuviera contratada primero, o ante la "conveniencia de diseño" que una cuadrícula estructural lineal le ofrece a un Colaborador Estructural sin importar lo que los espacios realmente necesitaran. La falla fue directa. La propia experiencia de Woodfine muestra que esto salió mal en aproximadamente la mitad de los proyectos anteriores, donde la participación junto con los diseñadores de un inquilino en los Planos Maestros llegó solo después de que el edificio ya estaba construido. Para entonces era demasiado tarde para cambiar lo que esos Planos Maestros podrían haber significado para el diseño del edificio en sí, no solo para el espacio individual en acondicionamiento.

## Por qué el arrendamiento fija los términos, no al revés

Una [[fixed-floor-plates|Placa de Piso Fija]] cuyos muros divisorios caen en los límites del [[key-plans-and-tiles|Módulo]] solo queda libre de columnas a nivel de espacio arrendable si la cuadrícula estructural se colocó alrededor de los Módulos — no al revés. Secuenciar el Plan de Arrendamiento primero es lo que lo hace posible. Un Colaborador Estructural que trabaja a partir de una capa de Planos Maestros y Módulos ya completada coloca las columnas alineadas con los límites de los espacios arrendables, en lugar de ajustar los espacios arrendables a una cuadrícula elegida por economía de vigas. La misma lógica rige la [[tile-level-climate-zoning|zonificación climática a nivel de módulo]], donde Servicios del Edificio solo puede dimensionar una zona de termostato a un Módulo una vez que el Módulo mismo está fijado. También rige la [[structural-bay-depth-discipline|profundidad del vano estructural]], que depende de conocer lo que necesita un espacio arrendable antes de elegir el vano de viga que lo sirve.

## Consecuencia para la disciplina de construcción

La secuencia también es lo que le permite a Woodfine evitar depender de un solo colaborador para mantener unido todo el diseño. Debido a que cada capa está completa antes de que comience el siguiente colaborador, ninguna disciplina puede forzar un rediseño de una capa anterior sin una decisión explícita de reabrirla. Esa disciplina es lo que permite que un diseño de [[fixed-floor-plates|Placa de Piso Fija]], desarrollado una sola vez por clase de prototipo, se reproduzca en múltiples Sitios de Desarrollo sin renegociar las mismas preguntas de secuenciación en cada despliegue.

## Véase también

- [[key-plans-and-tiles]] — la capa del Plan de Arrendamiento que abre la secuencia
- [[fixed-floor-plates]] — la placa de piso cuyas subdivisiones protege esta secuencia
- [[structural-bay-depth-discipline]] — la consecuencia a nivel estructural de secuenciar correctamente
- [[tile-level-climate-zoning]] — la consecuencia a nivel de Servicios del Edificio de secuenciar correctamente
- [[four-to-one-parking-ratio]] — un dato de diseño a nivel de sitio evaluado junto con esta secuencia
