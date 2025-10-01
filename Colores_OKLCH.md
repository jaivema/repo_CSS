# OK Luminosidad - Cromaticidad - Tono.

El espacio de color **OKLCH** es una alternativa moderna y cada vez más popular a los modelos tradicionales como RGB, HEX o HSL, especialmente en diseño digital y desarrollo web.

1. Percepción unifomr del color.

2. Separación clara de atributos.

3. Mejor manejo de la accesibilidad.

4. Compatibilidada con CSS.

5. Facilidad para crear paletas armoniosas.

6. Menos dependencia del dispositivo.

---

## Ventajas

---

### 1. **Percepción uniforme del color.**

OKLCH está diseñado para que los cambios numéricos en sus componentes (luminosidad, cromaticidad y tono) correspondan de manera más uniforme a cómo los humanos percibimos los colores. Esto significa que, por ejemplo, aumentar la cromaticidad en 10 unidades tendrá un impacto visual similar en cualquier tono, algo que no ocurre en HSL o HSV.

---

### 2. **Separación clara de atributos.**

- **L (Luminosidad):** Controla qué tan claro u oscuro es un color, de forma perceptualmente uniforme.
- **C (Cromaticidad):** Controla la intensidad o saturación del color, también de forma uniforme.
- **H (Tono):** Define el matiz (rojo, azul, verde, etc.) en una escala de 0 a 360 grados.

Esta separación facilita la manipulación precisa de los colores sin efectos secundarios no deseados.

---

### 3. **Mejor manejo de la accesibilidad.**

OKLCH permite ajustar la luminosidad y el contraste de manera más intuitiva y efectiva, lo que facilita la creación de paletas accesibles. Por ejemplo, es más fácil garantizar que un texto sea legible sobre un fondo si trabajas con valores de luminosidad en OKLCH.

---

### 4. **Compatibilidad con CSS moderno.**

OKLCH ya está soportado en CSS mediante la función `oklch()`, lo que permite usarlo directamente en estilos web sin necesidad de conversiones manuales. Ejemplo:

```css```
.element {
  color: oklch(70% 0.2 120);
}
```

### 5. **Facilidad para crear paletas armoniosas.**

Gracias a su estructura, es más sencillo generar paletas de colores armoniosas y variaciones de un mismo tono, ya que los cambios en cromaticidad y luminosidad son predecibles y consistentes.

---

### 6. **Menos dependencia del dispositivo.**

OKLCH está basado en el espacio de color OKLab, que a su vez se basa en la percepción humana, lo que reduce las variaciones de color entre diferentes pantallas y dispositivos.

---

> ### **¿Cuándo usar OKLCH?.**
> 
> - Cuando necesitas precisión en la manipulación de colores.
> - Para proyectos que requieren alta accesibilidad.
> - Si trabajas con CSS moderno y quieres aprovechar sus ventajas perceptivas.
> - Para crear sistemas de diseño consistentes y escalables.
