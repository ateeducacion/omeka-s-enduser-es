# Archivo web

El [módulo Archivo web](https://omeka.org/s/modules/WebArchive){target=_blank} permite importar y reproducir archivos de archivo web como contenido multimedia. Los archivos web son capturas de páginas web o de sitios web completos en un momento determinado. El módulo utiliza el [reproductor ReplayWeb.page](https://replayweb.page/){target=_blank} para reproducirlos en reproductores integrados dentro de las páginas públicas de Omeka S. 

![Página de visualización de un elemento con el título del mismo y un navegador virtual integrado que muestra una página de Wikipedia.org junto con la marca de tiempo de cuándo se archivó.](modulesfiles/webarchive_public.png)

## Requisitos del servidor

Este reproductor carga los archivos de archivo mediante solicitudes HTTP Range. Si tu servidor aplica `Content-Encoding` a un archivo de archivo web, la reproducción fallará.

Esto suele afectar sobre todo a los archivos `.warc` sin comprimir, ya que los archivos `.wacz` y `.warc.gz` ya están comprimidos y, por lo general, no se ven afectados. Cuando el módulo detecta esta situación, muestra un mensaje de error en lugar de un reproductor que no funciona. Consulta la [página de documentación para desarrolladores de este módulo](https://omeka.org/s/docs/developer/module_docs/WebArchive/){target=_blank} en GitHub para obtener más información técnica sobre cómo resolver este error si lo detectas. 

Los archivos de archivo web pueden llegar a ser bastante grandes, así que asegúrate de que la configuración de tu servidor permita archivos de gran tamaño (más de 20 MB).

## Configuración

Al instalar el módulo por primera vez, verás la pantalla de configuración. Se te pedirá que establezcas un «modo de incrustación predeterminado», que se aplicará a todos los archivos web incorporados a la instalación. Este ajuste se puede anular en cada incrustación individual. 

![La página de configuración del módulo con un menú desplegable disponible, ampliado para mostrar las opciones que se explican a continuación.](modulesfiles/webarchive_config.png)

El modo de incrustación predeterminado controla lo que muestra el reproductor alrededor del contenido archivado. Hay [cuatro opciones, derivadas de las opciones de ReplayWeb.page](https://replayweb.page/docs/embedding/#embed-modes){target=_blank}:

- «Predeterminado» muestra el sitio web reproducible en un marco similar al de un navegador, con una barra de direcciones que muestra la URL capturada. Los usuarios pueden acceder a la lista de páginas/URL del archivo y navegar a otras páginas. Hay botones para descargar el archivo y para consultar información sobre el tamaño del archivo y su origen.
- «Completo» añade una barra superior con el logotipo de ReplayWeb.page a la visualización predeterminada. 
- «Solo reproducción» no muestra controles similares a los de un navegador y requiere una URL de inicio para que tenga sentido. (Véase más abajo.) Esto resulta útil para incrustar una sola página. Los usuarios pueden intentar navegar dentro del archivo haciendo clic en los enlaces a otras páginas. 
- «Reproducir con información» muestra la página archivada igual que en «Solo reproducción». En la parte superior del marco hay un menú desplegable que muestra la misma información disponible en otras vistas: un enlace de descarga, el tamaño del archivo e información sobre cuándo se grabó.

Un archivo web configurado en modo «Completo»:

![Una página de visualización multimedia en el panel de administración que muestra un reproductor web incrustado con una barra situada encima de los botones de navegación del navegador. El botón de los tres puntos situado a la derecha de la barra de navegación está desplegado para mostrar opciones como «Información del archivo» y «Descargar archivo».](modulesfiles/webarchive_full.png)

Un archivo web configurado en el modo «Reproducir con información»:

![Una página de visualización de medios en el panel de administración que muestra un reproductor web integrado con un menú desplegable encima de la página web y sin barra de navegación. El menú desplegable está abierto y muestra un botón de descarga y cierta información sobre el archivo, como el tamaño del archivo y su fecha de creación.](modulesfiles/webarchive_info.png)

## Subir un archivo web

Los archivos web se pueden subir como archivos multimedia adjuntos a elementos. También se pueden incorporar proporcionando una URL a un archivo web disponible públicamente en línea, como [el archivo de ejemplo proporcionado por WebRecorder](https://webrecorder.github.io/example-webarchive/items/wikipedia/){target=_blank} en [esta URL](https://webrecorder.github.io/example-webarchive/items/wikipedia/archive.wacz) (3,7 MB). 

Dependiendo del tamaño del archivo, Omeka puede tardar un tiempo en incorporar el archivo multimedia.

Una vez subido el archivo web, el reproductor debería aparecer inmediatamente en la página de archivos multimedia del panel de administración y ser visible en cualquier sitio público que incluya el elemento. Comprueba estos enlaces de inmediato para asegurarte de que el archivo se reproduce según lo esperado. Si ves algún error, consulta la sección anterior sobre [Requisitos del servidor](#server-requirements). 

Ten en cuenta que un elemento con un archivo web subido como único contenido multimedia no generará una miniatura, pero puedes añadir una al elemento manualmente. 

### Configuración de contenidos multimedia

Cada archivo web que subas o importes como contenido multimedia tiene su propia configuración. Ve a la página de contenidos multimedia en la interfaz de administración, haz clic en el botón «Editar contenido multimedia» y ve a la pestaña «Avanzado». Verás dos campos específicos para este archivo: 

- **URL de inicio**: Introduce la URL original de la página que se abrirá en primer lugar. Déjalo en blanco para mostrar la lista de páginas del archivo, donde los usuarios pueden navegar por todas las páginas capturadas. Es obligatorio si el modo de incrustación está configurado en «Solo reproducción». Esta URL se puede encontrar dentro del propio reproductor, seleccionando una sola página y copiando la URL de la barra de direcciones. Una vez introducida esa URL en este campo, puedes cambiar la configuración que aparece a continuación para ocultar la barra de direcciones. Asegúrate de que esta URL sea exactamente la misma que la que se encuentra dentro del archivo. 
- **Modo de incrustación**: controla lo que muestra el reproductor alrededor del contenido archivado. (Véase más arriba.)

![La pestaña «Avanzado» en el modo de edición de medios. Debajo del contenido habitual de la pestaña «Avanzado» —Miniatura, Propietario, Texto alternativo, Idioma— aparecen dos opciones que ofrecen «URL de inicio» y «Modo de incrustación», tal y como se ha explicado anteriormente.](modulesfiles/webarchive_mediaAdvanced.png)

## Visualización pública

En un sitio público, el reproductor de archivos web aparecerá en los [bloques de recursos «Representación de medios» o «Incrustaciones de medios»](../sites/site_theme.md#configure-resource-pages). Puedes «Configurar las páginas de recursos» desde la página de configuración del tema de cada sitio. Ten en cuenta que la «Galería Lightbox» no mostrará este reproductor, por lo que quizá tengas que sopesar las prioridades de cada sitio a la hora de mostrar su gama de archivos multimedia en las páginas de vista de elementos. La Galería Lightbox generará una lista de «Otros medios» que no se pueden mostrar en su reproductor, por lo que los usuarios pueden hacer clic en esos enlaces para ver el archivo web en la página de medios en lugar de en la página del elemento. 

Los archivos web se pueden incrustar en las páginas de un sitio de Omeka S utilizando el bloque «Incrustación de archivos multimedia». Los bloques de página que utilizan imágenes derivadas, como el bloque «Carrusel de elementos», no mostrarán el reproductor de archivos web. 

## Solución de problemas

Tras la instalación, este módulo añade automáticamente `wacz`, `warc` y `gz` a la lista de «Extensiones de archivo permitidas» de la instalación, y `application/wacz`, `application/warc` y `application/gzip` a la lista de «Tipos de contenido multimedia permitidos». Comprueba que aparezcan tal y como se espera. 