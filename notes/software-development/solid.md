---
id: SOLID
aliases:
  - SOLID
tags:
  - basic
  - clean arch
---

# SOLID

Los principios SOLID son un conjunto de cinco principios de diseño que buscan mejorar la calidad y mantenibilidad del software.

## 1. `Single Responsability Principle`

El primero de los 5 principios nos dice que cada clase debe de tener una única responsabilidad. Por lo tanto, esa clase debe de realizar su única tarea y hacerla bien.

```typescript
export class OrderService {
  processOrder(orderId: string) {
    // Logic to process the order
    console.log(`Processing order ${orderId}`);
  }
}

export class OrderRepository {
  saveOrder(orderId: string) {
    // Logic to save the order to the database
    console.log(`Order ${orderId} saved to the database`);
  }
}

export class NotificationService {
  sendOrderConfirmation(orderId: string) {
    console.log(`Order confirmation for ${orderId} sent`);
  }
}
```

## 2. `Open/Close Principle`

Las entidades de software deben de estar abiertas para su extensión, más no para su modificación, esto significa que cuando modifiquemos una entidad, como puede ser una clase, esta modificación debe ser para agregar un comportamiento, más no para quitar o modificar uno ya definido.

```typescript
export abstract class PaymentProcessor {
  abstract processPayment(amount: number): void;
}

export class PayPalProcessor extends PaymentProcessor {
  processPayment(amount: number): void {
    console.log(`Processing payment of $${amount} through PayPal`);
  }
}

export class CreditCardProcessor extends PaymentProcessor {
  processPayment(amount: number): void {
    console.log(`Processing payment of $${amount} through Credit Card`);
  }
}
```

## 3. `Liskov Sustitution Principle`

Los objetos derivados de una clase deben poder remplazar a los objetos de su clase base sin alterar el comportamiento del programa.

```typescript
export abstract class Shape {
  abstract area(): number;
}

export class Rectangle extends Shape {
  constructor(
    private width: number,
    private height: number,
  ) {
    super();
  }

  area(): number {
    return this.width * this.height;
  }
}

export class Circle extends Shape {
  constructor(private radius: number) {
    super();
  }

  area(): number {
    return Math.PI * this.radius * this.radius;
  }
}

const shapes: Shape[] = [new Rectangle(10, 20), new Circle(5)];
shapes.forEach((shape) => {
  console.log(`Area: ${shape.area()}`);
});
```

## 4. `Interface Segregation Principle`

Se deben tener interfaces especificas para un cliente y no una interfaz general.

```typescript
interface Orderable {
  placeOrder(): void;
}

interface Trackable {
  trackOrder(): void;
}

interface Cancelable {
  cancelOrder(): void;
}

export class OnlineOrder implements Orderable, Trackable {
  placeOrder(): void {
    console.log("Order placed");
  }

  trackOrder(): void {
    console.log("Order tracked");
  }
}

export class InStoreOrder implements Orderable, Cancelable {
  placeOrder(): void {
    console.log("Order placed in-store");
  }

  cancelOrder(): void {
    console.log("Order cancelled");
  }
}
```

## 5. `Dependency Inversion Principle`

Los módulos de alto nivel no deben depender de módulos de bajo nivel, ambos deben depender de abastracciones. Además las abstracciones no deben depender de los detalles, sino que los detalles deben depender de las abstracciones. Esto ayuda al desacomplamiento del código.

```typescript
export interface Logger {
  log(message: string): void;
}

export class ConsoleLogger implements Logger {
  log(message: string): void {
    console.log(message);
  }
}

export class FileLogger implements Logger {
  log(message: string): void {
    // Logic to write the message to a file
    console.log(`Writing to file: ${message}`);
  }
}

import { Logger } from "./logger";

export class OrderProcessor {
  constructor(private logger: Logger) {}

  process(orderId: string): void {
    this.logger.log(`Order ${orderId} processed`);
  }
}
```
