---
schema: foundry-doc-v1
title: "Código urbano como geometría composable"
slug: city-code-as-composable-geometry
language: es
category: building-design
type: topic
content_type: topic
status: active
last_edited: 2026-08-24
editor: pointsav-engineering
short_description: "Un modelo arquitectónico que codifica requisitos regulatorios directamente en especificaciones de elementos como restricciones geométricas y numéricas en lugar de aplicarlas después del diseño, haciendo que las configuraciones no conformes sean estructuralmente imposibles por construcción."
cites: [ifc-4-3, ids-1-0, bsdd-v1]
paired_with: building-design/city-code-as-composable-geometry.md
---

Toda herramienta de verificación de cumplimiento normativo en producción sigue la misma arquitectura: un modelo de diseño terminado se envía a un motor de reglas, que genera un informe de infracciones, que un profesional debe revisar y corregir antes de reenviar. Este modelo de validación posterior al diseño ha sido el estándar de la industria durante veinte años y genera una tensión estructural entre la velocidad de iteración del diseño y la verificación del cumplimiento. Es posible una arquitectura diferente: si los requisitos normativos se codifican directamente en los elementos disponibles para un diseñador — no como reglas aplicadas a un modelo terminado, sino como restricciones geométricas y numéricas incorporadas en la especificación del elemento — entonces las configuraciones no conformes no pueden colocarse. Este es el modelo del Código Urbano como Geometría Composable, y es la afirmación arquitectónica subyacente a la plataforma de [[bim-objects-what-they-are|Objetos BIM]].

## El paradigma de validación posterior

Las herramientas de validación posterior al diseño operan con un patrón común: el diseñador crea un modelo en una herramienta de autoría BIM compatible con IFC, lo exporta en formato IFC, lo envía a un servicio de validación que aplica un conjunto de reglas y produce un informe de infracciones, y luego un profesional revisa el informe, vuelve a la herramienta de autoría, realiza correcciones y reenvía. La mayoría de las herramientas de autoría no aplican ninguna restricción en el momento de colocación.

Las consecuencias son operativas. Los equipos de diseño presupuestan tiempo de iteración para la revisión normativa. En proyectos complejos, los ciclos de revisión regulatoria añaden semanas a las fases de diseño.
El validador es una función de bloqueo que se sitúa fuera del entorno de diseño y se comunica
con él de forma asíncrona.

## Estado del arte

La investigación realizada en abril de 2026 identificó cuatro categorías de estado del arte,
todas situadas en el cuadrante de validación posterior.

**IDS 1.0 (Information Delivery Specification).** El estándar IDS de buildingSMART codifica
restricciones de propiedades en XML. Un archivo IDS declara qué debe contener un modelo válido
— es un lenguaje de validación, no una restricción sobre las paletas de elementos. Los
archivos IDS son entradas para validadores, no restricciones aplicadas durante el diseño.

**bSDD (buildingSMART Data Dictionary).** El bSDD proporciona identidad semántica para tipos
de elementos entre jurisdicciones y herramientas. No codifica restricciones normativas ni
requisitos de rendimiento de zona climática. Una URI bSDD es un ancla de identidad, no una
especificación de restricciones.

**Plataformas de validación posterior al diseño.** Las plataformas comerciales de validación
BIM operan después del diseño. Sus motores de reglas pueden verificar geometría, topología,
valores de propiedades y relaciones espaciales — pero operan como herramientas de auditoría
sobre modelos ya enviados. Los modelos no conformes pasan por los entornos de autoría sin
objeción hasta el momento del envío.

**Singapur CORENET X.** El sistema gubernamental de envío BIM más avanzado en producción
pública. CORENET X acepta modelos IFC enviados para solicitudes de permisos de construcción y
ejecuta verificaciones automatizadas de cumplimiento normativo contra los requisitos
regulatorios de Singapur. Sigue siendo un validador: los modelos se crean libremente, se
envían a CORENET X y se devuelven con informes de infracciones. La implementación de 2024
añade orientación en tiempo real en algunos complementos de herramientas de autoría,
estrechando pero no cerrando la brecha entre la validación posterior y la composición previa.
Es específico de la jurisdicción y no está disponible como plataforma neutral para otras
jurisdicciones.

**Evaluación.** Todo el estado del arte identificado ocupa el cuadrante de validación
posterior. El cuadrante de composición previa — codificar restricciones en las
especificaciones de elementos antes de la autoría — no tiene estado del arte establecido en
producción pública a partir de 2026.

## El mecanismo composicional

El Código Urbano como Geometría Composable opera a través de un mecanismo técnico de tres capas.

**Capa 1: Identidad semántica mediante bSDD.** Cada [[bim-objects-what-they-are|Objeto BIM]] lleva una URI de concepto bSDD que identifica su tipo de elemento de manera neutral a la jurisdicción y a la herramienta.

**Capa 2: Restricción normativa mediante IDS 1.0.** Cada superposición jurisdiccional registrada para un Objeto BIM incluye un archivo de restricción IDS 1.0 que codifica restricciones numéricas y de propiedades: valores máximos de transmitancia térmica, clasificaciones mínimas estructurales, requisitos de clase de resistencia al fuego, espacios libres de accesibilidad. Cuando se coloca un Objeto BIM, sus restricciones IDS registradas son parte de su especificación — la herramienta de autoría las recibe como requisitos del elemento en el momento de la colocación, no como reglas post-colocación.

**Capa 3: Geometría de exclusión mediante fragmento IFC.** Donde un requisito normativo tiene expresión geométrica — un límite de compartimento contra incendios, un retranqueo de lindero, una envolvente de accesibilidad que debe permanecer libre — la superposición jurisdiccional incluye un fragmento IFC: una geometría sólida codificada en formato IFC que define el espacio excluido o requerido. Este fragmento se instancia en el momento de la colocación y no puede ser anulado por restricciones numéricas.

La composición de estas [[bim-objects-three-layers|tres capas]] es lo que hace que la
geometría "codifique" la norma. La restricción normativa no se almacena en una base de datos
de validación separada que se revisa después de la autoría. Se almacena en la especificación
del Objeto BIM y se instancia junto con el elemento.

## La exclusión geométrica en detalle

El mecanismo de fragmento IFC aborda la clase de requisitos normativos que las restricciones
numéricas no pueden expresar.

Considérese un muro de compartimento contra incendios en un edificio de varios pisos. El
requisito no es simplemente "este muro debe tener una clase de resistencia al fuego REI 90".
También es "este muro debe formar un plano continuo desde la losa de piso hasta la losa de
techo, sin penetraciones excepto las cubiertas por dispositivos de cierre con clasificación
adecuada". El segundo requisito es topológico y geométrico: el muro debe ocupar una relación
espacial específica con los elementos circundantes.

Una restricción numérica IDS puede expresar REI 90. No puede expresar el requisito de
continuidad topológica. Un fragmento de exclusión geométrica IFC sí puede: codifica el
volumen espacial que debe ocupar el límite del compartimento contra incendios y los volúmenes
espaciales adyacentes que deben llenarse con construcción conforme. Las herramientas de
autoría que consumen el fragmento pueden mostrar la geometría requerida como guía de diseño y
señalar desviaciones en tiempo real.

Esto es cualitativamente distinto de la validación posterior al diseño. El diseñador ve la
configuración espacial requerida durante la autoría, no después del envío.

## Restricciones estructurales sobre los enfoques centralizados

La investigación identificó tres razones estructurales por las que los enfoques centralizados
en la nube no pueden replicar el modelo del Código Urbano como Geometría Composable para
todos los contextos de despliegue.

**Soberanía de los datos regulatorios.** Los datos regulatorios jurisdiccionales son derecho
público. Codificarlos como un servicio alojado en una plataforma comercial de nube genera
preocupaciones de adquisición y soberanía para jurisdicciones fuera de EE. UU., bajo los
requisitos de residencia de datos de la UE, las restricciones del RGPD y marcos nacionales
equivalentes. Una plataforma neutral que ciudades y gobiernos nacionales puedan alojar por
cuenta propia, o hacer alojar bajo marcos de nube nacionales, es estructuralmente necesaria
para una adopción amplia.

**Requisito de funcionamiento sin conexión.** Los sitios de construcción operan con
frecuencia sin conectividad de red confiable. Los proyectos restringidos por ITAR, los
sitios remotos y muchos proyectos de infraestructura pública requieren que los datos de
restricción estén disponibles sin conexión. Un servicio de validación dependiente de la nube
no puede atender estos casos de uso. Una [[asset-anchored-bim-vault|bóveda de Objetos BIM]]
clonada mediante git y almacenada localmente está disponible sin conexión de forma
incondicional.

**Neutralidad de plataforma comercial.** Las ciudades y los gobiernos nacionales que emiten
requisitos normativos necesitan publicarlos para todas las plataformas BIM conformes, no
para proveedores comerciales específicos. Publicar los requisitos normativos en un estándar
JSON neutral y abierto (W3C DTCG con extensiones BIM) y distribuirlos mediante repositorios
git públicos es análogo a publicar códigos de construcción en PDF — neutral, reproducible e
independiente de proveedores.

## Relevancia para América Latina y España

Los mandatos de BIM para obras públicas están en expansión en la región hispanohablante. España tiene previsto el mandato completo de BIM para todas las obras públicas en 2026 bajo el Plan de Impulso de la Contratación Pública (PPRE 2022–2026). México, Colombia, Chile y Argentina cuentan con iniciativas BIM en distintas fases de implementación, con Chile entre los más avanzados (Estrategia Nacional BIM 2023–2025). En todos estos contextos, la pregunta no es si se adoptará BIM, sino qué plataformas pueden cumplir los requisitos de soberanía de datos adjuntos a estos mandatos.

El modelo del Código Urbano como Geometría Composable es especialmente relevante para entornos donde los datos regulatorios son información pública: publicar los requisitos normativos en un estándar JSON neutro y abierto y distribuirlos mediante repositorios git públicos es análogo a publicar códigos de construcción en PDF — neutral, reproducible e independiente de proveedores.

## Etapas de implementación

**Etapa 1 (actual, prevista para v0.0.3):** [[asset-anchored-bim-vault|bóveda de Objetos BIM]] con capa de Especificación completa. Esqueleto de la capa de Normativa con el primer conjunto de superposiciones: requisitos de zonificación residencial RS-1 de Columbia Británica.

**Etapa 2 (prevista, v0.1.x):** generación de archivos de restricción IDS 1.0 para cada superposición normativa registrada, permitiendo que los validadores IDS existentes consuman especificaciones de restricción de PointSav.

**Etapa 3 (prevista, futuro):** integración en herramientas de autoría BIM mediante un plugin o superficie API que entregue las restricciones del Objeto BIM en el momento de la colocación, no al enviar el modelo.

## Véase también

- [[bim-objects-what-they-are]]
- [[bim-objects-three-layers]]
- [[flat-file-bim-leapfrog]]
- [[open-bim-regulatory-acceptance|open-bim-regulatory-acceptance]]
- [[leapfrog-2030-architecture]]
