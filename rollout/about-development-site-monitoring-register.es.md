---
schema: foundry-doc-v1
title: "Registro de Monitoreo de Sitios de Desarrollo"
slug: about-development-site-monitoring-register
category: rollout
index_group: development-regions-and-site-register
type: topic
content_type: topic
quality: complete
short_description: "Registro de seguimiento pasivo que conserva sitios de co-ubicación calificados retirados del pipeline activo por falta de terreno adyacente, puntuados y con criterios de re-entrada."
status: stable
bcsc_class: current-fact
last_edited: 2026-08-24
editor: pointsav-engineering
language_protocol: TRANSLATE-ES
source_refs:
  - "bfe6fb6bbb557fd15bdb7ffd53bce60e527911eb7658c906df5b69813bdb8747"
paired_with: about-development-site-monitoring-register.md
cites: []
---

El **Registro de Monitoreo de Sitios de Desarrollo** mantiene las ubicaciones de Objetivos Primarios que logran una puntuación de clúster de co-ubicación calificada pero no pueden ingresar al pipeline activo de Sitios de Desarrollo porque el terreno adyacente no está disponible actualmente para su adquisición. El registro es un inventario puntuado — no una lista inactiva o archivada — actualizado en el mismo ciclo anual o bienal que los datos de ventas por pie cuadrado del Objetivo Primario. Los sitios en el registro conservan su puntuación de clúster y perfil demográfico. Vuelven a ingresar al pipeline activo cuando la disponibilidad de terreno adyacente es confirmada a través del proceso de evaluación de profesionales inmobiliarios.

## Por qué la disponibilidad de terreno es una puerta separada

Un Objetivo Primario que supera un nivel calificante — Local, Distrital o Regional, según el [[geographic-co-location-methodology|sistema de niveles actual]] — ha demostrado las condiciones de co-ubicación y captación que Woodfine requiere. Un clúster Marginal no califica. El nivel verifica que el entorno comercial es correcto para un Woodfine Building.

**Corrección (2026-08-24):** esta sección citaba anteriormente un umbral de
puntuación fabricado ("T1 Valid ≥ 150") de un sistema de puntos ya retirado en
toda la plataforma el 16 de mayo de 2026 (véase [[gis-cluster-scoring-glossary]]).
La prueba real de re-entrada del registro — que un sitio se mantenga por encima
del umbral descalificante — se expresa ahora directamente contra el sistema de
niveles actual: cualquier nivel distinto de Marginal califica.

La disponibilidad de terreno adyacente es una condición separada. Un sitio puede tener la configuración de co-ubicación correcta y el perfil demográfico correcto, pero carecer de una parcela adyacente al Objetivo Primario disponible para adquisición en el momento de la evaluación. Esto es particularmente común en los [[about-regional-markets-system|Mercados Regionales]] donde la huella del [[power-centres|Power Centre]] ha sido completamente desarrollada y las parcelas circundantes están ocupadas por edificios existentes cuyos propietarios no son vendedores actuales.

El Registro de Monitoreo preserva la inversión realizada en la puntuación y elaboración de perfiles de estos sitios en lugar de descartarlos del conjunto de datos. Las características de clúster calificantes del sitio no se espera que cambien — el Objetivo Primario es típicamente un minorista de gran formato con un contrato de arrendamiento a largo plazo y capital sustancial invertido en el sitio. La probabilidad de que el terreno adyacente eventualmente esté disponible es una función de la rotación inmobiliaria comercial normal en el área circundante.

## Cadencia de actualización y mantenimiento de puntuación

Los sitios del Registro de Monitoreo se revisan en el mismo calendario que el pipeline activo: anualmente o bienalmente cuando se actualizan los datos de ventas por pie cuadrado del Objetivo Primario. En cada ciclo de actualización, los profesionales inmobiliarios comprometidos por Woodfine en el mercado relevante evalúan la disponibilidad de terreno para cada sitio del Registro de Monitoreo en su área. Un sitio donde el terreno adyacente ha quedado disponible es escalado desde el Registro de Monitoreo al pipeline activo y avanza a la etapa del [[transaction-summary-report-protocol|Informe de Resumen de Transacción]].

El nivel del clúster para cada sitio del Registro de Monitoreo también se reevalúa en cada ciclo de actualización, utilizando la misma metodología aplicada a toda la población de Objetivos Primarios. Un sitio que era [[gis-cluster-scoring-glossary|Distrital]] en la evaluación inicial puede ser actualizado a Regional si un nuevo ancla abre cerca y cambia la composición del clúster, si los datos de población de captación actualizados desplazan su rango percentil nacional, o si un hospital dentro de su anillo cívico es reclasificado.

## Criterios de re-entrada

Un sitio del Registro de Monitoreo vuelve a ingresar al pipeline activo de Sitios de Desarrollo cuando se satisfacen dos condiciones:

1. **Disponibilidad de terreno confirmada.** El profesional inmobiliario comprometido en el mercado identifica una parcela adyacente al Objetivo Primario — definida como contigua o inmediatamente accesible al sitio del Power Centre — disponible para adquisición o arrendamiento de terreno en términos consistentes con los parámetros de suscripción de la Direct-Hold Solution aplicable.

2. **Nivel del clúster mantenido o mejorado.** El nivel del clúster del sitio en el momento de la evaluación de re-entrada debe ser Local, Distrital o Regional — no Marginal. Un sitio que ha caído a Marginal — por ejemplo, porque un ancla ha cerrado y la composición del clúster ya no supera las compuertas de ningún nivel — no vuelve a ingresar al pipeline activo hasta que se restauren las condiciones de co-ubicación calificantes.

Los sitios que satisfacen ambas condiciones proceden a la preparación del Informe de Resumen de Transacción y al proceso de revisión de los Directores Independientes. El período de monitoreo no tiene una duración máxima definida: un sitio permanece en el registro hasta que cumpla ambas condiciones, o hasta que las condiciones de co-ubicación se deterioren permanentemente, momento en el cual el sitio se elimina del conjunto de datos por completo.

## Relación con los conteos del pipeline

Los conteos de desarrollo requeridos para cada Direct-Hold Solution — 26 sitios para Canadá, 52 para Estados Unidos, 26 para México — se basan únicamente en sitios del pipeline activo. Los sitios del Registro de Monitoreo no se contabilizan para el total de desarrollo requerido. La proporción mínima de preselección de 2:1 se aplica a los sitios del pipeline activo; el Registro de Monitoreo es una reserva de candidatos futuros del pipeline, no un componente del cálculo actual de la preselección.
