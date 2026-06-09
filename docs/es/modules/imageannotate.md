# Anotar imágenes

El [módulo «Anotar imágenes»](https://omeka.org/s/modules/ImageAnnotate/){target=_blank} permite a los usuarios del sitio adjuntar información a coordenadas en archivos de imagen, incluyendo [recursos de instalación](../admin/assets.md) y [archivos multimedia adjuntos a elementos](../content/media.md). 

Este módulo añade una nueva pestaña «Anotar imagen» a la interfaz de edición de archivos multimedia en el panel de administración, donde se puede dibujar sobre la imagen seleccionada. Los usuarios pueden dibujar rectángulos y añadir leyendas de texto específicas para cada área. También añade nuevos [bloques de recursos](../sites/site_theme.md#configure-resource-pages) para que las anotaciones se puedan ver en las páginas de visualización de elementos y medios, y nuevos [bloques de página](../sites/site_pages.md#page-blocks) para que las anotaciones se puedan añadir y mostrar en las páginas del sitio. 

![Una página pública que muestra una imagen con una anotación. La imagen tiene dos selecciones rectangulares alrededor de las personas que aparecen en la fotografía; una es un rectángulo amarillo que indica que está activa, y una ventana emergente muestra el texto «Piloto James Ray» y un botón que dice «Cerrar».](modulesfiles/imageAnnotate_publicPage.png)

En el caso de los archivos multimedia que generan miniaturas de imagen (como los PDF, que obtienen una miniatura de la primera página), puedes anotar la miniatura a tamaño completo que crea Omeka S. Ten en cuenta que, aunque puedes anotar elementos como miniaturas de vídeo, tus anotaciones solo se verán en determinados contextos en los que no se muestre el archivo multimedia original. 

Dependiendo de su propósito, puede anotar los propios archivos multimedia adjuntos a los elementos, haciendo que las anotaciones estén disponibles en toda la instalación, o anotar los medios solo en el contexto de una página específica del sitio. Considera si deseas que la anotación esté ampliamente disponible (como identificar a todas las personas de una fotografía) o limitada al contexto de una exposición o un ensayo (como señalar a una persona concreta de interés). Si lo deseas, puedes combinar las anotaciones multimedia con anotaciones específicas de la página.

Si solo desea anotar imágenes mientras crea exposiciones, puede pasar a la [sección sobre bloques de página](#page-blocks). 

### Permisos

Los usuarios con nivel de Autor o superior pueden anotar imágenes. Los Autores solo pueden anotar los archivos multimedia de su propiedad; los usuarios con nivel de Revisor o superior pueden anotar cualquier archivo multimedia de la instalación. 

Cualquier persona con permiso para editar una página puede añadir bloques de página. 

## Anotar archivos multimedia

Una vez instalado el módulo, no hay opciones de configuración para toda la instalación. 

Puede encontrar la pestaña «Anotar imagen» navegando hasta un archivo multimedia específico, ya sea a través de los archivos adjuntos de un elemento o desde la tabla de archivos multimedia. 

![La página de administración de un elemento multimedia, en la pestaña «Anotar imagen», sin ninguna anotación aún en la imagen.](modulesfiles/imageAnnotate_mediaEdit.png)

Puede anotar imágenes con selecciones rectangulares, que pueden ser tan grandes o pequeñas como desee. Cuando se crea un rectángulo, introduzca un pie de foto. Es necesario un pie de foto para guardar la anotación. Asegúrese de guardar la anotación en la imagen y, a continuación, guarde la página.

![La misma página, con dos rectángulos definidos. A uno se le ha añadido texto como anotación: «Senador Hiram Bingham». Hay un botón «Cancelar» y un botón «Aceptar» para guardar la anotación.](modulesfiles/imageAnnotate_mediaEdit2.png)

Una vez guardadas las anotaciones, aparece la pestaña «Anotaciones de imagen» en el modo de visualización y se puede interactuar con las anotaciones como si se tratara de una página pública. 

![La misma página, guardada (no en modo de edición), con un banner verde que dice «Medios actualizados correctamente» y los dos rectángulos visibles en la imagen.](modulesfiles/imageAnnotate_mediaSaved.png)

Si deseas modificar las anotaciones existentes, puedes volver a editar el archivo multimedia y editar o eliminar las anotaciones que se han guardado. Puedes eliminar anotaciones individuales con el icono rojo de la papelera, o hacer clic en el botón «Restablecer anotaciones» para eliminar todas las anotaciones. 

![La misma página y pestaña, en modo de edición, con un rectángulo resaltado en amarillo y su anotación visible. En la ventana emergente de la anotación hay ahora un icono de papelera roja. El cursor se encuentra sobre el botón que muestra la información sobre herramientas «Eliminar». También aparece un botón «Restablecer anotaciones» debajo de la imagen.](modulesfiles/imageAnnotate_mediaReset.png)

## Publicar anotaciones

Las anotaciones aparecen en los sitios a través de bloques de página de recursos y bloques de página en los sitios. Por defecto, no aparecen en ningún sitio; tendrás que modificar cada sitio en el que desees que aparezcan las anotaciones. 

### Bloques de página de recursos

Para mostrar anotaciones de imágenes en las páginas de vista de elemento y de vista de medios, debes añadir los bloques de página de recursos.  

En la [página del tema del sitio](../sites/site_theme.md), haz clic en el [botón «Configurar páginas de recursos»](../sites/site_theme.md#configure-resource-pages). 

En la pestaña «Página de elemento», verás un nuevo bloque llamado «Incrustaciones multimedia (con anotaciones de imagen)». Si sustituyes el bloque normal «Incrustaciones multimedia» por este bloque, las anotaciones de imagen se mostrarán cuando estén disponibles; de lo contrario, los medios aparecerán en las páginas de vista de elemento como de costumbre. 

En la pestaña «Página de medios», verás un nuevo bloque llamado «Representación de medios (con anotaciones de imagen)». Si sustituyes el bloque normal «Representación de medios» por este bloque, las anotaciones de imagen se mostrarán cuando estén disponibles; de lo contrario, los medios aparecerán en las páginas de vista de medios como de costumbre. 

![La configuración de la página de recursos multimedia, con «Representación de medios (con anotaciones de imagen)» apareciendo como un bloque encima de «Representación de medios» y «Galería Lightbox», que aparecen en rojo ya que se están eliminando de la página.](modulesfiles/imageAnnotate_resourceMedia.png)

Cuando haya anotaciones de imagen disponibles, aparecerá un botón en las páginas de visualización de elementos públicos y de medios con el texto «Ver anotaciones». Este botón aparecerá debajo de cada imagen que tenga anotaciones. Al hacer clic en él, aparecerán las anotaciones (que están ocultas por defecto) y el botón cambiará a «Ver sin anotaciones». 

![El recurso multimedia con sus anotaciones, mostrado en la página de visualización del elemento. Debajo de la imagen hay un botón negro que dice «Ver sin anotaciones».](modulesfiles/imageAnnotate_publicResource.png)

Ten en cuenta que si sueles utilizar la galería Lightbox para mostrar tus archivos multimedia en las páginas de visualización de elementos y de archivos multimedia, esto no se puede modificar para incluir anotaciones en las imágenes. Si deseas mostrar anotaciones, debes utilizar los formatos de incrustación o de visualización de archivos multimedia. 

En el caso de los vídeos y los PDF, el botón «Ver anotaciones» aparecerá junto a la representación multimedia habitual y, al hacer clic en él, el contenido multimedia se sustituirá por su miniatura anotada. Módulos como PDF Embed pueden determinar si se muestra un fotograma del contenido multimedia o su miniatura en lugares como la página de vista del elemento o del contenido multimedia. 

### Bloques de página

Este módulo añade dos bloques de página: «Anotar imagen de activo» y «Anotar imagen de medio». 

Al mostrar una imagen de activo con anotaciones, tendrá la opción de añadir un pie de foto a la imagen.

![El bloque de página «Anotar imagen de activo», configurado con una imagen, con texto en el pie de foto y mostrando un espacio para anotaciones con rectángulos dibujados sobre la imagen.](modulesfiles/imageAnnotate_asset.png)

Al mostrar una imagen multimedia con anotaciones, puede añadir un pie de foto con el mismo estilo que el bloque de página «Incrustar multimedia», así como elegir mostrar el título del elemento o el título del archivo multimedia como un enlace en el que se puede hacer clic debajo de la imagen. 

![El bloque de página «Anotar imagen» con los ajustes reflejados a continuación.](modulesfiles/imageAnnotate_pageBlock.png)

Puede añadir anotaciones específicas de la página al contenido multimedia en las opciones del bloque de página, y elegir si mostrar o no las anotaciones guardadas en el propio contenido multimedia. Si muestra las propias anotaciones del contenido multimedia y dibuja también anotaciones específicas de la página, la página pública mostrará ambos conjuntos de cuadros. 

![El recurso con sus anotaciones, tanto las dos establecidas en el recurso como las del bloque de página, mostradas en una página con el título del elemento y un pie de foto.](modulesfiles/imageAnnotate_publicPage2.png)

Ten en cuenta que cuando eliges un medio en el que solo las miniaturas son imágenes, como un vídeo o un PDF, la miniatura a tamaño completo se mostrará en la página con sus anotaciones. Los usuarios no podrán ver el vídeo completo ni el PDF en la página.

Una vez que la página se haya guardado con las anotaciones específicas del bloque, este incluirá un botón «Restablecer anotaciones» que borrará todas las anotaciones específicas del bloque (pero no las anotaciones guardadas en el propio archivo multimedia).  
