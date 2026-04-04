### 💡 idea conceptual

Tradicionalmente, los *custom checkboxes* o *switches* se hacen con `position: absolute;` para mover el “slider” sobre un track. Pero si planteas usar **Flexbox** con `justify-content: flex-start` / `flex-end`, puedes lograr el mismo efecto **sin posiciones absolutas**, siempre que estructures bien el HTML y los estados del input.

> El inconvenientente es que no es animable, por lo que la transición del slider al utilizar flex no surge efecto.
> 
> Una técnica conocida es utilizar el gap. Pero es más difícil de controlar y depende del layout.
> 
> Aun así, aunque pierdo animación suave, **gano layout adaptable y perfecto con el escalado de la pantalla**.

---

### 🧠 Explicación

- El `label` actúa como contenedor flexible.

- El `span.slider` es el "botón" que se mueve dentro.

- En lugar de trasladar el slider con `transform` o `left`, **cambiamos la alineación de flexbox** (`flex-start` → `flex-end`).

- El selector `:has(input:checked)` nos permite que el contenedor reaccione al estado del `input`.

---

### ✅ Ventajas

- Sin `position: absolute;`

- Estructura más simple y semántica.

- Transiciones suaves y naturales.

- Compatible con temas oscuros / claros fácilmente.

---

### ⚠️ Consideraciones

- `:has()` todavía no está soportado en todos los navegadores antiguos (pero sí en los modernos: Chrome, Edge, Safari, Firefox 121+).

- Si necesitas compatibilidad amplia, tendrías que recurrir a un enfoque híbrido o JS.

---

### 🧩 ¿Qué es un *wrapper de estado*?

En este contexto, un **wrapper de estado** es simplemente un **elemento contenedor** que refleja el estado del checkbox (si está marcado o no).  

Como `:has()` aún no es completamente universal, podemos usar un **div contenedor** que reaccione al `checked` del input con un poco de CSS o una clase de apoyo (por ejemplo, usando el selector `input:checked + ...`).

La idea es:

- El `input` cambia de estado (`checked`).

- Un elemento “wrapper” (el padre o un hermano) cambia su estilo en respuesta.

- Luego, dentro de ese wrapper, usamos `flexbox` para mover el slider (`flex-start` o `flex-end`).

--- 

### ⚙️ Cómo funciona

1. El `label.switch` engloba todo.

2. El `input` está antes de `.state`, por lo que puedes usar `input:checked + .state` para aplicar estilos al contenedor de estado.

3. `.state` usa `flexbox` y cambia su `justify-content` entre `flex-start` y `flex-end` según si el checkbox está marcado.

---

### ⚙️ En resumen

| Propiedad            | ¿Animable? | Alternativa recomendada          |
| -------------------- | ---------- | -------------------------------- |
| `justify-content`    | ❌ No       | ✅ Usa `transform: translateX()`  |
| `align-items`        | ❌ No       | —                                |
| `gap`                | ✅ Sí       | Efectos sutiles de separación    |
| `padding` / `margin` | ✅ Sí       | Pequeños desplazamientos fluidos |