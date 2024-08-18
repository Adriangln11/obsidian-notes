---
id: design-patterns
aliases:
  - Design Patterns
tags:
  - architecture
  - clean arch
  - algorithms
---

# Design Patterns

Los patrones de diseño son soluciones típicas a problemas comunes en diseño de software. Son soluciones maleables según lo necesite tu proyecto. Son una base, más no obligatorias o limitativas.

---

## `Beneficios`

- Reusabilidad: Proporcionan soluciones probadas y reutilizables para problemas comunes.
- Mantenibilidad: Facilita la creación de código más limpio y organizado. El software se vuelve más fácil de entender y mantener a largo plazo.
- Flexibilidad: Permite que el software sea más adaptable a cambios futuros. Puedes extender o modificar el sistema sin hacer cambios drásticos.
- Comunicación: Crean un vocabulario efectivo. Al hablar de un `Singleton` se entiende claramente a que solución te refieres sin entrar en detalles.
- Escalabilidad: Pueden adaptarse a nuevos requisitos o funcionalidades.
- Reducción de errores: Al implementar soluciones que han sido probadas reduces la posibilidad de fallas.
- Desacoplamiento: Permite que cada una de las partes del sistema evolucione de manera independiente.
- Consistencia: Promueven un enfoque coherente, lo que facilita la integración de nuevos componentes y sistemas diferentes.
- Documentación: La estructura y el propósito del código son claros, lo que mejora la documentación y hace que sea más clara.

## `Desventajas`

- Complejidad adicional: Si se aplican en una situación innecesaria puede hacer que el sistema sea difícil de entender.
- Rendimiento: Algunos patrones pueden sobrecargar en términos de rendimiento debido a la carga adicional de abstracción, por ejemplo, patrones como el `Proxy`, o el `Decorator` pueden incrementar el número de objetos y el costo de llamadas al método.
- Mala aplicación: Si se aplican de mala manera puede provocar que el código sea poco entendible o de mala calidad.
- Mayor tiempo de desarrollo: El implementar patrones de diseño puede requerir mas tiempo para configurar y diseñar el sistema.

---

## `Clasificación`

Los patrones de diseño se catalogan según su complejidad, nivel de detalle, y escala de aplicabilidad en todo el sistema.

#### `Modismos`

Los patrones más básicos y de bajo nivel se denominan `modismos`, por lo general se aplican a un solo lenguaje de programación.

#### `Arquitectónicos`

Los patrones universales y de más alto nivel son los `arquitectónicos`. Estos se pueden implementar en prácticamente cualquier lenguaje. Se pueden usar para diseñar la arquitectura de una aplicación completa.

También se pueden catalogar según su intención o propósito. Hay tres grupos principales.

#### `Patrones de Creacion`

Estos patrones proporcionan mecanismos de creación de objetos que aumentan la flexibilidad y la reutilización del código existente.

#### `Patrones Estructurales`

Explican cómo ensamblar objetos y clases en estructuras más grandes, mientras se mantienen estas estructuras flexibles y eficientes.

#### `Patrones de Comportamiento`

Se encargan de la comunicación efectiva y la asignación de responsabilidades entre objetos.

---

## `Patrones de creación`

1.  [Factory Method](./factory-method.md): Proporciona una interfaz para crear objetos en una superclase, pero permite que las subclases alteren el tipo de objetos que se crearán.
2.  [[Abstract Factory]]: Permite introducir familias de objetos relacionados sin especificar sus clases concretas.
3.  [[Constructor]]: Permite construir objetos complejos paso a paso. Permite introducir diferentes tipos y representaciones de un objeto utilizando el mismo código de construcción.
4.  [[Prototype]]: Permite copiar objetos existentes sin que el código dependa de sus clases.
5.  [[Singleton]]: Permite asegurarse de que una clase solo tiene una instancia, a la vez que proporciona un punto de acceso global a esta instancia.

## `Patrones estructurales`

1. [[Adapter]]: Permite que los objetos con interfaces incompatibles colaboren.
2. [[Bridge]]: Permite dividir una clase grande o un conjunto de clases estrechamente relacionadas en dos jerarquías separadas (abstracción e implementación) que se pueden desarrollar de forma independiente entre sí.
3. [[Composite]]: Permite componer objetos en estructuras de árbol y, a continuación, trabajar con estas estructuras como si fueran objetos individuales.
4. [[Decorator]]: Permite asociar nuevos comportamientos a los objetos colocándolos dentro de objetos contenedor especiales que contienen los comportamientos.
5. [[Facade]]: Proporciona una interfaz simplificada a una biblioteca, un marco o cualquier otro conjunto complejo de clases.
6. [[Flyweight]]: Permite ajustar más objetos en la cantidad disponible de RAM compartiendo partes comunes de estado entre varios objetos en lugar de mantener todos los datos en cada objeto.
7. [[Proxy]]: Permite proporcionar un sustituto o marcador de posición para otro objeto. Un proxy controla el acceso al objeto original, lo que le permite realizar algo antes o después de que la solicitud llegue al objeto original.

## `Patrones de comportamiento`

1. [[Chain of responsability]]: Permite pasar solicitudes a lo largo de una cadena de controladores. Al recibir una solicitud, cada controlador decide procesar la solicitud o pasarla al siguiente controlador de la cadena.
2. [[Command]]: Convierte una solicitud en un objeto independiente que contiene toda la información sobre la solicitud. Esta transformación le permite pasar solicitudes como argumentos de método, retrasar o poner en cola la ejecución de una solicitud y admitir operaciones que se pueden deshacer.
3. [[Iterator]]: Permite recorrer los elementos de una colección sin exponer su representación subyacente (lista, pila, árbol, etc).
4. [[Mediator]]: Permite reducir las dependencias caóticas entre objetos. El patrón restringe las comunicaciones directas entre los objetos y los obliga a colaborar solo a través de un objeto mediador.
5. [[Memento]]: Permite guardar y restaurar el estado anterior de un objeto sin revelar los detalles de su implementación.
6. [[Observer]]: Permite definir un mecanismo de suscripción para notificar a varios objetos sobre cualquier evento que le ocurra al objeto que están observando.
7. [[State]]: Permite a un objeto alterar su comportamiento cuando cambia su estado interno. Parece como si el objeto hubiera cambiado de clase.
8. [[Strategy]]: Permite definir una familia de algoritmos, colocar cada uno de ellos en una clase separada y hacer que su objetos sea intercambiables.
9. [[Template Method]]: Define el esqueleto de un algoritmo en la superclase, pero permite que las subclases anulen pasos específicos del algoritmo sin cambiar su estructura.
10. [[Visitor]]: Permite separar los algoritmos de los objetos sobre los que operan.
