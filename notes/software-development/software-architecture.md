---
id: software-architecture
aliases:
  - Arquitectura de Software
tags:
  - architecture
---

# Arquitectura de Software

La arquitectura de software se refiere a la estructura fundamental de una aplicación de software, la cuál tiene como función principal definir los componentes que integran la aplicación y el como interactuan entre sí. Al tener bien definidos los componentes y sus responsabilidades es más sencillo el lograr que la aplicación sea escalable, mantenible, y eficiente.

En el desarrollo de aplicaciones hay diferentes tipos de arquitectura, y el que utilices en tu proyecto dependerá del tipo de aplicación que quieras construir.

## Tipos de Arquitectura de Software

#### 1. Monolítica

Imagina que tienes una aplicación sencilla con unas cuantas funcionalidades y que no necesitará mucho mantenimiento, siendo así puedes usar una arquitectura `Monolítica` para construirla.

Un proyecto monolítico es simple de desarrollar, probar, y desplegar, es ideal para proyectos pequeños que no necesiten escalar mucho en un futuro, con la desventaja de que pueden volverse difíciles de mantener y sí necesitas extender el proyecto te puede obligar a cambiar el tipo de arquitectura.

Las aplicaciones que desarrollamos cuando iniciamos en el Desarrollo de Software, tales como aplicaciones de notas, suelen ser ejemplos de monolitos.

#### 2. Micro-servicios

Cuando se tiene en mente el desarrollar un proyecto grande es necesario identificar las tecnologías a utilizar en base a los requerimientos de la aplicación, en ocasiones optarás por utilizar diferentes lenguajes en ese mismo proyecto, esto debido a que cada uno de ellos puede ofrecerte diferentes funcionalidades, más rapidez, mejor eficiencia, etc. En estos casos es cuando se puede aplicar una estructura de micro-servicios, ya que en esta puedes dividir el proyecto en servicios pequeños e independientes uno del otro y los cuales se comunicarán a través de APIs.

Puedes tener un servicio que se encargue de traer la información de la base de datos, otro servicio que se encargue de la pasarela de pagos, otro servicio que se encargue del procesamiento de archivos, y otro que se encargue de las notificaciones en tiempo real.

AL tener una arquitectura de micro-servicios aseguras que el desarrollo del proyecto sea mas sencillo, más escalable, y que si algo llega a fallar afecte solo a un servicio, ya que estos son independientes uno del otro.

#### 3. Cliente - Servidor

El módelo cliente servidor es aquel que se basa en las peticiones `HTTP` que se realizan en la web, un `Cliente` solicita un recurso al `Servidor` y este responde ya sea con el recurso solicitado, o lo definido por ese servidor.

Las ventajas de este tipo de arquitectura son la escalabilidad, el mantenimiento, la seguridad de los datos, y la optimización de recursos.

#### 4. Capas

La arquitectura de capas es conocida por organizar el sistema en capas jerarquicas en donde cada una de ellas tiene una responsabilidad especifica. Las capas superiores solo interactuan con las inferiores y así sucesivamente.

Este sistema puede ser útil cuando quieres mejorar la separación de responsabilidades y es mayormente utilizado en aplicaciones empresariales que mantienen dividido la interfaz, la lógica de negocio, y el acceso a los datos.

#### 5. Event-Driven

Cuando se producen eventos en el sistema y la apliacación reacciona ante ello, se dice que se esta utilizando una arquitectura Event-Driven.

Esta estructura es útil cuando se trabaja con sistemas de mensajería en tiempo real, por ejemplo.
