# Estrategia de DevOps para EdenApp

## Contenido

- [Introducción](#Introducción)
- [Contexto tecnológico](#Contexto-tecnológico)
- [Motivadores y restricciones](#Motivadores-y-restricciones)
- [Requerimientos](#Requerimientos)  
- [Diseño](#Diseño)

## Introducción

En este documento se presenta de manera concisa las decisiones de diseño tomadas para al implementación de una estrategia de DevOps para el desarrollo del producto minimo viable de la plataforma EdenApp, con este se pretende dejar unas bases solidas para el desarrollo sostenible del concepto.

## Contexto tecnológico

Con el fin de garantizar la entrega rápida de nuevas caracteristicas se elige el uso del proveedor de servicios en la nube AWS por tres principales razones:

- Al ofrecer capacidades de infraestructura, permite al equipo en su mayoría con experiencia en desarrollo a enfocarse en agregar valor desde el punto de vista técnico construyendo software.

- La mayoría de los integrantes del equipo de arquitectura y desarrollo tienen experiencia previa en esta plataforma, por lo que no se requiere tiempo de aprendizaje de nuevas herramientas.

- Luego de una evaluación desde el punto de vista [funcional y de arquitectura](../arquitectura/propuesta-arquitectura-solucion.md) se establecio que GitHub y AWS proporcionan las capacidades necesarias ahora y en el futuro inmediato para soportar la creación y evolución del prototipo propuesto.

## Motivadores y restricciones

Como se mencionó en el punto anterior, debido a la naturaleza del proyecto; en el cual se pretende construir un producto mínimo viable con base a escasa información sobre los usuarios de la plataforma, se considera que la mantenibilidad y la entrega continua son dos pilares fundamentales para la continuidad del producto por parte del equipo de la alcaldía municipal.

La restricción de tiempo (este proyecto se debe ejectutar en una ventana de tiempo de 1-2 meses) además de la imposibilidad de tener un equipo de trabajo a jornada completa es un punto importante a considerar alternativas de solución.

## Requerimientos

Para la definición de requerimientos técnicos se tienen en cuenta tres escenarios para la construcción del software asociado al proyecto y al producto EdenApp:

- Escenario de front-end: en este caso se requiere el despliegue fácil, sin intervención humana (o en lo mínimo posible) de la aplicación para clientes y el portal de administración de manera independiente, como ambas son aplicaciones web tipo PWA, el problema se reduce a:
    - La transpilación y adecuación de archivos estáticos
    - publicación de artefactos en el sistema de almacenamiento de acceso público.

- Escenario de back-end: en este caso se requiere el despliegue fácil y con minima intervención humana de (micro) servicios escritos en Java. Las tareas incluyen:
    - Validación reglas de estilo
    - Ejecución de pruebas unitarias automáticas
    - Validación de buenas prácticas (reportadas como violaciones y _code smells_)
    - Validaciones de seguridad básica
    - Validacion de no presencia de bugs
    - compilación y empaquetado
    - despliegue en el servidor de aplicaciones

- Escenario de infrastructura: en este caso se requiere usar infraestructura como código (IoC) para facilitar la replicación y mantenimiento a nivel de infrastructura en el proyecto y sacar máximo provecho al proveedor de servicios en la nube. Los componentes de infraestructura deben estar descritos y versionados apropiadamente.

## Diseño

Teniendo en cuenta los requerimientos anteriormente presentados, se crea la siguiente tabla donde se mapean los requerimientos con las herramientas disponibles en el mercado.

Es necesario aclarar que la selección de las herramientas no fue debido a un proceso exhaustivo, si no mas bien usando un enfoque práctico, partiendo de las herramientas disponibles en AWS y que requieran el minimo de configuración y curva de aprendizaje, esto debido a las restricciones de tiempo y capacidad del equipo.

TODO tabla


### Ambientes

Se definen tres ambientes para el despliegue de cambios, dependiendo del ciclo de desarrollo:

- develop: Ambiente de desarrollo, es el primer ambiente donde los desarrolladores pueden desplegar y realizar pruebas de concepto, validar ideas, etc.

- stage: Ambiente de pruebas de validación por parte de QA (aunque carecemos de equipo de QA no descartamos que se tenga en el futuro) en este caso se hace la validación con las partes interesadas (stakeholders) y usuarios friendly.

- prod: Ambiente de producción, donde se libera finalmente la funcionalidad para ser usada por los usuarios objetivos del aplicación. Se puede decir que una caracteristica o funcionalidad no agrega valor hasta que este en este punto.

Puede ver mas sobre la [estrategia de versionamiento](./estrategia-versionamiento.md)

Puede ver mas sobre el [estandar de commits](../desarrollo/estandar-commits.md).

### Vista escenario front-end

TODO escenario front-end

### Vista escenario back-end

TODO escenario back-end

### Vista escenario infraestructura

TODO escenario infra
