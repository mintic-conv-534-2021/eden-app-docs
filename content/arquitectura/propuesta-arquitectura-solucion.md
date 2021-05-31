# DISEÑO DE ARQUITECTURA DE SOFTWARE PARA ELEDENAPP

## Contenido

- [Introducción](#Introducción)
- [Método](#Método)
- [Requerimientos del sistema](#Requerimientos-del-sistema)
- [Identificación y selección de conceptos de diseño](#identificación-y-selección-de-conceptos-de-diseño)
- [Producción de estructuras](#Producción-de-estructuras)
- [Definición de interfaces](#Definición-de-interfaces)
- [Vistas de arquitectura: modelo 4+1](#Vistas-de-arquitectura-modelo-4+1)
- [Evaluación con ATAM](#Evaluación-con-ATAM)
- [Referencias](#Referencias)

## Introducción

Este documento sirve como base para la creación de servicios similares dentro del equipo y como guía para los desarrolladores el entender la razón de las decisiones de diseño tomadas en el momento de la concepción del producto minimo viable para ElEdenApp. Esperamos que sea lo suficientemente claro para entender las necesidades, restricciones y demás consideraciones que nos han llevado al diseño final del servicio, el entendimiento del por qué funciona como está planteado aquí y las restricciones bajo las cuales fue desarrollado pueden servir de insumo para planear y ejecutar cambios en el futuro. 

Para el levantamiento de estos motivadores se usó un árbol de utilidad para definir una priorización inicial de los atributos de calidad.

Se toma como base los principios del marco de trabajo Amazon Well-Architected Framework.

Se hace énfasis en habilitar la capacidad de autoservicio dentro del servicio de forma que la célula transversal no sea un cuello de botella para realizar cambios de configuración o personalizaciones propias de cada cliente del servicio.  Nuestro objetivo como servicio transversal consiste en simplificar el consumo y ocultar la complejidad asociada al consumo y orquestación de servicios de operadores de seguridad.

## Método

El método usado para la creación de la arquitectura del producto EdenApp, está dirigido por los atributos de calidad y su relación con los requerimientos del sistema. Se busca alinear al máximo los objetivos y necesidades de negocio con los capacidades técnicas a través de los requerimientos del sistema, también definir las bases que permitirán evolucionar el producto a medida que se aprende mas sobre las necesidades de los usuarios.

## Requerimientos del sistema

Fuente: [./content/arquitectura/source/requerimientos.xlsx](./source/requerimientos.xlsx)

**Nota**: Si realiza un cambio en el excel de requerimientos, por favor actualice esta tabla con la herramienta [Table2Markdown](https://tabletomarkdown.com/).

*Tabla requerimientos*

TODO agregar

## Diseño de Arquitectura

La solución de arquitectura propuesta para ElEdenApp se basa en un estilo arquitectural de microservicios, permitiendo la encapsulación de responsabilidades definidas y un desacoplamiento e independencia de los servicios. Lo cual posibilita la adición o modificación de características a la arquitectura de forma ágil y sin generar indisponibilidades en la prestación de servicio o en el funcionamiento de los demás servicios.

# Objetivos de la Arquitectura

- Generar una herramienta para la automatización del proceso de registro, gestion y publicación del contenido turistico y comercial.
- Definir una arquitectura de solución completamente nativa en nube.
- Definir una estrategia de arquitectura que asegure la disponibilidad del servicio de 99.999.
- Modelar una solución arquitectural de escalabilidad/elasticidad que asegure el crecimiento y decrecimiento del sistio en incrementos de carga.

## Diseño Guiado por Dominio (DDD)

- DOMINIO:
Entendido como el negocio en si, es todo aquello a lo que la alcaldia de La Tebaida hace como entidad a traves de la plataforma ElEdenApp y en consecuencia es el "problema" que se desea resolver, en este caso tener una herramienta que sirva como catalogo de los producto y servicios de las empresas del municipio. El subdominio es la estrategia que permite separar el problema en pequeñas partes funcionales, se debe clasificar en «Core» (Por lo que visita el cliente la plataforma) el cual soporta una funcionalidad para que opere la plataforma y en «soporte» y/o «generico» que son funcionalidades que pueden usarse en este u otro dominio.

![alt text](../../assets/EE_Dominio_v1.0.jpg?raw=true)

- BOUNDED CONTEXT:
Módulo de software especifico que puede abarcar un sistema, aplicaicon o servicio comercial.

![alt text](../../assets/EE_BoundedContext_v1.0.jpg?raw=true)

- ENTIDAD:
El libro de Vernon, "Implementación del diseño controlado por dominio", tiene una excelente definición de Entidad: "Diseñamos un concepto de dominio como una Entidad cuando nos preocupamos por su individualidad, cuando distinguir si de todos los objetos en un sistema es una restricción obligatoria. Una Entidad es una cosa única y es capaz de cambiar continuamente durante un largo período de tiempo". La mutabilidad y la identidad única son las dos características principales que tienen las entidades.

![alt text](../../assets/EE_Entidades_1.0.jpg?raw=true)


![alt text](../../assets/EE_Servicios_v1.0.jpg?raw=true)


![alt text](../../assets/EE_EventStormingParte1_v1.0.jpg?raw=true)




### Modelo de casos de uso

Los casos de uso se pueden ver rapidamente en el siguiene diagrama:

| Rol | Descripción |
| --- | --- |
| Turista | Consultar los productos y servicios de la oferta turistica y comercial del municipio de La Tebaida |
| Dueño de Organización | Crear y gestionar los recursos que permitan dar a conocer los productos y servicios a los turistas de una o mas organizaciones a su nombre. |
| Administrador | Crear y gestionar categorias de empresa y de productos, asi como de gestionar la visibilidad de sus contenidos en la plataforma. |

![alt text](../../diagrams/EE_DiagramaCasosDeUso_v1.0.jpg?raw=true)





### Escenarios de atributos de calidad

Debido a que son tablas complejas, preferimos que se remita a la fuenta para revisarlas.

Fuente: [./content/arquitectura/source/requerimientos.xlsx - Hoja "escenarios"](./source/requerimientos.xlsx)

### Restricciones

De negocio:

Tecnológicos: 

Otros:

### Preocupaciones arquitectónicas

- Manejo de la configuración del servicio

- Manejo de secretos del servicio

- Observabilidad

- Definición de métricas

- Trazabilidad

- Lineamientos de auditoría por registros.

Gestión de errores y excepciones

Procesamiento secuencial. Problemas de contingencia que afecten la escalabilidad

*P-001: Fácil de operar y auditar*

Se debe poder rastrear el estado de las peticiones, registro de casos excepcionales, errores técnicos y errores de negocio para facilitar la resolución de problemas en ambiente de producción.

*P-002: Fácil de mantener*

El servicio debe poderse adaptar a las necesidades del negocio y ser modificado rápidamente (TODO definir cuanto tiempo estimado base) por el equipo de desarrollo.

 

## Identificación y selección de conceptos de diseño

### Arquitectura de referencia

Estilo de arquitectura nuclear y patrones complementarios

### Patrones de arquitectura

Patrones de diseño 
Basado en los patrones descritos en el libro [Microservices Pattern: A pattern language for microservices](https://microservices.io/patterns/) , [Cloud design patterns - Azure Architecture Center](https://docs.microsoft.com/en-us/azure/architecture/patterns/), [SOA Design Patterns](https://patterns.arcitura.com/soa-patterns).

Fuente: [./content/arquitectura/source/requerimientos.xlsx - Hoja "patrones"](./source/requerimientos.xlsx)

**Nota**: Si realiza un cambio en el excel de requerimientos, por favor actualice esta tabla con la herramienta [Table2Markdown](https://tabletomarkdown.com/)

Tabla Patrones de diseño seleccionados para EdenApp

TODO agregar tabla

## Producción de estructuras

### Estructura global

En este diagrama se muestra una visión global del sistema:

![Markitecture](../../diagrams/markitecture.png)


### Identificación de estructuras que soporten la funcionalidad principal

#### Modelo de dominio de alto nivel

En la descomposición de la funcionalidad nos guiaremos con los siguientes principios:

- *Single Responsability Principle*: Una clase debe tener solo una razón para cambiar. En nuestro caso aplica para los componentes/funciones internas del servicio.

- *Common Closure Principle*: Las funciones dentro de la misma capa deben estar lo suficientemente juntas contra el mismo tipo de cambio. Un cambio en la capa afecta todos los componentes en esa capa. 

Restricciones de la descomposición:

Latencia de red

Disponibilidad limitada debido a la comunicación síncrona.

TODO agregar tabla de descompisción de funcionalidad.

## Definición de interfaces

### Interfaces externas

Externamente las interfaces UI deben ser creadas con [React](https://reactjs.org/) para dos tipos de usuarios diferentes:

- Aplicación [PWA](https://developers.google.com/web/ilt/pwa/) con un enfoque [Mobile-first](https://medium.com/@Vincentxia77/what-is-mobile-first-design-why-its-important-how-to-make-it-7d3cf2e29d00) para usuarios finales, en este caso visitantes o turistas.

Los diseños de las vistas creados en Figma los puede ver [aquí](https://www.figma.com/proto/LLRFtLkKFzHDbscyIO0lD9/Prototipo-Copy?node-id=582%3A245&scaling=min-zoom&page-id=0%3A1)

- Portal de administración para usuarios finales, en este caso dueños de comercio o administradores.

Los diseños de las vistas creados en Figma los puede ver [aquí](TODO )

### Interfaces internas

#### Estrategia de diseño API-first

Con el fin de agilizar la participación de los interesados en consumir este servicio e integrar las valiosos aportes que estos nos pueden proveer durante el proceso de desarrollo e implementación se propone la estrategia de diseño API-first en donde el equipo se concentra en definir las interfaces a través de las cuales se expondrán las capacidades de los servicios Backend a la aplicación PWA para clientes y el Portal de administración.

El uso de un estilo REST para la interfaz y OpenAPI, impacta AC-4: Interoperabilidad y AC-7: Capacidad de aprendizaje.

- Puede consultar las API aquí: TODO agregar link de interfaz swagger.


## Vistas de arquitectura: modelo 4+1

Para la documentación de la arquitectura el equipo se decantó por el modelo 4+1 por ser el mas aceptado y manejado dentro de la industria, ademas de la experiencia que tienen los integrantes del equipo con este tipo de vistas.

La herramienta para la creación de los diagramas es [draw.io](https://draw.io), no es la mas apropiada para realizar este tipo de diagramas, sin embargo nuestro enfoque es la practicidad ademas de ser una herramienta disponible y facil de usar para cualquier persona que deseé modificar y actualizar las vistas.

### Vista lógica

### Vista de procesos

Para mayor detalle puede visitar [Procesos de negocio](../procesos/procesos-negocio.md)

### Vista física

### Vista de desarrollo

### Vista de Escenarios

## Evaluación con ATAM

TODO evaluación ATAM, Workshop interno, grabarlo y subirlo al classroom.

## Referencias
- Designing Software Architectures - A Practical Approach, 2016, Humberto Cervantes, Rick Kazman

- Software Architecture in Practice (3rd Edition), 2019, Bass, Clements, Kazman.

- Microservices Patterns, 2019,  Chris Richardson.

- Cloud Design Patterns, 2018, Alex Homer, Jhon Sharp, Larray Brader, Masashi Narumoto, Trent Swanson
