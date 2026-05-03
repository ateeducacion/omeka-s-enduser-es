# Elementos

Los elementos son los componentes básicos del sistema Omeka.

Los elementos no tienen por qué representar objetos físicos (fotografías, mapas, libros), ni tienen por qué tener [archivos multimedia adjuntos](media.md) (un escaneo de una foto, imágenes de varias páginas o un PDF). Un elemento puede utilizarse como un nodo, es decir, una forma de representar a una persona, un lugar o una cosa. Puedes utilizar los elementos y sus clases para crear tipos distintos de nodos que se adapten a los fines de tus sitios.

Los elementos pueden vincularse a otros elementos, o incluirse en conjuntos de elementos, para representar relaciones complejas. Por ejemplo, un elemento utilizado como ubicación puede vincularse a elementos que representen eventos que tuvieron lugar en esa ubicación, y los elementos de evento pueden vincularse a elementos de personas que asistieron a ese evento, quienes a su vez están vinculados a elementos de texto que crearon, o a elementos fotográficos en los que aparecen. Todos estos elementos pueden agruparse en conjuntos de elementos superpuestos que representen jurisdicciones que contengan ubicaciones, eventos y personas durante un periodo de tiempo concreto. O bien, puede utilizar conjuntos de elementos para representar a personas, que contengan sus obras creadas como elementos, y vincular esos conjuntos de elementos de personas a eventos y fotografías.

Muchas de estas clases, así como numerosas plantillas de recursos que le ayudarán a describir estos tipos de elementos, ya existen en una instalación básica de Omeka S, pero puede modificarlas y añadir más según sea necesario.

## Permisos de elementos

Cuando un usuario crea un elemento, se convierte en el «propietario» de ese elemento. La mayoría de los niveles de usuario tienen la capacidad de crear elementos y siempre pueden eliminar sus propios elementos. Solo los niveles superiores pueden eliminar elementos que pertenecen a otros.

| Categoría | Permiso | Administrador global | Supervisor | Editor | Revisor | Autor | Investigador |
|-----|-----|---|---|---|---|---|---|
| Elementos y medios | Añadir | Sí | Sí | Sí | Sí | Sí | No |
| | Editar | Todos | Todos | Todos | Todos | Los propios | No |
| | Eliminar | Todos | Todos | Todos | Los propios | Los propios | No |
| Anotaciones de valor | Añadir/Editar | Sí | Sí | Sí | Sí | Sí | No |
| Objetos privados | Ver | Sí | Sí | Sí | Sí | No | No |

Tenga en cuenta que cuando cambie el rol de un usuario, por ejemplo, de Autor a Investigador, seguirá siendo propietario de los elementos que creó cuando tenía permiso para hacerlo. Los elementos no se transfieren. Al eliminar un usuario, sus elementos quedan huérfanos: aparecerán como si no tuvieran propietario. Actualmente no es posible buscar ni editar por lotes elementos sin propietario, por lo que la mejor práctica es reasignar estos elementos antes de eliminar la cuenta de usuario.

### Permisos de sitio para los elementos

Todos los elementos de una instalación de Omeka S están disponibles para ser añadidos a todos los sitios, pero deben añadirse a un sitio de forma manual o mediante configuraciones específicas del usuario o del sitio.

Cada sitio puede configurarse para que se le añadan automáticamente todos los elementos nuevos.

Cada usuario puede tener [uno o más sitios a los que añadir siempre elementos nuevos de forma predeterminada](../admin/users.md#user-settings). Si un usuario tiene un sitio configurado como sus «Sitios predeterminados para elementos», también debe añadirse al sitio como Creador o Gestor para que esa configuración funcione.

| Categoría | Permiso | Administrador del sitio | Creador del sitio | Visor del sitio | Administrador global | Supervisor |
|-----|-----|---|---|---|---|---|
| Elementos | Añadir al sitio | Sí | Sí (por defecto), manualmente no | No | Sí | Sí |
| | Eliminar del sitio | Sí | No | No | Sí | Sí |

### Vistas públicas de los elementos

Los elementos de un sitio Omeka se pueden explorar desde la página «Explorar elementos», que se añade automáticamente a la navegación de cada sitio al crearlo. Los elementos individuales, una vez añadidos al conjunto de recursos de un sitio, mostrarán una página de vista de elemento individual. El diseño de esta página se configura en la pestaña «Tema», utilizando el botón «Configurar páginas de recursos». 

Por defecto, la página de visualización del elemento muestra el título del elemento en la parte superior, seguido de una representación de cualquier archivo multimedia adjunto al elemento y, a continuación, los valores de las propiedades en forma de texto.

![Página de configuración de la página de recursos de un elemento de un sitio recién creado, con las opciones predeterminadas activadas.](contentfiles/items_configurePage.png)

Cualquier bloque de página añadido a una de las regiones disponibles en el tema solo se mostrará en la página de vista de un elemento individual si tiene contenido; de lo contrario, permanecerá oculto.

![Una página de vista de un elemento que muestra la configuración predeterminada con un título, un elemento multimedia y algunos metadatos.](contentfiles/items_publicPage.png)

## La pestaña «Elementos»

Los elementos se enumeran en la pestaña **Elementos** (con el icono de un cuadro) en el panel de navegación de la izquierda del panel de administración.

![Vista básica de la página de elementos de administración, que muestra varios recursos de elementos](contentfiles/items_browse.png)

Cada elemento aparece como una fila, con columnas para:

- el **Título**
- iconos para **editar** (lápiz), **eliminar** (papelera) o **detalles** (tres puntos)
- la **Clase**
- el **Propietario** del elemento
- la fecha en que se **creó** el elemento. 

En la esquina superior derecha de la pantalla de elementos se encuentra el botón «Añadir nuevo elemento».

Las opciones para navegar y crear elementos se encuentran en el encabezado de la tabla de elementos.

- En el lado izquierdo se encuentran los controles para las páginas de elementos, con flechas de avance y retroceso, y un cuadro editable para el número de página actual: introduce un número de página válido y pulsa Intro para ir a esa página.

- En el centro hay un enlace a [Búsqueda avanzada](../search.md#item-advanced-search).

- A la derecha se encuentran las opciones para ordenar la tabla de elementos, con dos menús desplegables. Por defecto, los elementos de la tabla se ordenan con los añadidos más recientemente en la parte superior (Creados y Descendente). El primero te permite seleccionar entre **Título**, **Identificador**, **Clase**, **Propietario** y **(Fecha) de creación**; el segundo te permite ordenar de forma ascendente (A-Z o de más antiguo a más reciente) o descendente (Z-A o de más reciente a más antiguo). Para aplicar la ordenación, haz clic en el botón «Ordenar».

Entre estos y la tabla, a la izquierda, hay un menú desplegable para acciones por lotes, que incluye editar seleccionados, editar todo, eliminar seleccionados y eliminar todo.

## Ver elementos

Para ver rápidamente la información básica sobre un elemento, haz clic en el botón **Detalles** (tres puntos) en la fila del elemento, situado junto a los botones de editar y eliminar. Esto abrirá un panel a la derecha de la lista que muestra el título del elemento, la descripción, el número de identificación de Omeka, la visibilidad, los conjuntos de elementos, los sitios en los que se utiliza y los archivos multimedia adjuntos. Los enlaces a los conjuntos de elementos y a los sitios le llevarán a la página de administración correspondiente; el icono de flecha situado a la derecha de cada enlace de sitio le llevará a la vista pública de ese elemento en ese sitio. 

Para ver un elemento concreto con más detalle, haz clic en su título en la tabla de exploración de elementos o al visualizar sus detalles.

![Vista de exploración de elementos, con los detalles abiertos del elemento «Informe anual 2012-2013» en el panel de la derecha.](contentfiles/items_detailview.png)

Al visualizar un elemento individual, hay pestañas para los **metadatos** del elemento y sus **recursos vinculados**. El lado derecho de la página muestra los medios del elemento, cualquier **sitio** y **conjunto de elementos** al que pertenezca, su fecha de creación, propietario y visibilidad.

### Recursos vinculados

Los **recursos vinculados** de un elemento son otros recursos de Omeka (elementos, conjuntos de elementos o archivos multimedia) que están [vinculados a este elemento a través de sus propiedades](#omeka-resource). Tenga en cuenta que esta sección solo muestra los recursos que se han vinculado *a* este elemento (que lo tienen como propiedad); los recursos que están vinculados *desde* este elemento se mostrarán en la propiedad que completan.

Los recursos vinculados se agrupan por la propiedad para la que utilizan el elemento actual. En el ejemplo siguiente, el elemento actual «William Shakespeare» se utiliza para las propiedades «Creador», «Referencias» y «Lista de autores» de los recursos vinculados. 

Puede filtrar los recursos vinculados para mostrar solo aquellos que hacen referencia a una propiedad específica utilizando el menú desplegable «Filtrar por propiedad». Solo se mostrarán las propiedades que estén en uso.

![Vista de recursos vinculados al elemento para William Shakespeare, con seis obras que utilizan a Shakespeare como Creador, el elemento Folger Shakespeare Library listado como «referencias» de Shakespeare, y el Globe Theatre que utiliza a Shakespeare para la «lista de autores». Cada grupo de propiedades se encuentra en un rectángulo independiente, encabezado por la propiedad a la que se hace referencia.](contentfiles/items_linked.png)

Cuando se visualiza un recurso en un sitio público, los recursos vinculados se muestran en una serie de tablas basadas en la propiedad de metadatos en uso. Los recursos se ordenan por tipo de recurso (elemento, conjunto de elementos o medio) y solo se muestra un tipo a la vez. Un recurso sin recursos vinculados no mostrará estas tablas. Las tablas se pueden incluir, excluir o reorganizar mediante [la configuración del tema del sitio, en «Configurar páginas de recursos»](../sites/site_theme.md#configure-resource-pages).

Un recurso con enlaces a otros recursos que no estén incluidos en el sitio público en cuestión mostrará de todos modos esos recursos no incluidos. Esos recursos vinculados parecerán formar parte del sitio (es decir, se puede hacer clic en ellos para ver las páginas de elementos y conjuntos de elementos). [Esta configuración se puede desactivar para cada sitio](../sites/site_settings.md#show). Cuando se excluyen los recursos ajenos al sitio, los valores de metadatos del elemento y las tablas de recursos vinculados no mostrarán los recursos de Omeka excluidos.

Ten en cuenta que las páginas multimedia no muestran tablas de recursos vinculados, independientemente de si los elementos enlazan con ellas o no.

El siguiente elemento tiene varios recursos de Omeka incluidos en su propiedad «Colaboradores», que se muestran como parte de sus metadatos. También tiene esos mismos elementos que enlazan con él, lo cual se muestra en la tabla de recursos vinculados.

![Visualización de un elemento en el tema predeterminado que muestra varios recursos de Omeka como «Colaboradores» y varios elementos de Omeka que enlazan con el elemento como «Publicaciones»](contentfiles/items_linkedresources.png)

La visualización de los recursos vinculados en las páginas de recursos se puede configurar en cada sitio. Haga clic en «Tema» y, a continuación, en el botón que dice «[Configurar páginas de recursos](../sites/site_theme.md#configure-resource-pages)», y luego decida si desea mostrar las tablas de «Recursos vinculados» para cada recurso y en qué lugar. 

También puede controlar si los recursos vinculados mostrarán esos enlaces incluso cuando [los recursos en cuestión no estén incluidos en el sitio en cuestión](../sites/site_resources.md). En [Configuración del sitio, en la sección «Mostrar»](../sites/site_settings.md#show), encontrará una casilla de verificación para «Excluir recursos que no estén en el sitio». 

## Añadir un elemento

Para añadir un nuevo elemento, empieza seleccionando el botón «Añadir nuevo elemento».

Antes de crear elementos, es posible que los supervisores quieran crear [plantillas de recursos](resource-template.md), que cargarán campos específicos para diversos tipos de elementos.

### Valores

La pestaña Valores es donde se introducen los metadatos, como el título, la descripción, etc.

![Vista básica de la página de añadir elementos, sin contenido introducido](contentfiles/items_add.png)

Puede seleccionar una plantilla de recursos en el menú desplegable. Las plantillas de recursos las definen los supervisores y los editores.

- Si utiliza una plantilla de recursos, la clase del elemento debería cargarse automáticamente.
- Si no utiliza una plantilla de recursos, puede seleccionar una clase del menú desplegable (estas se rellenan a partir de los [Vocabularios](vocabularies.md) de su instalación).

Añada información a las propiedades que se carguen. Si no selecciona una plantilla de recursos ni una clase, las propiedades de Dublin Core Título y Descripción se cargarán automáticamente.  

Tanto si utiliza una plantilla de recursos como si no, puede añadir más propiedades al elemento utilizando el panel situado en la parte derecha de la pantalla. Basta con abrir uno de los vocabularios (Dublin Core, Ontología Bibliográfica, etc.) y hacer clic en la propiedad que desee añadir, o bien puede utilizar el cuadro «Filtrar propiedades» para buscar una propiedad específica (esto resulta útil cuando se dispone de varios vocabularios de gran tamaño).

![Primer plano del panel de la derecha con el texto «date» introducido en el cuadro de filtro de propiedades y una serie de propiedades que contienen la palabra «date» cargadas desde Dublin Core y Bibliographic Ontology](contentfiles/items_filterprop.png)

Al hacer clic en la etiqueta de la propiedad en el panel, esta se añadirá automáticamente al elemento. Si añades una propiedad por error, déjala en blanco y se eliminará del elemento cuando guardes los cambios.

Puede añadir texto, un recurso de la instalación o un enlace externo en cada campo.

Puede configurar propiedades individuales como **privadas o públicas** utilizando el icono del ojo de cada propiedad. Tenga en cuenta que las propiedades configuradas como privadas siguen siendo visibles para los administradores globales, supervisores y editores. Los autores podrán ver todas las propiedades de los elementos que les pertenecen, pero no verán las propiedades privadas creadas por otros usuarios.

En la imagen siguiente, la primera propiedad (Título) es pública, tal y como indica el icono del ojo abierto. La segunda propiedad (Descripción) es privada, tal y como indica el icono del ojo tachado. Al hacer clic o pulsar Intro en el icono del ojo, se alterna entre público y privado.

![Como se describe](contentfiles/items_propviz.png)

Si tienes varios valores para una propiedad, puedes **reordenarlos** arrastrando y soltando. Haz clic en la barra situada a la izquierda del valor para seleccionarlo y arrástralo hasta la posición que desees.

![Primer plano de la propiedad «Asunto» con dos valores. Un círculo rojo muestra la ubicación de la barra de selección del valor.](contentfiles/items_valuereorder.png)

#### Texto
Los campos de texto permiten introducir texto sin formato. No se permite el uso de marcado en estos campos (por ejemplo, Markdown, HTML).

![Imagen de un campo de entrada de texto con el icono del teclado que indica la introducción de texto, el icono del globo terráqueo para configurar el idioma y un icono de papelera para borrar](contentfiles/items_textedit.png)

Puede indicar el idioma del contenido de un campo de entrada de texto utilizando el símbolo del globo terráqueo situado encima del campo (véase la imagen a continuación). Haga clic en el globo terráqueo para activar un campo de texto y, a continuación, introduzca el código [etiqueta de idioma de dos letras de la IETF](https://en.wikipedia.org/wiki/IETF_language_tag){target=_blank} correspondiente al idioma en el que está escrito el texto.

![Un campo de entrada de texto, con un icono de globo terráqueo a la izquierda, resaltado en azul con el cursor activo en el campo. Se está aplicando una etiqueta de idioma de dos letras al contenido del campo de texto de abajo.](contentfiles/items_lang.png)

#### Recurso de Omeka

Al elegir un recurso de Omeka como valor de metadatos, se crea un [enlace interno entre el recurso que estás creando y el recurso que rellena ese campo](#linked-resources). 

Al crear un elemento, tienes la opción de utilizar otro elemento o un conjunto de elementos. Si el elemento tiene archivos multimedia adjuntos, también puede elegir entre esos archivos, no entre otros archivos multimedia de la instalación. 

Al seleccionar un tipo de recurso, se abrirá un panel lateral donde podrá explorar todos los recursos de la instalación. Puede utilizar la función de búsqueda situada en la parte superior del panel para filtrar la lista o encontrar rápidamente un recurso específico. 

Una vez seleccionado un recurso, se cargará información detallada, y deberá hacer clic en «Seleccionar recurso» para finalizar la vinculación de los recursos. También puede hacer clic en el botón «X» de la esquina superior derecha para volver a la lista de recursos.

![Interfaz de edición de elementos, con el valor de la propiedad «Recurso de Omeka» añadido a la propiedad Descripción. Los botones «Elementos» y «Conjuntos de elementos» están resaltados dentro de un cuadrado rojo. El panel de la derecha está abierto en el menú «Seleccionar elemento», con una lista de elementos entre los que elegir.](contentfiles/items_addresource.png)

Si utiliza un recurso de **Elemento** para la propiedad, podrá seleccionar un elemento existente o crear un esbozo de un nuevo elemento. 

Si desea utilizar un elemento existente como valor, tendrá tres opciones para encontrar el elemento que desea en el panel. Abra estas opciones haciendo clic en el botón triangular situado junto a la frase «Filtrar búsqueda». Esto abrirá un menú con las siguientes opciones para filtrar los elementos del panel:

- Filtrar por clase: un menú desplegable en el que puede seleccionar cualquier clase proporcionada por los vocabularios de la instalación.
- Filtrar por conjunto de elementos: un menú desplegable en el que puede limitar los elementos mostrados en el panel a solo aquellos asociados a un conjunto de elementos concreto.
- Filtrar por ID de elemento: un campo de texto donde puede introducir el ID del elemento que desea utilizar. Puede encontrar el ID de un elemento en la URL de su página de edición; si está editando el elemento y la URL es `admin/item/11547/edit`, entonces el ID del elemento es 11547. El ID de un elemento también aparecerá en el panel de la derecha de su página de vista. No se puede introducir un rango ni buscar por un número parcial o un comodín, solo por el ID exacto.

Una vez que introduzcas algo en un filtro, debes hacer clic en el icono de la lupa de la barra de búsqueda para aplicar los filtros.

![opciones descritas anteriormente](contentfiles/items_addresItem.png)

Los recursos de los elementos también tienen una opción de «Añadir rápidamente». Cuando se activa esta opción, todos los elementos del panel tienen una casilla de verificación. Puede utilizar estas casillas para añadir varios elementos como una propiedad a la vez. Tenga en cuenta que solo puede editar una propiedad a la vez, por lo que todos los elementos deben rellenar la misma propiedad (por ejemplo, «Creador», «Tiene parte»).

![una flecha roja señala el botón deslizante de «Añadir rápidamente». Los dos elementos visibles tienen una casilla de verificación vacía a la izquierda de su miniatura representativa](contentfiles/items_quickadd.png)

Si deseas crear un nuevo elemento, puedes crear un esbozo para ese elemento directamente en el cajón seleccionando la opción Crear un elemento. A continuación, se te mostrará un formulario de creación de elementos abreviado en el que podrás seleccionar:

- Plantilla de recurso
- Clase
- Visibilidad para el nuevo elemento.

También puede introducir valores para dos campos básicos:
- Título
- Descripción.

Una vez que haya completado el formulario, puede añadir el esbozo del elemento y, simultáneamente, seleccionarlo como entrada para la propiedad. Puede volver al elemento marcador de posición para completar su descripción más adelante.

![El formulario de creación de esbozo de elemento está abierto en el panel, mostrando el menú desplegable para las opciones de Plantilla de recurso, Clase y Visibilidad, y los campos de entrada para Título y Descripción](contentfiles/items_createItemStub.png)

Si está utilizando un recurso de **Conjunto de elementos** para la propiedad, tendrá dos opciones para encontrar el conjunto de elementos que desea en el panel:

- Filtrar por clase: un menú desplegable en el que puede seleccionar cualquier clase proporcionada por los vocabularios de la instalación.
- Filtrar por ID del conjunto de elementos: Un campo de texto donde puede introducir el ID del conjunto de elementos que desea utilizar. Puede encontrar el ID de un conjunto de elementos en la URL de su página de edición; si está editando el elemento y la URL es `admin/item-set/15/edit`, entonces el ID del conjunto de elementos es 15. El ID del conjunto de elementos también aparecerá en el panel de la derecha de su página de vista. No puede introducir un rango ni buscar por un número parcial o un comodín, solo un ID exacto.

Una vez que introduzcas algo en un filtro, debes hacer clic en el icono de la lupa en la barra de búsqueda para aplicar tus filtros.

Los recursos de conjuntos de elementos también tienen una opción de «Añadir rápidamente». Cuando se activa esta opción, todos los conjuntos de elementos del panel tienen una casilla de verificación. Puedes utilizar estas casillas para añadir varios conjuntos de elementos como propiedades. Ten en cuenta que solo puedes editar una propiedad a la vez, por lo que todos los conjuntos de elementos rellenarán la misma propiedad (por ejemplo, «Creador», «Tiene parte»).

#### URI

Los campos URI enlazan con un sitio web externo o un recurso en línea. Puedes utilizarlos para indicar un archivo de autoridad de otra parte de la web, o incluso para indicar recursos en otras plataformas Omeka.

Opcionalmente, puede proporcionar una etiqueta que oculte el URI, lo cual es obligatorio. También puede introducir una [etiqueta de idioma de dos letras de la IETF](https://en.wikipedia.org/wiki/IETF_language_tag){target=_blank} para identificar el idioma de aquello a lo que apunta el URI.

![Añadir un URI como valor de una propiedad a un elemento y añadir una anotación de valor a esa propiedad.](contentfiles/items_addURI.png)

Puede añadir otros campos seleccionando una propiedad de la lista de la derecha. Explore los campos por vocabulario (Dublin Core, Ontología Bibliográfica, etc.) o busque en la barra de **filtrado de propiedades** situada encima de la lista de propiedades y vocabularios.

#### Anotación de valor

Cuando introduce un valor para una propiedad asociada a un recurso, está realizando una afirmación sobre ese recurso. Si lo desea, Omeka le permite realizar afirmaciones sobre esa afirmación. A esto lo llamamos anotación de valor. La ventaja de la anotación de valor es que puede optar por concretar hechos ambiguos mediante anotaciones como:

- Procedencia: ¿De dónde procede este hecho?
- Tiempo: ¿Cuándo ocurrió este hecho?
- Ubicación: ¿Cuál es la ubicación asociada a este hecho?
- Certeza: ¿Cuál es el grado de confianza de este hecho?
- Tipo: ¿Qué tipo de concepto o entidad es este hecho?

En el mundo de los datos enlazados, este proceso se conoce como [reificación](https://www.w3.org/wiki/RdfReification){target=_blank}. Cada valor puede tener cualquier número de anotaciones.

Para crear una anotación, haz clic en los tres puntos situados a la derecha de la interfaz de introducción de valores y, a continuación, haz clic en el icono de anotación (el bocadillo).

![Detalle de un valor con el bocadillo de anotación resaltado](contentfiles/annotation_add.png)

La barra lateral de anotaciones se abrirá a la derecha. Seleccione cualquier propiedad disponible en la instalación de Omeka S para describir la relación entre la anotación y el valor que describe. Por ejemplo, el valor asociado a la propiedad `dcterms:Contributor` podría anotarse con más detalles sobre la naturaleza de la contribución. O tal vez desee simplemente incluir una nota utilizando el campo `dcterms:Description`.

Seleccione un tipo de datos para la anotación: un campo de texto, un URI o un recurso de su instalación de Omeka S. Es posible que los módulos ofrezcan tipos de datos adicionales. Haga clic en el botón «Añadir anotación» y aparecerá un nuevo campo debajo. Introduzca su anotación. Si lo desea, puede hacerlo varias veces para el valor elegido. A continuación, haz clic en «Establecer anotaciones» para finalizar el proceso.

![La barra lateral de anotaciones de valor con una propiedad seleccionada y una anotación incluida](contentfiles/annotation_sidebar.png)

[Cada sitio tiene una configuración](../sites/site_settings.md#show) para indicar si las anotaciones de valor son visibles para el público. Esto incluirá las anotaciones de valor en conjuntos de elementos y medios.

Puede establecer vocabularios controlados para las anotaciones utilizando el [módulo Custom Vocab](../modules/customvocab.md). En este caso, no es necesario aplicar un vocabulario personalizado a una propiedad mediante una plantilla de recursos; puede seleccionar cualquier vocabulario instalado en el menú desplegable de tipos de valor del panel. Esto cargará las opciones de su vocabulario en un menú desplegable de términos.

![Una entrada de elemento con una anotación en DC:Contributor, cargando un vocabulario personalizado llamado «Contributor Annotation Type», y los términos mostrados, entre los que se incluyen «Editor», «Traductor», «Organización editora» y más.](contentfiles/annotation_customvocab.png)

### Medios

Utilice la pestaña **Medios** para añadir imágenes, vídeos u otros archivos a un elemento. Consulte la [página de Medios de este manual](media.md) para obtener información más detallada.

Utilizando los botones del menú **Añadir nuevos medios** situado en la parte derecha de la pantalla, seleccione un tipo de medio (Subir, URL, HTML, oEmbed, IIIF o YouTube). Hay módulos, como [File Sideload](../modules/filesideload.md), que pueden añadir más formas de recopilar medios en Omeka. Alternativamente, otros módulos pueden importar materiales de otras plataformas directamente a Omeka como elementos con medios adjuntos, como el módulo [Zotero import](../modules/zoteroimport.md).

!["Cajón de "Añadir nuevo medio" mostrando las opciones](contentfiles/items_mediaadd.png)

- **Subir**: Selecciona uno o más archivos para subirlos desde tu ordenador.
- **URL**: Importa archivos multimedia a través de un URI.
- **HTML**: Añade contenido HTML como recurso multimedia para tu elemento.
- **Imagen IIIF**: Añade una [imagen IIIF](https://iiif.io/api/image/3.0/){target=_blank} a través de una URL.
- **Presentación IIIF**: Añade una [presentación IIIF](https://iiif.io/api/presentation/3.0/){target=_blank} a través de una URL.
- **oEmbed**: Inserta una representación incrustada de una URL externa. Ten en cuenta que esto solo funcionará con contenido de [implementaciones oEmbed existentes](http://oembed.com/#section7){target=_blank}: utiliza la URL de la barra de direcciones de tu navegador.
- **YouTube**: Añade un enlace para incrustar un vídeo de YouTube. Utiliza la URL de la barra de direcciones de tu navegador (que incluya `/watch/`) en lugar de un enlace `youtu.be`.

Puedes editar los archivos multimedia más tarde accediendo a la edición de un elemento, navegando a la pestaña **Multimedia** y haciendo clic en el botón de edición (icono del lápiz) de un archivo multimedia al editar el elemento.

Puedes eliminar cualquier instancia multimedia de la página de edición del elemento utilizando el botón de eliminar (icono de la papelera) situado en la esquina superior derecha del bloque multimedia.

Si tiene más de un archivo multimedia adjunto a un elemento, puede reordenarlos arrastrando y soltando cada bloque de archivo multimedia, utilizando el icono de tres líneas situado en la esquina superior izquierda del bloque como punto de anclaje al arrastrar.

Omeka S utiliza el archivo multimedia situado en la parte superior como «archivo multimedia principal» de un elemento, para crear imágenes en miniatura de ese elemento en las páginas de exploración y visualización. Si utiliza algo como un archivo de audio como archivo multimedia principal, Omeka no generará una miniatura y mostrará una miniatura predeterminada basada en el tipo de archivo. 

### Conjuntos de elementos
Solo puede añadir elementos a conjuntos de elementos existentes.

En el menú de la derecha, haz clic en el propietario de un conjunto de elementos y, a continuación, haz clic en el nombre del conjunto de elementos para añadir el elemento a ese conjunto.

También puedes filtrar los conjuntos de elementos utilizando la barra de entrada de texto situada encima de la lista de usuarios.

Para eliminar una conexión entre un elemento y un conjunto de elementos, haz clic en el botón de eliminar (papelera) situado a la derecha del título del conjunto de elementos.

![pestaña de conjuntos de elementos con 1 conjunto de elementos asignado](contentfiles/items_itemset.png)

### Sitios
Seleccione los sitios a los que desea añadir sus elementos.

![pestaña «sitios» del elemento con el elemento añadido a dos sitios. Cada sitio se encuentra en su propia fila, con un icono de eliminación en el extremo derecho de la fila](contentfiles/items_addItemSite.png)

Para añadir un elemento a un sitio, selecciona un sitio del menú del panel de la derecha. Puedes filtrar los sitios buscando en el campo situado en la parte superior del panel.

Si hay sitios que tienen activada la opción «asignar automáticamente nuevos elementos» en su configuración, puedes utilizar esta pestaña para eliminar este elemento de dichos sitios. Haz clic en el icono de la papelera situado a la derecha de la fila del sitio para eliminarlo.

### Avanzado
La pestaña Avanzado tiene dos opciones. Una te permite establecer una miniatura personalizada para el elemento. La otra te permite cambiar qué usuario es el propietario del elemento.

#### Miniatura

Por defecto, Omeka S utilizará el archivo multimedia situado en la parte superior para generar una miniatura del elemento. Si deseas utilizar una imagen que no sea un archivo multimedia como miniatura de un elemento, puedes configurarlo aquí.

![Pestaña Avanzado sin ningún recurso seleccionado. La pestaña muestra un mensaje sobre la creación de miniaturas y un botón para «seleccionar» un recurso](contentfiles/items_advtab.png)

Cuando utilizas una miniatura de un recurso en lugar de subir un archivo multimedia, la miniatura del recurso no se muestra en la página pública del elemento. Esto hace que estas miniaturas sean útiles para elementos que no tienen archivos multimedia pero que se beneficiarían de una miniatura para la vista de exploración, o para elementos cuyos archivos multimedia no generan una miniatura elegante, como los archivos de audio o vídeo.

Los activos que seleccione y suba como miniaturas en esta pestaña son los mismos que los creados para los [logotipos del sitio](../sites/site_theme.md#logo).

Para asignar un recurso como miniatura, haz clic en el botón Seleccionar en el área de trabajo principal de la pestaña. Esto abrirá un panel deslizante en el lado derecho.

![Panel deslizante de selección con opción de subir y dos recursos, ambos imágenes.](contentfiles/items_thumbdrawer.png)

El panel ofrece dos opciones: subir un archivo mediante el navegador o seleccionar uno de los recursos existentes. Para seleccionar un recurso existente, basta con hacer clic en él y se asignará automáticamente al elemento.

Para eliminar un recurso que hayas asignado como miniatura, haz clic en el botón «Borrar» situado debajo de la imagen del recurso. Para sustituirlo, haz clic en «Seleccionar» y elige o sube un nuevo recurso de miniatura.

#### Propietario

La propiedad de un elemento suele asignarse a la cuenta de usuario que lo crea. Puede utilizar este menú desplegable para reasignar la propiedad. El menú desplegable mostrará los nombres de usuario (no las direcciones de correo electrónico) de los usuarios de la instalación. Seleccione un nuevo usuario y guarde los cambios.

### Visibilidad
Utilice el botón **hacer público/privado** (icono de ojo) para establecer si el elemento es visible para el público o solo para los usuarios del sistema Omeka S.

El elemento es público: ![botón «Hacer público» con un icono de ojo](../content/contentfiles/item_public.png){style="display:inline;"}

El elemento es privado: ![botón «Hacer privado» con un icono de ojo tachado por una línea diagonal](../content/contentfiles/item_private.png){style="display:inline;"}

Tenga en cuenta que, si un elemento es privado, todos los archivos multimedia adjuntos son privados, pero un elemento que es público puede tener archivos multimedia adjuntos que se pueden configurar como públicos o privados.

## Editar un elemento
Una vez que haya creado un elemento, puede editarlo en cualquier momento, ya sea haciendo clic en el icono de edición (botón del lápiz) o haciendo clic en el título del elemento y, a continuación, en el botón «Editar» situado en la esquina superior derecha de la pantalla.

Para cancelar la edición, haz clic en el botón «Cancelar» situado en la parte superior derecha de la pantalla.

Las opciones de edición son las mismas que al crear un nuevo elemento, con la adición de la posibilidad de añadir cualquier archivo multimedia que se haya guardado en un elemento como propiedad.

### Archivos multimedia como propiedad
Una vez que haya creado un elemento y le haya añadido archivos multimedia, también tendrá la opción de utilizar los archivos multimedia **adjuntos a ese elemento** como propiedad.

![Un contorno azul de un rectángulo resalta las opciones de recursos para Elementos, Conjuntos de elementos y Archivos multimedia que se utilizarán como entrada para el elemento «Descripción»](contentfiles/items_addmediaresource.png)

Para utilizar un recurso multimedia como propiedad, seleccione la opción multimedia del elemento (1). El panel que se abre mostrará todos los archivos multimedia adjuntos al elemento. Seleccione el archivo multimedia que desee utilizar (2); esto hará que el panel se centre únicamente en ese archivo (segunda imagen). Haga clic en el botón «Seleccionar recurso» en la parte inferior del panel para completar el proceso (3).

![Enfoque en la parte de edición de una ventana del elemento «Sentido y sensibilidad», con los elementos Título y Descripción visibles. En el lado derecho de la ventana, hay un rectángulo vertical (el panel) abierto que muestra cinco recursos multimedia adjuntos al elemento, incluyendo vídeo, imágenes y texto. Esta imagen contiene los pasos 1 y 2.](contentfiles/items_mediaresource1.png)

![La misma ventana que antes, pero ahora el panel de la derecha muestra una miniatura del archivo multimedia «Tráiler del DVD de Sentido y sensibilidad» con un botón gris oscuro etiquetado como «seleccionar recurso» en la parte inferior del área del panel. Esta imagen contiene el paso 3](contentfiles/items_mediaresource2.png)

### Eliminar un elemento

Para eliminar un elemento, puede:

- Hacer clic en el icono de la papelera en la página de exploración de elementos. Esto abrirá un panel lateral derecho para confirmar la eliminación.
- Hacer clic en el título del elemento en la tabla de la página de exploración de elementos y, a continuación, hacer clic en el botón «Eliminar» situado en la parte superior derecha de la pantalla.
- Utilizar los métodos de eliminación por lotes que se describen a continuación para eliminar varios elementos a la vez.

## Acciones por lotes

Desde la página de exploración de elementos (`admin/item`) puedes editar elementos por lotes utilizando el menú desplegable situado a la izquierda, cerca de los botones de paginación. Puedes seleccionar varios elementos utilizando las casillas de verificación situadas a la izquierda de la fila de cada elemento.

![Una flecha roja señala el menú desplegable con las opciones de edición y eliminación por lotes](contentfiles/items_batch.png)

Los editores, supervisores y administradores globales pueden editar y eliminar en bloque todos los elementos de la instalación. Los usuarios con permisos de nivel de autor pueden editar o eliminar en bloque sus propios elementos, pero no los de otros. En este caso, al seleccionar todos los elementos de la página, o al seleccionar todos los elementos, solo se incluirán los elementos de su propiedad. Los usuarios con nivel de revisor no pueden eliminar en bloque todos los recursos, pero sí pueden eliminar en bloque los recursos seleccionados.

Las acciones por lotes son las siguientes:  

- Editar seleccionados: edita solo los elementos seleccionados en la página
- Editar todo: edita todos los elementos devueltos por una búsqueda (por defecto, todos los elementos)
- Eliminar seleccionados: elimina solo los elementos seleccionados en la página
- Eliminar todo: elimina todos los elementos devueltos por una búsqueda (por defecto, todos los elementos).

Puede seleccionar fácilmente todos los elementos de la página utilizando la casilla de verificación situada en la parte superior de la tabla Elementos. El número de resultados por página se configura en la [configuración global de la instalación](../admin/settings.md#general).

!!! nota
  Las actividades de edición por lotes a veces se muestran en el [Registro de tareas](../admin/jobs.md), que se encuentra en la barra de la izquierda bajo el encabezado «Admin». Aquí solo aparecen las operaciones «Editar todo» o «Eliminar todo». La edición por lotes de solo los elementos seleccionados, incluso una página completa de elementos, no aparecerá aquí.

Primero puede utilizar el enlace «🔍 Búsqueda avanzada» para reducir los elementos a un subconjunto para su edición. Por ejemplo, puede utilizar la [Búsqueda avanzada](../search.md#item-advanced-search) para limitar la búsqueda a elementos que no estén en ningún conjunto de elementos, o a elementos que pertenezcan a un usuario específico. En la imagen siguiente, la búsqueda está configurada para capturar cualquier elemento sin un valor de «Fecha de creación».

![La pantalla de búsqueda avanzada de elementos, con un campo rellenado.](contentfiles/items_advSearch.png)

Si realiza una búsqueda, o llega a la página de exploración de elementos desde un conjunto de elementos u otro filtro, volverá a ver la página de exploración, con los parámetros seleccionados apareciendo en la parte superior de la pantalla. Desde esta pantalla de exploración puede seleccionar elementos manualmente para la edición por lotes utilizando las casillas de verificación de la izquierda, o seleccionar todos los elementos de la página, o utilizar el menú desplegable para editar todos los elementos que se encuentran actualmente en el subconjunto.

Si completas una acción por lotes desde la siguiente pantalla, volverás a este mismo subconjunto de elementos.

### Edición por lotes

La **edición por lotes** de elementos te lleva a una nueva página. Los elementos que se están editando se mostrarán en el lado derecho en un panel. Asegúrate de que el número de elementos que se están editando es correcto.

El formulario de edición por lotes le ofrece las siguientes opciones:  

- **Establecer visibilidad**: un botón de opción. Seleccione entre «público» o «no público» para que el elemento sea visible o no visible para los usuarios que no hayan iniciado sesión.
- **Establecer plantilla**: un menú desplegable. Seleccione entre las plantillas de recursos de la instalación. Puede eliminar plantillas de los elementos seleccionados con la opción «[Desactivar plantilla]». Aparece una barra de búsqueda en la parte superior del menú desplegable si desea escribir para buscar.
- **Establecer clase**: un menú desplegable. Seleccione entre las clases de los vocabularios instalados. Puede eliminar todas las clases de los elementos seleccionados con la opción «[Desactivar clase]». Aparece una barra de búsqueda en la parte superior del menú desplegable si desea escribir para buscar.
- **Establecer propietario**: un menú desplegable. Seleccione entre los usuarios de la instalación para elegir quién debe establecerse como propietario de los elementos seleccionados. La propiedad determina quién puede editar y eliminar esos elementos, al margen de los [niveles de permisos de usuario](../admin/users.md#roles-and-permissions) superiores.
- **Añadir al conjunto de elementos**: un menú desplegable y un campo de texto. Seleccione entre los conjuntos de elementos de la instalación, organizados por propietario, o escriba para buscar. Puede añadir los elementos seleccionados a varios conjuntos de elementos: haga clic de nuevo en el campo de texto para ver las opciones restantes.
- **Eliminar del conjunto de elementos**: un menú desplegable y un campo de texto. Seleccione entre los conjuntos de elementos de la instalación, organizados por propietario, o escriba para buscar. Puede eliminar los elementos seleccionados de varios conjuntos de elementos: haga clic de nuevo en el campo de texto para ver las opciones restantes.
- **Añadir a sitios**: un menú desplegable y un campo de texto. Seleccione entre los sitios de la instalación o escriba para buscar. Puede añadir los elementos seleccionados a varios sitios: haga clic de nuevo en el campo de texto para ver las opciones restantes.
- **Eliminar de sitios**: un menú desplegable y un campo de texto. Seleccione entre los sitios de la instalación o escriba para buscar. Puede eliminar los elementos seleccionados de varios sitios: haga clic de nuevo en el campo de texto para ver las opciones restantes.
- **Borrar valores de propiedad**: un menú desplegable y un campo de texto, con todas las propiedades de todos los vocabularios. Al seleccionar una de estas opciones, se eliminarán todos los valores de esa propiedad en los elementos afectados. Puede eliminar varios valores de propiedad a la vez: haga clic de nuevo en el campo de texto para ver las opciones restantes.
- **Establecer visibilidad del valor**: un menú desplegable y un campo de texto, con botones de opción. Establezca la visibilidad de una o varias propiedades específicas como pública o no pública. A diferencia de los botones de opción de la parte superior del formulario, esto solo afectará a uno o varios campos de metadatos, en lugar de a todo el elemento (por ejemplo, es posible que desee ocultar el valor «Creador» en algunos elementos públicos). Seleccione una propiedad en el campo de texto (escriba para iniciar la búsqueda) y, a continuación, elija el botón de opción «Público» o «No público» para esta opción. Puede añadir varias propiedades haciendo clic de nuevo en el campo de texto, pero todas pasarán a ser «Públicas» o «No públicas».

![Formulario de edición por lotes de elementos, con las opciones descritas anteriormente.](contentfiles/items_batchedit.png)

Además, puede utilizar los botones de la parte inferior del formulario de edición por lotes para **convertir los valores existentes en cualquier propiedad de un tipo de datos a otro**, como por ejemplo un valor de texto «1900-01-01» en una fecha. 

También puede **añadir propiedades** a cada elemento:

- Añadir valor de texto
- Añadir valor de recurso
- Añadir valor URI.  

Al seleccionar cualquiera de estas opciones, se añadirá un bloque al formulario en el que podrá seleccionar una propiedad de los vocabularios instalados e introducir el valor de dicha propiedad.

![La imagen muestra únicamente el bloque «Añadir valor de texto» del formulario de edición por lotes, con un menú desplegable etiquetado como «seleccionar propiedad» sobre un campo de texto vacío](contentfiles/items_beproperty.png)

### Eliminación por lotes

Para las **acciones de eliminación**, se abrirá un panel en el lado derecho de la pantalla que le indicará el número de elementos que se eliminarán. No se eliminará nada a menos que haga clic en el botón rojo «Confirmar eliminación». Esta acción no se puede deshacer. Para cancelar la eliminación de los elementos, haga clic en la «X» situada en la esquina superior derecha del panel de eliminación. Para confirmar esta acción, marca la casilla «¿Estás seguro?» (para «Eliminar todo», pero no para «Eliminar seleccionados») y, a continuación, haz clic en «Confirmar eliminación».

![Primer plano de la advertencia, con el texto que describe el número de elementos que se van a eliminar en rojo.](contentfiles/items_batchdelwarn.png)

Los módulos individuales también pueden añadir acciones de edición por lotes. Estas opciones se indican en la documentación de cada módulo.
