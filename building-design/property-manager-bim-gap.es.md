---
schema: foundry-doc-v1
title: "Brecha BIM del administrador de propiedades"
slug: property-manager-bim-gap
language: es
category: building-design
index_group: design-philosophy-and-system
type: topic
content_type: topic
status: active
last_edited: 2026-08-24
editor: pointsav-engineering
short_description: "Una parte sustancial de los gerentes de instalaciones no utiliza activamente los modelos BIM entregados en la entrega del proyecto, debido al costo del software, los requisitos de capacitación y la opacidad del formato de archivo — una brecha que los registros de construcción de Woodfine están diseñados para cerrar."
cites: [ifc-4-3, iso-19650]
paired_with: building-design/property-manager-bim-gap.md
---

Los Modelos de Información para la Construcción son elaborados por arquitectos e ingenieros estructurales, entregados a los contratistas para la construcción, y luego transferidos a los administradores de propiedades en la finalización práctica. En la práctica, la mayor parte de ese valor nunca se aprovecha — un gerente de instalaciones que carece de un visor BIM, de la capacitación para usarlo, o del presupuesto para una licencia de herramienta de autoría no puede aprovechar el archivo que recibió. Véase [[bim-design-philosophy|la filosofía de diseño de Woodfine]] para conocer cómo el enfoque de Woodfine aborda esto.

## Una brecha documentada de la industria

La brecha entre la producción BIM y el consumo BIM en la gestión de instalaciones está documentada en la literatura revisada por pares: una parte sustancial de los gerentes de instalaciones no utiliza activamente los modelos BIM que reciben en la entrega. Las barreras recurrentes citadas son el costo del software, un requisito de capacitación significativo y la opacidad del formato de archivo. Varios investigadores llaman a esto la "brecha de transferencia BIM" — existe un modelo digital detallado, fue pagado por el promotor y cumple el requisito de entrega contractual, y aun así permanece sin usar.

Los proveedores de plataformas de gestión de instalaciones han comenzado a abordar esto integrando visores BIM directamente en su software CAFM/CMMS. Sin embargo, importar datos BIM a una plataforma CAFM suele implicar pérdidas: los atributos que el esquema CAFM no reconoce se descartan, y los datos importados se desincronizan del modelo canónico a medida que el edificio se renueva.

## El enfoque de Woodfine

Los registros de construcción de Woodfine están diseñados para dar a un gerente de instalaciones acceso directo y de solo lectura a los datos del modelo con fidelidad completa. No requieren una licencia de herramienta de autoría, ni una importación CAFM con pérdidas que se desincroniza con el tiempo. Se prevé que el mismo enfoque se extienda a los datos del registro de arrendamiento, manteniendo los registros espaciales, operativos y financieros de un edificio como un solo sistema en lugar de tres que deben reconciliarse manualmente.

## Dónde vive la especificación

Los componentes de interfaz, el mecanismo de acceso a datos y el detalle de implementación detrás de este enfoque se mantienen directamente en [bim.woodfinegroup.com](https://bim.woodfinegroup.com).

## Consulte también

- [[bim-design-philosophy]] — por qué los registros de Woodfine están diseñados para permanecer utilizables de forma independiente durante toda la vida de un edificio
