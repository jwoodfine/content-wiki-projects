---
schema: foundry-doc-v1
title: "Esquema de datos POI"
slug: poi-data-schema
language: es
category: gis
type: topic
content_type: topic
status: active
last_edited: 2026-06-20
editor: pointsav-engineering
short_description: "El esquema de datos POI define estructuras de registro para datos de ubicación ingeridos de OpenStreetMap y Overture Maps Foundation, normalizados en un formato JSONL unificado antes del análisis de cluster. Los QIDs de Wikidata sirven como identificador de cadena principal y los modelos de sublocalización padre-hijo manejan servicios complementarios de marca compartida."
cites:
 - ni-51-102
 - osm-odbl
 - overture-maps-cdla-2-0
paired_with: gis/poi-data-schema.md
---

## Resumen estratégico

El esquema de datos POI define la estructura de registro utilizada por la plataforma de inteligencia de co-ubicación para sus dos clases de datos de ubicación: ubicaciones de cadenas minoristas ingestadas desde OpenStreetMap, y ubicaciones de anclas institucionales ingestadas desde la Fundación Overture Maps. Ambas clases se normalizan en un esquema JSONL de archivo plano unificado antes del [[co-location-methodology|análisis de agrupaciones]]. No se requiere ninguna compra de datos propietarios: todos los registros se derivan de fuentes con licencias públicas y son versionables en el mismo registro que el resto de la plataforma.

## Dos clases de registros

**Registros service-business** — ubicaciones individuales de cadenas minoristas: ferreterías de gran formato, clubes de almacén, hipermercados y anclas alimentarias. Cada registro se identifica por un `chain_id` vinculado al archivo de configuración de la cadena, y por un campo `brand_wikidata` con el QID de Wikidata de la marca. Los QID de Wikidata son persistentes e independientes del idioma: dos tiendas con distinta ortografía del nombre pero con el mismo QID pertenecen a la misma cadena.

**Registros service-places** — anclas institucionales: hospitales, universidades y aeropuertos, ingestados desde Overture Maps usando el campo `taxonomy.primary`. Este campo reemplazó al `categories.primary` deprecado en la versión 2025-11 de Overture. Los identificadores de categoría no cambiaron: las consultas que antes leían `categories.primary = 'hospital'` pasan a `taxonomy.primary = 'hospital'` sin modificar los valores de filtro.

## Campos principales

Ambas clases comparten los campos: `location_name`, `brand_wikidata`, `street_address`, `city`, `region`, `iso_country_code`, `latitude`, `longitude`, `naics_code`, `top_category`, `sub_category`, `source` (osm / overture), y `confidence`.

## Deduplicación espacial

El pipeline deduplica los registros redondeando las coordenadas de cada ubicación a cuatro decimales (aproximadamente 11 metros) y tratando los registros que redondean a la misma coordenada como el mismo edificio, conservando el registro con los campos de dirección más completos. Los registros que comparten coordenadas a esta resolución pero tienen distintos `chain_id` bajo el mismo QID de Wikidata se consideran formatos secundarios o tiendas de marca compartida — por ejemplo, una gasolinera bajo la misma marca que el minorista principal. Estos son candidatos para el modelo padre-hijo.

## Modelo padre-hijo y estándar Placekey

La plataforma resuelve esto mediante una asignación padre configurada: cada `chain_id` de sub-entidad reconocido como servicio auxiliar se asigna a su cadena matriz canónica — por ejemplo, un subformato de farmacia asignado a su cadena de gran formato matriz. Las sub-entidades quedan excluidas de la puntuación de clústeres y solo se muestran en la ficha informativa de la ubicación matriz; el mapa muestra una sola burbuja por ubicación matriz. Esto sigue el patrón estándar de POI padre-hijo del sector: el registro padre contiene la dirección y coordenadas canónicas, y cada sub-entidad hereda ese ancla mientras mantiene su propia clasificación de servicio.

El estándar Placekey — identificador global de ubicación con estructura `Qué@Dónde` — expresa esta relación mediante un sufijo `Dónde` compartido: dos POI en la misma dirección comparten el sufijo geocelda, mientras que su prefijo de marca difiere. Un enfoque de coincidencia espacial basado en Placekey sigue siendo un mecanismo futuro previsto, no el mecanismo actual; el esquema conserva un campo `placekey` para este fin, pero aún no se completa durante la ingestión [ni-51-102].

## Completitud de direcciones y cadencia de actualización

La cobertura de `addr:housenumber` y `addr:street` en OSM es sólida en Europa Occidental y Canadá, moderada en EE.UU., y escasa en algunos mercados nórdicos y del sur de Europa. Una mejora prevista realizará una unión espacial (radio ≤15 m) contra el tema Addresses de Overture para rellenar direcciones incompletas [ni-51-102].

Los registros service-business se reingesan por cadena bajo demanda; los registros service-places se reingesan con cada nueva versión trimestral de Overture.

## Véase también

- location-intelligence-platform — plataforma de inteligencia de ubicación y niveles de puntuación V2
- location-intelligence-substrate — arquitectura de datos GIS de archivo plano
- el pipeline de ingestión — el servicio de aplicación GIS que ejecuta el pipeline de ingestión descrito en este artículo
