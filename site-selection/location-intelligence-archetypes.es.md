---
schema: foundry-doc-v1
title: "Arquetipos de Co-localización en Inteligencia de Ubicación"
slug: location-intelligence-archetypes
category: site-selection
index_group: the-method
type: topic
content_type: topic
quality: complete
status: active
audience: customer-woodfine
bcsc_class: current-fact
language_protocol: TRANSLATE-ES
language: es
last_edited: 2026-06-15
editor: pointsav-engineering
short_description: "Tres arquetipos de co-localización — Centros Comerciales (PRO), Franja Urbana (VWH) y Área de Acceso (PKS) — que identifican patrones de agrupación comercial diferenciados en 17 países de Norteamérica y Europa."
paired_with: site-selection/location-intelligence-archetypes.md
---

La plataforma de Inteligencia de Ubicación identifica la gravedad comercial y
minorista mediante tres arquetipos de co-localización: Centros Comerciales
(PRO), Franja Urbana (VWH) y Área de Acceso (PKS). Cada arquetipo describe un
patrón de agrupación distinto que refleja un tipo diferente de actividad
comercial y una relación diferente con la geografía urbana circundante.

Los códigos de tres letras fueron ratificados el 1 de junio de 2026.

## Los tres arquetipos

| Código | Nombre | Tipo de ancla | Estado |
|--------|--------|---------------|--------|
| **PRO** | Centros Comerciales | Hipermercado de alimentación con ferretería y al menos uno de: club de precio, estilo de vida o electrónica | Activo — canal de co-localización T1/T2/T3 |
| **VWH** | Franja Urbana | Ferretería + ecosistema de suministro industrial (MRO, alquiler de herramientas, distribuidores de construcción, recambios de auto) | Activo — canal de co-localización productivo en tres niveles |
| **PKS** | Área de Acceso | Ancla de tránsito regional (aeropuerto, tren, bus) + aparcamiento disuasorio + alquiler de vehículos/hotel | Activo — canal de co-localización productivo en tres niveles |

PRO es el producto de mapa base — la base del conjunto de datos de selección
de ubicaciones. VWH y PKS son arquetipos superpuestos que identifican
estructuras de mercado adyacentes no capturadas por la agrupación anclada en
alimentación.

---

## PRO — Centros Comerciales

Los clústeres PRO representan co-localizaciones comerciales ancladas en
alimentación a tres escalas. El canal agrupa ubicaciones de categorías ancla
que se encuentran dentro de una distancia de extensión definida y asigna cada
grupo a uno de tres niveles según la composición de anclas.

### Definiciones de nivel

**T1 — Regional:** Un clúster que contiene un hipermercado de alimentación y
un establecimiento de ferretería, más al menos uno de los siguientes: club de
precio, establecimiento de estilo de vida o retailer de electrónica.
Alternativamente: cuatro o más minoristas de categoría ancla en un clúster
compacto, o tres o más anclas en cualquier clúster compacto.

**T2 — Distrito:** Un clúster que contiene un hipermercado de alimentación y
un establecimiento de ferretería, dentro de una extensión de distrito más
amplia.

**T3 — Local:** Todos los pares de anclas restantes que no cumplen los
criterios de T1 ni T2.

### Conjunto de datos actual

El conjunto de datos de producción actual abarca miles de clústeres PRO en
los tres niveles, cubriendo 17 países en Norteamérica y Europa. Los límites
de nivel se reajustan periódicamente a medida que cambia la huella
minorista subyacente; el radio de distrito de T2 se ha estrechado en
sucesivas reconstrucciones con respecto a fases anteriores.

---

## VWH — Franja Urbana

Los clústeres VWH identifican concentraciones de minoristas de ferretería y
suministros industriales en ausencia de anclas de alimentación. Estos
emplazamientos ocupan la franja urbana — una banda de distancia más allá del
núcleo metropolitano inmediato pero por debajo del territorio de mercado
independiente — y tienden a agruparse cerca de intercambiadores de autopista
en zonas con uso del suelo industrial adyacente.

### Definición

Un candidato VWH es una ubicación donde hay uno o más establecimientos de
ferretería, no existe ningún hipermercado de alimentación dentro del radio
del clúster, y el emplazamiento se encuentra dentro de la banda de distancia
metropolitana de la Franja Urbana. La forma construida típica es un edificio
de almacén o fabricación ligera de varias plantas, distinto del formato de
caja grande de una planta del parque comercial.

Las ubicaciones VWH prestan servicio a contratistas del sector de la
construcción, operadores de fabricación ligera y arrendatarios de logística
de aprovisionamiento inmediato — no a consumidores minoristas generales.

### Señales de co-localización

**Esenciales:**

| Señal | Justificación |
|-------|--------------|
| Intercambiador de autopista cercano | Acceso de camiones y salida de mercancías |
| Población suficiente en un radio de desplazamiento corto | Mano de obra para fabricación y logística |
| Uso del suelo industrial adyacente | Compatibilidad de zonificación |

**Significativas:**

| Señal | Justificación |
|-------|--------------|
| Aeropuerto de carga al alcance | Electrónica y componentes, reposición rápida |
| Ferrocarril de mercancías cercano | Entrega de componentes justo a tiempo |
| Corredor de transporte público cercano | Acceso de la mano de obra |

**Descalificadoras:** Zona residencial densa inmediatamente adyacente; llanura
de inundación; zona de conservación del patrimonio; ubicación dentro de un
clúster PRO.

### Estado de producción

El canal VWH es de calidad productiva. Se perfilaron establecimientos de
ferretería como anclas proxy, y la agrupación de suministro industrial se
validó frente a datos de anclas de ferretería reservados para validación,
con un umbral de aceptación interno para la calidad del clúster que la
compilación de producción supera.

El conjunto de datos abarca miles de clústeres en los 17 países cubiertos,
con la concentración más alta en Estados Unidos y una cobertura significativa
en varios otros mercados de Norteamérica y Europa.

Los clústeres se distribuyen entre los tres niveles con la forma esperada:
una minoría reducida alcanza el nivel de Hub comercial completo, una
proporción mayor alcanza el nivel Establecido, y la mayoría se sitúa en el
nivel Emergente/Reducido. Esa distribución con predominio de T3 es esperada
— un hub de suministro completo que combine MRO, alquiler de herramientas,
distribuidor de construcción y recambios es una combinación legítimamente
poco frecuente.

Un indicador de control de calidad señala los clústeres que se encuentran
lo bastante cerca de un hipermercado de alimentación como para considerarse
parques comerciales de uso mixto — co-localizaciones VWH válidas que también
incluyen comercio de alimentación.

---

## PKS — Área de Acceso

Los clústeres PKS identifican concentraciones comerciales cerca de aeropuertos
regionales y estaciones de tren interurbano situados en una corona de acceso
más allá del núcleo metropolitano inmediato pero por debajo de la distancia de
mercado independiente. El patrón de demanda definitorio es el desplazamiento
de estacionamiento y vuelo, o estacionamiento y tren: los residentes de un
Mercado Regional conducen hasta un nodo de transporte, estacionan y viajan al
Mercado Metropolitano.

### Definición

Un candidato PKS es un nodo de transporte regional — aeropuerto o estación de
tren interurbano — dentro de la banda de distancia metropolitana del Área de
Acceso. Los nodos más cercanos que esa banda se clasifican como suburbanos en
lugar de regionales; los nodos más allá de ella se consideran mercados
independientes con una relación metropolitana propia.

La señal comercial definitoria en una ubicación PKS es el alquiler de
vehículos. Los recambios de automoción, las gasolineras, los restaurantes de
servicio rápido y las tiendas de conveniencia son señales secundarias.

### Señales de co-localización

**Esenciales:**

| Señal | Justificación |
|-------|--------------|
| Ancla de transporte regional cercana | Aeropuerto o estación con servicio directo al área metropolitana |
| Aislamiento metropolitano dentro de la banda del Área de Acceso | Define la relación regional |
| Clúster T1 o T2 de PRO cercano | La misma población genera demanda de estacionamiento |
| Población regional suficiente | Demanda mínima para estacionamiento de varios pisos |

**Significativas:**

| Señal | Justificación |
|-------|--------------|
| Alquiler de vehículos cercano | Los viajeros que llegan requieren transporte |
| Concentración hotelera cercana | Viajes de negocios y estacionamiento de varios días |
| Segundo modo de transporte cercano | Integración multimodal |

**Descalificadoras:** Gran hub dentro del núcleo metropolitano inmediato;
población por debajo de un umbral mínimo viable; sin servicio directo al
área metropolitana.

### Estado de producción

El canal PKS es de calidad productiva. Los registros de aparcamiento
disuasorio son el ancla geográfica principal — puntos de transición
coche→tránsito distribuidos de forma independiente de la geometría de la
red ferroviaria. Los modos de transporte son señales de enriquecimiento; la
presencia de alquiler de vehículos y hoteles define la madurez comercial.
Las categorías de modo de transporte relacionadas se agrupan antes de
asignar el nivel, para evitar que modos relacionados infle artificialmente
una señal aparente de multimodalidad.

Los clústeres se distribuyen entre tres niveles. Un nivel de Hub regional
combina acceso multimodal con un ecosistema comercial completo. Un nivel de
Intercambiador de tránsito combina tránsito con al menos una señal comercial.
Un nivel más amplio de Nodo de tránsito es aquel donde el tránsito está
presente pero la oportunidad comercial aún está por confirmarse.

El enriquecimiento comercial se apoya en las principales cadenas de alquiler
de vehículos y hoteles activas en cada mercado, incorporadas y reflejadas en
la compilación de producción.

### Filtro de grandes hubs

Los aeropuertos adyacentes a un gran clúster minorista PRO se excluyen como
probables grandes hubs comerciales. Los grandes aeropuertos generan su propia
gravedad minorista y no exhiben el patrón de estacionamiento y tránsito. El
filtro excluye correctamente hubs como LAX, JFK, LHR y CDG.

### Mejoras futuras

- Datos de pasajeros aeroportuarios (CAPA o IATA) para sustituir el proxy de
  adyacencia actual por un clasificador basado directamente en el tráfico
- Directorio de operadores de estacionamiento: Q-Park, APCOA, NCP, Indigo/Vinci (UE); SP+ (EE. UU.)

---

## Integración en el mapa

VWH y PKS aparecen como capas superpuestas bajo la sección **★ Mercados
Regionales** en el panel de control de capas.

**Selector VWH** — muestra puntos naranja en las ubicaciones candidatas de
Franja Urbana. Cuando está activo, las burbujas de clúster se atenúan para
reducir la interferencia visual.

**Selector PKS** — muestra puntos turquesa en los candidatos integrados
(cerca de un clúster T1/T2 de PRO) y puntos grises en los candidatos
independientes. Se aplica la misma atenuación de las burbujas.

Ambas capas persisten en las transiciones de vista: el estado de atenuación
se mantiene al cambiar entre la Vista Minorista y el panel de detalle de
mercado BentoBox.

## Véase también

- [[co-location-methodology|Metodología de co-ubicación]] — la puntuación de composición de anclas que impulsa la asignación de niveles PRO
- [[co-location-ranking-system|Sistema de clasificación de co-ubicación]] — el índice de densidad comercial de cinco rangos que clasifica los clústeres PRO
- [[about-regional-markets-system|Sistema de Inteligencia de Mercados Regionales]] — el ranking de 400 mercados construido sobre datos de clústeres PRO
- [[atlas-top-400-north-america|Top 400 Mercados Regionales — Norteamérica]] — lista clasificada de mercados PRO suburbano-regionales en NA
- [[atlas-top-400-europe|Top 400 Mercados Regionales — Europa]] — lista clasificada de mercados PRO suburbano-regionales en EU
- [[od-catchment-methodology|Metodología de Área de Influencia O-D]] — cómo se miden las zonas de influencia alrededor de cada centroide de clúster

## Fuentes de datos

Datos de mapa y localización © [colaboradores de OpenStreetMap](https://www.openstreetmap.org/copyright) / [ODbL](https://opendatacommons.org/licenses/odbl/).
