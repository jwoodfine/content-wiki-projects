---
schema: foundry-doc-v1
title: "Metodología de Co-Ubicación Geográfica"
slug: geographic-co-location-methodology
category: site-selection
index_group: scoring-and-clustering
type: topic
content_type: topic
quality: complete
short_description: "Sistema de cinco grados de clúster que puntúa nodos minoristas por co-ocurrencia de objetivos Primarios, Secundarios y Terciarios para clasificar sitios de desarrollo."
status: stable
bcsc_class: current-fact
last_edited: 2026-07-01
editor: pointsav-engineering
language_protocol: TRANSLATE-ES
source_refs:
  - "bfe6fb6bbb557fd15bdb7ffd53bce60e527911eb7658c906df5b69813bdb8747"
paired_with: geographic-co-location-methodology.md
cites: []
---

La **Metodología de Co-Ubicación Geográfica** es la disciplina de análisis espacial que MCorp aplica para identificar y clasificar Sitios de Desarrollo potenciales en sus tres jurisdicciones principales. La metodología puntúa los nodos minoristas según la proximidad y la combinación de minoristas ancla que operan en la geografía, produciendo un conjunto de datos clasificados de sitios en los que la inversión de desarrollo está validada por los compromisos comerciales demostrables de minoristas institucionales, en lugar de proyecciones demográficas especulativas.

La metodología produce cinco grados de clústeres, cada uno representando un nivel más refinado de co-ocurrencia de anclas. Los clústeres de mayor grado indican que una geografía ha atraído múltiples categorías de inversión comercial institucional — una validación compuesta que supera el umbral que cualquier ancla individual produce por sí sola.

## El Sistema de Clústeres de Cinco Grados

Los cinco grados de clústeres se construyen a partir de dos umbrales de radio: un umbral más estrecho aplicado a la co-ocurrencia de Objetivos Primarios y Secundarios, y un umbral más amplio aplicado a la proximidad de Objetivos Terciarios. Cada grado se construye sobre el anterior.

### Clústeres de primer y segundo grado

**Clúster de Primer Grado** — Un sitio de [[co-location-target-hierarchy|Objetivo Primario]] (Walmart Supercentre) con alguno de los dos Objetivos Secundarios (Home Depot o Costco Wholesale) ubicados dentro del umbral de proximidad Primario-Secundario entre sí. Es el indicador de base de una Inversión Calificada: la co-presencia de un operador de comestibles en volumen y un gran minorista de mejoras para el hogar o almacén de membresía a esa proximidad confirma que la geografía cumple los umbrales de dos operadores minoristas institucionalmente distintos.

**Clúster de Segundo Grado** — Un Clúster de Primer Grado con cualquiera de los Objetivos Terciarios (institución de educación superior o centro médico importante) ubicado dentro del umbral de proximidad Terciario, más amplio. La adición de un Objetivo Terciario introduce una fuente de demanda para el arrendamiento de servicios profesionales que es estructuralmente independiente del nodo minorista.

### Clústeres de tercer y cuarto grado

**Clúster de Tercer Grado** — Un Objetivo Primario con ambos Objetivos Secundarios (Home Depot y Costco) dentro del umbral de proximidad Primario-Secundario entre sí. El requisito de que ambos operadores secundarios estén presentes a ese mismo radio estrecho es un listón materialmente más alto que el estándar de Primer Grado. Home Depot y Costco validan independientemente una geografía a través de sus propios procesos de selección de sitios; su presencia simultánea confirma que múltiples operadores institucionales evaluaron la misma geografía y llegaron a la misma conclusión.

**Clúster de Cuarto Grado** — Un Clúster de Tercer Grado con cualquiera de los Objetivos Terciarios dentro del umbral de proximidad Terciario, más amplio. La combinación de ambos operadores secundarios más una fuente de demanda institucional terciaria.

### Clústeres de quinto grado como sitios de mayor convicción

**Clúster de Quinto Grado** — Un Clúster de Tercer Grado con ambos Objetivos Terciarios dentro del umbral de proximidad Terciario, más amplio. Los Clústeres de Quinto Grado son los sitios de mayor convicción en el conjunto de datos: la presencia simultánea de Walmart, Home Depot, Costco, una institución de educación superior y un centro médico importante, dentro de los umbrales de radio respectivos.

## Calibración del Radio

El umbral Primario-Secundario refleja la realidad operativa del diseño de sitios de [[power-centres|centros comerciales]]: los minoristas de un mismo nodo o corredor comercial suelen estar muy próximos entre sí. El umbral Terciario, más amplio, refleja el patrón de captación más amplio de los empleadores institucionales, a una escala coherente con la tolerancia de desplazamiento en automóvil de los arrendatarios de servicios profesionales.

### Recalibración periódica

Si los Clústeres de Quinto Grado llegan a representar una proporción desproporcionada de todas las entradas de Objetivo Primario en el conjunto de datos completo, los umbrales se ajustan a la baja — tanto el umbral Terciario como el Primario-Secundario se reducen. Este mecanismo de recalibración evita que el nivel superior de clústeres crezca demasiado como para seguir siendo un filtro operativamente útil de selección de sitios.

## Métricas de Salida del Conjunto de Datos

Para cada entrada de Objetivo Primario, la salida de co-ubicación geográfica registra: la ciudad, pueblo o municipio del Objetivo Primario; la población de la comunidad circundante; las ventas por pie cuadrado del Objetivo Primario; y el ranking global de ese Objetivo Primario por ventas por pie cuadrado en todas las entradas del conjunto de datos.

## Cantidad de Sitios Requerida por Jurisdicción

Los requisitos de shortlist de sitios están calibrados a las captaciones de capital planificadas y calendarios de construcción de cada Direct-Hold Solution. Cada jurisdicción — Canadá, Estados Unidos y México — tiene su propia cantidad de desarrollo requerida, a lo largo de los financiamientos de capital y deuda planificados durante el período de construcción plurianual.

### Proporción de shortlist y disponibilidad de suelo

Dado que no siempre habrá terrenos de desarrollo disponibles adyacentes a los mejores Objetivos Primarios, y algunos sitios disponibles conllevarán calendarios de recalificación o permisos que se extienden por varios años, la shortlist de sitios debe superar el número requerido de desarrollo en un margen sustancial. Se preseleccionan suficientes candidatos por sitio requerido para absorber el desgaste por disponibilidad de suelo y trámites de permisos. Se mantienen tres conjuntos de datos separados, uno por jurisdicción.
