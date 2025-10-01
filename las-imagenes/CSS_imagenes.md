# Imágenes.

**img**, el elemento inline.

### *object-fit*

*Establece como se ajusta una imagen dentro de un contenedor.*

> *El valor por defecto es fill.*

- fill: Esta es la configuración predeterminada. La imagen se redimensiona para ajustarse a la dimensión especificada. Si es necesario, se estira o se comprime para ajustarla.
- contain: La imagen mantiene su relación de aspecto, pero se redimensiona para ajustarse a la dimensión dada.
- cover: La imagen mantiene su relación de aspecto y ocupa la dimensión indicada. La imagen se recortará para ajustarse.
- none: La imagen no se redimensiona.
- scale-down: la imagen se reduce a la versión más pequeña de `none` o `contain`.

| Propiedad  | Valores                                                  |
| ---------- | -------------------------------------------------------- |
| object-fit | fill (default) \| contain \| cover \| none \| scale-down |

[Ejemplo de uso w3schools](https://www.w3schools.com/cssref/playdemo.php?filename=playcss_object-fit)

### object-position

*Establece la posición de una imagen dentro de un contenedor.*

> *El valor por defecto es 50% 50%*

```
#myDIV {
  height:300px;
  padding:20px;
  background-color:#FFFFFF;
}
img{
  object-fit: none;
  object-position: 60% 60%;
}
<div id="myDIV">
    <img src="pineapple.jpg" alt="Pineapple" width="100" height="300">
</div>
```

[Ejemplo de uso w3schools](https://www.w3schools.com/cssref/playdemo.php?filename=playcss_object-position)
