# PROYECTO DE IMPLEMENTACIÓN GUÍA TURISTICA PASEO EL ÉDEN

**Importante**: Le recomendamos por favor clone este repositorio y realice los ajustes necesarios cuando se requiera. El contenido de este repositorio incluye archivos en formato [Markdown](https://www.markdownguide.org/), excel y [draw.io](https://draw.io). Cualquier actualización que realice versionelo adecuadamente para que todo el equipo de desarrollo de producto lo tenga sincronizado.

```
git clone https://github.com/mintic-conv-534-2021/eden-app-docs.git
```

## Introducción

Este repositorio documental tiene como intención describir la arquitectura de referencia, el alcance y el enfoque que actualmente de utiliza para la implementación de la guia turistica del paseo El Éden del municipio de La Tebaida, Quindío. En este se define el contexto y la necesidad de negocio que motiva su implementación. Se analiza de forma general el funcionamiento del sistema, la integración con el cliente, las organizaciones partícipes, las restricciones funcionales, atributos de calidad y las características tecnológicas de la aplicación. Este trabajo de arquitectura fue realizado por los arquitectos:

![alt text](./assets/EE_Arquitectos_v1.0.jpg?raw=true)

Como requisito para la condonación del crédito beca ofrecido por el MinTic, con el cual realizaron sus estudios formales de arquitectura empresarial y de software en la Pontificia Universidad Javeriana.

Para complementar el contenido presentado en este repositorio puede ver algunos videos explicativos en nuestro classroom: https://classroom.google.com/c/MjkwMzQ5MTM5NzE3?cjc=f2hpo4j

## Contexto de negocio

Actualmente Colombia ha tenido un aumento notable en el mercado de retail por internet. Si se analizan los números que dejaba este tipo de comercio hace seis años y los comparamos con cifras actuales, es evidente que los colombianos cada año les apuestan mucho más a los canales digitales para suplir sus necesidades. El país ha pasado de un valor anual del Internet retailing de $471 millones de dólares en 2013 a más de $5.207 millones en 2019, según Euromonitor.

Una de las mayores razones se debe a que si bien la penetración de Internet en Colombia está lejos de ser la ideal en 2019, los colombianos que tienen acceso a la red le dan una frecuencia de uso alta a la herramienta: ocho de cada diez personas navegan en la red diariamente, y lo hacen, en su mayoría, desde sus teléfonos móviles y en sus hogares o sitios de trabajo, reporta la Cámara Colombiana de Comercio Electrónico.

Por tanto, el sistema que aquí se implementa es una solución a la necesidad tanto de clientes y proveedores para poder ofrecer información relevante sobre los productos y empresas del sector turistico del municipio de La Tebaida.

![alt text](./assets/EE_NecesidadesDeNegocio_v1.0.jpg?raw=true)

### Objetivos de negocio

1. Presentar a los turistas y lugareños una herramienta que permita conocer la oferta turistica, gastronomica y empresarial de la tebaida.
2. Implulsar el credimiento comercial y turistico del municipio de la Tebaida.
3. Motivar a los empresarios y microempresarios a cumplir con los requisitos comerciales.

## Arquitectura

Esta arquitectura actua como el instrumento para la alcaldia del municipio de La Tebaida para apalancar el cumplimiento de su misión institucional permitiendo resaltar en el mercado por la calidad del servicio que proporciona a sus clientes y el mejoramiento de la calidad de vida de quienes conforman este equipo de trabajo.

![alt text](./assets/EE_MotivacionArquitectura_v1.0.jpg?raw=true)

Esta arquitectura esta diseñada bajo 3 grandes pilares:

- La innovación al permitir que el comercio de La Tebaida se reinvente y permita cohesionar nuevas estrategias de negocio y que se puedan llevar a la realidad en el menor tiempo posible y sin generar traumatismos.

- Confianza al implementar las mejores prácticas de diseño e implementación de arquitecturas que permiten evolucionar de manera eficaz, ordenada, rapida y segura.

- Competitividad en cada uno de los procesos que se implementen dentro de la arquitectura, logrando validar nuevas estrategias comerciales y ofreciendo las mejores soluciones a sus clientes.

![alt text](./assets/EE_NecesidadesTecnicas_v1.1.jpg?raw=true)

La solución debe permitir a la alcadia y a las organizaciones de La Tebaida realizar actualizaciones, creaciones y cambios del contenido de sus productos sin tener que desplegar nuevamente el sistema, además de agregar nuevas organizaciones o categorias sin que esto sea traumático, se espera poder en un futuro recolectar información de los usuarios y servidores para futuro análisis, la disponibilidad del servicio debe ser mínimo del 99.999% del tiempo, es decir la plataforma debe estar en línea las 24 horas del día, los 7 días a la semana, los 365 días del año.

La plataforma debe tener una capacidad de respuesta a las funcionalidades del negocio para temporadas altas, permitiendo crecer y decrecer dinámicamente según la demanda, como en ferias y fiestas, festivos, vacaciones, fiestas decembrina o en otros donde la demanda por los servicios puede crecer hasta 250% sobre la operación normal. 

Las peticiones de consulta de productos no deben tardar más de 1.5 segundos promedio por usuario y ninguna petición puede tardar más de 3 segundos. El contenido digital (Imágenes, archivos, iconos, etc) juega un factor relevante en el sitio, en promedio este representa alrededor del 60% de lo que se despliega en la página, por lo que se requiere una solución que permita manejar este contenido y hacerlo disponible de manera cercana al usuario que lo solicita. 

Con esto la alcaldia de La Tebaida espera poder mejorar la experiencia a los turistas y lugareños con un canal disponible en todo momento, así mismo espera poder ser más agile en la adaptación a los cambios del negocio y automatizar las actividades que actualmente realiza de forma manual.

- Para ver mas sobre la arquitectura de la aplicación puede ir a: [Propuesta arquitectura](./content/arquitectura/propuesta-arquitectura-solucion.md)

## Procesos

- Para ver mas sobre los procesos de desarrollo que recomendamos seguir: [Procesos Desarrollo](./content/procesos/procesos-desarrollo.md)

- Para conocer los procesos de negocio de EdenApp: [Procesos de negocio](./content/procesos/procesos-negocio.md)

## Desarrollo

- [Estandar de commits](./content/desarrollo/estandar-commits.md)
- [Desarrollo seguro](./content/desarrollo/guía-desarrollo-seguro.md)

## Devops

- [Estrategia de DevOps para EdenApp](./content/devops/estrategia-devops-para-eden-app.md)
- [Estrategia de Observabilidad y Monitoreo](./content/devops/estrategia-observabilidad-monitoreo.md)
- [Estrategia de Versionamiento](./content/devops/estrategia-versionamiento.md)

Cualquier duda o inquietud con el proceso de desarrollo creación de nuevos requerimientos o reportar errores: [edenapplatebaida@gmail.com](mailto:edenapplatebaida@gmail.com).


