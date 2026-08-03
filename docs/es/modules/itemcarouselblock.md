# Bloque de carrusel de elementos

El [módulo «Bloque de carrusel de elementos»](https://omeka.org/s/modules/ItemCarouselBlock){target=_blank} te permite añadir un bloque de presentación de diapositivas a las [páginas del sitio](../sites/site_pages.md#page-blocks).

Una vez activado, el bloque «Carrusel de elementos» añade un bloque de página denominado «Carrusel de elementos» a la lista disponible en la interfaz de edición de la página.

![Una presentación de diapositivas básica en una página pública.](modulesfiles/itemcarouselblock-public.png)

## Añadir elementos

Al editar una página, añade un bloque de página «Item Carousel» que encontrarás en la lista de la derecha. Haz clic en el botón «Añadir archivo adjunto» para añadir una selección de elementos al bloque. Esto abrirá una barra lateral a la derecha de la página para explorar y seleccionar elementos.

Una vez seleccionados los elementos que deseas adjuntar, puedes hacer clic en el icono de configuración (la llave inglesa) para seleccionar la miniatura de cada archivo multimedia que se mostrará y añadir un pie de foto para cada elemento. Los elementos adjuntos se pueden reordenar arrastrándolos y soltándolos.

![La interfaz de edición de la página, con «Carrusel de elementos» apareciendo en el menú de bloques de la derecha y un bloque «Carrusel de elementos» en blanco en la página.](modulesfiles/itemcarouselblock.png)

## Configuración básica
El bloque incluye dos ajustes de configuración básicos:

![Un bloque «Item Carousel» con elementos adjuntos y ajustes de configuración.](modulesfiles/itemcarouselblock-basicconfiguration.png)

Añade un título para el carrusel y selecciona el número de elementos que aparecerán en la página a la vez. El bloque debe mostrar al menos 1 elemento y puede mostrar un máximo de 10. Al elegir un elemento, seleccionas un archivo multimedia específico de ese elemento. También puedes introducir aquí un texto de pie de foto.

## Opciones avanzadas
Mediante el menú desplegable del bloque, puedes acceder a una serie de opciones avanzadas para configurar con mayor detalle el aspecto del bloque.

![Un bloque de página de carrusel de elementos con las opciones avanzadas desplegadas, tal y como se muestra a continuación.](modulesfiles/itemcarouselblock-advanced.png)

Puedes utilizar esos ajustes para:

- Seleccionar el tipo de miniatura para el archivo adjunto. Las opciones son [grande, mediana o cuadrada](../configuration.md#thumbnails).
- Decidir qué título del archivo adjunto mostrar. Las opciones de configuración incluyen «título del elemento», «título del archivo multimedia» o «sin título».
- Decidir si se muestra o no un pie de foto del archivo adjunto, tal y como se haya configurado en los archivos adjuntos.
	- Si has seleccionado mostrar el título y/o el pie de foto, puedes decidir si superponer o no el título/pie de foto sobre la imagen adjunta. Visualiza y actualiza la página pública para ver cómo queda. Ten en cuenta que seleccionar esta opción puede requerir realizar algunos ajustes en el CSS de tu tema.
- Establece la alineación del título o pie de foto. Las opciones de configuración son: izquierda, derecha y centrada.
- Decide si deseas estirar la imagen del elemento adjunto para que ocupe todo el espacio de la diapositiva. Las opciones son: Ninguna, Rellenar ancho, Rellenar altura y Rellenar toda la diapositiva.
- Establece un ancho de «punto de ruptura» para el carrusel. Por encima de este número de píxeles de ancho, aparecerá el número de elementos que hayas elegido por diapositiva; por debajo, solo se mostrará un elemento a la vez. Esto es para garantizar la compatibilidad con dispositivos móviles, pero puede depender del número de elementos que muestres y del tamaño de las miniaturas que hayas elegido. Si tienes un elemento por diapositiva, ignora este ajuste. Puedes dejarlo en blanco. 
- Establece el tiempo que la diapositiva del carrusel permanece en pausa antes de pasar automáticamente al siguiente elemento. La duración se expresa en milisegundos (por lo tanto, un valor de «1000» cambiaría de diapositiva una vez por segundo). **Establece la duración en 0 para desactivar el avance automático**.
- Establece si las diapositivas deben avanzar en un bucle infinito, de modo que, una vez que el carrusel haya recorrido todos los elementos adjuntos, el ciclo comience de nuevo.
- Decide si deseas aplicar un fundido entre las diapositivas adjuntas que se van sucediendo. Nota: Esta opción solo funciona cuando has configurado tu carrusel para mostrar 1 elemento por página (y no cuando se activa el punto de ruptura).

## Vistas públicas

En tu página pública, el carrusel tendrá automáticamente la misma altura que tu elemento más alto, incluyendo el título y el texto de la leyenda, dependiendo de la configuración avanzada anterior. Tendrá el ancho que permita el bloque de la página según tu [diseño y configuración de la página](../sites/site_pages.md).

!!! nota
  Es posible que tu carrusel tenga un aspecto y un comportamiento diferentes en dispositivos móviles y de menor tamaño que en la pantalla de un ordenador. Asegúrate de visualizar tu página pública en diferentes configuraciones para garantizar que los visitantes del sitio puedan acceder a los elementos. 

Un carrusel visualizado en el navegador de un portátil:

![](modulesfiles/itemcarouselblock-desktop.png)

Y el mismo carrusel en un dispositivo móvil: fíjate en que la configuración del punto de ruptura ha reducido los elementos visibles a 1:

![](modulesfiles/itemcarouselblock-mobile.png)


