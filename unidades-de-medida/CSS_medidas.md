# 

Unidades de medida en CSS

- Absolutas: estas medidas no cambian de tamaño, siempre son iguales independientemente del tamaño de pantalla.
- Relativas: Se adaptan según el tamaño de la pantalla, son las medidas más recomendadas de usar.

### *Medidas Relativas*

| Unidad                                                              | Relativa a                                                                      |
| ------------------------------------------------------------------- | ------------------------------------------------------------------------------- |
| em                                                                  | Esta propiedad depende el font-size del elemento padre.                         |
| rem                                                                 | Esta propiedad depende el font-size del elemento raíz (seria la etiqueta html). |
| vh                                                                  | Altura de la ventana del navegador.                                             |
| vw                                                                  | Ancho de la ventana del navegador.                                              |
| %                                                                   | Tamaño relativo al elemento padre                                               |
| *Las medidas relativas más usadas son los rems, ems y porcentajes.* |                                                                                 |

### *Medidas Absolutas*

| Unidad | Nombre      | Medida(px)             | Uso actual         |
| ------ | ----------- | ---------------------- | ------------------ |
| cm     | Centímetros | 96px/2.54 = 37.79px    | Apenas no es usado |
| mm     | Milímetros  | 1cm(~37.8)/10 = 3.77px | Apenas no es usado |
| in     | Pulgadas    | 96px                   | Apenas no es usado |
| pt     | Puntos      | 1.33px                 | Apenas no es usado |
| pc     | Picas       | 16px                   | Apenas no es usado |
| px     | Píxeles     | 1px                    | Muy usado          |

## Imágenes

### *object-fit*

*Establece como se ajusta una imagen dentro de un contenedor.*

El valor por defecto es fill.

- fill: Esta es la configuración predeterminada. La imagen se redimensiona para ajustarse a la dimensión especificada. Si es necesario, se estira o se comprime para ajustarla.
- contain: La imagen mantiene su relación de aspecto, pero se redimensiona para ajustarse a la dimensión dada.
- cover: La imagen mantiene su relación de aspecto y ocupa la dimensión indicada. La imagen se recortará para ajustarse.
- none: La imagen no se redimensiona
- scale-down: la imagen se reduce a la versión más pequeña de `none` o `contain`

| Propiedad  | Valores                                        |
| ---------- | ---------------------------------------------- |
| object-fit | fill \| contain \| cover \| none \| scale-down |

[Ejemplo de uso w3schools](https://www.w3schools.com/cssref/playdemo.php?filename=playcss_object-fit)

### object-position

*Establece la posición de una imagen dentro de un contenedor.*

*El valor por defecto es 50% 50%*

| Propiedad       | Valores      |
| --------------- | ------------ |
| object-position | <left> <top> |

[Ejemplo de uso w3schools](https://www.w3schools.com/cssref/playdemo.php?filename=playcss_object-position)
