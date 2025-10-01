# Basicos

*Es un módulo de CSS creado para diseñar layouts de una manera más sencilla, gracias a su flexibidad.*

- ### Propiedades.
  
  | Propiedad                                                            | Valor                                                                                            |
  | -------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------ |
  | `display`                                                            | flex                                                                                             |
  | `flex-direction`                                                     | row \| column \| row-reverse \| column-reverse                                                   |
  | `flex-wrap`                                                          | wrap \| wrap-reverse \| nowrap                                                                   |
  | `flex-flow`                                                          | <flex-direction> \| <wrap>                                                                       |
  | `justify-content` (main-axis)                                        | center \| space-evenly \| space-between \|space-around \| space-evenly \| flex-start \| flex-end |
  | `align-items` (cross-axis)                                           | center \| flex-start \| flex-end \| baseline \| stretch                                          |
  | `align-content` (cross-axis, solo si existe la propiedad wrap)       | center \| space-evenly \| space-between space-around \| space-evenly \| flex-start \| flex-end   |
  | `align-self` (cross-axis)                                            | auto \| flex-start \| flex-end \| center \| baseline \| stretch                                  |
  | `flex` (shorthand)                                                   | <flex-grow> \| <flex-shrink> \| <flex-basis>                                                     |
  | `flex-grow` - `flex-shrink` - `flex-basis`                           | <number> \| <length> \| auto                                                                     |
  | `order` El valor por defecto es 0 e indica el orden de los elementos | <integer>                                                                                        |
  
  
  
  | Propiedad       | Valor por defecto | Descripción                                                                  |
  | --------------- | ----------------- | ---------------------------------------------------------------------------- |
  | flex-direction  | row               | Los elementos se disponen en una fila horizontal.                            |
  | justify-content | flex-start        | Los elementos se alinean al inicio del eje principal (izquierda, si es row). |
  | align-items     | stretch           | Los elementos se estiran para ocupar todo el espacio del eje cruzado.        |
  | flex-wrap       | nowrap            | Los elementos no se envuelven a la siguiente línea si no caben.              |
  | align-content   | stretch           | Solo aplica si hay múltiples líneas (flex-wrap: wrap).                       |

- ## Declarando Flexbox.
  
  - Opera mediante contenedores(padre) e items(hijos).
  
  - En el contenedor se declara la pripoedad `display:flex`.
  
  - Por defecto, las propiedades se inicializan en `row` y siempre pordemos cambiar la orientación.

- ## Los ejes en Flexbox.
  
  - Al entrar al modo flexbox, se crean dos ejes principales: **Cross-axis** y **Main-axis**.
  
  - El cross axis se refiere a la orientación perpendicular al main axis. Por ejemplo, si el main axis es el eje X, el cross axis sería el eje Y.
  
  - El main axis se refiere a la orientación principal del contenedor. Por ejemplo, si el main axis es el eje X, el cross axis sería el eje Y.
    
    - ##### Flex-direction.
      
      - flex-row | flex-column | flex-row-reverse | flex-column-reverse
    
    - ##### Flex wrap.
      
      - El valor por defecto es `nowrap`, lo que significa que si los elementos sobrepasan el tamaño del flex container, los items se encogen.
      
      - El valor `wrap` creará una nueva línea cuando los elementos sobrepasen el tamaño del contenedor del main-axis. Dependiendo de la orientación.en fila o columna.
      
      - Define el comportamiento de los flex-items cuando su tamaño sumado rebasa el tamaño del main-axis.
        
        - Permite que los items se envuelvan en la orientación principal del contenedor.

- ## Alineamiento en Flexbox.
  
  - En Flexbox se puede repartir el espacio disponible tanto en el main como en el cross. Esto es el alineamiento.
  
  - Para aplicar el alineamiento debe haber espacio disponible en el eje que opere, de lo contrario no surte efecto.
    
    - ##### Alineación.
      
      - `justify-content` eje principal.
      
      - `align-items` eje secundario.
      
      - `align-content` eje secundario. Cuando hay `wrap` en el contenedor, es decir, cuando el contenedor tiene envoltorio.
    
    - 
