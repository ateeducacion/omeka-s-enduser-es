# Archivos multimedia

Omeka S admite la mayoría de archivos y tipos de archivo, y se puede personalizar para aceptar o rechazar los tipos de archivo que elijas. Es posible que desee formatear sus archivos multimedia de acuerdo con lo que mejor se pueda incrustar y reproducir en los navegadores modernos; consulte la [sección Tipos de archivos multimedia al final de esta página](#media-file-types). Si tiene dificultades o ve errores de validación de archivos, puede ajustar los tipos de archivos y las extensiones aceptadas en las [opciones de archivos y medios permitidos de la configuración de seguridad](../admin/settings.md#security).

Los archivos multimedia solo se crean añadiéndolos a un elemento; no pueden existir de forma independiente. Si desea subir archivos no vinculados a elementos, como logotipos y banners, consulte la [página de activos](../admin/assets.md).

Para ver los archivos multimedia asociados a un elemento, haga clic en el nombre del archivo multimedia en la barra lateral derecha de la página de visualización del elemento.

Para ver todos los archivos multimedia de la instalación, vaya primero a la sección **Elementos**. A continuación, haga clic en la subsección **Archivos multimedia** que aparece debajo de Elementos en el panel de navegación de la izquierda.

## Permisos de archivos multimedia

Cuando un usuario adjunta un archivo multimedia a un elemento, se convierte en el «propietario» de dicho archivo. La mayoría de los niveles de usuario tienen la capacidad de crear archivos multimedia y siempre pueden eliminar sus propios archivos. Solo los niveles superiores pueden eliminar archivos multimedia que sean propiedad de otros.

| Categoría | Permiso | Administrador global | Supervisor | Editor | Revisor | Autor | Investigador |
|-----|-----|---|---|---|---|---|---|
| Elementos y archivos multimedia | Añadir | Sí | Sí | Sí | Sí | Sí | No |
| | Editar | Todos | Todos | Todos | Todos | Los propios | No |
| | Eliminar | Todos | Todos | Todos | Los propios | Los propios | No |
| Anotaciones de valor | Añadir/Editar | Sí | Sí | Sí | Sí | Sí | No |
| Objetos privados | Ver | Sí | Sí | Sí | Sí | No | No |

La propiedad de los archivos multimedia no coincide automáticamente con la propiedad del elemento adjunto. Un administrador global o un supervisor puede cambiar el propietario de un archivo multimedia en la pestaña «Avanzado» del mismo.

Ten en cuenta que cuando cambias el rol de un usuario, por ejemplo, de Autor a Investigador, seguirá siendo propietario de los archivos multimedia que creó cuando tenía permiso para hacerlo. Al eliminar a un usuario, sus archivos multimedia quedan huérfanos: aparecerán como si no tuvieran propietario.

## Ver archivos multimedia
Para explorar los archivos multimedia, primero haz clic en Elementos en el panel de navegación de la izquierda. En esa barra lateral, aparecerá una opción para Archivos multimedia debajo del botón Elementos (es posible que tengas que hacer clic en el triángulo para expandir el menú debajo de Elementos).

![La sección «Recursos» de la barra de navegación, con texto azul claro sobre fondo azul oscuro. Debajo de la opción «Elementos», con sangría, hay una opción de navegación para «Medios». A diferencia de las demás opciones, no tiene ningún icono representativo.](contentfiles/media-browsenav.png)

Los archivos multimedia se muestran en una tabla. Cada archivo multimedia ocupa una fila, con columnas para:

- una casilla de verificación para seleccionar el archivo multimedia
- el **Título**
- iconos para **editar** (lápiz), **eliminar** (papelera) o ver **detalles** (tres puntos)
- la **Clase** del archivo multimedia
- el **Propietario** del archivo multimedia
- y la fecha en que se **Creó** el archivo multimedia.

![La tabla de exploración de archivos multimedia muestra 5 elementos. Todos los archivos multimedia tienen títulos que son URL de MediaWiki, y todos son propiedad de la usuaria Megan.](contentfiles/media_browse.png)

Las opciones para navegar y crear elementos se muestran encima de la tabla de elementos:

- En el lado izquierdo hay un indicador del número de páginas de archivos multimedia, con flechas de avance y retroceso. El número de página actual es un campo editable: introduce cualquier número de página válido y pulsa Intro en tu teclado para ir a esa página.
- En la parte superior central hay un botón para la [Búsqueda avanzada](../search.md#media-advanced-search).
- Justo encima de la tabla, a la derecha, hay opciones para ordenar los archivos multimedia, con dos menús desplegables. El primero te permite seleccionar entre **Título**, **Clase**, **Propietario**, **(fecha) de creación** y **Tamaño**; el segundo te permite ordenar de forma ascendente o descendente. Para aplicar la ordenación, haz clic en el botón «Ordenar».

Al hacer clic en el título de cualquier archivo multimedia, accederás a su página de metadatos. Esta página muestra los metadatos en el área de trabajo principal, con una barra lateral a la derecha que enumera la visibilidad, el elemento asociado (un enlace activo), la fecha de creación, el tipo MIME, el tamaño, el ingestor, la fuente y enlaces a los derivados del archivo.

![Página de visualización de un archivo de imagen. A la derecha de la imagen se encuentra la información de la base de datos del archivo multimedia, incluidos enlaces a varios derivados, el elemento del que forma parte, el tipo de archivo y el tamaño.](../content/contentfiles/media_view.png)

## Añadir archivos multimedia a un elemento

Los archivos multimedia solo se pueden añadir a través de un [elemento](../content/items.md). Las opciones para añadir medios a tus elementos incluyen subir un archivo o adjuntar contenido directamente mediante:

- URL, 
- [oEmbed](https://oembed.com/){target=_blank},
- URL de YouTube,
- una [imagen IIIF](https://iiif.io/api/image/3.0/){target=_blank} por URL,
- una [presentación IIIF](https://iiif.io/api/presentation/3.0/){target=_blank} mediante URL,
- o escribiendo código HTML con el editor HTML.

Para obtener más información sobre oEmbed, [consulte la información sobre el uso del bloque de página oEmbed en las páginas de su sitio](../sites/site_pages.md#oembed). 

Para obtener más información sobre IIIF, [consulte la información sobre el uso de los bloques de página IIIF en las páginas de su sitio](../sites/site_pages.md#iiif-image).

### Describa sus archivos multimedia 

En la fase de adición de archivos multimedia, el único metadato que se puede introducir es el título. Si desea describir cada archivo con más detalle, puede editarlo una vez que se haya subido. Si no proporciona un título, el nombre de archivo original aparecerá como título del archivo multimedia. Tenga en cuenta que el nombre de archivo real del archivo multimedia habrá cambiado al subirlo a Omeka S; este nombre de archivo, que se conserva como título, es solo para su referencia y puede cambiarse en cualquier momento.

Puede subir varios archivos a la vez, añadir varios tipos de archivos multimedia a la vez o añadir más archivos multimedia cada vez que guarde. Aparecerán en el orden en que se subieron.

Puede arrastrar y soltar los archivos multimedia en el orden que desee, tanto mientras los añade como después de haberlos añadido. En la pantalla de edición del elemento, haga clic en la pestaña «Archivos multimedia» y utilice las barras horizontales situadas a la izquierda de cada archivo para moverlos hacia arriba y hacia abajo en la lista.

### Archivo multimedia principal

Puedes seleccionar un archivo para que sea el **archivo multimedia principal** del elemento. Para ello, ve a la pantalla de edición del elemento, selecciona la pestaña «Archivos multimedia» y utiliza el botón de opción que aparece a la derecha del título de cada archivo para seleccionar uno.

![Un elemento en proceso de edición, en la pestaña «Archivos multimedia», con varios archivos visibles. El primer archivo, un PDF, se muestra como el medio principal actual.](../content/contentfiles/media_primary.png)

Esto hará que el medio principal elegido:

- se convierta en la miniatura del elemento (si no se ha seleccionado manualmente una miniatura en la pestaña Avanzado), y
- aparezca como el medio principal en presentaciones de diapositivas, vitrinas y otros bloques de página donde se haya añadido el elemento.

No cambiará el orden de los archivos cuando se muestren en páginas de administración o públicas. Por ejemplo, seleccionar el último archivo como medio principal no influirá en el orden de los archivos en el visor de la galería de la página pública del elemento.

Por defecto, el primer medio subido (el primero de la lista) es el medio principal. Si se elimina el medio principal elegido, el elemento volverá por defecto al archivo que se encuentra en la parte superior de la lista como medio principal.

### Miniaturas de archivos multimedia

Las miniaturas se crean automáticamente para muchos tipos de archivos. La creación de miniaturas depende de la capacidad de la [utilidad de miniaturas elegida](../configuration.md#thumbnails) (la predeterminada es ImageMagick) y de los tipos de archivo que pueda procesar. Consulta la utilidad que estés utilizando (como ImageMagick, Imagick o GD) para averiguar qué tipos de archivo admite.

Si desea que su elemento tenga una miniatura genérica (como el icono de un libro o una nota musical para un archivo de audio), puede subir esas imágenes predeterminadas como [recursos](../admin/assets.md) y, a continuación, adjuntarlas manualmente a los archivos mediante la [pestaña Avanzado de la pantalla de edición de elementos](../content/items.md#advanced).

Las miniaturas seleccionadas a través de la pestaña Avanzado de la pantalla de edición de un elemento (desde la colección de activos de una instalación) anularán cualquier otra miniatura que se haya generado para el elemento a partir de sus archivos multimedia.

Se crean tres miniaturas para cada elemento con un tipo de archivo multimedia aceptable: 

- una derivada grande, con la relación de dimensiones original pero con un tamaño máximo del lado más largo de 800 píxeles
- una derivada mediana, con la relación de dimensiones original pero con un tamaño máximo del lado más largo de 200 píxeles
- una derivada cuadrada, con su lado más pequeño fijado en 200 píxeles y su lado más largo recortado hasta los 200 píxeles centrales.

La miniatura grande se muestra en la mayoría de las páginas de vista de elementos y de vista de medios, con un enlace al archivo original sin editar. Las miniaturas cuadradas o medianas se utilizan, dependiendo del tema y otros ajustes, en las listas de navegación y de resultados de búsqueda, en los marcadores de mapas, etc. Los temas también pueden mostrar estas imágenes con un tamaño inferior al de sus dimensiones de archivo. 

Estas dimensiones son las predeterminadas en todas las instalaciones nuevas de Omeka S, pero [se pueden cambiar editando el archivo `config`](../configuration.md#thumbnails). La miniatura cuadrada siempre recortará el lado más largo, y la miniatura mediana siempre se redimensionará por el lado más corto. 

### Tamaños de los archivos

Omeka S no impone limitaciones de tamaño de archivo. Sin embargo, es posible que su servidor tenga restricciones en cuanto al tamaño o la velocidad de carga de archivos, lo que podría causar problemas. Estas limitaciones varían de un servidor a otro y no podemos modificarlas por usted. Si tiene algún problema al cargar archivos multimedia, consulte primero con su servicio de alojamiento o con el administrador de su servidor local.

Para gestionar los archivos multimedia de su instalación de Omeka S en función del tamaño, puede acceder a la pestaña «Multimedia» y ordenar los archivos por «Tamaño» y «Descendente». Esto colocará los archivos más grandes en la parte superior de la tabla; los tamaños de los archivos se indican en bytes. Esto puede ayudarle a identificar recursos para el alojamiento externo o el reformateo derivado, dependiendo de sus necesidades de almacenamiento. 

![La pestaña «Medios», con los archivos más grandes en la parte superior de la tabla.](contentfiles/media_sizes.png)


## Editar metadatos de los medios

Para editar medios existentes, puedes:

- Ir a la página de exploración de medios y hacer clic en el icono del lápiz/editar de la fila del medio
- Ir a la página de exploración de medios, hacer clic en el título para ver los metadatos del medio y, a continuación, hacer clic en el botón «Editar medio» situado en la esquina superior derecha
- Hacer clic en el nombre del medio en la barra lateral derecha de la página de un elemento para ir a los metadatos del medio y, desde allí, hacer clic en «Editar medio».

Los metadatos generados automáticamente, como la fuente, la fecha de creación y la parte del elemento, no se pueden editar.

La edición de archivos multimedia es muy similar a la edición de [elementos](../content/items.md) o [conjuntos de elementos](../content/item-sets.md).

![Página de edición de archivos multimedia, sin propiedades cargadas](../content/contentfiles/media_edit.png)

Utilice el botón **Hacer público/privado** (icono de ojo) para establecer si el medio es visible para el público o solo para los usuarios de la instalación de Omeka S.

El medio es público: ![botón «Hacer público» que muestra un icono de ojo](../content/contentfiles/item_public.png){style="display:inline;"}

El medio es privado: ![botón «Hacer privado» que muestra un icono de ojo tachado con una barra diagonal](../content/contentfiles/item_private.png){style="display:inline;"}

Ten en cuenta que si un elemento es privado, todos los medios adjuntos son privados, pero un elemento que es público puede tener medios adjuntos que estén configurados como públicos o privados.

### Valores

Si lo desea, puede seleccionar una plantilla de recursos en el menú desplegable. Las plantillas de recursos son definidas por los administradores y editores del sitio.

- Si utiliza una plantilla de recursos, la clase de medio debería cargarse automáticamente.
- Si no utiliza una plantilla de recursos, puede seleccionar una clase en el menú desplegable (estas se rellenan a partir de los [Vocabularios](vocabularies.md) de su instalación).

Añada información a las propiedades que se carguen. Si no selecciona una plantilla de recursos o una clase, no se cargarán automáticamente otros campos.

Tanto si utiliza una plantilla de recursos como si no, puede añadir más propiedades al elemento utilizando el panel situado en la parte derecha de la pantalla. Simplemente abra uno de los vocabularios (Dublin Core, Ontología Bibliográfica, etc.) y haga clic en la propiedad que desee añadir, o utilice el cuadro «Filtrar propiedades» para buscar una propiedad específica (esto resulta útil cuando se dispone de varios vocabularios de gran tamaño).

Al hacer clic en la etiqueta de la propiedad en el panel, esta se añadirá automáticamente al elemento. Si añades una propiedad por error, déjala en blanco y se eliminará del elemento cuando guardes los cambios.

Puede añadir texto, un recurso de la instalación o un enlace externo en cada campo.  

Tenga en cuenta que si añade la propiedad `dcterms:title`, su contenido sustituirá al título generado automáticamente del medio. Esto resulta útil si se trata de URL o de archivos multimedia subidos con nombres generados automáticamente.  

Puedes configurar propiedades individuales como **privadas o públicas** utilizando el icono del ojo de cada propiedad. Ten en cuenta que las propiedades configuradas como privadas siguen siendo visibles para los administradores globales, los administradores del sitio y los editores. Los autores podrán ver todas las propiedades de los elementos que les pertenecen, pero no verán las propiedades privadas creadas por otros usuarios.

En la imagen siguiente, la primera propiedad (Título) es pública, como indica el icono del ojo abierto. La segunda propiedad (Descripción) es privada, como indica el icono del ojo tachado. Al hacer clic o pulsar Intro en el icono del ojo, se alterna entre público y privado.

![Las propiedades individuales tienen un icono de ojo rojo a la derecha que permite alternar la visibilidad; una flecha roja señala el icono](contentfiles/items_propviz.png)

#### Texto
Los campos de texto permiten introducir texto sin formato.

Puede indicar el idioma del contenido de un campo de entrada utilizando el símbolo del globo terráqueo situado encima del campo (véase la flecha roja en la imagen de abajo). Haga clic en el icono del globo terráqueo para activar un campo de texto y, a continuación, introduzca el código [ISO 639-1](https://en.wikipedia.org/wiki/List_of_ISO_639-1_codes){target=_blank} del idioma en el que está escrito el texto.

![Un campo de entrada de texto, con un icono de globo terráqueo a la izquierda, resaltado en azul con el cursor activo en el campo. Se está aplicando una etiqueta de idioma de dos letras al contenido del campo de texto de abajo.](contentfiles/items_lang.png)

#### Recurso de Omeka

Los campos de recursos de Omeka crean un enlace interno entre el recurso que está creando y el recurso que rellena ese campo.

Tienes la opción de utilizar un elemento o un conjunto de elementos. Al elegir un tipo de recurso, se abrirá un panel lateral donde podrás explorar todos los recursos de la instalación. Puedes utilizar la función de búsqueda situada en la parte superior del panel para filtrar la lista o para encontrar rápidamente un elemento o conjunto de elementos específico.

Si utiliza un recurso de elemento para la propiedad, dispondrá de opciones adicionales para encontrar el elemento que desea en el panel lateral. Abra estas opciones haciendo clic en el botón triangular situado junto a la frase «Filtrar búsqueda».

Esto abrirá un menú debajo del botón con las siguientes opciones para filtrar los elementos del panel lateral:

- Filtrar por clase: un menú desplegable en el que puede seleccionar cualquier clase proporcionada por los vocabularios de la instalación.
- Filtrar por conjunto de elementos: un menú desplegable en el que puedes limitar los elementos mostrados en el cajón a solo aquellos asociados a un conjunto de elementos concreto.
- Filtrar por ID de elemento: un campo de búsqueda en el que puedes introducir el ID del elemento que deseas utilizar. Puedes encontrar el ID de un elemento en la URL de su página de edición; si estás editando el elemento y la URL es `admin/item/11547/edit`, entonces el ID del elemento es 11547.

![opciones descritas anteriormente](contentfiles/items_addresItem.png)

Los recursos de los elementos también tienen una opción de «Añadir rápidamente». Cuando se activa esta opción, todos los elementos del cajón tienen una casilla de verificación. Puedes utilizar estas casillas para añadir varios elementos como una propiedad a la vez. Ten en cuenta que solo puedes editar una propiedad a la vez, por lo que todos los elementos deben rellenar la misma propiedad (por ejemplo, «Creador», «Tiene parte»).

![una flecha roja señala el botón deslizante de «Añadir rápidamente». Los dos elementos visibles tienen una casilla de verificación vacía a la izquierda de su miniatura representativa](contentfiles/items_quickadd.png)

Las páginas públicas y de administración de medios no muestran tablas de recursos vinculados.

#### URI

Los campos URI enlazan con un sitio web externo o un recurso en línea. Cada valor URI tiene el enlace en sí mismo y una etiqueta textual opcional para sustituir el URI por algo legible para los humanos. Por ejemplo, es posible que desee introducir un «Creador» como URI a un vocabulario controlado de artistas o autores, y luego incluir el nombre del creador en texto sin formato como etiqueta. Omeka no extraerá automáticamente la información del URI.

#### Anotación de valores

Cuando introduces un valor para una propiedad asociada a un recurso, estás haciendo una afirmación sobre ese recurso. Si lo deseas, Omeka te permite hacer afirmaciones sobre esa afirmación. A esto lo llamamos anotación de valores. La ventaja de la anotación de valores es que puedes optar por concretar hechos ambiguos mediante la anotación de aspectos como:

- Procedencia: ¿De dónde procede este hecho?
- Tiempo: ¿Cuándo ocurrió este hecho?
- Ubicación: ¿Cuál es la ubicación asociada a este dato?
- Certeza: ¿Cuál es el grado de confianza de este dato?
- Tipo: ¿Qué tipo de concepto o entidad es este dato?

En el mundo de los datos enlazados, este proceso se conoce como [reificación](https://www.w3.org/wiki/RdfReification){target=_blank}. Cada valor puede tener cualquier número de anotaciones.

Para crear una anotación, haz clic en los tres puntos situados a la derecha de la interfaz de introducción de valores y, a continuación, haz clic en el icono de anotación (el bocadillo).

![Detalle de un valor con el bocadillo de anotación resaltado](contentfiles/annotation_add.png)

La barra lateral de anotaciones se abrirá a la derecha. Seleccione cualquier propiedad disponible en la instalación de Omeka S para describir la relación entre la anotación y el valor que describe. Por ejemplo, el valor asociado a la propiedad `dcterms:Contributor` podría anotarse con más detalles sobre la naturaleza de la contribución. O tal vez desee simplemente incluir una nota utilizando el campo `dcterms:Description`.

Seleccione un tipo de datos para la anotación: un campo de texto, un URI o un recurso de su instalación de Omeka S. Es posible que los módulos ofrezcan tipos de datos adicionales. Haga clic en el botón «Añadir anotación» y aparecerá un nuevo campo debajo. Introduzca su anotación. Si lo desea, puede hacerlo varias veces para el valor elegido. A continuación, haga clic en «Establecer anotaciones» para finalizar el proceso.

![Imagen de la barra lateral de anotaciones de valor con una propiedad seleccionada y una anotación incluida](contentfiles/annotation_sidebar.png)

[Cada sitio tiene una configuración](../sites/site_settings.md#show) para indicar si las anotaciones de valor son visibles para el público. Esto incluirá las anotaciones de valor en los elementos y conjuntos de elementos.

Puede establecer vocabularios controlados para las anotaciones utilizando el [módulo Custom Vocab](../modules/customvocab.md). En este caso, no es necesario aplicar un vocabulario personalizado a una propiedad mediante una plantilla de recursos; puede seleccionar cualquier vocabulario instalado en el menú desplegable de tipos de valor del panel. Esto cargará las opciones de su vocabulario en un menú desplegable de términos.

### Avanzado

#### Miniatura

No todos los medios generan miniaturas elegantes, por ejemplo, los documentos PDF o de texto, o algunos archivos de vídeo. Puede utilizar esta opción para establecer una miniatura representativa para el medio que se utilizará en las páginas de exploración, pero no en la página del elemento o de su medio.

Los activos que seleccione o suba como miniaturas en esta pestaña son los mismos que los creados para los [logotipos del sitio](../admin/assets.md). Una miniatura subida como recurso estará disponible para todos los usuarios de todos los sitios. Si deseas subir una captura de vídeo como miniatura para un vídeo específico, es posible que prefieras subirla como archivo multimedia adjunto al elemento en lugar de como recurso.

Para asignar un recurso como miniatura, haz clic en el botón «Seleccionar» en el área de trabajo principal de la pestaña. Esto abrirá un panel deslizante en el lado derecho.

![Panel de selección con opción de subir y dos activos, ambos imágenes.](contentfiles/media_thumbnail1.png)

El panel ofrece dos opciones: subir un archivo utilizando el navegador o seleccionar uno de los activos existentes. Para seleccionar un activo existente, basta con hacer clic en él y se asignará automáticamente al medio.

![Editar medios: se abre la pestaña Avanzado, donde se encuentra un recurso que es una imagen de un mapa del National Mall en el área de trabajo principal. Debajo hay botones para Seleccionar y Borrar](contentfiles/media_thumbnail2.png)

Para eliminar un recurso que haya asignado como miniatura, haga clic en el botón «Borrar» situado debajo de la imagen del recurso. Para sustituirlo, haga clic en Seleccionar y elija o suba un nuevo recurso de miniatura.

#### Propietario

Puede asignar un propietario al archivo multimedia seleccionándolo en el menú desplegable.

#### Texto alternativo

Puede proporcionar un texto alternativo para todos los archivos multimedia escribiendo un texto descriptivo en el área de entrada.

![Edición de archivos multimedia abierta en la pestaña Avanzado, mostrando el cuadro de entrada de texto alternativo](contentfiles/media_alttext.png)

#### Idioma

Puede indicar el idioma de un archivo multimedia introduciendo el código de idioma de dos letras [ISO 639-1](https://en.wikipedia.org/wiki/List_of_ISO_639-1_codes){target=_blank} en este campo. Este campo no admite varios valores.

## Acciones por lotes

Desde la página de exploración de archivos multimedia (`admin/media`), puede editar archivos multimedia por lotes utilizando el menú desplegable situado a la izquierda, cerca de los botones de paginación. Puede seleccionar archivos multimedia manualmente para la edición por lotes utilizando las casillas de verificación de la izquierda, seleccionar todos los archivos multimedia de la página o utilizar el menú desplegable para editar todos los archivos multimedia que se encuentran actualmente en el subconjunto.

Los editores, supervisores y administradores globales pueden editar y eliminar en bloque todos los archivos multimedia de la instalación. Los usuarios con permisos de nivel de autor pueden editar o eliminar en bloque sus propios archivos multimedia, pero no los de otros. En este caso, al seleccionar todos los archivos multimedia de la página, o al seleccionar todos los archivos multimedia, solo se incluirán los archivos multimedia de su propiedad. Los usuarios con nivel de revisor no pueden eliminar por lotes todos los recursos, pero sí pueden eliminar por lotes los recursos seleccionados.

![Una flecha roja señala el menú desplegable de opciones de edición y eliminación por lotes](contentfiles/media_batch1.png)

Las acciones por lotes son las siguientes:  

- Editar seleccionados: edita solo los archivos multimedia seleccionados en la página
- Editar todo: edita todos los archivos multimedia devueltos por una búsqueda (por defecto, todos los archivos multimedia)
- Eliminar seleccionados: elimina solo los archivos multimedia seleccionados en la página
- Eliminar todo: elimina todos los archivos multimedia devueltos por una búsqueda (por defecto, todos los archivos multimedia).

El número de resultados por página se configura en la [configuración global de la instalación](../admin/settings.md#general).

Primero puede utilizar el enlace «🔍 Búsqueda avanzada» para reducir los archivos multimedia a un subconjunto para su edición. Por ejemplo, puede utilizar la [Búsqueda avanzada](../search.md#media-advanced-search) para limitar la búsqueda a archivos multimedia de un tipo MIME específico, o a archivos multimedia propiedad de un usuario concreto.

Si realiza una búsqueda, volverá a ver la página de exploración, con los parámetros seleccionados apareciendo en la parte superior de la pantalla. Desde esta pantalla de exploración, puede seleccionar los archivos multimedia manualmente para la edición por lotes utilizando las casillas de verificación de la izquierda, seleccionar todos los archivos multimedia de la página o utilizar el menú desplegable para editar todos los archivos multimedia que se encuentran actualmente en el subconjunto.

Si completa una acción por lotes desde la siguiente pantalla, volverá a este mismo subconjunto de archivos multimedia.

### Edición por lotes

La edición por lotes de archivos multimedia le lleva a una nueva página. Los archivos multimedia que se están editando se mostrarán en el lado derecho en un panel. Asegúrese de que el número de archivos multimedia que se están editando es correcto.

El formulario de edición por lotes le ofrece las siguientes opciones:  

- **Establecer visibilidad**: un botón de opción. Seleccione entre «público» o «no público» para que el archivo sea visible o no visible para los usuarios que no hayan iniciado sesión.
- **Establecer plantilla**: un menú desplegable. Seleccione una de las plantillas de recursos de la instalación. Puede eliminar plantillas de los elementos seleccionados con la opción «[Desactivar plantilla]». Aparece una barra de búsqueda en la parte superior del menú desplegable si desea escribir para buscar.
- **Establecer clase**: un menú desplegable. Seleccione entre las clases de los vocabularios instalados. Puede eliminar todas las clases de los archivos seleccionados con la opción «[Desactivar clase]». Aparece una barra de búsqueda en la parte superior del menú desplegable si desea escribir para buscar.
- **Establecer propietario**: un menú desplegable. Seleccione entre los usuarios de la instalación para elegir quién debe establecerse como propietario de los medios seleccionados. Cambiar la propiedad de los medios no cambiará la propiedad de los elementos asociados. La propiedad determina [quién puede editar y eliminar esos archivos multimedia](#media-permissions), al margen de los [niveles de permisos de usuario](../admin/users.md#roles-and-permissions) superiores.
- **Borrar idioma**: una casilla de verificación para eliminar la configuración de idioma existente.
- **Establecer idioma**: un campo de texto. Introduzca un código de idioma de dos letras [ISO 639-1](https://en.wikipedia.org/wiki/List_of_ISO_639-1_codes){target=_blank}. Aquí solo puede indicar un idioma.
- **Borrar valores de propiedad**: un menú desplegable y un campo de texto, con todas las propiedades de todos los vocabularios. Al seleccionar una opción, se eliminarán todos los valores de esa propiedad en los medios afectados. Puede eliminar varios valores de propiedad a la vez: haga clic de nuevo en el campo de texto para ver las opciones restantes.
- **Establecer visibilidad del valor**: un menú desplegable y un campo de texto, con botones de opción. Establezca la visibilidad de una o varias propiedades específicas como pública o no pública. A diferencia de los botones de opción de la parte superior del formulario, esto solo afectará a uno o varios campos de metadatos, en lugar de a todo el contenido multimedia (por ejemplo, es posible que desee ocultar el valor «Creador» en algunos contenidos multimedia públicos). Seleccione una propiedad en el campo de texto (escriba para iniciar la búsqueda) y, a continuación, elija el botón de opción «Público» o «No público» para esta opción. Puede añadir varias propiedades haciendo clic de nuevo en el campo de texto, pero todas pasarán a ser «Públicas» o «No públicas».

![Formulario de edición por lotes de archivos multimedia, con las opciones descritas anteriormente.](contentfiles/media_batchedit.png)

Además, puede utilizar los botones de la parte inferior del formulario de edición por lotes para **convertir los valores existentes de cualquier propiedad de un tipo de datos a otro**, como por ejemplo, un valor de texto «1900-01-01» en una fecha. 

También puede **añadir propiedades** a cada archivo multimedia:

- Añadir valor de texto
- Añadir valor de recurso
- Añadir valor URI.  

Al seleccionar cualquiera de estas opciones, se añadirá un bloque al formulario en el que podrá seleccionar una propiedad de los vocabularios instalados e introducir el valor de dicha propiedad.

### Eliminación por lotes

Para las **acciones de eliminación**, se abrirá un panel en el lado derecho de la pantalla que le indicará el número de archivos multimedia que se eliminarán. No se eliminará nada hasta que haga clic en el botón rojo «Confirmar eliminación». Esta acción no se puede deshacer. 

Para cancelar la eliminación de los archivos multimedia, haga clic en la «X» situada en la esquina superior derecha del panel de eliminación. Para confirmar una acción de «eliminar todo», marque la casilla «¿Está seguro?» y, a continuación, haga clic en «Confirmar eliminación».

![La advertencia que verán los usuarios cuando todos los archivos multimedia estén a punto de ser eliminados. Hay una casilla que el usuario debe marcar para que el botón situado debajo de ella se active.](contentfiles/media_batchdelwarn.png)

## Tipos de archivos multimedia

Omeka S utiliza etiquetas HTML 5 de audio y vídeo al incrustar audio y vídeo. Esto significa, en general, una mejor compatibilidad con los navegadores más recientes, pero una peor compatibilidad con los más antiguos y, especialmente, con los formatos de vídeo más antiguos.

Al elegir entre unos pocos formatos bien compatibles para archivos de audio y vídeo, puedes ofrecer una experiencia mucho mejor a tus usuarios en diferentes plataformas y dispositivos.

### Vídeo

#### MP4
El contenedor MP4 (.mp4 o .m4v) es el formato de vídeo mejor compatible en todos los navegadores y plataformas. La mejor opción, con diferencia, para que el vídeo funcione bien en diferentes navegadores son los archivos .mp4 con vídeo H.264 y audio AAC.

Los archivos .mp4 pueden contener otros tipos de vídeo (o audio), incluidos los más recientes como H.265 y los más antiguos como MPEG-4 Visual. Cualquier códec de vídeo que no sea H.264 tiene una compatibilidad con los navegadores *mucho* peor.

#### Otros formatos
El contenedor WebM (.webm) con vídeo VP8 o VP9 es compatible con varios navegadores, pero Internet Explorer y Safari son excepciones notables y significativas.

El contenedor Ogg (.ogg, .ogv) y el vídeo Theora son compatibles con algunos navegadores, pero hay poca compatibilidad entre los navegadores móviles y ninguna en absoluto en IE o Safari.

### Audio

#### MP3
El MP3 (.mp3) es uno de los formatos más comunes para audio comprimido y goza de una amplia compatibilidad en todos los navegadores, tanto de escritorio como móviles.

#### AAC

El AAC es un formato algo más reciente que el MP3, pero también es ampliamente compatible con la mayoría de los navegadores. La compatibilidad más amplia se da con el AAC en un contenedor MP4 (que suele llevar la extensión de archivo .m4a), con una compatibilidad algo menor para otros contenedores y formatos (que suelen encontrarse con la extensión .aac).

#### Otros formatos

El audio WAV o WAVE (.wav) es compatible con la mayoría de los navegadores (con la notable excepción de Internet Explorer). La principal desventaja para su uso en la web es que el audio WAV no está comprimido, por lo que ocupa mucho más espacio de almacenamiento y ancho de banda que los formatos comprimidos mencionados anteriormente. Si es posible, es mejor utilizar uno de esos en lugar de WAV.

El audio Ogg Vorbis (.ogg, .oga) es un formato comprimido como el MP3 y el AAC, pero su compatibilidad es mucho menos generalizada. Es de esperar que el audio Vorbis solo funcione en Firefox, Chrome y Android.

Opus (.opus) es uno de los formatos de audio más recientes disponibles. Por el momento, tiene un problema similar al de Vorbis: la falta de compatibilidad entre los navegadores, pero hay indicios de que Opus podría ganar más compatibilidad en el futuro.

### Imágenes

Omeka S admite la mayoría de los tipos de archivos de imagen, incluidos JPEG, PING, TIFF y WEBP. 

Ten en cuenta que la mayoría de los navegadores no muestran de forma nativa archivos TIFF o JPEG2000; Omeka crea imágenes derivadas de los TIFF y JPEG2000 (`.jp2`), en formato JPEG, que se muestran como miniaturas y en las páginas de visualización de elementos/medios. Los usuarios pueden descargar estos tipos de archivo cuando se ofrece el archivo original. 

A partir de la versión 4.1 de Omeka S, el visor de galería Lightbox, utilizado para mostrar medios en su formato original en una interfaz con zoom, puede extraer la imagen derivada de tamaño «grande» en lugar del TIFF o JPEG2000 original, lo que limita la granularidad del zoom. 

La compatibilidad con WEBP es una novedad en Omeka S 4.1. Es posible que las instalaciones existentes que se hayan actualizado a la versión 4.1 deban actualizar la lista de tipos de archivo y extensiones permitidos en la pestaña [Configuración](../admin/settings.md) pulsando los botones «Restaurar» («Restaurar tipos de medios predeterminados» y «Restaurar extensiones predeterminadas»).  

### Formatos heredados
Existen muchos archivos multimedia que no se encuentran en ninguno de los formatos enumerados aquí. Con ciertos complementos o en determinadas plataformas (como Safari en Mac en muchos casos), puede ser posible incrustar algunos de esos archivos con HTML 5, pero es de esperar que muchos o la mayoría de los usuarios no puedan reproducirlos. Los complementos de los navegadores también pueden reproducir muchos tipos de archivos, pero los navegadores están reduciendo y eliminando progresivamente su compatibilidad con este tipo de complementos.

En el caso de los archivos multimedia antiguos, a menudo la mejor opción es simplemente proporcionar un enlace de descarga para que el usuario pueda reproducir o convertir el archivo localmente. Esto es lo que hace Omeka cuando no reconoce un tipo de archivo o cuando un navegador indica que no puede reproducir un archivo.

Los formatos de archivo que dan lugar a un enlace de descarga, en lugar de una reproducción incrustada, incluyen:

- Vídeo: .avi, .wmv
- Audio: .aiff (excepto Safari), .midi, .wha

Si no ves aquí un formato que crees que debería estar, pruébalo y cuéntanos los resultados.
