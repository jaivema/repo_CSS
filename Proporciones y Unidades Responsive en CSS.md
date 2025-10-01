# Proporciones y unidades Responsive en CSS.

1. Viewport width.

2. Regla aspect-ratio.

3. Función clamp().

---

## Viewport width.

**vw** significa **"viewport width"** (ancho de la ventana de visualización). Es una unidad de medida relativa en CSS que representa un porcentaje del ancho total de la pantalla del dispositivo.

- **Diseño responsive:** Permite que el tamaño de la fuente, los márgenes, el padding, etc., se ajusten automáticamente al tamaño de la pantalla.

- **Tipografía fluida:** Útil para títulos o textos que deben escalar con el dispositivo.

- > **1vw** = 1% del ancho de la pantalla.
  > 
  > **100vw** = 100% del ancho de la pantalla (el ancho completo).
  > 
  > 2vw = 2/100 x 1500px = 30px

### Otras unidades:

- **px:** Fijo, no se adapta al tamaño de pantalla.
- **%:** Relativo al tamaño del elemento padre.
- **rem:** Relativo al tamaño de la fuente del elemento raíz (`<html>`).
- **em**: Relativo al tamaño de la fuente del elemento padre.
- **vw/vh:** Relativo al tamaño de la ventana del navegador.

---

## Regla aspect-ratio.

**Proporción de aspecto (aspect ratio)** de los elementos visuales en la página.

Si un elemento tiene un ancho de 200px, su altura será de 100px.

Si el ancho es 100vw, la altura será 50vw.

Se aplica a contenedores, imágenes, videos, etc., no a fuentes.

### CSS moderno:

```css
.elemento {
  aspect-ratio: 2 / 1;
  width: 100%; /* o cualquier valor de ancho */
  /* La altura se calculará automáticamente para mantener */
  /* la proporción 2:1 */
}
```

### CSS compatible:

```css
.elemento {
  width: 100%;
  padding-top: 50%; /* (1/2) * 100% */
  position: relative;
}
.elemento-content {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
}
```

#### Notas

> **2:1 ratio** = ancho es el doble de la altura.
> 
> Usa `aspect-ratio: 2 / 1;` en CSS moderno.

---

## Función Clamp().

Forma parte de **CSS Values and Units Module Level 4** (estándar del W3C).

`clamp()` es una **función de CSS** (nativa, no necesitas librerías) que sirve para definir un valor **con tres límites**:

**clamp(valor-mínimo, valor-preferido, valor-máximo)**

- **valor-mínimo** → nunca será más pequeño que valor.

- **valor-preferido** → el valor “ideal” que puede variar (normalmente en **vw**, **vh**, etc.).

- **valor-máximo** → nunca será más grande que este valor.

> Todos los navegadores modernos ya lo soportan (Chrome, Firefox, Safari, Edge).
> 
> Está pensado para **tipografía y layouts fluidos** → evita el típico `@media` repetido.

```css
h1 {
  font-size: clamp(1.5rem, 4vw, 3rem);
}
```

Nunca baja de **1.5rem**.

Escala de forma fluida con el ancho de pantalla (4vw).

Nunca sube de **3rem**.

```css
.container__bar {
  height: clamp(15rem, 22vh, 25rem);
}
```

Mínimo **15rem** (accesible, aunque la pantalla sea muy pequeña).

Escala con el **22vh** (alto relativo a la pantalla).

Máximo **25rem** (no crecerá desproporcionado en pantallas enormes).

```css
.card {
  width: clamp(250px, 50%, 800px);
}
```

Nunca será más pequeña que **250px**, ni más ancha que **800px**, pero tratará de ocupar el **50%** del contenedor.

> Ventaja principal: **ya no tienes que escribir media queries manuales** para esos casos básicos.
