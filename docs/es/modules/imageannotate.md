# Anotar imagen El módulo [Anotar imagen](https://omeka.org/s/modules/ImageAnnotate/){target=_blank} permite a los usuarios del sitio adjuntar información a las coordenadas de los archivos de imagen, incluidos [activos de instalación](../admin/assets.md) y [medios adjuntos a elementos](../content/media.md). 

Este módulo añade una nueva pestaña "Anotar imagen" a la interfaz de edición de medios en la parte de administración, en la que se puede dibujar sobre la imagen seleccionada. Los usuarios pueden dibujar rectángulos y añadir leyendas de texto específicas para cada zona. También añade nuevos [bloques de recursos](../sites/site_theme.md#configure-resource-pages) para que las anotaciones puedan verse en las páginas de visualización de elementos y medios, y nuevos [bloques de página](../sites/site_pages.md#page-blocks) para que las anotaciones puedan añadirse y mostrarse en las páginas del sitio. 

![](modulesfiles/imageAnnotate_publicPage.png) Para los medios que generan miniaturas de imágenes (como los PDF, que obtienen una miniatura de la primera página), puedes anotar la miniatura a tamaño completo que crea Omeka S. Ten en cuenta que, aunque puedes anotar cosas como miniaturas de vídeo, tus anotaciones sólo se verán en determinados contextos en los que no se muestre el medio original. 

Dependiendo de su propósito, puede anotar los propios archivos multimedia como adjuntos a los elementos, haciendo que las anotaciones estén disponibles en toda la instalación, o anotar los medios sólo en el contexto de una página específica del sitio. Considere si desea que la anotación esté disponible para todos (por ejemplo, identificar a todas las personas de una fotografía) o limitada al contexto de una exposición o ensayo (por ejemplo, señalar a una persona en particular). Si lo desea, puede combinar anotaciones de medios con anotaciones específicas de páginas. Si sólo desea anotar imágenes en el curso de la construcción de exposiciones, puede pasar a la [sección sobre bloques de páginas](#bloques-de-páginas). 

### Permisos Los usuarios de nivel Autor y superior pueden anotar imágenes. Los autores sólo pueden anotar los medios que les pertenecen; los usuarios de nivel Revisor o superior pueden anotar cualquier medio de la instalación. 

Los bloques de página pueden ser añadidos por cualquiera que tenga permiso para editar una página. 

## Una vez instalado el módulo, no existen opciones de configuración para toda la instalación. 

Puede encontrar la pestaña "Anotar imagen" navegando a un medio específico, ya sea a través del medio adjunto de un elemento, o desde la tabla de medios. 

![](modulesfiles/imageAnnotate_mediaEdit.png) Puede anotar imágenes con selecciones rectangulares, que pueden ser tan grandes o pequeñas como desee. Cuando se crea un rectángulo, introduzca un pie de foto. Es necesario introducir un título para guardar la anotación. Asegúrese de guardar la anotación en la imagen y, a continuación, guarde la página. ![](modulesfiles/imageAnnotate_mediaEdit2.png) Una vez guardadas las anotaciones, la pestaña "Anotaciones de imagen" aparece en modo de visualización y se puede interactuar con las anotaciones como si se tratara de una página pública. 

![](modulesfiles/imageAnnotate_mediaSaved.png) Si desea modificar las anotaciones existentes, puede volver a editar el soporte y editar o eliminar las anotaciones que se hayan guardado. Puede eliminar anotaciones individuales con el icono rojo de la papelera, o hacer clic en el botón "Restablecer anotaciones" para eliminar todas las anotaciones. 

![](modulesfiles/imageAnnotate_mediaReset.png) ## Publicar anotaciones Las anotaciones aparecen en los sitios a través de bloques de páginas de recursos, y bloques de páginas en los sitios. No aparecen en ningún sitio por defecto; tendrá que modificar cada sitio en el que desee que aparezcan las anotaciones. 

### Bloques de página de recursos Para mostrar las anotaciones de imagen en las páginas de vista de elementos y vista multimedia, debe añadir los bloques de página de recursos.  

En la [página del tema del sitio](../sites/site_theme.md), haga clic en el botón ["Configurar páginas de recursos"](../sites/site_theme.md#configure-resource-pages). 

En la pestaña "Item page", verá un nuevo bloque llamado "Media embeds (with image annotations)". Si sustituye el bloque normal "Media embeds" por este bloque, las anotaciones de imagen se mostrarán cuando estén disponibles; de lo contrario, los medios aparecerán en las páginas de vista de elementos de forma normal. 

En la pestaña "Página multimedia", verás un nuevo bloque llamado "Renderizado multimedia (con anotaciones de imagen)". Si sustituye el bloque normal "Renderizado de medios" por este bloque, las anotaciones de imagen se mostrarán donde estén disponibles; de lo contrario, los medios aparecerán en las páginas de vista de medios de forma normal. 

(modulesfiles/imageAnnotate_resourceMedia.png) Cuando las anotaciones de imagen estén disponibles, aparecerá un botón en el elemento público y en las páginas de vista multimedia con el texto "Ver anotaciones". Este botón aparecerá debajo de cada imagen que tenga anotaciones. Al pulsarlo, aparecerán las anotaciones (están ocultas por defecto) y el botón cambiará a "Ver sin anotaciones". 

(modulesfiles/imageAnnotate_publicResource.png) Tenga en cuenta que si suele utilizar la galería Lightbox para mostrar sus medios en las páginas de visualización de artículos y medios, no podrá modificarla para incluir anotaciones en las imágenes. Si desea mostrar anotaciones, debe utilizar los formatos Media embed o Media render. 

En el caso de los vídeos y los PDF, el botón "Ver anotaciones" aparecerá junto a la representación multimedia habitual y, al hacer clic en él, el contenido multimedia se sustituirá por su miniatura anotada. Módulos como PDF Embed pueden determinar si se muestra un marco multimedia o su miniatura en lugares como la página de visualización de elementos o multimedia. 

### Bloques de página Este módulo añade dos bloques de página: "Image annotate asset" e "Image annotate media". 

Al mostrar una imagen de activo con anotaciones, tendrá la opción de añadir un pie de texto a la imagen. (modulesfiles/imageAnnotate_asset.png) Al mostrar una imagen multimedia con anotaciones, puede añadir un pie de foto en el mismo estilo que un bloque de página de incrustación multimedia, así como elegir mostrar el título del elemento o el título multimedia como un enlace en el que se puede hacer clic debajo de la imagen. 

(modulesfiles/imageAnnotate_pageBlock.png) Puedes añadir anotaciones específicas de la página al medio en las opciones del bloque de página, y elegir mostrar o no las anotaciones guardadas en el propio medio. Si muestra las anotaciones propias del medio y dibuja también anotaciones específicas de la página, la página pública mostrará ambos conjuntos de cuadros. 

(modulesfiles/imageAnnotate_publicPage2.png) Tenga en cuenta que cuando elija un medio en el que sólo las miniaturas sean imágenes, como un vídeo o un PDF, la miniatura a tamaño completo se mostrará en la página con sus anotaciones. Los usuarios no podrán ver el vídeo o PDF completo en la página. Una vez guardada la página con anotaciones específicas del bloque, éste incluirá un botón "Restablecer anotaciones" que borrará todas las anotaciones específicas del bloque (pero no las anotaciones guardadas en el propio medio).  
