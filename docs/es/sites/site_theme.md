# Temas

La sección «Temas» del menú de cada sitio te permite seleccionar el tema de tu sitio y configurar los ajustes específicos de cada tema. Cada sitio de tu instalación de Omeka S puede tener un tema independiente y numerosas personalizaciones. Una instalación nueva de Omeka S incluye un tema, llamado «Predeterminado».

## Instalar temas

Para que aparezcan en la página **Temas** de los sitios, los temas deben añadirse manualmente a la carpeta `/themes` de la instalación, utilizando un programa FTP o una conexión SSH.

Para añadir un tema al sitio mediante FTP:

1. Descarga el tema comprimido en tu ordenador.
1. Abre tu cliente FTP, inicia sesión en el servidor que aloja la instalación de Omeka S y navega hasta la carpeta `/themes` (debería estar ubicada en la carpeta principal de la instalación).
1. Sube el tema comprimido a la carpeta `/themes`.
1. Descomprime el tema.
1. Puedes eliminar el archivo comprimido si permanece en tu servidor.
1. Cuando accedas a la página Temas del menú Sitios, deberías ver allí el tema que acabas de añadir.

!!! nota
  La carpeta que aparece en la carpeta `/themes` debe mostrar el nombre del tema, sin ningún número de versión. Si tienes problemas para instalar un tema, comprueba que lo has descomprimido correctamente, sin crear niveles de carpetas adicionales.

También puedes utilizar SSH para clonar un tema directamente desde el repositorio Git de ese tema. Hazlo solo si te sientes cómodo con Git, GitHub y el uso de SSH. Puedes encontrar enlaces al repositorio GitHub de cada tema en [el directorio de Temas de nuestro sitio web](https://omeka.org/s/themes/){target=_blank}: haz clic en un tema y busca encima de la tabla del historial de versiones.

Para **desinstalar un tema**, simplemente elimina la carpeta del directorio `/themes` de tu instalación de Omeka S. Todos los ajustes de ese tema, de todos los sitios, se guardan en otro lugar y no se eliminarán. Esto significa que puedes volver a instalar el tema más adelante y recuperar tus ajustes.

Para **actualizar un tema**:

1. Descarga la nueva versión del tema que deseas actualizar.
1. Abre tu cliente FTP e inicia sesión en el servidor que aloja la instalación de Omeka S.
Navega hasta la carpeta `/themes`.
1. Mueve la copia antigua del tema a tu ordenador.
1. Sube la carpeta comprimida de la última versión del tema a la carpeta `/themes`.
1. En tu cliente FTP, descomprime la nueva versión del tema.
1. En el panel de control de la instalación de Omeka S, ve a un sitio, luego a la página Temas y comprueba que ves la nueva versión del tema.
1. Comprueba que se han conservado tus ajustes y que no hay errores. Después de esto, puedes eliminar con seguridad la carpeta del tema antiguo que guardaste en tu ordenador.

## Seleccionar un tema

Los temas instalados actualmente estarán disponibles para su selección durante el proceso de [añadir un nuevo sitio](../sites/index.md). Haz clic en la pestaña «Tema» antes de guardar para seleccionar uno y, a continuación, guarda tu sitio. Si no seleccionas un tema, tu nuevo sitio utilizará el tema predeterminado.

Cuando accedas a la pantalla «Tema» de un sitio, el tema actualmente activo aparecerá en la parte superior de la página.

A la izquierda aparece una imagen grande del tema activo, con el título del tema, la versión y el creador, y a la derecha hay dos botones: «[Editar configuración del tema](#edit-theme-settings)» y «[Configurar páginas de recursos](#configure-resource-pages)».

![Pestaña Tema con Center Row como tema actual](../sites/sitesfiles/sitetheme_tab.png)

Debajo del tema actual se encuentran los mosaicos de todos los demás temas instalados. Los mosaicos incluyen una pequeña imagen del tema en acción, el nombre y la versión del tema, y un enlace al creador del tema.

Para cambiar de tema, haz clic en el tema que desees utilizar. Se resaltará ligeramente en gris y aparecerá una casilla de verificación en la esquina inferior derecha del mosaico del tema.

![Un tema seleccionado que muestra el resaltado y la marca de verificación](../sites/sitesfiles/sites_themeselect.png)

Haga clic en el botón «Guardar» situado en la esquina superior derecha de la ventana para guardar los cambios. Haga clic en el botón «Cancelar» para salir sin guardar los cambios.

Una vez que haya seleccionado un nuevo tema y guardado la página, tendrá las opciones «Editar configuración del tema» o «Configurar páginas de recursos» para ese tema activo.

## Editar la configuración del tema

La configuración del tema le permite personalizar aspectos del tema del sitio, como añadir un logotipo en la parte superior o escribir texto en el pie de página.

Para editar la configuración del tema seleccionado, haga clic en el botón «Editar configuración del tema» situado a la derecha de la miniatura del tema actual.

![Botón de configuración del tema](../sites/sitesfiles/sitetheme_settings.png)

Ten en cuenta que la configuración de un tema específico en un sitio se guardará cuando cambies de tema. Por ejemplo, si personalizaste el pie de página del tema Predeterminado, luego cambiaste a The Daily durante un tiempo y después volviste al tema Predeterminado, tu pie de página personalizado seguirá ahí.

### Configuración

![Opción de logotipo](../sites/sitesfiles/sitetheme_configure.png)

Dependiendo del tema que hayas seleccionado, es posible que veas las siguientes opciones:

#### Logotipo

(Todos los temas)

Sube un recurso para que funcione como logotipo en el encabezado de tu sitio. Los tipos de archivo permitidos son: jpg, gif, png, svg y svgz.

Este recurso no está asociado a ningún elemento y se almacenará por separado; una vez subido a un sitio, podrás volver a seleccionarlo sin necesidad de volver a subirlo, incluso si cambias de tema durante un tiempo. Cualquier recurso subido a un sitio estará disponible para todos los sitios de la instalación.

Para subir un logotipo, haz clic en el botón «Seleccionar». Se abrirá una barra lateral en la que podrás subir un nuevo archivo desde tu ordenador o elegir entre los recursos ya subidos a la instalación.

Ten en cuenta que el logotipo puede sustituir por completo al encabezado, incluido el título del sitio, por lo que quizá te interese utilizar una imagen con texto si te parece importante que los usuarios vean el título del sitio.

Para eliminar un logotipo, haz clic en el botón «Borrar» de ese bloque (solo visible cuando hay un logotipo activo) y guarda los cambios.

#### Banner

(Todos los temas)

Sube un recurso para que se muestre en la parte superior de cada página de tu sitio. Puede ser un logotipo o un elemento visual decorativo. En algunos temas, esta imagen se sitúa detrás del texto. A veces se denomina «encabezado» en lugar de «banner».

La mayoría de los temas también te permiten configurar la posición del banner o su altura. 

#### Contenido del pie de página

(Todos los temas)

Un campo de texto en el que puedes introducir contenido para que aparezca en el pie de página del sitio.

Por defecto, el mensaje es «Desarrollado por Omeka S».

Puedes añadir formato HTML al texto añadiendo manualmente las etiquetas.

#### Profundidad de la navegación superior

(Predeterminado, Cozy, Foundation)

La profundidad de la navegación superior te permite limitar la profundidad del menú de navegación superior en la parte pública del sitio.  La configuración predeterminada, 0, no restringe el número de niveles del menú de navegación superior. Si se establece en uno, solo se mostrarán las páginas o enlaces de nivel superior de tu sitio.

#### Selección de color

(Predeterminado, Cozy, The Daily, Thanks Roy, Freedom)

Los temas Predeterminado, Cozy y The Daily incluyen una opción para introducir valores para el **color de acento principal**; Cozy también tiene una opción para el **color de fondo de la navegación**. Thanks Roy tiene ocho opciones de color distintas. 

![Campos de opciones de color](../sites/sitesfiles/sitetheme_color.png)

El color de acento principal se utiliza para el texto de los enlaces y los colores al pasar el cursor, como se muestra en la imagen siguiente:

![Flecha que señala ejemplos del color de acento principal en uso](../sites/sitesfiles/sitetheme_mainaccent.png)

El color de fondo de la navegación establece el color de la barra lateral de navegación del tema.

![La flecha señala la barra lateral](../sites/sitesfiles/sitetheme_navcolor.png)

Edita cualquiera de los campos escribiendo un valor de color en él. Se puede utilizar tanto un triplete como un código hexadecimal de seis caracteres. Una vez que hayas introducido un valor válido, la barra de color de la izquierda se actualizará automáticamente para mostrar el color introducido, incluso sin guardar los cambios.

Los valores predeterminados se almacenan en el texto de ayuda del campo. Para el tema Cozy, el color de acento principal es `087b94` y el color de fondo de la navegación es `bfdcdc`.

#### Diseño de las páginas de navegación

(Fila central, Foundation, Freedom)

Selecciona cómo mostrar los elementos en sus vistas de navegación.

* **Cuadrícula**: Los elementos se organizan en filas y columnas. Se recomienda para elementos que destacan por sus imágenes.
* **Lista**: Los elementos se apilan en una sola columna.
* **Alternar** (cuadrícula predeterminada): Los visitantes del sitio pueden elegir mostrar las vistas de navegación como cuadrículas o listas, siendo las cuadrículas la opción predeterminada.
* **Alternar** (lista predeterminada): Los visitantes del sitio pueden elegir mostrar las vistas de navegación como cuadrículas o listas, siendo las listas la opción predeterminada.

#### Propiedad «Truncar cuerpo» 

Establezca qué parte de la propiedad del cuerpo de navegación se muestra en la página de navegación y en el bloque de la página de vista previa de navegación. Puede:
  * **Mostrar valor completo**, que muestra todo el texto de la propiedad.
	* **Mostrar 4 líneas y desvanecer**, que muestra 4 líneas de texto con un desvanecimiento al final del bloque de texto.
  * **Mostrar 4 líneas y puntos suspensivos**, que muestra 4 líneas de texto que concluyen con puntos suspensivos (...).

Tenga en cuenta que el desvanecimiento a blanco puede no mostrarse bien si el bloque de la página de vista previa de navegación tiene un color de fondo o una imagen. 

#### Pie de foto en el visor

Le permite seleccionar qué campo de metadatos (entre Título de Dublin Core o Descripción de Dublin Core) aparece junto al contenido en el visor de la galería Lightbox donde se muestra (por ejemplo, en las páginas de vista de elementos). 


### Ajustes del tema Foundation

Foundation es un tema que incluye algunas hojas de estilo predeterminadas para crear prototipos rápidamente o para empezar a modificar temas. Como resultado, tiene algunos ajustes únicos. Para obtener más información sobre el uso de Foundation, incluido el trabajo con Sass, consulte el [archivo Léame del tema](https://github.com/omeka-s-themes/foundation-s/blob/master/README.md){target=_blank}.

Configuraciones no descritas anteriormente:

* **Hoja de estilos:** El tema ofrece 4 opciones de estilo.
	  * **Predeterminado** utiliza los estilos predeterminados de ZURB Foundation para la creación de prototipos, todos ellos visibles en su documentación en la sección [Kitchen Sink](https://get.foundation/sites/docs/kitchen-sink.html){target=_blank}.
	  * **Revolution** pretende capturar el estilo de los documentos antiguos y lo combina con un toque de rojo brillante. Incluye una imagen de fondo de papel texturizado.
    * **Sea Foam** ofrece un aspecto limpio y acogedor con una paleta de colores verde azulado.
    * **Inkwell** presenta una tipografía de familia serif de alto contraste, así como toques de amarillo brillante.
* **Diseño de navegación:** La navegación global puede mostrarse como una **barra superior horizontal con menús desplegables opcionales** o como una **columna vertical a la izquierda**.
* **Mostrar páginas secundarias en la navegación superior:** Activa o desactiva la visualización de las páginas secundarias dentro de la navegación principal. Si no está marcada, solo se mostrará la navegación de nivel superior.
* **Diseño de metadatos para páginas de muestra:** Los metadatos de los recursos pueden mostrarse **apilados**, con las propiedades como encabezados encima de sus valores, o **en línea**, con las propiedades como encabezados junto a sus valores.

Foundation también ofrece importantes herramientas de personalización de temas para desarrolladores, incluyendo la mayor parte del desarrollo en plantillas de páginas y bloques. Foundation incluye las siguientes plantillas de bloques:

* Activo
  * Tarjeta: utiliza los estilos del [contenedor de tarjetas de Foundation Framework](https://get.foundation/sites/docs/card.html){target=_blank}.
  * Objeto multimedia: utiliza los estilos del [contenedor de objetos multimedia de Foundation Framework](https://get.foundation/sites/docs/media-object.html){target=_blank}.
* Vista previa de exploración
  * Lista: ignora la configuración del tema para los diseños de vista de exploración y muestra todos los recursos como una lista de una sola columna.
  * Cuadrícula: ignora la configuración del tema para los diseños de vista de exploración y muestra todos los recursos en una cuadrícula con un máximo de 4 columnas.
  * Alternar (predeterminado: lista): ignora la configuración del tema para los diseños de vista de exploración y permite al usuario elegir su estilo de exploración, con una lista de recursos de una sola columna como opción predeterminada.
	* Alternar (predeterminado: cuadrícula): ignora la configuración del tema para los diseños de vista de exploración y permite al usuario elegir su estilo de exploración; el valor predeterminado es una cuadrícula de recursos con un máximo de 4 columnas.
* Elemento con metadatos
  * Multimedia grande a la izquierda: un diseño de 2 columnas con el contenido multimedia del elemento a la izquierda de los metadatos.
	* Multimedia grande a la derecha: un diseño de 2 columnas con el contenido multimedia del elemento a la derecha de los metadatos.
* Lista de páginas
  * Con contenedor: proporciona un contenedor en forma de cuadro gris.
* Lista de sitios
  * Tarjeta: utiliza los estilos del [contenedor de tarjetas de Foundation Framework](https://get.foundation/sites/docs/card.html){target=_blank} para cada sitio.
* Título de la página
  * Acentuado: muestra el título de la página con el color principal del tema como color de fondo.

Y las siguientes plantillas de página:

* Predeterminada: limita el contenido de la página a un ancho de 1200 píxeles, si la navegación está configurada como «desplegable horizontal» en lugar de «columna a altura completa». Esto incluirá la subnavegación de la página dentro de los 1200 píxeles si se muestra.
* Ancho completo: ocupa todo el ancho disponible en la ventana del navegador, menos la columna de navegación vertical si procede. La subnavegación de la página aparecerá encima del contenido de la página en lugar de al lado.

## Configurar páginas de recursos

Dentro de un sitio es posible configurar los bloques de contenido que aparecen en las páginas de recursos: la página de elemento, la página de medios y la página de conjunto de elementos.

Cada tema definirá las regiones disponibles (por ejemplo, Principal o Barra lateral) donde se pueden colocar los bloques. Es posible que algunos temas no ofrezcan estas opciones.

Estos ajustes están disponibles para los [administradores del sitio](../sites/site_users.md), así como para los [supervisores de instalación y administradores globales](../admin/users.md).

En la página Tema de un sitio, su tema actual aparecerá en la parte superior, con dos botones a la derecha: «Editar configuración del tema» y «Configurar páginas de recursos». Seleccione el botón «Configurar páginas de recursos» para modificar cómo se mostrarán estas páginas en este tema.

Tenga en cuenta que su configuración para un tema específico en un sitio se guardará si cambia de tema. Por ejemplo, si personalizó la página de elementos para el tema Predeterminado, luego cambió a Foundation durante un tiempo y después volvió al tema Predeterminado, se mantendrían los ajustes de su página de elementos.

### Seleccionar regiones y bloques
En el panel de la derecha, seleccione una región del menú desplegable y, a continuación, añádale un bloque de la lista de bloques disponibles haciendo clic en el nombre del bloque. Los bloques se pueden reordenar o mover a otras regiones arrastrándolos y soltándolos.

Para eliminar un bloque, haz clic en el icono de eliminar y, a continuación, guarda la página. Volverá a aparecer en la barra lateral derecha.

La imagen siguiente muestra la pantalla «Configurar páginas de recursos» con la pestaña «Página de elemento» seleccionada. La barra lateral derecha incluye un menú desplegable para seleccionar una región y una lista de los bloques restantes que se pueden añadir a la página. Se está utilizando el tema Foundation y hay cuatro regiones: Principal a ancho completo, Principal con barra lateral, Barra lateral derecha y Barra lateral izquierda.

![Captura de pantalla de las opciones de configuración de la página de recursos del tema Foundation.](../sites/sitesfiles/sitetheme_configureResourcePages.png)

Si no se incluye contenido en una región específica, como una barra lateral, esta no aparecerá y las demás regiones se expandirán para ocupar el espacio.

Puede utilizar el [módulo Editor CSS](../modules/csseditor.md) para modificar los anchos relativos u otras propiedades de visualización de las regiones que decida utilizar, como establecer diferentes colores de fondo, añadir bordes o configurar estilos de texto independientes. Utilice la herramienta de inspección de su navegador para identificar las regiones a las que llamar: por ejemplo, en el tema Foundation, las regiones se identifican con las clases `.full-width-main`, `.left-sidebar`, `.main-with-sidebar` y `.right-sidebar`. 

Ten en cuenta que otros ajustes del tema y del sitio también pueden influir en cómo estas páginas muestran la información. Por ejemplo, el tema Foundation incluye un ajuste sobre si apilar una propiedad y su valor (por ejemplo, mostrar «Descripción» en una línea y el contenido de la descripción en la siguiente, o ambos en la misma línea), lo que puede influir en tu decisión sobre dónde colocar el bloque «Valores» en las regiones de la página.

También puede utilizar el Editor CSS para aplicar estilos a bloques específicos dentro de esas regiones (como el bloque `.resource-class`) y a las propiedades de metadatos (`.property`) dentro del bloque «Valores». Los valores (`.value`) se muestran con una clase CSS que indica su tipo de datos (como `.literal`), y también puede aplicar estilos a los indicadores `.language`, al icono `.has-annotation`, etc. 

### Bloques disponibles

Una instalación básica de Omeka S creará los siguientes bloques configurables, pero los módulos también pueden añadir sus propios bloques. Por ejemplo, el [módulo Mapping](../modules/mapping.md) te permitirá reposicionar el mapa en las páginas de elementos y conjuntos de elementos (no en los medios).

Si un bloque no tiene contenido (por ejemplo, si no hay recursos vinculados, ni medios, ni nada establecido como clase de recurso, o si no hay páginas del sitio), no se mostrará en ese elemento concreto.

#### Página del elemento

Bloques disponibles:

- Conjuntos de elementos: muestra la lista de conjuntos de elementos que contienen el elemento.
- Galería Lightbox: muestra los medios adjuntos utilizando el visor de galería Lightbox.
- Recursos vinculados: muestra una tabla filtrable de los recursos vinculados al elemento.
- Archivos multimedia incrustados: muestra todos los archivos multimedia adjuntos como archivos incrustados.
- Lista de archivos multimedia: muestra los archivos multimedia adjuntos como una lista con miniatura y título.
- Páginas del sitio: muestra la lista de todas las páginas del sitio en las que está adjunto el elemento.
- Clase de recurso: muestra la clase de recurso del elemento.
- Valores: muestra todos los valores de las propiedades del elemento.

La imagen siguiente muestra la página pública del elemento en el tema Foundation, con los bloques configurados como en la captura de pantalla anterior: Galería Lightbox en la región principal de ancho completo; Valores y Recursos vinculados en la región principal; Lista de archivos multimedia en la región de la barra lateral derecha; Clase de recurso y Conjuntos de elementos en la región de la barra lateral izquierda.

![Captura de pantalla de un elemento titulado «Spigelia marilandica» con la galería Lightbox mostrando el escaneo de una página de un libro de una flor, e información en las tres regiones de abajo.](../sites/sitesfiles/sitetheme_configureResourcePages2.png)

#### Página de medios

Bloques disponibles:

- Galería Lightbox: muestra los medios utilizando el visor de galería Lightbox.
- Recursos vinculados: muestra una tabla filtrable de recursos vinculados al medio.
- Visualización del medio: muestra el medio actual.
- Clase de recurso: muestra la clase de recurso del medio.
- Valores: muestra todos los valores de las propiedades del medio.

#### Página del conjunto de elementos

Bloques disponibles:

- Valores: muestra todos los valores de las propiedades del medio.
- Clase de recurso: muestra la clase de recurso del conjunto de elementos.
- Recursos vinculados: muestra una tabla filtrable de los recursos vinculados al conjunto de elementos.

La página de vista del conjunto de elementos siempre contendrá una lista de los elementos incluidos en el conjunto, que se puede encontrar con la clase CSS `item-set-items` en algunos temas. Esta área no aparece como un bloque configurable en el panel de administración, y debe localizarse consultando el sitio público. En la mayoría de los temas aparece debajo de las regiones configuradas, pero en algunos aparecerá en una columna junto a las regiones. 