## ¿Qué es `display`?

La propiedad **`display`** define el **comportamiento de caja** de un elemento:

- Cómo se coloca en el flujo del documento.

- Si ocupa toda la línea o solo el espacio necesario.

- Si permite colocar otros elementos a su lado.

- Cómo se comportan sus hijos.

---

## 🔹 Valores más comunes de `display`

### 📦 1. Elementos de bloque y en línea

- **`block`**
  
  - Ocupa **toda la línea** disponible.
  
  - Se le pueden aplicar márgenes, paddings, ancho y alto.
  
  - Ejemplos naturales: `<div>`, `<p>`, `<h1>`...
  
  `display: block;`

- **`inline`**
  
  - Solo ocupa el **espacio de su contenido**.
  
  - No rompe la línea.
  
  - No respeta `width` ni `height`, pero sí `padding` y `margin` horizontales.
  
  - Ejemplos naturales: `<span>`, `<a>`, `<strong>`...
  
  `display: inline;`

- **`inline-block`**
  
  - Combina características: se comporta como `inline` (no rompe línea) pero acepta `width`, `height`, `margin` y `padding`.
  
  `display: inline-block;`

---

### 📐 2. Modelos de layout modernos

- **`flex`**
  
  - Convierte el contenedor en un **flex container**.
  
  - Sus hijos se convierten en **flex items**, que se alinean en fila o columna.
  
  `display: flex;`

- **`inline-flex`**
  
  - Igual que `flex`, pero el contenedor se comporta como un elemento en línea.

- **`grid`**
  
  - Activa el **Grid Layout**: los hijos se organizan en filas y columnas.
  
  `display: grid;`

- **`inline-grid`**
  
  - Igual que `grid`, pero el contenedor sigue siendo en línea.

---

### 🎭 3. Otros valores útiles

- **`none`**
  
  - Elimina el elemento del flujo del documento (como si no existiera).
  
  `display: none;`

- **`contents`**
  
  - Hace que el contenedor **no genere caja propia** pero mantiene visibles sus hijos.
  
  - Útil para heredar estilos sin añadir nodos extra al flujo.
  
  `display: contents;`

- **`list-item`**
  
  - Se comporta como bloque pero con viñetas (ej. `<li>`).
  
  `display: list-item;`

- **`table`, `table-row`, `table-cell`...**
  
  - Permiten emular la estructura de tablas sin usar `<table>`.

---

## 🔹 Ejemplo visual rápido

```html
<div style="display:block; background:lightblue">
    Bloque
</div>
<span style="display:inline; background:lightgreen">
    En línea
</span>
<span style="display:inline-block; width:100px; background:pink">
    Inline-block
</span>    
<div style="display:flex; gap:10px; background:lightyellow"> 
    <div>1</div>
    <div>2</div>
    <div>3</div>
</div>
```

---

## 🔹 Resumen

- `block`, `inline`, `inline-block` → básicos.

- `flex` y `grid` → layouts modernos y potentes.

- `none` y `contents` → control de visibilidad/estructura.

- `list-item`, `table-*` → casos específicos.

---

¿Quieres que te arme un **cuadro comparativo** con ejemplos prácticos de cada valor (`block`, `inline`, `flex`, `grid`, etc.) para que lo tengas como chuleta rápida?

##### Tú dijiste:

ejemplo de flex-inline 😳

###### ChatGPT Plus

¡Claro! 😎  
El valor correcto es **`inline-flex`** (no existe `flex-inline`).

📌 La diferencia con `flex` es que el contenedor se comporta como un **elemento en línea**, es decir:

- Ocupa solo el ancho de su contenido.

- Puede convivir en la misma línea con otros elementos.

- Sus hijos se siguen distribuyendo como un **flexbox** normal.

---

### 🔹 Ejemplo práctico

```html
<style>
    .flex-container {
        display: inline-flex;
        gap: 10px;
        padding: 10px;
        border: 2px solid steelblue;
        background: lightblue;
    }
    .item {
        background: coral;
        padding: 10px;
        border-radius: 5px;
    } 
</style>

<p> 
    Texto antes 
<span class="flex-container"> 
<div class="item">1</div> 
<div class="item">2</div> 
<div class="item">3</div> 
</span> 
    Texto después 
</p>
```

---

### 🔹 ¿Qué pasa aquí?

- El contenedor `.flex-container` es un **flexbox**, pero como es `inline-flex`, se comporta como si fuera un `<span>`.

- Eso significa que se puede poner **en línea con texto u otros elementos**, a diferencia de `display:flex` que **rompe la línea**.

📖 Con `flex` el bloque ocuparía todo el ancho disponible, pero con `inline-flex` se ajusta al contenido y no baja de línea.

###### El **alto (`height`)** en `inline-flex` funciona igual que en `flex`:

- El contenedor puede tener `height` fijo, o crecer según el contenido.

- A diferencia de `inline` o `inline-block`, los elementos **flex items** dentro del `inline-flex` se alinean en el eje cruzado (vertical, si la dirección es `row`) gracias a propiedades como `align-items`.

---

### 🔹 Diferencia clave

- **`flex`**: el bloque ocupa **todo el ancho disponible**, y su `height` se aplica normalmente.

- **`inline-flex`**: el bloque se comporta como un elemento **en línea**, es decir, solo ocupa el ancho de su contenido (pero el `height` sigue funcionando).

👉 La diferencia está en el **ancho y el flujo del documento**, no en la altura: ambos respetan `height` y alineaciones.

---

**`display:inline-flex`**:

- Se comporta como un **elemento en línea** hacia afuera.

- Se comporta como un **contenedor flex** hacia adentro.

Un poco Frankenstein, pero súper útil para cosas como botones con íconos, chips, badges o elementos que deben alinearse dentro del texto pero con flexibilidad interna.

---

### 🔹 Escenario con `inline-flex` (se queda en línea con el texto)

`lorem | item1 | item2 | item3 | ipsum distrl upsen lokin abden para luin.`

👉 Aquí el `inline-flex` se porta como si fuera una palabra más dentro de la frase,  
pero **por dentro sigue siendo un contenedor flex** que distribuye a `item1`, `item2`, `item3`.

---

### 🔹 Si le das altura fija (`height: 3 líneas`, por ejemplo)

`lorem | [ item1 item2 item3 ] | ipsum distrl        |                       |        |    (altura extra)     | upsen lokin abden para luin.`

👉 El bloque `inline-flex` respeta la altura, pero el texto de arriba y abajo fluye como siempre.

---

📌 En resumen en modo ASCII:

- **`flex`** → bloque gordo que rompe la línea.

- **`inline-flex`** → mini-bloque flexible que se mete dentro de la misma línea de texto.

---

### 🔹 Concepto clave

- `vertical-align` afecta a **elementos en línea o en línea con caja** (`inline`, `inline-block`, `inline-flex`, `img`, etc.).

- Controla **cómo se alinea el contenedor respecto a la línea base** del texto (o de otros elementos en la misma línea).

---

### 🔹 Valores comunes

| Valor                     | Qué hace                                                                         |
| ------------------------- | -------------------------------------------------------------------------------- |
| `baseline` (default)      | La base del `inline-flex` se alinea con la línea base del texto.                 |
| `top`                     | El borde superior del `inline-flex` se alinea con el borde superior de la línea. |
| `middle`                  | Centra verticalmente respecto a la línea (aproximadamente).                      |
| `bottom`                  | El borde inferior del `inline-flex` se alinea con el borde inferior de la línea. |
| `sub`, `super`            | Para alineación tipo subíndice o superíndice.                                    |
| `text-top`, `text-bottom` | Basado en la caja de texto adyacente.                                            |
