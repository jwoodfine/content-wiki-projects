---
schema: foundry-doc-v1
title: "Bóveda BIM anclada al activo"
slug: asset-anchored-bim-vault
language: es
category: building-design
index_group: bim-objects-and-the-digital-record
type: topic
content_type: topic
status: active
last_edited: 2026-07-31
editor: pointsav-engineering
short_description: "El registro digital autoritario de un edificio estructurado como archivos de texto plano y binarios estandarizados en un directorio versionado con git, calificando como un Entorno de Datos Común conforme a ISO 19650 que viaja con la escritura de propiedad."
cites: [ifc-4-3, iso-19650, ids-1-0]
paired_with: building-design/asset-anchored-bim-vault.md
---

El registro digital autorizado de un edificio es un directorio de archivos de texto simple y binarios estandarizados que viven en el almacenamiento del propietario, viajan con la escritura de propiedad cuando cambia la titularidad y permanecen legibles sin una licencia de software propietario mientras se mantengan los estándares abiertos subyacentes. Este artículo describe el diseño de la bóveda, la capa de versiones que proporciona trazabilidad de grado git, y la calificación [[open-bim-regulatory-acceptance|ISO 19650]] que hace de un repositorio git de archivos planos un Entorno de Datos Común conforme.

## El Diseño de la Bóveda

La bóveda canónica para un archivo de propiedad Woodfine está estructurada de la siguiente manera:

```
vault/
├── ifc/             # Archivos IFC-SPF autorizados (ISO 16739-1:2024)
├── elements/        # Sidecars YAML por elemento (Pset_* + sensor + orden de trabajo)
├── bcf/             # Directorios BCF 3.0 por tema (XML + PNG; descomprimidos)
├── ids/             # Contratos de validación IDS 1.0 (por superposición jurisdiccional)
├── materials/       # Base de datos de materiales (archivos planos)
├── codes/           # Superposiciones de códigos de construcción como geometría composable
├── geometry/        # glTF 2.0 + CityJSONSeq (cachés regenerables; no canónicas)
├── drawings/        # Planos 2D SVG (regenerables; GUIDs IFC en IDs de elementos SVG)
├── objects/<hash>.json  # Almacén de objetos direccionados por hash
└── refs/            # Punteros de referencia estilo Git (ramas, etiquetas, HEAD)
```

Los archivos `.ifc` son el único estado espacial y semántico autorizado del edificio. Todos los demás directorios validan el estado IFC, lo enriquecen con datos no geométricos, o almacenan en caché una representación derivada que puede regenerarse a partir de la fuente canónica.

## El Archivo IFC-SPF como Archivo Canónico

IFC-SPF es la codificación de Archivo Físico STEP de IFC, especificada en ISO 10303-21. Es un formato de texto claro orientado a líneas: cualquier persona con un editor de texto puede leer un archivo IFC-SPF. El formato ha estado en producción desde IFC 1.0 en 1996.

IFC 4.3, publicado como ISO 16739-1:2024, es la revisión vigente. El modelo de gobernanza del estándar —mantenido por buildingSMART International y ratificado por ISO— ofrece la vida útil más fiable de cualquier formato de datos de construcción en uso actualmente.

## Sidecars YAML por Elemento

Cada elemento IFC que lleva datos operativos no geométricos tiene un sidecar YAML correspondiente en `vault/elements/`. El nombre del archivo del sidecar es el GUID IFC del elemento, que es estable a través de las revisiones del modelo.

El sidecar puede llevar:

- **Anulaciones Pset** — valores de propiedad no geométricos no capturados en la sesión de autoría IFC
- **Lecturas de sensores** — registros con marca de tiempo de un broker MQTT escritos como entradas de registro de solo adición
- **Órdenes de trabajo** — referencias a tareas de mantenimiento, registros de inspección e historial de reparaciones
- **Referencias de arrendamiento** — identificador del inquilino y plazo de arrendamiento, vinculando el elemento espacial con el registro de arrendamiento

## El Almacén de Objetos Direccionados por Hash

El directorio `vault/objects/` implementa un almacén de objetos direccionados por hash. Cada objeto es un archivo JSON cuyo nombre de archivo es el hash SHA-256 de su contenido. El resultado es un DAG de Merkle: el hash raíz de un estado del modelo está criptográficamente vinculado a cada elemento que contiene.

La estructura Merkle ofrece dos beneficios estructurales:

1. **Integridad del registro de auditoría.** Un estado histórico declarado del modelo puede verificarse contra el hash raíz sin necesidad de confiar en el servidor que lo almacenó.
2. **Transferencia eficiente de deltas.** Cuando dos partes sincronizan bóvedas, solo es necesario transferir los objetos cuyos hashes difieren.

## Calificación ISO 19650

Un repositorio git satisface los requisitos del EDC de [[open-bim-regulatory-acceptance|ISO 19650]]:

| Concepto ISO 19650 | Implementación Git + bóveda |
|---|---|
| Contenedor de información | Archivo IFC o sidecar YAML |
| UID del contenedor | Hash de objeto Git o GUID IFC |
| Estado | Nombre de rama (`work-in-progress`, `shared`, `published`) |
| Revisión | Hash de confirmación Git |
| Clasificación | Ruta de directorio + encabezado YAML |
| Historial de cambios | `git log --follow <filename>` |
| Estados de flujo de trabajo EDC | Flujo de fusión de ramas / solicitud de extracción (pull request) en Git |

Un repositorio git local en una estación de trabajo aislada cumple con ISO 19650 tan completamente como una plataforma alojada. Esto hace que la arquitectura de la bóveda sea apropiada para proyectos de defensa sujetos a ITAR, jurisdicciones de la Ley de Datos de la UE, e instalaciones sanitarias reguladas por HIPAA.

## Supervivencia a la Obsolescencia de Proveedores

Los edificios están diseñados típicamente para durar de 50 a 100 años. La arquitectura de la bóveda aborda esta asimetría de dos formas: los formatos canónicos son estándares abiertos gobernados por ISO, y los derivados regenerables están marcados explícitamente como no canónicos.

## El Archivo Viaja con el Terreno

Un activo inmobiliario físico se transfiere junto con una escritura de propiedad. La bóveda Woodfine está prevista para ser incluida en esa transferencia: el mismo repositorio git que contiene el archivo IFC, las referencias del registro de arrendamiento y el historial operativo acompaña a la propiedad cuando cambia la titularidad.

Ninguna plataforma en la nube puede ofrecer esta garantía. Una plataforma SaaS multiinquilino retiene el gemelo digital en nombre del inquilino actual; cuando la suscripción de ese inquilino caduca o el proveedor discontinúa el producto, los datos requieren una exportación explícita — y los formatos de exportación son invariablemente deficientes respecto de la representación nativa de la plataforma.

Una bóveda de archivos planos es propiedad del dueño en el mismo sentido en que el edificio físico es propiedad del dueño: de forma incondicional, transferible, y sin necesidad de autorización continua del proveedor.
