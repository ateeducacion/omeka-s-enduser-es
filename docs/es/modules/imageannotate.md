# Anotación de imágenes

El [módulo «Anotación de imágenes»](https://omeka.org/s/modules/ImageAnnotate/){target=_blank} permite a los usuarios del sitio adjuntar información a coordenadas en archivos de imagen, incluidos [los recursos de instalación](../admin/assets.md) y [los archivos multimedia adjuntos a los elementos](../content/media.md). 

Este módulo añade una nueva pestaña «Anotar imagen» a la interfaz de edición de archivos multimedia en el panel de administración, donde se puede dibujar sobre la imagen seleccionada. Los usuarios pueden dibujar rectángulos y añadir leyendas de texto específicas para cada área. También añade nuevos [bloques de recursos](../sites/site_theme.md#configure-resource-pages) para que las anotaciones se puedan ver en las páginas de visualización de elementos y archivos multimedia, así como nuevos [bloques de página](../sites/site_pages.md#page-blocks) para que las anotaciones se puedan añadir y mostrar en las páginas del sitio. 

![Una página pública que muestra una imagen con una anotación. La imagen tiene dos selecciones rectangulares alrededor de las personas que aparecen en la fotografía; una es un rectángulo amarillo que indica que está activa, y una ventana emergente muestra el texto «Piloto James Ray» y un botón que dice «Cerrar».](modulesfiles/imageAnnotate_publicPage.png)

En el caso de los archivos multimedia que generan miniaturas de imagen (como los PDF, que obtienen una miniatura de la primera página), puedes añadir anotaciones a la miniatura a tamaño completo que crea Omeka S. Ten en cuenta que, aunque puedes añadir anotaciones a elementos como las miniaturas de vídeo, estas solo se verán en determinados contextos en los que no se muestre el archivo multimedia original. 

Dependiendo de tu objetivo, puedes añadir anotaciones a los propios archivos multimedia adjuntos a los elementos, de modo que las anotaciones estén disponibles en toda la instalación, o bien añadir anotaciones a los archivos multimedia únicamente en el contexto de una página específica del sitio. Valora si deseas que la anotación esté ampliamente disponible (por ejemplo, para identificar a todas las personas de una fotografía) o si prefieres limitarla al contexto de una exposición o un ensayo (por ejemplo, para señalar a una persona concreta de interés). Si lo deseas, puedes combinar las anotaciones multimedia con las anotaciones específicas de cada página.

Si solo deseas añadir anotaciones a las imágenes mientras creas exposiciones, puedes pasar directamente a la [sección sobre bloques de página](#page-blocks). 

### Permisos

Los usuarios con el nivel de «Autor» o superior pueden anotar imágenes. Los autores solo pueden anotar los archivos multimedia de su propiedad; los usuarios con el nivel de «Revisor» o superior pueden anotar cualquier archivo multimedia de la instalación. 

Cualquier persona con permiso para editar una página puede añadir bloques de página. 

## Anotar archivos multimedia

Una vez instalado el módulo, no hay opciones de configuración para toda la instalación. 

Puedes encontrar la pestaña «Anotar imagen» accediendo a un archivo multimedia específico, ya sea a través de los archivos adjuntos de un elemento o desde la tabla de archivos multimedia. 

![La página de administración de un elemento multimedia, en la pestaña «Anotar imagen», sin ninguna anotación aún en la imagen.](modulesfiles/imageAnnotate_mediaEdit.png)

Puedes anotar imágenes con selecciones rectangulares, que pueden ser tan grandes o pequeñas como desees. Cuando se crea un rectángulo, introduce un texto de anotación. Es obligatorio introducir un texto de anotación para guardar la anotación. Asegúrate de guardar la anotación en la imagen y, a continuación, guarda la página.

![La misma página, con dos rectángulos definidos. A uno se le ha añadido texto como anotación: «Senador Hiram Bingham». Hay un botón «Cancelar» y un botón «Aceptar» para guardar la anotación.](modulesfiles/imageAnnotate_mediaEdit2.png)

Una vez guardadas las anotaciones, aparece la pestaña «Anotaciones de imagen» en el modo de visualización y se puede interactuar con las anotaciones como si se tratara de una página pública. 

![La misma página, guardada (no en modo de edición), con un banner verde que dice «Archivo multimedia actualizado correctamente» y los dos rectángulos visibles en la imagen.](modulesfiles/imageAnnotate_mediaSaved.png)

Si deseas modificar las anotaciones existentes, puedes volver a editar el contenido multimedia y modificar o eliminar las anotaciones que se han guardado. Puedes eliminar anotaciones individuales con el icono rojo de la papelera, o hacer clic en el botón «Restablecer anotaciones» para eliminar todas las anotaciones. 

![La misma página y pestaña, en modo de edición, con un rectángulo resaltado en amarillo y su anotación visible. En la ventana emergente de la anotación aparece ahora un icono de papelera roja. El cursor se encuentra sobre el botón, mostrando la información sobre herramientas «Eliminar». También aparece un botón «Restablecer anotaciones» debajo de la imagen.](modulesfiles/imageAnnotate_mediaReset.png)

## Publicar anotaciones

Las anotaciones aparecen en los sitios a través de bloques de página de recursos y bloques de página en los sitios. Por defecto, no aparecen en ningún sitio; tendrás que modificar cada sitio en el que desees que aparezcan las anotaciones. 

### Bloques de página de recursos

Para mostrar las anotaciones de imágenes en las páginas de vista de elemento y de vista de medios, debes añadir los bloques de página de recursos.  

En la [página del tema del sitio](../sites/site_theme.md), haz clic en el [botón «Configurar páginas de recursos»](../sites/site_theme.md#configure-resource-pages). 

En la pestaña «Página de elemento», verás un nuevo bloque llamado «Incrustaciones multimedia (con anotaciones de imagen)». Si sustituyes el bloque normal «Incrustaciones multimedia» por este bloque, las anotaciones de imagen se mostrarán cuando estén disponibles; de lo contrario, los archivos multimedia aparecerán en las páginas de vista de elemento como de costumbre. 

En la pestaña «Página de medios», verás un nuevo bloque llamado «Representación de medios (con anotaciones de imagen)». Si sustituyes el bloque normal «Representación de medios» por este bloque, se mostrarán las anotaciones de imagen cuando estén disponibles; de lo contrario, los medios aparecerán en las páginas de visualización de medios como de costumbre. 

![Configuración de la página de recursos multimedia, donde «Representación de medios (con anotaciones en imágenes)» aparece como un bloque encima de «Representación de medios» y «Galería Lightbox», que aparecen en rojo ya que se están eliminando de la página.](modulesfiles/imageAnnotate_resourceMedia.png)

Cuando haya anotaciones de imagen disponibles, aparecerá un botón en las páginas de visualización de elementos públicos y de recursos multimedia con el texto «Ver anotaciones». Este botón aparecerá debajo de cada imagen que tenga anotaciones. Al hacer clic en él, aparecerán las anotaciones (que están ocultas por defecto) y el botón cambiará a «Ver sin anotaciones». 

![El recurso multimedia con sus anotaciones, mostrado en la página de visualización del elemento. Debajo de la imagen hay un botón negro que dice «Ver sin anotaciones».](modulesfiles/imageAnnotate_publicResource.png)

Ten en cuenta que, si sueles utilizar la galería Lightbox para mostrar tus archivos multimedia en las páginas de visualización de elementos y de archivos multimedia, esta no se puede modificar para incluir anotaciones en las imágenes. Si deseas mostrar anotaciones, debes utilizar los formatos «Incrustar multimedia» o «Reproducir multimedia». 

En el caso de los vídeos y los PDF, el botón «Ver anotaciones» aparecerá junto a la representación multimedia habitual y, al hacer clic en él, el contenido multimedia se sustituirá por su miniatura con anotaciones. Módulos como «PDF Embed» pueden determinar si se muestra el fotograma del contenido multimedia o su miniatura en lugares como la página de visualización del elemento o del contenido multimedia. 

### Bloques de página

Este módulo añade dos bloques de página: «Anotar imagen de recurso» y «Anotar imagen de contenido multimedia». 

Al mostrar una imagen de recurso con anotaciones, tendrás la opción de añadir un pie de foto a la imagen.

![El bloque de página «Anotar imagen de activo», configurado con una imagen, con texto en el pie de foto y mostrando un espacio para anotaciones con rectángulos dibujados sobre la imagen.](modulesfiles/imageAnnotate_asset.png)

Al mostrar una imagen multimedia con anotaciones, puedes añadir un pie de foto con el mismo estilo que el bloque de página «Incrustar multimedia», así como elegir mostrar el título del elemento o el título del archivo multimedia como un enlace en el que se puede hacer clic debajo de la imagen. 

![El bloque de página «Anotar imagen» con los ajustes que se muestran a continuación.](modulesfiles/imageAnnotate_pageBlock.png)

Puedes añadir anotaciones específicas de la página al contenido multimedia en las opciones del bloque de página, y elegir si mostrar o no las anotaciones guardadas en el propio contenido multimedia. Si muestras las anotaciones propias del contenido multimedia y, además, dibujas anotaciones específicas de la página, la página pública mostrará ambos conjuntos de recuadros. 

![El recurso con sus anotaciones —tanto las dos configuradas en el propio recurso como las configuradas en el bloque de página— mostradas en una página con el título del elemento y un pie de foto.](modulesfiles/imageAnnotate_publicPage2.png)

Ten en cuenta que, cuando elijas un archivo multimedia en el que solo las miniaturas sean imágenes, como un vídeo o un PDF, la miniatura a tamaño completo se mostrará en la página junto con sus anotaciones. Los usuarios no podrán ver el vídeo completo ni el PDF en la página.

Una vez guardada la página con las anotaciones específicas del bloque, este incluirá un botón «Restablecer anotaciones» que borrará todas las anotaciones específicas del bloque (pero no las anotaciones guardadas en el propio archivo multimedia).  
