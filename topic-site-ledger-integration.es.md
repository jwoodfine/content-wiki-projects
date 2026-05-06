---
schema: foundry-doc-v1
title: "Integración del Libro Contable del Sitio"
slug: topic-site-ledger-integration
category: governance
type: reference
quality: complete
status: active
audience: customer-woodfine
bcsc_class: current-fact
language_protocol: PROSE-TOPIC
last_edited: 2026-05-06
editor: pointsav-engineering
paired_with: topic-site-ledger-integration.md
cites:
  - ni-51-102
  - osc-sn-51-721
---

La Integración del Libro Contable del Sitio es el vínculo operativo entre un sitio de construcción físico y su contenedor de registro digital. Cada sitio de desarrollo activo se mapea a un archivo digital aislado mantenido por la plataforma PointSav. Los dos están vinculados: los eventos en el sitio físico generan registros digitales inmutables; el libro contable es el rastro legal y de auditoría del desarrollo.

## El modelo de contenedor digital

Cada sitio recibe un contenedor de archivo independiente — no una base de datos compartida con otros sitios. El aislamiento es estructural: un evento de datos que afecte al archivo de un sitio no puede afectar al de otro. Esto refleja la arquitectura financiera de Tenencia Directa, donde cada activo es un vehículo legalmente aislado.

## Registro diario de progreso

Los gestores de sitio generan registros de progreso diarios que documentan hitos de construcción, entregas de materiales, resultados de inspecciones y variaciones de programación. Estos registros se comprometen al contenedor digital como archivos planos — registros de texto sin formato con entradas marcadas con fecha y hora. Una vez comprometidas, las entradas son inmutables. Un registro diario para una fecha determinada no puede sobrescribirse ni corregirse — las correcciones son nuevas entradas con una notación explícita de enmienda.

## Auditorías de construcción verificables

La acumulación de registros diarios a lo largo del período de construcción constituye un rastro de auditoría verificable. Un inversor, un organismo regulador o un futuro comprador puede reconstruir el historial de desarrollo a partir del libro contable sin depender del relato auto-informado del promotor. Esta transparencia es un resultado fiduciario del Mandato de Datos Fiduciarios — la obligación de mantener la propiedad matemática de los datos relevantes para los inversores se extiende a los registros de construcción de los activos mantenidos en la cartera de Tenencia Directa.

---

*Copyright © 2026 Woodfine Capital Projects Inc. Licenciado bajo [Creative Commons Attribution 4.0 International](https://creativecommons.org/licenses/by/4.0/).*
