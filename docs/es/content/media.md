# Archivos multimedia

Omeka S admite la mayoría de archivos y tipos de archivo, y se puede personalizar para que acepte o rechace los tipos de archivo que elijas. Es posible que te interese ajustar el formato de tus archivos multimedia para que se puedan incrustar y reproducir de forma óptima en los navegadores actuales; consulta la [sección «Tipos de archivos multimedia» al final de esta página](#media-file-types). Si tienes dificultades o te aparecen errores de validación de archivos, puedes ajustar los tipos de archivo y las extensiones aceptadas en las [opciones de «Archivos y medios permitidos» de la configuración de seguridad](../admin/settings.md#security).

Los archivos multimedia solo se crean al añadirlos a un elemento; no pueden existir de forma independiente. Si deseas subir archivos que no estén asociados a ningún elemento, como logotipos y banners, consulta la [página «Recursos»](../admin/assets.md).

Para ver los archivos multimedia asociados a un elemento, haz clic en el nombre del archivo multimedia en la barra lateral derecha de la página de visualización del elemento.

Para ver todos los archivos multimedia de la instalación, ve primero a la sección **Elementos**. A continuación, haz clic en la subsección **Archivos multimedia** que aparece debajo de «Elementos» en el panel de navegación de la izquierda.

## Permisos de los archivos multimedia

Cuando un usuario adjunta un archivo multimedia a un elemento, se convierte en el «propietario» de dicho archivo. La mayoría de los niveles de usuario tienen la capacidad de crear archivos multimedia y siempre pueden eliminar sus propios archivos. Solo los niveles superiores pueden eliminar archivos multimedia que sean propiedad de otros.

| Categoría | Permiso | Administrador global | Supervisor | Editor | Revisor | Autor | Investigador |
|-----|-----|---|---|---|---|---|---|
| Elementos y archivos multimedia | Añadir | Sí | Sí | Sí | Sí | Sí | No |
| | Editar | Todos | Todos | Todos | Todos | Los propios | No |
| | Eliminar | Todos | Todos | Todos | Los propios | Los propios | No |
| Anotaciones de valores | Añadir/Editar | Sí | Sí | Sí | Sí | Sí | No |
| Objetos privados | Ver | Sí | Sí | Sí | Sí | No | No |

La propiedad de un archivo multimedia no coincide automáticamente con la propiedad del elemento al que está adjunto. Un administrador global o un supervisor puede cambiar el propietario de un archivo multimedia en la pestaña «Avanzado» del mismo.

Ten en cuenta que, cuando cambias el rol de un usuario, por ejemplo, de «Autor» a «Investigador», este seguirá siendo propietario de los archivos multimedia que creó cuando tenía permiso para hacerlo. Al eliminar a un usuario, sus archivos multimedia quedan huérfanos, es decir, aparecerán como si no tuvieran propietario.

## Ver archivos multimedia
Para explorar los archivos multimedia, primero haz clic en «Elementos» en el panel de navegación de la izquierda. En esa barra lateral, aparecerá una opción para «Archivos multimedia» debajo del botón «Elementos» (puede que tengas que hacer clic en el triángulo para desplegar el menú que hay debajo de «Elementos»).

![La sección «Recursos» de la barra de navegación, con texto azul claro sobre fondo azul oscuro. Debajo de la opción «Elementos», con sangría, aparece una opción de navegación para «Contenidos multimedia». A diferencia de las demás opciones, no tiene ningún icono representativo.](contentfiles/media-browsenav.png)

Los archivos multimedia se muestran en una tabla. Cada archivo multimedia ocupa una fila, con columnas para:

- una casilla de selección para marcar el archivo multimedia
- el **Título**
- iconos para **editar** (lápiz), **eliminar** (papelera) o ver **detalles** (tres puntos)
- la **Clase** del archivo multimedia
- el **Propietario** del archivo multimedia
- y la fecha en que se **creó** el archivo multimedia.

![La tabla de exploración de archivos multimedia muestra 5 elementos. Todos los archivos multimedia tienen títulos que son URL de MediaWiki, y todos son propiedad de la usuaria Megan.](contentfiles/media_browse.png)

Las opciones para navegar y crear elementos se muestran encima de la tabla de elementos:

- A la izquierda aparece el número de páginas de archivos multimedia, con flechas de avance y retroceso. El número de página actual es un campo editable: introduce cualquier número de página válido y pulsa «Retorno» o «Intro» en tu teclado para ir a esa página.
- En la parte superior central hay un botón para la [Búsqueda avanzada](../search.md#media-advanced-search).
- Justo encima de la tabla, a la derecha, hay opciones para ordenar los archivos multimedia, con dos menús desplegables. El primero te permite seleccionar entre **Título**, **Clase**, **Propietario**, **(fecha) de creación** y **Tamaño**; el segundo te permite ordenar de forma ascendente o descendente. Para aplicar la ordenación, haz clic en el botón «Ordenar».

Al hacer clic en el título de cualquier archivo multimedia, accederás a su página de metadatos. Esta página muestra los metadatos en el área de trabajo principal, con una barra lateral a la derecha que enumera la visibilidad, el elemento asociado (un enlace activo), la fecha de creación, el tipo MIME, el tamaño, el ingestor, la fuente y los enlaces a los derivados del archivo.

![Página de visualización de un archivo de imagen. A la derecha de la imagen se encuentra la información de la base de datos del archivo multimedia, incluidos enlaces a diversos derivados, el elemento del que forma parte, el tipo de archivo y el tamaño.](../content/contentfiles/media_view.png)

## Añadir archivos multimedia a un elemento

Los archivos multimedia solo se pueden añadir a través de un [elemento](../content/items.md). Las opciones para añadir archivos multimedia a tus elementos incluyen subir un archivo o adjuntar contenido directamente mediante:

- URL, 
- [oEmbed](https://oembed.com/){target=_blank},
- URL de YouTube,
- una [imagen IIIF](https://iiif.io/api/image/3.0/){target=_blank} mediante URL,
- una [presentación IIIF](https://iiif.io/api/presentation/3.0/){target=_blank} mediante una URL,
- o escribiendo código HTML con el editor HTML.

Para obtener más información sobre oEmbed, [consulta la información sobre cómo utilizar el bloque de página oEmbed en las páginas de tu sitio](../sites/site_pages.md#oembed). 

Para obtener más información sobre IIIF, [consulta la información sobre cómo utilizar los bloques de página IIIF en las páginas de tu sitio](../sites/site_pages.md#iiif-image).

### Describe tus archivos multimedia 

En la fase de añadir archivos multimedia, el único metadato que se puede introducir es el título. Si deseas describir cada archivo con más detalle, puedes editarlo una vez que se haya subido. Si no proporcionas un título, el nombre de archivo original aparecerá como título del archivo multimedia. Ten en cuenta que el nombre de archivo real del recurso multimedia habrá cambiado al subirlo a Omeka S; este nombre de archivo, que se conserva como título, es solo para tu referencia y puede modificarse en cualquier momento.

Puedes subir varios archivos a la vez, añadir varios tipos de archivos multimedia a la vez o añadir más archivos multimedia cada vez que guardes. Aparecerán en el orden en que se hayan subido.

Puedes arrastrar y soltar los archivos multimedia en el orden que prefieras, tanto mientras los añades como una vez que ya se hayan añadido. En la pantalla de edición del elemento, haz clic en la pestaña «Multimedia» y utiliza las barras horizontales situadas a la izquierda de cada archivo para moverlos hacia arriba o hacia abajo en la lista.

### Multimedia principal

Puedes seleccionar un archivo para que sea el **contenido multimedia principal** del elemento. Para ello, ve a la pantalla de edición del elemento, selecciona la pestaña «Contenido multimedia» y utiliza el botón de opción que aparece a la derecha del título de cada archivo para seleccionar uno.

![Un elemento en proceso de edición, en la pestaña «Contenido multimedia», con varios archivos visibles. El primer archivo, un PDF, aparece como el medio principal actual.](../content/contentfiles/media_primary.png)

Esto hará que el medio principal elegido:

- se convierta en la miniatura del elemento (si no se ha seleccionado manualmente una miniatura en la pestaña «Avanzado»), y
- aparecerá como el archivo multimedia principal en presentaciones de diapositivas, vitrinas y otros bloques de página en los que se haya añadido el elemento.

No cambiará el orden de los archivos cuando se muestren en páginas de administración o públicas. Por ejemplo, seleccionar el último archivo como archivo multimedia principal no influirá en el orden de los archivos en el visor de la galería de la página pública del elemento.

Por defecto, el primer archivo multimedia subido (el que aparece en la parte superior de la lista) es el archivo multimedia principal. Si se elimina el archivo multimedia principal elegido, el elemento volverá a utilizar por defecto el archivo que se encuentra en la parte superior de la lista como archivo multimedia principal.

### Miniaturas de archivos multimedia

Las miniaturas se crean automáticamente para muchos tipos de archivo. La creación de miniaturas depende de las capacidades de la [herramienta de miniaturas elegida](../configuration.md#thumbnails) (la predeterminada es ImageMagick) y de los tipos de archivo que pueda procesar. Consulta la herramienta que estés utilizando (como ImageMagick, Imagick o GD) para averiguar qué tipos de archivo admite.

Si deseas que tu elemento tenga una miniatura genérica (como el icono de un libro o una nota musical para un archivo de audio), puedes subir esas imágenes predeterminadas como [recursos](../admin/assets.md) y, a continuación, adjuntarlas manualmente a los archivos mediante la [pestaña «Avanzado» de la pantalla de edición del elemento](../content/items.md#advanced).

Las miniaturas seleccionadas a través de la pestaña «Avanzado» de la pantalla de edición de un elemento (desde la colección de recursos de una instalación) anularán cualquier otra miniatura que se haya generado para el elemento a partir de sus archivos multimedia.

Se crean tres miniaturas para cada elemento con un tipo de archivo multimedia válido: 

- una derivada grande, con la relación de dimensiones original pero con un tamaño máximo del lado más largo de 800 píxeles
- una derivada mediana, con la relación de dimensiones original pero con un tamaño máximo del lado más largo de 200 píxeles
- una miniatura cuadrada, con el lado más corto fijado en 200 píxeles y el lado más largo recortado hasta los 200 píxeles centrales.

La miniatura grande se muestra en la mayoría de las páginas de vista de elementos y de vista de archivos multimedia, con un enlace al archivo original sin editar. Las miniaturas cuadradas o medianas se utilizan, dependiendo del tema y otros ajustes, en las listas de navegación y de resultados de búsqueda, en los marcadores de mapas, etc. Los temas también pueden mostrar estas imágenes con un tamaño inferior al de sus dimensiones de archivo. 

Estas dimensiones son las predeterminadas en todas las instalaciones nuevas de Omeka S, pero [se pueden modificar editando el archivo `config`](../configuration.md#thumbnails). La miniatura cuadrada siempre recortará el lado más largo, y la miniatura mediana siempre se redimensionará por el lado más corto. 

### Tamaños de los archivos

Omeka S no impone ninguna limitación en cuanto al tamaño de los archivos. Sin embargo, es posible que tu servidor tenga restricciones en cuanto al tamaño o la velocidad de subida de archivos, lo que podría estar causando problemas. Estas limitaciones varían de un servidor a otro y no podemos modificarlas por ti. Si tienes algún problema al subir archivos multimedia, consulta primero con tu servicio de alojamiento o con el administrador de tu servidor local.

Para gestionar los archivos multimedia de tu instalación de Omeka S en función del tamaño, puedes acceder a la pestaña «Multimedia» y ordenar los archivos por «Tamaño» y «Descendente». De este modo, los archivos más grandes aparecerán en la parte superior de la tabla; los tamaños de los archivos se indican en bytes. Esto puede ayudarte a identificar recursos para el alojamiento externo o el reformateo derivado, en función de tus necesidades de almacenamiento. 

![La pestaña «Multimedia», con los archivos más grandes en la parte superior de la tabla.](contentfiles/media_sizes.png)


## Editar los metadatos de los archivos multimedia

Para editar archivos multimedia existentes, puedes:

- Ir a la página de exploración de archivos multimedia y hacer clic en el icono del lápiz/editar de la fila correspondiente al archivo
- Ir a la página de exploración de archivos multimedia, hacer clic en el título para ver los metadatos del archivo y, a continuación, hacer clic en el botón «Editar archivo multimedia» situado en la esquina superior derecha
- Hacer clic en el nombre del archivo multimedia en la barra lateral derecha de la página de un elemento para acceder a sus metadatos y, a continuación, hacer clic en «Editar archivo multimedia» desde allí.

Los metadatos generados automáticamente, como la fuente, la fecha de creación y la parte del elemento, no se pueden editar.

La edición de archivos multimedia es muy similar a la edición de [elementos](../content/items.md) o [conjuntos de elementos](../content/item-sets.md).

![Página de edición de un archivo multimedia, sin propiedades cargadas](../content/contentfiles/media_edit.png)

Utiliza el botón **Hacer público/privado** (icono del ojo) para establecer si el archivo multimedia es visible para el público o solo para los usuarios de la instalación de Omeka S.

El archivo multimedia es público: ![Botón «Hacer público» con un icono de ojo](../content/contentfiles/item_public.png){style="display:inline;"}

El recurso multimedia es privado: ![Botón «Hacer privado» con un icono de ojo tachado con una barra diagonal](../content/contentfiles/item_private.png){style="display:inline;"}

Ten en cuenta que, si un elemento es privado, todos los archivos multimedia adjuntos también lo son; sin embargo, un elemento público puede tener archivos multimedia adjuntos que estén configurados como públicos o privados.

### Valores

Si lo deseas, puedes seleccionar una plantilla de recurso en el menú desplegable. Las plantillas de recurso las definen los administradores y editores del sitio.

- Si se utiliza una plantilla de recurso, la clase de contenido multimedia debería cargarse automáticamente.
- Si no se utiliza una plantilla de recurso, puedes seleccionar una clase del menú desplegable (estas se rellenan a partir de los [Vocabularios](vocabularies.md) de tu instalación).

Añade información a las propiedades que se carguen. Si no seleccionas una plantilla de recurso ni una clase, no se cargarán automáticamente otros campos.

Tanto si utilizas una plantilla de recurso como si no, puedes añadir más propiedades al elemento utilizando el panel lateral situado a la derecha de la pantalla. Basta con abrir uno de los vocabularios (Dublin Core, Ontología Bibliográfica, etc.) y hacer clic en la propiedad que desee añadir, o bien puede utilizar el cuadro «Filtrar propiedades» para buscar una propiedad específica (esto resulta útil cuando se dispone de varios vocabularios de gran tamaño).

Al hacer clic en la etiqueta de la propiedad en el panel, esta se añadirá automáticamente al elemento. Si añades una propiedad por error, déjala en blanco y se eliminará del elemento cuando guardes los cambios.

En cada campo puedes añadir texto, un recurso de la instalación o un enlace externo.  

Ten en cuenta que, si añades la propiedad `dcterms:title`, su contenido sustituirá al título generado automáticamente del archivo multimedia. Esto resulta útil al trabajar con URL o archivos multimedia subidos con nombres generados automáticamente.  

Puedes configurar propiedades individuales como **privadas o públicas** utilizando el icono del ojo correspondiente a cada propiedad. Ten en cuenta que las propiedades configuradas como privadas siguen siendo visibles para los administradores globales, los administradores del sitio y los editores. Los autores podrán ver todas las propiedades de los elementos de los que sean propietarios, pero no verán las propiedades privadas creadas por otros usuarios.

En la imagen siguiente, la primera propiedad (Título) es pública, tal y como indica el icono del ojo abierto. La segunda propiedad (Descripción) es privada, tal y como indica el icono del ojo tachado. Al hacer clic o pulsar Intro en el icono del ojo, se alterna entre público y privado.

![Las propiedades individuales tienen un icono de ojo rojo a la derecha que te permite cambiar la visibilidad; una flecha roja señala el icono](contentfiles/items_propviz.png)

#### Texto
Los campos de texto permiten introducir texto sin formato.

Puedes indicar el idioma del contenido de un campo de entrada utilizando el símbolo del globo terráqueo situado encima del campo (véase la flecha roja en la imagen siguiente). Haz clic en el icono del globo terráqueo para activar un campo de texto y, a continuación, introduce el código [ISO 639-1](https://en.wikipedia.org/wiki/List_of_ISO_639-1_codes){target=_blank} del idioma en el que está escrito el texto.

![Un campo de entrada de texto, con un icono de globo terráqueo a la izquierda, resaltado en azul con el cursor activo en el campo. Se está aplicando una etiqueta de idioma de dos letras al contenido del campo de texto que aparece a continuación.](contentfiles/items_lang.png)

#### Recurso de Omeka

Los campos de recursos de Omeka crean un enlace interno entre el recurso que estás creando y el recurso que rellena ese campo.

Tienes la opción de utilizar un elemento o un conjunto de elementos. Al elegir un tipo de recurso, se abrirá un panel lateral en el que podrás explorar todos los recursos de la instalación. Puedes utilizar la función de búsqueda situada en la parte superior del panel para acotar la lista o para encontrar rápidamente un elemento o conjunto de elementos específico.

Si utilizas un recurso de tipo «Elemento» para la propiedad, dispondrás de opciones adicionales para encontrar el elemento que deseas en el panel lateral. Abre estas opciones haciendo clic en el botón con forma de triángulo situado junto a la frase «Filtrar búsqueda».

Esto abrirá un menú debajo del botón con las siguientes opciones para filtrar los elementos del panel lateral:

- Filtrar por clase: un menú desplegable en el que puedes seleccionar cualquier clase proporcionada por los vocabularios de la instalación.
- Filtrar por conjunto de elementos: un menú desplegable en el que puedes limitar los elementos mostrados en el cajón únicamente a aquellos asociados a un conjunto de elementos concreto.
- Filtrar por ID de elemento: un campo de búsqueda en el que puedes introducir el ID del elemento que deseas utilizar. Puedes encontrar el ID de un elemento en la URL de su página de edición; si estás editando el elemento y la URL es `admin/item/11547/edit`, entonces el ID del elemento es 11547.

![opciones descritas anteriormente](contentfiles/items_addresItem.png)

Los recursos de elementos también cuentan con una opción de «Añadir rápidamente». Cuando se activa esta opción, todos los elementos del panel de selección muestran una casilla de selección. Puedes utilizar estas casillas para añadir varios elementos como una misma propiedad de una sola vez. Ten en cuenta que solo se puede editar una propiedad a la vez, por lo que todos los elementos deben rellenar la misma propiedad (por ejemplo, «Creador», «Tiene parte»).

![Una flecha roja señala el botón deslizante de «Añadir rápidamente». Los dos elementos visibles tienen una casilla de selección vacía a la izquierda de su miniatura correspondiente](contentfiles/items_quickadd.png)

Las páginas públicas y de administración de medios no muestran tablas de recursos enlazados.

#### URI

Los campos URI enlazan con un sitio web externo o un recurso en línea. Cada valor URI contiene el propio enlace, y una «Etiqueta» textual opcional para sustituir el URI por algo legible para los usuarios. Por ejemplo, es posible que desees introducir un «Creador» como URI a un vocabulario controlado de artistas o autores, y luego incluir el nombre del creador en texto sin formato como «Etiqueta». Omeka no extraerá automáticamente la información del URI.

#### Anotación de valores

Cuando introduces un valor para una propiedad asociada a un recurso, estás realizando una afirmación sobre ese recurso. Si lo deseas, Omeka te permite realizar afirmaciones sobre esa afirmación. A esto lo llamamos «anotación de valores». La ventaja de la anotación de valores es que puedes optar por concretar datos ambiguos mediante anotaciones sobre aspectos como:

- Procedencia: ¿De dónde procede este dato?
- Tiempo: ¿Cuándo ocurrió este dato?
- Ubicación: ¿Cuál es la ubicación asociada a este dato?
- Certeza: ¿Cuál es el grado de confianza de este dato?
- Tipo: ¿Qué tipo de concepto o entidad es este dato?

En el mundo de los datos enlazados, este proceso se conoce como [reificación](https://www.w3.org/wiki/RdfReification){target=_blank}. Cada valor puede tener cualquier número de anotaciones.

Para crear una anotación, haz clic en los tres puntos situados a la derecha del campo de introducción del valor y, a continuación, haz clic en el icono de anotación (el bocadillo).

![Detalle de un valor con el bocadillo de anotación resaltado](contentfiles/annotation_add.png)

Se abrirá la barra lateral de anotaciones a la derecha. Selecciona cualquier propiedad disponible en la instalación de Omeka S para describir la relación entre la anotación y el valor al que se refiere. Por ejemplo, el valor asociado a la propiedad `dcterms:Contributor` podría anotarse con más detalles sobre la naturaleza de la contribución. O quizá prefieras simplemente incluir una nota utilizando el campo `dcterms:Description`.

Selecciona un tipo de datos para la anotación: un campo de texto, un URI o un recurso de tu instalación de Omeka S. Es posible que los módulos ofrezcan tipos de datos adicionales. Haz clic en el botón «Añadir anotación» y aparecerá un nuevo campo más abajo. Introduce tu anotación. Si lo deseas, puedes hacerlo varias veces para el valor elegido. A continuación, haz clic en «Establecer anotaciones» para finalizar el proceso.

![Imagen de la barra lateral de anotaciones de valor con una propiedad seleccionada y una anotación incluida](contentfiles/annotation_sidebar.png)

[Cada sitio dispone de una configuración](../sites/site_settings.md#show) para indicar si las anotaciones de valor son visibles para el público o no. Esto incluirá las anotaciones de valor en los elementos y en los conjuntos de elementos.

Puedes configurar vocabularios controlados para las anotaciones utilizando el [módulo Custom Vocab](../modules/customvocab.md). En este caso, no es necesario aplicar un vocabulario personalizado a una propiedad mediante una plantilla de recursos; puedes seleccionar cualquier vocabulario instalado en el menú desplegable «tipo de valor» del panel lateral. Esto cargará las opciones de tu vocabulario en un menú desplegable de términos.

### Avanzado

#### Miniatura

No todos los archivos multimedia generan miniaturas elegantes, por ejemplo, los documentos PDF o de texto, o algunos archivos de vídeo. Puedes utilizar esta opción para establecer una miniatura representativa del archivo multimedia, que se utilizará en las páginas de exploración, pero no en la página del elemento ni en la de sus archivos multimedia.

Los recursos que selecciones o subas como miniaturas en esta pestaña son los mismos que los creados para los [logotipos del sitio](../admin/assets.md). Una miniatura subida como recurso estará disponible para todos los usuarios de todos los sitios. Si deseas subir un fotograma de un vídeo como miniatura para un vídeo específico, quizá te interese subirlo como archivo multimedia adjunto al elemento en lugar de como recurso.

Para asignar un recurso como miniatura, haz clic en el botón «Seleccionar» en el área de trabajo principal de la pestaña. Esto abrirá un panel deslizante en el lado derecho.

![Panel deslizante de selección con opción de subir archivos y dos recursos, ambos imágenes.](contentfiles/media_thumbnail1.png)

El panel ofrece dos opciones: subir un archivo mediante el navegador o seleccionar uno de los recursos existentes. Para seleccionar un recurso existente, basta con hacer clic en él y se asignará automáticamente al contenido multimedia.

![La ventana de edición del contenido multimedia está abierta en la pestaña «Avanzado», donde aparece en el área de trabajo principal un recurso que es una imagen de un mapa del National Mall. Debajo hay botones para «Seleccionar» y «Borrar»](contentfiles/media_thumbnail2.png)

Para eliminar un recurso que hayas asignado como miniatura, haz clic en el botón «Borrar» situado debajo de la imagen del recurso. Para sustituirlo, haz clic en «Seleccionar» y elige o sube un nuevo recurso de miniatura.

#### Propietario

Puedes asignar un propietario al contenido multimedia seleccionándolo en el menú desplegable.

#### Texto alternativo

Puedes proporcionar un texto alternativo para todos los archivos multimedia escribiendo un texto descriptivo en el campo de entrada.

![Edición de archivos multimedia: pestaña «Avanzado» abierta, mostrando el campo de entrada «Texto alternativo»](contentfiles/media_alttext.png)

#### Idioma

Puedes indicar el idioma de un archivo multimedia introduciendo en este campo el código de idioma de dos letras [ISO 639-1](https://en.wikipedia.org/wiki/List_of_ISO_639-1_codes){target=_blank}. Este campo no admite varios valores.

## Acciones por lotes

Desde la página de exploración de archivos multimedia (`admin/media`), puedes editar archivos multimedia por lotes utilizando el menú desplegable situado a la izquierda, junto a los botones de paginación. Puedes seleccionar manualmente los archivos multimedia para la edición por lotes mediante las casillas de selección de la izquierda, o seleccionar todos los archivos multimedia de la página, o utilizar el menú desplegable para editar todos los archivos multimedia que se encuentran actualmente en el subconjunto.

Los editores, supervisores y administradores globales pueden editar y eliminar de forma masiva todos los archivos multimedia de la instalación. Los usuarios con permisos de nivel de autor pueden editar o eliminar de forma masiva sus propios archivos multimedia, pero no los de otros usuarios. En este caso, al seleccionar todos los archivos multimedia de la página, o al seleccionar todos los archivos multimedia, solo se incluirán aquellos de los que sean propietarios. Los usuarios con nivel de «Revisor» no pueden eliminar en bloque todos los recursos, pero sí pueden eliminar en bloque los recursos seleccionados.

![Una flecha roja señala el menú desplegable de opciones de edición y eliminación en bloque](contentfiles/media_batch1.png)

Las acciones en bloque son las siguientes:  

- Editar los seleccionados: editar solo los archivos multimedia seleccionados en la página
- Editar todo: edita todos los archivos multimedia mostrados en una búsqueda (por defecto, todos los archivos multimedia)
- Eliminar los seleccionados: elimina solo los archivos multimedia seleccionados en la página
- Eliminar todo: elimina todos los archivos multimedia mostrados en una búsqueda (por defecto, todos los archivos multimedia).

El número de resultados por página se configura en la [configuración global de la instalación](../admin/settings.md#general).

Primero puedes utilizar el enlace «🔍 Búsqueda avanzada» para reducir los archivos multimedia a un subconjunto que desees editar. Por ejemplo, puedes utilizar la [Búsqueda avanzada](../search.md#media-advanced-search) para limitar la búsqueda a archivos multimedia de un tipo MIME específico o a archivos multimedia que pertenezcan a un usuario concreto.

Si realizas una búsqueda, volverás a ver la página de exploración, con los parámetros seleccionados apareciendo en la parte superior de la pantalla. Desde esta pantalla de exploración puedes seleccionar manualmente los archivos multimedia para su edición por lotes utilizando las casillas de selección de la izquierda, seleccionar todos los archivos multimedia de la página o utilizar el menú desplegable para editar todos los archivos multimedia que se encuentran actualmente en el subconjunto.

Si completas una acción por lotes desde la siguiente pantalla, volverás a este mismo subconjunto de archivos multimedia.

### Edición por lotes

La edición por lotes de archivos multimedia te lleva a una nueva página. Los archivos multimedia que se están editando se mostrarán en el lado derecho, en un panel deslizante. Asegúrate de que el número de archivos multimedia que se están editando es correcto.

El formulario de edición por lotes te ofrece las siguientes opciones:  

- **Establecer visibilidad**: un botón de opción. Selecciona «público» o «no público» para que el archivo sea visible o no para los usuarios que no hayan iniciado sesión.
- **Establecer plantilla**: un menú desplegable. Selecciona una de las plantillas de recursos de la instalación. Puedes eliminar plantillas de los elementos seleccionados con la opción «[Desactivar plantilla]». Aparecerá una barra de búsqueda en la parte superior del menú desplegable si deseas escribir algo para buscar.
- **Establecer clase**: un menú desplegable. Seleccione una de las clases de los vocabularios instalados. Puede eliminar todas las clases de los archivos seleccionados con la opción «[Desactivar clase]». Aparecerá una barra de búsqueda en la parte superior del menú desplegable si desea escribir algo para buscar.
- **Establecer propietario**: un menú desplegable. Selecciona entre los usuarios de la instalación para elegir quién debe establecerse como propietario de los archivos multimedia seleccionados. Cambiar la propiedad de los archivos multimedia no modificará la propiedad de los elementos asociados. La propiedad determina [quién puede editar y eliminar esos archivos multimedia](#media-permissions), al margen de los [niveles de permiso de usuario](../admin/users.md#roles-and-permissions) superiores.
- **Borrar idioma**: una casilla de selección para eliminar la configuración de idioma existente.
- **Establecer idioma**: un campo de texto. Introduce un código de idioma de dos letras [ISO 639-1](https://en.wikipedia.org/wiki/List_of_ISO_639-1_codes){target=_blank}. Aquí solo puedes indicar un idioma.
- **Borrar valores de propiedad**: un menú desplegable y un campo de texto, con todas las propiedades de todos los vocabularios. Al seleccionar una opción, se eliminarán todos los valores de esa propiedad en los archivos multimedia afectados. Puedes eliminar varios valores de propiedad a la vez: haz clic de nuevo en el campo de texto para ver las opciones restantes.
- **Establecer visibilidad del valor**: un menú desplegable y un campo de texto, con botones de opción. Establece la visibilidad de una o varias propiedades específicas como «pública» o «no pública». A diferencia de los botones de opción situados en la parte superior del formulario, esto solo afectará a uno o varios campos de metadatos, en lugar de a todo el contenido multimedia (por ejemplo, es posible que desees ocultar el valor «Creador» en algunos contenidos multimedia públicos). Selecciona una propiedad en el campo de texto (escribe para iniciar la búsqueda) y, a continuación, elige el botón de opción «Público» o «No público» para esta opción. Puedes añadir varias propiedades haciendo clic de nuevo en el campo de texto, pero todas pasarán a ser «Públicas» o «No públicas».

![Formulario de edición por lotes de archivos multimedia, con las opciones descritas anteriormente.](contentfiles/media_batchedit.png)

Además, puede utilizar los botones situados en la parte inferior del formulario de edición por lotes para **convertir los valores existentes de cualquier propiedad de un tipo de datos a otro**, como, por ejemplo, un valor de texto «1900-01-01» en una fecha. 

También puedes **añadir propiedades** a cada archivo multimedia:

- Añadir valor de texto
- Añadir valor de recurso
- Añadir valor URI.  

Al seleccionar cualquiera de estas opciones, se añadirá un bloque al formulario en el que podrás seleccionar una propiedad de los vocabularios instalados e introducir el valor correspondiente a dicha propiedad.

### Eliminación por lotes

En el caso de las **acciones de eliminación**, se abrirá un panel en la parte derecha de la pantalla que te indicará el número de elementos multimedia que se eliminarán. No se eliminará nada hasta que hagas clic en el botón rojo «Confirmar eliminación». Esta acción no se puede deshacer. 

Para cancelar la eliminación de los archivos multimedia, haz clic en la «X» situada en la esquina superior derecha del panel de eliminación. Para confirmar la acción «eliminar todo», marca la casilla «¿Estás seguro?» y, a continuación, haz clic en «Confirmar eliminación».

![La advertencia que verán los usuarios cuando estén a punto de eliminarse todos los archivos multimedia. Hay una casilla que el usuario debe marcar para que el botón situado debajo de ella se active.](contentfiles/media_batchdelwarn.png)

## Tipos de archivos multimedia

Omeka S utiliza etiquetas de audio y vídeo HTML 5 al incrustar archivos de audio y vídeo. Esto suele suponer una mejor compatibilidad con los navegadores más recientes, pero una peor compatibilidad con los más antiguos y, especialmente, con los formatos de vídeo más antiguos.

Al elegir entre unos pocos formatos bien compatibles para archivos de audio y vídeo, puedes ofrecer una experiencia mucho mejor a tus usuarios en diferentes plataformas y dispositivos.

### Vídeo

#### MP4
El contenedor MP4 (.mp4 o .m4v) es el formato de vídeo mejor compatible con todos los navegadores y plataformas. La mejor opción, con diferencia, para que el vídeo funcione bien en diferentes navegadores son los archivos .mp4 con vídeo H.264 y audio AAC.

Los archivos .mp4 pueden contener otros tipos de vídeo (o audio), incluidos los más recientes, como H.265, y los más antiguos, como MPEG-4 Visual. Cualquier códec de vídeo que no sea H.264 tiene una compatibilidad *mucho* peor con los navegadores.

#### Otros formatos
El contenedor WebM (.webm) con vídeo VP8 o VP9 es compatible con varios navegadores, pero Internet Explorer y Safari son excepciones notables y significativas.

El contenedor Ogg (.ogg, .ogv) y el vídeo Theora son compatibles con algunos navegadores, pero cuentan con escasa compatibilidad entre los navegadores móviles y ninguna en absoluto en IE o Safari.

### Audio

#### MP3
El MP3 (.mp3) es uno de los formatos más comunes para audio comprimido y goza de una amplia compatibilidad en todos los navegadores, tanto en ordenadores de sobremesa como en dispositivos móviles.

#### AAC

El AAC es un formato algo más reciente que el MP3, pero también es ampliamente compatible con la mayoría de los navegadores. La compatibilidad más amplia se da con el AAC en un contenedor MP4 (que suele llevar la extensión de archivo .m4a), mientras que la compatibilidad es algo menor con otros contenedores y formatos (que suelen encontrarse con la extensión .aac).

#### Otros formatos

El audio WAV o WAVE (.wav) es compatible con la mayoría de los navegadores (con la notable excepción de Internet Explorer). El principal inconveniente para su uso en la web es que el audio WAV no está comprimido, por lo que ocupa mucho más espacio de almacenamiento y ancho de banda que los formatos comprimidos mencionados anteriormente. Si es posible, es mejor utilizar uno de esos formatos en lugar de WAV.

El audio Ogg Vorbis (.ogg, .oga) es un formato comprimido como el MP3 y el AAC, pero su compatibilidad es mucho menos generalizada. Es probable que el audio Vorbis solo funcione en Firefox, Chrome y Android.

Opus (.opus) es uno de los formatos de audio más recientes disponibles. Por el momento, presenta un problema similar al de Vorbis: la falta de compatibilidad entre los navegadores, pero hay indicios de que Opus podría ganar más compatibilidad en el futuro.

### Imágenes

Omeka S admite la mayoría de los tipos de archivos de imagen, incluidos JPEG, PING, TIFF y WEBP. 

Ten en cuenta que la mayoría de los navegadores no muestran de forma nativa archivos TIFF o JPEG2000; Omeka crea imágenes derivadas de los archivos TIFF y JPEG2000 (`.jp2`), en formato JPEG, que se muestran como miniaturas y en las páginas de visualización de elementos y contenidos multimedia. Los usuarios pueden descargar estos tipos de archivo cuando se ofrece el archivo original. 

A partir de la versión 4.1 de Omeka S, el visor de galería Lightbox, utilizado para mostrar contenidos multimedia en su formato original en una interfaz con función de zoom, puede utilizar la imagen derivada de tamaño «grande» en lugar del TIFF o JPEG2000 original, lo que limita la precisión del zoom. 

La compatibilidad con WEBP es una novedad en Omeka S 4.1. Es posible que las instalaciones existentes que se hayan actualizado a la versión 4.1 tengan que actualizar la lista de tipos de archivo y extensiones permitidos en la pestaña [Configuración](../admin/settings.md) pulsando los botones «Restaurar» («Restaurar tipos de medios predeterminados» y «Restaurar extensiones predeterminadas»).  

### Formatos heredados
Existen muchos archivos multimedia que no se encuentran en ninguno de los formatos enumerados aquí. Con determinados complementos o en ciertas plataformas (como Safari en Mac en muchos casos), es posible incrustar algunos de esos archivos con HTML5, pero hay que tener en cuenta que muchos o la mayoría de los usuarios no podrán reproducirlos. Los complementos del navegador también pueden reproducir muchos tipos de archivos, pero los navegadores están reduciendo y eliminando progresivamente su compatibilidad con este tipo de complementos.

En el caso de los archivos multimedia antiguos, a menudo la mejor opción es simplemente ofrecer un enlace de descarga para que el usuario pueda reproducir o convertir el archivo localmente. Esto es lo que hace Omeka cuando no reconoce un tipo de archivo o cuando un navegador indica que no puede reproducir un archivo.

Entre los formatos de archivo que dan lugar a un enlace de descarga, en lugar de una reproducción integrada, se incluyen:

- Vídeo: .avi, .wmv
- Audio: .aiff (excepto Safari), .midi, .wha

Si echas en falta algún formato que crees que debería aparecer en esta lista, pruébalo y cuéntanos los resultados.
