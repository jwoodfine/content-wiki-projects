---
schema: foundry-doc-v1
title: "Transmisión de Tasas de Interés en Bienes Raíces Comerciales"
slug: interest-rate-transmission
category: industry
type: topic
content_type: topic
quality: complete
short_description: "Cómo los cambios en las tasas libres de riesgo y las condiciones crediticias se propagan a través de las tasas de capitalización, los costos del servicio de deuda y los márgenes de factibilidad de desarrollo hacia las valoraciones de propiedades comerciales y los rendimientos de inversión."
status: active
audience: customer-woodfine
bcsc_class: current-fact
language_protocol: TRANSLATE-ES
last_edited: 2026-08-24
editor: woodfine-editorial
paired_with: industry/interest-rate-transmission.md
---

Las tasas de interés afectan a los bienes raíces comerciales a través de varios canales de
transmisión distintos simultáneamente: la tasa de capitalización, el costo del financiamiento de deuda,
el margen de factibilidad para nueva construcción y la tasa de descuento aplicada
en la valoración por flujos de efectivo descontados. Estos canales no se mueven en sincronía
— la velocidad y completitud con que los cambios de tasas se propagan a través de cada canal
varían con la liquidez del mercado, el comportamiento de los prestamistas y las características
específicas del activo.

## Puntos clave

- El canal principal de transmisión de las tasas de interés a los valores de propiedades
  comerciales es la tasa de capitalización: cuando las tasas libres de riesgo aumentan, los
  inversores exigen mayores rendimientos en activos reales ilíquidos, expandiendo las tasas
  de capitalización y deprimiendo los valores implícitos a ION constante.
- La transmisión no es instantánea — las tasas de capitalización rezagan los movimientos
  de tasas de referencia porque las transacciones inmobiliarias comerciales son infrecuentes
  y el descubrimiento de precios es lento.
- Las restricciones de cobertura del servicio de deuda crean un segundo canal: las tasas
  de interés crecientes aumentan la obligación anual de servicio de deuda en deuda de tasa
  variable o deuda en refinanciamiento, reduciendo el superávit de ION disponible para
  distribución.

## Canal 1 — Tasas de capitalización

La tasa de capitalización en bienes raíces comerciales se negocia con un diferencial sobre
las tasas libres de riesgo a largo plazo. Cuando las tasas libres de riesgo aumentan, el
rendimiento total requerido en propiedad real aumenta correspondientemente, y las tasas de
capitalización se expanden.

El efecto cuantitativo es directo: para un activo que genera un ION estabilizado de
$1,000,000, una expansión de 100 puntos básicos en la tasa de capitalización de mercado
del 5.0% al 6.0% reduce el valor implícito de $20,000,000 a $16,667,000, una pérdida de
aproximadamente el 17%. Una expansión de 50 puntos básicos produce una reducción de valor
de aproximadamente el 9.1% — de $20,000,000 a una tasa del 5.0% a $18,182,000 al 5.5%, el
mismo ejemplo utilizado en [[net-operating-income]].

## Canal 2 — Cobertura del servicio de deuda

La razón de cobertura del servicio de deuda (RCSD) — ION dividido entre el servicio anual
de deuda — es la restricción principal de suscripción del prestamista. A una RCSD de 1.25×
y ION estable, un aumento en la tasa de interés de la deuda en refinanciamiento eleva la
obligación anual de servicio de deuda y reduce la RCSD. Si el aumento de tasa es
suficientemente grande, la RCSD puede caer por debajo del mínimo del convenio.

La deuda de tasa variable amplifica esta exposición: la obligación de servicio de deuda se ajusta en cada periodo en que cambia la tasa de referencia, reduciendo de inmediato el ingreso distribuible disponible para los tenedores de capital. La deuda de tasa fija aísla al prestatario de los movimientos de tasas durante el plazo, pero se reajusta al vencimiento; un refinanciamiento en un entorno de tasas más altas al vencimiento puede producir un salto súbito en el servicio de deuda que no era visible durante el plazo de tasa fija.

La interacción entre ambos canales es asimétrica en las recesiones: el aumento de las tasas reduce simultáneamente los valores de los activos (Canal 1) y aumenta los costos del servicio de deuda (Canal 2), comprimiendo el capital propio desde ambos frentes. La razón préstamo-valor empeora a medida que cae el valor; la RCSD empeora a medida que sube el servicio de deuda. Ambos deterioros pueden desencadenar la acción del prestamista simultáneamente.

## Canal 3 — Factibilidad de desarrollo

El nuevo desarrollo es viable solo cuando el valor del edificio terminado supera el costo
total de terreno, construcción, financiamiento y utilidad del desarrollador. Las tasas de
interés afectan tanto al denominador de la ecuación de valor (la expansión de la tasa de
capitalización reduce el valor implícito) como al numerador de la ecuación de costo (el mayor
costo de financiamiento aumenta el costo total durante la construcción).

Un aumento de 100 puntos básicos tanto en las tasas de financiamiento de construcción como en la tasa de capitalización terminal tiene un efecto compuesto sobre los márgenes de desarrollo: el valor del activo terminado cae mientras el costo de producirlo aumenta. Los proyectos que eran viables a un nivel de tasas dado pueden dejar de serlo tras un aumento sostenido de tasas, reduciendo la nueva oferta y, en última instancia, sosteniendo las tasas de ocupación en el inventario existente.

La restricción de oferta creada por la menor factibilidad de desarrollo es una compensación estructural a la presión de valoración que los aumentos de tasas generan en los activos existentes: se entregan menos edificios nuevos, reduciendo la competencia de oferta que enfrentan los activos estabilizados y sosteniendo sus niveles de renta de largo plazo.

## Canal 4 — Tasa de descuento en flujos de efectivo descontados

Para activos modelados mediante la metodología de flujos de efectivo descontados (FED), la
tasa de descuento aplicada a los flujos proyectados refleja el rendimiento requerido por el
inversor. Un aumento en la tasa libre de riesgo eleva el rendimiento requerido y, a flujos
de efectivo proyectados constantes, reduce el valor presente de esos flujos.

## Diferenciación por clase de activo

La sensibilidad a la transmisión de tasas de interés varía según la clase de activo. Las
estructuras de contratos a largo plazo — comunes en [[class-professional-centres|Centros Profesionales]] y activos de
oficinas — proporcionan estabilidad de ingresos durante los ciclos de tasas, pero impiden
el ajuste ascendente de rentas hasta las fechas de renovación del contrato. Los contratos
de retail e industrial a corto plazo se ajustan más rápidamente a las condiciones cambiantes
del mercado.

Los activos con altas proporciones de deuda a tasa fija están aislados del Canal 2 durante el período fijo, pero enfrentan una exposición abrupta ("cliff exposure") al vencimiento. Los activos con plazos de arrendamiento remanentes cortos enfrentan la sensibilidad del Canal 1 (expansión de la tasa de capitalización) agravada por el riesgo de renovación si las vacantes aumentan durante una desaceleración de la demanda de ocupantes inducida por las tasas.

## Consulte también

- [[capitalization-rate]] — el mecanismo principal mediante el cual los movimientos de tasas
  se transmiten a las valoraciones de propiedades
- [[net-operating-income]] — la métrica de ingresos que determina la cobertura del servicio
  de deuda en el contexto de los cambios de tasas
- [[commercial-real-estate-cycles]] — el contexto cíclico en el que ocurre la transmisión
  de tasas de interés
