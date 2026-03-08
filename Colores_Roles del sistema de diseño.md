# Colores.

## Roles de sistema de diseño.

En CSS moderno se acostumbra a **definir variables de color en un solo lugar** (generalmente en `:root`), y luego reutilizarlas en todas las propiedades que las necesiten. Esto mejora:

- Consistencia.

- Mantenibilidad.

- Legibilidad.

### Roles de color en un diseño web

#### 1. **Primary (Color primario)**

- Es el color principal de tu marca o identidad visual.

- Se usa para lo más importante: botones principales, enlaces destacados, iconos clave, encabezados de alto nivel.

- Debe transmitir la personalidad de la marca (ej. azul → confianza, verde → naturaleza, rojo → energía).

#### 2. **Secondary (Color secundario)**

- Complementa al primario.

- Se usa para diferenciar acciones secundarias, elementos de soporte o alternar en diseños muy grandes (secciones, tarjetas, gráficos).

- Ayuda a evitar que todo sea “monocromo” con el primario.

#### 3. **Accent (Color de acento)**

- Es el “toque especial”.

- Se usa en pequeñas dosis para atraer la atención: íconos, notificaciones, indicadores de estado, hover en botones, enlaces resaltados.

- Normalmente es un color vibrante o contrastante.

#### 4. **Neutral / Base (Grises, fondos, texto)**

- Colores que sirven de soporte:
  
  - Fondo claro/oscuro.
  
  - Texto primario (#000, #fff o gris oscuro).
  
  - Bordes, sombras, separadores.

- Son la base que hace que los primarios y acentos destaquen.

#### 5. **Success / Warning / Error / Info (Feedback)**

- Colores semánticos que transmiten estado:
  
  - **Success** → verde (acción correcta, completado).
  
  - **Warning** → amarillo/naranja (advertencia).
  
  - **Error** → rojo (fallo, peligro).
  
  - **Info** → azul (información).

### Dar nombres semánticos cuando sea posible.

--color-bg
--color-bg-alt
--color-text
--color-border
--color-text-muted
--color-accent
--color-primary

### Clave para elegirlos

1. **Empieza con tu branding** → tu primario debe ser tu color corporativo.

2. **Busca contraste suficiente** → revisa que texto y fondos tengan buena legibilidad (usa WCAG contrast checker).

3. **Usa la rueda de color** → el secundario suele ser un color complementario o análogo al primario.

4. **Limita la paleta** → 1 primario, 1 secundario, 1 acento, + neutros y semánticos suelen bastar.

5. **Piensa en jerarquía** → el primario guía al usuario, el acento llama la atención, los neutros permiten respirar.
