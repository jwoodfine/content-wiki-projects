---
schema: foundry-doc-v1
title: "Objetos BIM — Tres capas de composición"
slug: bim-objects-three-layers
language: es
category: building-design
index_group: bim-objects-and-the-digital-record
type: topic
content_type: topic
status: archived
archived: 2026-08-26
archived_reason: "Contenido de arquitectura de software/plataforma de PointSav ubicado por error en un wiki inmobiliario. Palabras del operador: el wiki de proyectos 'no es para software ni para PointSav, es para bienes raíces' -- si el contenido necesita un enlace a documentation.pointsav.com, hay algo mal en el contenido; debe reescribirse para encajar en corporate o projects, o trasladarse. Este artículo describía la regla de composición de tres capas (Especificación/Regulación/Zona Climática) del Objeto BIM -- una definición de esquema de datos de plataforma, no contenido inmobiliario de Woodfine. Consolidado (junto con bim-objects-substrate y bim-objects-what-they-are) en media-knowledge-documentation substrate/bim-object-specification (2026-08-26) -- tres facetas estrechamente ligadas de un mismo concepto, antes divididas en tres artículos breves."
superseded_by: none
last_edited: 2026-08-24
editor: pointsav-engineering
short_description: "Un Objeto BIM lleva tres capas de información a la vez — qué es, qué exige su jurisdicción y qué exige su clima — y prevalece la más estricta de las dos capas de requisitos cuando ambas se aplican a la misma propiedad."
cites: [ifc-4-3]
paired_with: building-design/bim-objects-three-layers.md
aliases:
  - bim-token-three-layers
---

Un [[bim-objects-what-they-are|Objeto BIM]] lleva tres capas de información a la vez: Especificación, Regulación y Zona Climática. Ninguna de las tres es una opción que un diseñador elija en el momento del diseño. Un elemento constructivo tiene un tipo fijo, se ubica en una jurisdicción fija y se desempeña en un clima fijo, de modo que el objeto refleja las tres como hechos sobre su contexto físico y no como preferencias del usuario.

## Por qué tres capas y no una

Una especificación de elemento del entorno construido debe responder tres preguntas distintas a la vez. Qué es el elemento — una identidad estable e independiente de la herramienta. Qué exige legalmente de él la jurisdicción donde se construye. Y qué exige de él el clima en el que se ubica para desempeñarse correctamente. Los requisitos regulatorios varían según la jurisdicción y cambian cuando se actualizan los códigos; los requisitos de desempeño climático varían según la zona y cambian cuando se revisan los códigos de energía. Mantener estas capas separadas, en lugar de reducirlas a un solo número, permite que cada aspecto se rastree, se documente y se actualice de forma independiente sin afectar a los otros dos.

## Qué lleva cada capa

La capa de Especificación es la identidad permanente del objeto — qué tipo de elemento es, independientemente de dónde se construya. La capa de Regulación contiene los requisitos legales específicos de la jurisdicción donde se ubica realmente el edificio. La capa de Zona Climática contiene los requisitos de desempeño que se derivan del clima físico del edificio, tomados del código de energía aplicable. Regulación y Zona Climática se elaboran cada una como una tabla creciente de todos los requisitos registrados, en lugar de un solo valor, porque una jurisdicción o una zona climática es un hecho sobre el sitio, no un ajuste que elige el usuario.

## Cuando aplican a la vez un requisito regulatorio y uno climático

Cuando un requisito regulatorio y un requisito de zona climática restringen la misma propiedad, prevalece el más estricto de los dos. Ambas capas expresan mínimos de desempeño, de modo que el requisito vinculante es siempre el mínimo más alto de los dos — una regla directa de "gana el más restrictivo", no una negociación.

## Dónde vive la especificación

El esquema completo a nivel de campo, la estructura de superposiciones jurisdiccionales y la regla de composición detrás de estas tres capas se mantienen directamente en [bim.woodfinegroup.com](https://bim.woodfinegroup.com).

## Véase también

- [[bim-objects-what-they-are]] — qué es un Objeto BIM y cómo difiere de los tipos de entidad IFC, formatos de Familia BIM propietarios y conjuntos de propiedades
- [[bim-objects-substrate]] — las ocho categorías de Objetos BIM primitivos y su formato de entrega
- [[open-bim-regulatory-acceptance]] — cómo las jurisdicciones adoptan los estándares BIM abiertos
- [[design-system-bim]] — el Sistema de Diseño de la Construcción para el entorno construido
