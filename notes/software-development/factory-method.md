---
id: factory-method
aliases:
  - Factory Method
tags:
  - clean arch
  - design patterns
  - algorithms
---

# Factory Method

## 1. `Problema`

Proporciona una forma de crear objetos sin especificar la clase exacta del objeto que se va a crear. En lugar de llamar al constructor de una clase, delega la responsabilidad a una `Factory`, permitiendo que las subclases modifiquen el tipo de objeto que se crea.

## 2. `Ventajas y desventajas`

###### Pros

- Puedes cambiar la clase de productos sin modificar el código que los utiliza.
- Las clases utilizan productos no necesitan saber la clase exacta de los objetos que crean.
- Simplifica el proceso de creación de objetos en entornos complejos.

###### Cons

- Puede añadir complejidad al código si se abusa de él o si el número de productos es limitado.

## 3. `¿Cuando usarlo?`

- Cuando una clase no puede anticipar que clase de objetos necesita crear.
- Cuando una clase quiere delegar la creación de subclases.
- Cuando quieres ofrecer a las subclases la opción de alterar el tipo de objetos que se crean.

## 4. `Ejemplo en TS`

```typescript
interface Button {
  render(): void;
  onClick(): void;
}

class HtmlButton implements Button {
  render(): void {
    console.log("Renderizando un botón HTML.");
  }

  onClick(): void {
    console.log("Clic en un botón HTML.");
  }
}

class WindowsButton implements Button {
  render(): void {
    console.log("Renderizando un botón de Windows.");
  }

  onClick(): void {
    console.log("Clic en un botón de Windows.");
  }
}

abstract class Dialog {
  abstract createButton(): Button;

  renderDialog(): void {
    const okButton = this.createButton();
    okButton.render();
  }
}

class HtmlDialog extends Dialog {
  createButton(): Button {
    return new HtmlButton();
  }
}

class WindowsDialog extends Dialog {
  createButton(): Button {
    return new WindowsButton();
  }
}

function main() {
  let dialog: Dialog;

  const platform = "Windows"; // Puede cambiarse a "HTML" según el entorno

  if (platform === "Windows") {
    dialog = new WindowsDialog();
  } else {
    dialog = new HtmlDialog();
  }

  dialog.renderDialog();
}

main();
```
