# Bloque de carrusel de elementos

El [módulo Bloque de carrusel de elementos](https://omeka.org/s/modules/ItemCarouselBlock){target=_blank} te permite añadir un bloque de presentación de diapositivas a las [páginas del sitio](../sites/site_pages.md#page-blocks).

Una vez activado, el bloque de carrusel de elementos añade un bloque de página «Carrusel de elementos» a la lista disponible en la interfaz de edición de la página.

![Una presentación de diapositivas básica en una página pública.](modulesfiles/itemcarouselblock-public.png)

## Adjuntar elementos

Al editar una página, añade un bloque de página «Item Carousel» que se encuentra en la lista de la derecha. Haz clic en el botón «Añadir archivo adjunto» para añadir una selección de elementos al bloque. Esto abrirá una barra lateral en la parte derecha de la página para explorar y seleccionar elementos.

Una vez que haya seleccionado los elementos que desea adjuntar, puede hacer clic en la llave de configuración para seleccionar cada miniatura multimedia que se mostrará y añadir un pie de foto para cada elemento. Los archivos adjuntos se pueden reordenar arrastrando y soltando.

![La interfaz de edición de la página, con «Carrusel de elementos» apareciendo en el menú de bloques de la derecha y un bloque «Carrusel de elementos» en blanco en la página.](modulesfiles/itemcarouselblock.png)

## Configuración básica
El bloque incluye dos ajustes de configuración básicos:

![Un bloque de carrusel de elementos con elementos adjuntos y ajustes de configuración.](modulesfiles/itemcarouselblock-basicconfiguration.png)

Añade un título para el carrusel y selecciona el número de elementos que aparecerán en la página a la vez. El bloque debe mostrar al menos 1 elemento y puede mostrar un máximo de 10 elementos. Al elegir un elemento, seleccionas un medio específico de ese elemento. También puedes introducir aquí un texto de pie de foto.

## Opciones avanzadas
Mediante el menú desplegable del bloque, puede acceder a varias opciones avanzadas para configurar aún más la apariencia del bloque.

![Un bloque de página de carrusel de elementos con las opciones avanzadas desplegadas, tal y como se muestra a continuación.](modulesfiles/itemcarouselblock-advanced.png)

Puede utilizar esos ajustes para:

- Seleccionar el tipo de miniatura para el archivo adjunto. Las opciones son [grande, mediana o cuadrada](../configuration.md#thumbnails).
- Decidir qué título del archivo adjunto mostrar. Las opciones de configuración incluyen título del elemento, título del medio o sin título.
- Decidir si mostrar o no un pie de foto del archivo adjunto, tal y como se ha configurado en los archivos adjuntos.
	- Si has seleccionado mostrar el título y/o el pie de foto, puedes decidir si superponer o no el título/pie de foto sobre la imagen adjunta. Visualiza y actualiza la página pública para ver cómo queda. Ten en cuenta que seleccionar esta opción puede requerir algunos ajustes en el CSS de tu tema.
- Establece la alineación del título o pie de foto. Las opciones de configuración son izquierda, derecha y centro.
- Decide si quieres estirar la imagen del elemento adjunto para que ocupe todo el espacio de la diapositiva. Las opciones incluyen Ninguna, Rellenar ancho, Rellenar alto y Rellenar toda la diapositiva.
- Establece un ancho de «punto de ruptura» para el carrusel. Por encima de este número de píxeles de ancho, aparecerá el número de elementos que hayas elegido por diapositiva; por debajo, solo se mostrará un elemento a la vez. Esto es para la compatibilidad con dispositivos móviles, pero puede depender del número de elementos que estés mostrando y del tamaño de las miniaturas que hayas elegido. Si tiene un elemento por diapositiva, ignore esta configuración. Puede dejarlo en blanco. 
- Establezca el tiempo que la diapositiva del carrusel permanece en pausa antes de avanzar automáticamente al siguiente elemento. La duración se expresa en milisegundos (por lo tanto, un valor de «1000» cambiaría de diapositiva una vez por segundo). **Establece la duración en 0 para desactivar el avance automático**.
- Establece si las diapositivas deben avanzar en un bucle infinito, de modo que, una vez que el carrusel haya recorrido todos los elementos adjuntos, el ciclo comience de nuevo.
- Decide si quieres implementar un fundido entre las diapositivas adjuntas que se suceden. Nota: Esta opción solo funciona cuando has configurado tu carrusel para mostrar 1 elemento por página (y no cuando se activa el punto de ruptura).

## Vistas públicas

En tu página pública, el carrusel tendrá automáticamente la altura del elemento más alto, incluyendo el título y el texto de la leyenda, dependiendo de la configuración avanzada anterior. Tendrá el ancho que permita el bloque de la página según tu [diseño y configuración de la página](../sites/site_pages.md).

!!! nota
  Es posible que tu carrusel tenga un aspecto y un comportamiento diferentes en dispositivos móviles y más pequeños que en la pantalla de un ordenador. Asegúrate de ver tu página pública en diferentes configuraciones para garantizar que los visitantes del sitio puedan acceder a los elementos. 

Un carrusel visto en el navegador de un ordenador portátil:

![](modulesfiles/itemcarouselblock-desktop.png)

Y el mismo carrusel en un dispositivo móvil: ten en cuenta que la configuración del punto de ruptura ha reducido los elementos visibles a 1:

![](modulesfiles/itemcarouselblock-mobile.png)


