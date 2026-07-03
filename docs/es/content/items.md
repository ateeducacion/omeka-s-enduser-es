# Elementos

Los elementos son los componentes básicos del sistema Omeka.

Los elementos no tienen por qué representar objetos físicos (fotografías, mapas, libros), ni tienen por qué tener [archivos multimedia adjuntos](media.md) (una digitalización de una foto, imágenes de varias páginas o un PDF). Un elemento puede utilizarse como nodo, es decir, como una forma de representar a una persona, un lugar o una cosa. Puedes utilizar los elementos y sus clases para crear distintos tipos de nodos que se adapten a los objetivos de tus sitios web.

Los elementos pueden vincularse a otros elementos o formar parte de conjuntos de elementos, para representar relaciones complejas. Por ejemplo, un elemento utilizado como ubicación puede vincularse a elementos que representen acontecimientos que tuvieron lugar en esa ubicación, y los elementos de acontecimiento pueden vincularse a elementos de personas que asistieron a ese acontecimiento, quienes a su vez están vinculados a elementos de texto que crearon o a elementos fotográficos en los que aparecen. Todos estos elementos pueden agruparse en conjuntos de elementos superpuestos que representan ámbitos que abarcan ubicaciones, eventos y personas durante un periodo de tiempo concreto. O bien, puedes utilizar conjuntos de elementos para representar a personas, que contengan sus obras creadas como elementos, y vincular esos conjuntos de elementos de personas a eventos y fotografías.

Muchas de estas clases, así como numerosas plantillas de recursos que te ayudarán a describir estos tipos de elementos, ya existen en una instalación básica de Omeka S, pero puedes modificarlas y añadir más según sea necesario.

## Permisos de los elementos

Cuando un usuario crea un elemento, se convierte en el «propietario» de dicho elemento. La mayoría de los niveles de usuario tienen la capacidad de crear elementos y siempre pueden eliminar sus propios elementos. Solo los niveles superiores pueden eliminar elementos que pertenezcan a otros usuarios.

| Categoría | Permiso | Administrador global | Supervisor | Editor | Revisor | Autor | Investigador |
|-----|-----|---|---|---|---|---|---|
| Elementos y archivos multimedia | Añadir | Sí | Sí | Sí | Sí | Sí | No |
| | Editar | Todos | Todos | Todos | Todos | Los propios | No |
| | Eliminar | Todos | Todos | Todos | Los propios | Los propios | No |
| Anotaciones de valores | Añadir/Editar | Sí | Sí | Sí | Sí | Sí | No |
| Objetos privados | Ver | Sí | Sí | Sí | Sí | No | No |

Ten en cuenta que, cuando cambias el rol de un usuario, por ejemplo, de Autor a Investigador, seguirá siendo propietario de los elementos que creó cuando tenía permiso para hacerlo. Los elementos no se transfieren. Al eliminar a un usuario, sus elementos quedan huérfanos, es decir, aparecerán como si no tuvieran propietario. Actualmente no es posible buscar ni editar por lotes elementos sin propietario, por lo que se recomienda reasignar estos elementos antes de eliminar la cuenta de usuario.

### Permisos del sitio para los elementos

Todos los elementos de una instalación de Omeka S pueden añadirse a cualquier sitio, pero deben añadirse a un sitio de forma manual o mediante configuraciones específicas del usuario o del sitio.

Cada sitio puede configurarse para que todos los elementos nuevos se añadan automáticamente a él.

Cada usuario puede tener [uno o más sitios a los que añadir siempre nuevos elementos de forma predeterminada](../admin/users.md#user-settings). Si un usuario tiene un sitio configurado como sus «Sitios predeterminados para elementos», también debe ser añadido a dicho sitio como Creador o Gestor para que esa configuración funcione.

| Categoría | Permiso | Gestor del sitio | Creador del sitio | Lector del sitio | Administrador global | Supervisor |
|-----|-----|---|---|---|---|---|
| Elementos | Añadir al sitio | Sí | Sí (por defecto), manualmente no | No | Sí | Sí |
| | Eliminar del sitio | Sí | No | No | Sí | Sí |

### Vistas públicas de los elementos

Los elementos de un sitio de Omeka se pueden explorar desde la página «Explorar elementos», que se añade automáticamente a la navegación de cada sitio al crearlo. Los elementos individuales, una vez añadidos al conjunto de recursos de un sitio, mostrarán una página de visualización individual del elemento. El diseño de esta página se configura en la pestaña «Tema», mediante el botón «Configurar páginas de recursos». 

Por defecto, la página de visualización del elemento muestra el título del elemento en la parte superior, seguido de una representación de cualquier archivo multimedia adjunto al elemento y, a continuación, los valores de las propiedades en forma de texto.

![Página de configuración de la página de recursos de un elemento de un sitio recién creado, con las opciones predeterminadas activadas.](contentfiles/items_configurePage.png)

Cualquier bloque de página añadido a una de las regiones disponibles en el tema solo se mostrará en la página de vista de un elemento concreto si tiene contenido; de lo contrario, permanecerá oculto.

![Página de vista de un elemento que muestra la configuración predeterminada con un título, un elemento multimedia y algunos metadatos.](contentfiles/items_publicPage.png)

## La pestaña «Elementos»

Los elementos aparecen en la pestaña **Elementos** (con el icono de un cuadro) en el panel de navegación de la izquierda del panel de administración.

![Vista básica de la página de elementos de administración, en la que se muestran varios recursos de elementos](contentfiles/items_browse.png)

Cada elemento aparece como una fila, con columnas para:

- el **Título**
- iconos para **editar** (lápiz), **eliminar** (papelera), o **ver detalles** (tres puntos)
- la **Clase**
- el **Propietario** del elemento
- la fecha en que se **creó** el elemento. 

En la esquina superior derecha de la pantalla de elementos se encuentra el botón «Añadir nuevo elemento».

Las opciones para navegar y crear elementos se encuentran en el encabezado de la tabla de elementos.

- En el lado izquierdo hay controles para las páginas de elementos, con flechas de avance y retroceso, y un cuadro editable para el número de página actual: introduce un número de página válido y pulsa Intro para ir a esa página.

- En el centro hay un enlace a [Búsqueda avanzada](../search.md#item-advanced-search).

- A la derecha se encuentran las opciones para ordenar la tabla de elementos, con dos menús desplegables. Por defecto, los elementos de la tabla se ordenan con los añadidos más recientemente en la parte superior (Creados y Descendente). El primero te permite elegir entre **Título**, **Identificador**, **Clase**, **Propietario** y **(Fecha) de creación**; el segundo te permite ordenar de forma ascendente (A-Z o de más antiguo a más reciente) o descendente (Z-A o de más reciente a más antiguo). Para aplicar la ordenación, haz clic en el botón «Ordenar».

Entre estos botones y la tabla, a la izquierda, hay un menú desplegable para acciones en bloque, que incluye «Editar seleccionados», «Editar todo», «Eliminar seleccionados» y «Eliminar todo».

## Ver elementos

Para ver rápidamente la información básica sobre un elemento, haz clic en el botón **Detalles** (tres puntos) de la fila correspondiente al elemento, situado junto a los botones de editar y eliminar. Esto abrirá un panel a la derecha de la lista que muestra el título del elemento, la descripción, el número de identificación de Omeka, la visibilidad, los conjuntos de elementos, los sitios en los que se utiliza y los archivos multimedia adjuntos. Los enlaces a los conjuntos de elementos y a los sitios te llevarán a la página de administración correspondiente; el icono de flecha situado a la derecha de cada enlace de sitio te llevará a la vista pública de ese elemento en dicho sitio. 

Para ver un elemento concreto con más detalle, haz clic en su título en la tabla de exploración de elementos o cuando estés viendo sus detalles.

![Vista de exploración de elementos, con los detalles abiertos del elemento «Informe anual 2012-2013» en el panel deslizante de la derecha.](contentfiles/items_detailview.png)

Al visualizar un elemento individual, aparecen pestañas para los **metadatos** del elemento y sus **recursos vinculados**. En la parte derecha de la página se muestran los archivos multimedia del elemento, los **sitios** y **conjuntos de elementos** a los que pertenece, su fecha de creación, su propietario y su visibilidad.

### Recursos vinculados

Los **recursos vinculados** de un elemento son otros recursos de Omeka (elementos, conjuntos de elementos o archivos multimedia) que están [vinculados a este elemento a través de sus propiedades](#omeka-resource). Ten en cuenta que esta sección solo muestra los recursos que se han vinculado *a* este elemento (que lo tienen como propiedad); los recursos vinculados *desde* este elemento se mostrarán en la propiedad que ocupen.

Los recursos vinculados se agrupan según la propiedad para la que utilizan el elemento actual. En el ejemplo siguiente, el elemento actual «William Shakespeare» se utiliza para las propiedades «Creador», «Referencias» y «Lista de autores» de los recursos vinculados. 

Puedes filtrar los recursos vinculados para mostrar únicamente aquellos que hacen referencia a una propiedad específica utilizando el menú desplegable «Filtrar por propiedad». Solo se mostrarán las propiedades que estén en uso.

![Vista de los recursos vinculados al elemento «William Shakespeare», con seis obras de teatro que utilizan a Shakespeare como «Creador», el elemento «Folger Shakespeare Library» incluido como «referencias» de Shakespeare y el «Globe Theatre» que utiliza a Shakespeare para la «lista de autores». Cada grupo de propiedades se encuentra en un rectángulo independiente, encabezado por la propiedad a la que se hace referencia.](contentfiles/items_linked.png)

Cuando se visualiza un recurso en un sitio público, los recursos vinculados se muestran en una serie de tablas basadas en la propiedad de metadatos utilizada. Los recursos se ordenan por tipo de recurso (elemento, conjunto de elementos o medio) y solo se muestra un tipo a la vez. Un recurso que no tenga recursos vinculados no mostrará estas tablas. Las tablas se pueden incluir, excluir o reorganizar mediante [la configuración del tema del sitio, en «Configurar páginas de recursos»](../sites/site_theme.md#configure-resource-pages).

Un recurso con enlaces a otros recursos que no estén incluidos en el sitio público en cuestión mostrará de todos modos dichos recursos no incluidos. Esos recursos vinculados parecerán formar parte del sitio (es decir, se puede hacer clic en ellos para ver las páginas de elementos y conjuntos de elementos). [Esta configuración se puede desactivar para cada sitio](../sites/site_settings.md#show). Cuando se excluyen los recursos ajenos al sitio, los valores de metadatos del elemento y las tablas de recursos enlazados no mostrarán los recursos de Omeka excluidos.

Ten en cuenta que las páginas multimedia no muestran tablas de recursos enlazados, independientemente de si los elementos enlazan con ellas o no.

El siguiente elemento incluye varios recursos de Omeka en su propiedad «Colaboradores», que se muestran como parte de sus metadatos. Además, esos mismos elementos enlazan con él, lo que se muestra en la tabla de recursos vinculados.

![Visualización de un elemento en el tema predeterminado que muestra varios recursos de Omeka como «Colaboradores» y varios elementos de Omeka que enlazan con él como «Publicaciones»](contentfiles/items_linkedresources.png)

La visualización de los «Recursos vinculados» en las páginas de recursos se puede configurar en cada sitio. Haz clic en «Tema» y, a continuación, en el botón que dice «[Configurar páginas de recursos](../sites/site_theme.md#configure-resource-pages)», y a continuación decide si quieres mostrar las tablas de «Recursos vinculados» para cada recurso y en qué lugar. 

También puedes controlar si los recursos vinculados mostrarán dichos enlaces incluso cuando los [recursos en cuestión no estén incluidos en el sitio en cuestión](../sites/site_resources.md). En [Configuración del sitio, en la sección «Mostrar»](../sites/site_settings.md#show), encontrarás una casilla de selección para «Excluir recursos que no estén en el sitio». 

## Añadir un elemento

Para añadir un nuevo elemento, empieza seleccionando el botón «Añadir nuevo elemento».

Antes de crear elementos, es posible que los supervisores quieran crear [plantillas de recursos](resource-template.md), que cargarán campos específicos para diversos tipos de elementos.

### Valores

La pestaña «Valores» es donde se introducen los metadatos, como el título, la descripción, etc.

![Vista básica de la página de añadir elementos, sin contenido introducido](contentfiles/items_add.png)

Puedes seleccionar una plantilla de recursos en el menú desplegable. Las plantillas de recursos las definen los supervisores y los editores.

- Si se utiliza una plantilla de recursos, la clase del elemento debería cargarse automáticamente.
- Si no se utiliza una plantilla de recursos, se puede seleccionar una clase del menú desplegable (estas se rellenan a partir de los [Vocabularios](vocabularies.md) de tu instalación).

Añade información a las propiedades que se carguen. Si no seleccionas una plantilla de recurso ni una clase, las propiedades de Dublin Core «Título» y «Descripción» se cargarán automáticamente.  

Tanto si utilizas una plantilla de recurso como si no, puedes añadir más propiedades al elemento utilizando el panel situado a la derecha de la pantalla. Basta con abrir uno de los vocabularios (Dublin Core, Ontología Bibliográfica, etc.) y hacer clic en la propiedad que desees añadir, o bien puedes utilizar el casilla «Filtrar propiedades» para buscar una propiedad específica (esto resulta útil cuando se dispone de varios vocabularios extensos).

![Primer plano del panel lateral derecho con el texto «fecha» introducido en la casilla «Filtrar propiedades» y una serie de propiedades que contienen la palabra «fecha» cargadas desde Dublin Core y la Ontología Bibliográfica](contentfiles/items_filterprop.png)

Al hacer clic en la etiqueta de la propiedad en el panel, esta se añadirá automáticamente al elemento. Si añades una propiedad por error, déjala en blanco y se eliminará del elemento cuando guardes los cambios.

Puedes añadir texto, un recurso de la instalación o un enlace externo en cada campo.

Puedes configurar propiedades individuales como **privadas o públicas** utilizando el icono del ojo de cada propiedad. Ten en cuenta que las propiedades configuradas como privadas siguen siendo visibles para los administradores globales, los supervisores y los editores. Los autores podrán ver todas las propiedades de los elementos de los que son propietarios, pero no verán las propiedades privadas creadas por otros usuarios.

En la imagen siguiente, la primera propiedad (Título) es pública, tal y como indica el icono del ojo abierto. La segunda propiedad (Descripción) es privada, tal y como indica el icono del ojo tachado. Al hacer clic o pulsar Intro en el icono del ojo, se alterna entre público y privado.

![Tal y como se describe](contentfiles/items_propviz.png)

Si tienes varios valores para una propiedad, puedes **reordenarlos** arrastrando y soltando. Haz clic en la barra situada a la izquierda del valor para seleccionarlo y arrástralo hasta la posición que desees.

![Primer plano de la propiedad «Asunto» con dos valores. Un círculo rojo muestra la ubicación de la barra de selección del valor.](contentfiles/items_valuereorder.png)

#### Texto
Los campos de texto permiten introducir texto sin formato. No se permite el uso de marcado en estos campos (por ejemplo, Markdown, HTML).

![Imagen de un campo de entrada de texto con el icono de un teclado que indica la introducción de texto, el icono del globo terráqueo para configurar el idioma y un icono de papelera para borrar](contentfiles/items_textedit.png)

Puedes indicar el idioma del contenido de un campo de texto utilizando el símbolo del globo terráqueo situado encima del campo (véase la imagen a continuación). Haz clic en el globo terráqueo para activar el campo de texto y, a continuación, introduce el [código de idioma de dos letras de la IETF](https://en.wikipedia.org/wiki/IETF_language_tag){target=_blank} del idioma en el que está escrito el texto.

![Un campo de entrada de texto, con un icono de globo terráqueo a la izquierda, resaltado en azul con el cursor activo en el campo. Se está aplicando una etiqueta de idioma de dos letras al contenido del campo de texto que aparece a continuación.](contentfiles/items_lang.png)

#### Recurso de Omeka

Al elegir un recurso de Omeka como valor de metadatos, se crea un [enlace interno entre el recurso que estás creando y el recurso que rellena ese campo](#linked-resources). 

Al crear un elemento, tienes la opción de utilizar otro elemento o un conjunto de elementos. Si el elemento tiene archivos multimedia adjuntos, también puedes elegir entre esos archivos, y no entre otros archivos multimedia de la instalación. 

Al seleccionar un tipo de recurso, se abrirá un panel lateral en el que podrás explorar todos los recursos de la instalación. Puedes utilizar la función de búsqueda situada en la parte superior del panel para filtrar la lista o encontrar rápidamente un recurso específico. 

Una vez seleccionado un recurso, se cargará información detallada y deberás hacer clic en «Seleccionar recurso» para finalizar el enlace entre los recursos. También puede hacer clic en el botón «X» de la esquina superior derecha para volver a la lista de recursos.

![Interfaz de edición de elementos, con el valor de la propiedad «Recurso de Omeka» añadido a la propiedad Descripción. Los botones «Elementos» y «Conjuntos de elementos» aparecen resaltados dentro de un cuadrado rojo. El panel de la derecha está abierto en el menú «Seleccionar elemento», con una lista de elementos entre los que elegir.](contentfiles/items_addresource.png)

Si utilizas un recurso de tipo **Elemento** para la propiedad, podrás seleccionar un elemento existente o crear un esbozo de un nuevo elemento. 

Si deseas utilizar un elemento existente como valor, tendrás tres opciones para encontrar el elemento que buscas en el panel lateral. Accede a estas opciones haciendo clic en el botón triangular situado junto a la frase «Filtrar búsqueda». Se abrirá un menú con las siguientes opciones para filtrar los elementos del panel:

- Filtrar por clase: un menú desplegable en el que puedes seleccionar cualquier clase proporcionada por los vocabularios de la instalación.
- Filtrar por conjunto de elementos: un menú desplegable en el que puedes limitar los elementos que se muestran en el panel a solo aquellos asociados a un conjunto de elementos concreto.
- Filtrar por ID de elemento: Un campo de texto en el que puedes introducir el ID del elemento que deseas utilizar. Puedes encontrar el ID de un elemento en la URL de su página de edición; si estás editando el elemento y la URL es `admin/item/11547/edit`, entonces el ID del elemento es 11547. El ID de un elemento también aparecerá en el panel de la derecha de su página de visualización. No se puede introducir un rango ni buscar por un número parcial o un comodín, solo el ID exacto.

Una vez introducido algo en un filtro, debes hacer clic en el icono de la lupa de la barra de búsqueda para aplicar los filtros.

![opciones tal y como se ha descrito anteriormente](contentfiles/items_addresItem.png)

Los recursos de los elementos también cuentan con una opción de «Añadir rápidamente». Cuando se activa esta opción, todos los elementos del panel disponen de una casilla de selección. Puedes utilizar estas casillas para añadir varios elementos como una misma propiedad a la vez. Ten en cuenta que solo puedes editar una propiedad a la vez, por lo que todos los elementos deben rellenar la misma propiedad (por ejemplo, «Creador», «Tiene pieza»).

![Una flecha roja señala el botón deslizante de «Añadir rápidamente». Los dos elementos visibles tienen una casilla de selección vacía a la izquierda de su miniatura correspondiente](contentfiles/items_quickadd.png)

Si deseas crear un nuevo elemento, puedes crear un esbozo de dicho elemento directamente en el panel seleccionando la opción «Crear un elemento». A continuación, se te mostrará un formulario de creación de elementos abreviado en el que podrás seleccionar:

- Plantilla de recurso
- Clase
- Visibilidad del nuevo elemento.

También puedes introducir valores para dos campos básicos:
- Título
- Descripción.

Una vez que hayas completado el formulario, puedes añadir el esbozo del elemento y, al mismo tiempo, seleccionarlo como valor para la propiedad. Puedes volver al elemento esbozo más tarde para completar su descripción.

![El formulario de creación del esbozo de elemento está abierto en el panel lateral y muestra el menú desplegable para las opciones «Plantilla de recurso», «Clase» y «Visibilidad», así como los campos de entrada para «Título» y «Descripción»](contentfiles/items_createItemStub.png)

Si utiliza un recurso de **conjunto de elementos** para la propiedad, dispondrá de dos opciones para encontrar el conjunto de elementos que desee en el panel lateral:

- Filtrar por clase: Un menú desplegable en el que puedes seleccionar cualquier clase proporcionada por los vocabularios de la instalación.
- Filtrar por ID del conjunto de elementos: Un campo de texto en el que puedes introducir el ID del conjunto de elementos que deseas utilizar. Puedes encontrar el ID de un conjunto de elementos en la URL de su página de edición; si estás editando el elemento y la URL es `admin/item-set/15/edit`, el ID del conjunto de elementos es 15. El ID de un conjunto de elementos también aparecerá en el panel de la derecha de su página de vista. No puedes introducir un rango ni buscar por un número parcial o un comodín, solo el ID exacto.

Una vez que introduzcas algo en un filtro, debes hacer clic en el icono de la lupa de la barra de búsqueda para aplicar los filtros.

Los recursos de conjuntos de elementos también cuentan con una opción de «Añadir rápidamente». Cuando esta opción está activada, todos los conjuntos de elementos del panel lateral muestran una casilla de selección. Puedes utilizar estas casillas de selección para añadir varios conjuntos de elementos como propiedades. Ten en cuenta que solo puedes editar una propiedad a la vez, por lo que todos los conjuntos de elementos se incluirán en la misma propiedad (por ejemplo, «Creador», «Tiene parte»).

#### URI

Los campos URI enlazan con un sitio web externo o un recurso en línea. Puedes utilizarlos para indicar un archivo de autoridad de otra parte de la web, o incluso para indicar recursos en otras plataformas de Omeka.

Opcionalmente, puedes proporcionar una etiqueta que oculte el URI, lo cual es obligatorio. También puedes introducir una [etiqueta de idioma de dos letras de la IETF](https://en.wikipedia.org/wiki/IETF_language_tag){target=_blank} para identificar el idioma de aquello a lo que apunta el URI.

![Añadir un URI como valor de una propiedad a un elemento y añadir una anotación de valor a esa propiedad.](contentfiles/items_addURI.png)

Puedes añadir otros campos seleccionando una propiedad de la lista de la derecha. Explora los campos por vocabulario (Dublin Core, Ontología Bibliográfica, etc.) o realiza una búsqueda en la barra de **filtrado de propiedades** situada encima de la lista de propiedades y vocabularios.

#### Anotación de valor

Cuando introduces un valor para una propiedad asociada a un recurso, estás realizando una afirmación sobre ese recurso. Si lo deseas, Omeka te permite realizar afirmaciones sobre esa afirmación. A esto lo llamamos «anotación de valor». La ventaja de la anotación de valor es que puedes optar por concretar hechos ambiguos mediante anotaciones sobre aspectos como:

- Procedencia: ¿De dónde procede este hecho?
- Tiempo: ¿Cuándo ocurrió este hecho?
- Ubicación: ¿Cuál es la ubicación asociada a este dato?
- Certeza: ¿Cuál es el grado de confianza de este dato?
- Tipo: ¿Qué tipo de concepto o entidad es este dato?

En el mundo de los datos enlazados, este proceso se conoce como [reificación](https://www.w3.org/wiki/RdfReification){target=_blank}. Cada valor puede tener cualquier número de anotaciones.

Para crear una anotación, haz clic en los tres puntos situados a la derecha del campo de introducción de valores y, a continuación, haz clic en el icono de anotación (el bocadillo).

![Detalle de un valor con el bocadillo de anotación resaltado](contentfiles/annotation_add.png)

Se abrirá la barra lateral de anotaciones a la derecha. Selecciona cualquier propiedad disponible en la instalación de Omeka S para describir la relación entre la anotación y el valor al que se refiere. Por ejemplo, el valor asociado a la propiedad `dcterms:Contributor` podría anotarse con más detalles sobre la naturaleza de la contribución. O quizá prefieras simplemente incluir una nota utilizando el campo `dcterms:Description`.

Selecciona un tipo de datos para la anotación: un campo de texto, un URI o un recurso de tu instalación de Omeka S. Es posible que los módulos ofrezcan tipos de datos adicionales. Haz clic en el botón «Añadir anotación» y aparecerá un nuevo campo más abajo. Introduce tu anotación. Si lo deseas, puedes hacerlo varias veces para el valor elegido. A continuación, haz clic en «Establecer anotaciones» para finalizar el proceso.

![La barra lateral de anotaciones de valor con una propiedad seleccionada y una anotación incluida](contentfiles/annotation_sidebar.png)

[Cada sitio dispone de una configuración](../sites/site_settings.md#show) para indicar si las anotaciones de valor son visibles para el público o no. Esto incluirá las anotaciones de valor en conjuntos de elementos y archivos multimedia.

Puedes configurar vocabularios controlados para las anotaciones utilizando el [módulo Custom Vocab](../modules/customvocab.md). En este caso, no es necesario aplicar un vocabulario personalizado a una propiedad mediante una plantilla de recursos; puedes seleccionar cualquier vocabulario instalado en el menú desplegable de tipo de valor del panel lateral. Esto cargará las opciones de tu vocabulario en un menú desplegable de términos.

![Una entrada de elemento con una anotación en DC:Contributor, que carga un vocabulario personalizado denominado «Tipo de anotación de colaborador», y los términos mostrados incluyen «Editor», «Traductor», «Organización editora» y más.](contentfiles/annotation_customvocab.png)

### Multimedia

Utiliza la pestaña **Multimedia** para añadir imágenes, vídeos u otros archivos a un elemento. Consulta la [página «Multimedia» de este manual](media.md) para obtener información más detallada.

Mediante los botones del menú **Añadir nuevos medios**, situado en la parte derecha de la pantalla, selecciona un tipo de medio (Subir, URL, HTML, oEmbed, IIIF o YouTube). Algunos módulos, como [File Sideload](../modules/filesideload.md), pueden ofrecer más formas de incorporar medios a Omeka. Por otra parte, otros módulos pueden importar materiales desde otras plataformas directamente a Omeka como elementos con archivos multimedia adjuntos, como el módulo [Importación de Zotero](../modules/zoteroimport.md).

!["Panel 'Añadir nuevo archivo multimedia' mostrando las opciones](contentfiles/items_mediaadd.png)

- **Subir**: Selecciona uno o más archivos para subirlos desde tu ordenador.
- **URL**: Importa archivos multimedia a través de un URI.
- **HTML**: Añade contenido HTML como recurso multimedia para tu elemento.
- **Imagen IIIF**: Añade una [imagen IIIF](https://iiif.io/api/image/3.0/){target=_blank} a través de una URL.
- **Presentación IIIF**: Añade una [presentación IIIF](https://iiif.io/api/presentation/3.0/){target=_blank} mediante una URL.
- **oEmbed**: Inserta una representación incrustada de una URL externa. Ten en cuenta que esto solo funcionará con contenido de [implementaciones oEmbed existentes](http://oembed.com/#section7){target=_blank}; utiliza la URL de la barra de direcciones de tu navegador.
- **YouTube**: Añade un enlace para incrustar un vídeo de YouTube. Utiliza la URL de la barra de direcciones de tu navegador (que incluya `/watch/`) en lugar de un enlace `youtu.be`.

Puedes editar los archivos multimedia más tarde accediendo a la edición de un elemento, navegando a la pestaña **Multimedia** y haciendo clic en el botón de edición (icono del lápiz) correspondiente a un archivo multimedia mientras editas el elemento.

Puedes eliminar cualquier archivo multimedia de la página de edición del elemento utilizando el botón de eliminar (icono de la papelera) situado en la esquina superior derecha del bloque multimedia.

Si tienes más de un elemento multimedia adjunto a un elemento, puedes reordenarlos arrastrando y soltando cada bloque de elemento multimedia, utilizando el icono de las tres líneas situado en la esquina superior izquierda del bloque como punto de anclaje al arrastrar.

Omeka S utiliza el elemento multimedia situado en la parte superior como «elemento multimedia principal» de un elemento, para crear imágenes en miniatura de dicho elemento en las páginas de exploración y visualización. Si utilizas algo como un archivo de audio como elemento multimedia principal, Omeka no generará una miniatura y mostrará una miniatura predeterminada basada en el tipo de archivo. 

### Conjuntos de elementos
Solo puedes añadir elementos a conjuntos de elementos ya existentes.

En el menú de la derecha, haz clic en el propietario de un conjunto de elementos y, a continuación, haz clic en el nombre del conjunto para añadir el elemento a dicho conjunto.

También puedes filtrar los conjuntos de elementos utilizando la barra de entrada de texto situada encima de la lista de usuarios.

Para eliminar la relación entre un elemento y un conjunto de elementos, haz clic en el botón de eliminar (papelera) situado a la derecha del título del conjunto de elementos.

![pestaña «Conjunto de elementos» con 1 conjunto de elementos asignado](contentfiles/items_itemset.png)

### Sitios
Selecciona los sitios a los que deseas añadir tus elementos.

![pestaña «sitios» del elemento con el elemento añadido a dos sitios. Cada sitio aparece en su propia fila, con un icono de eliminación en el extremo derecho de la fila](contentfiles/items_addItemSite.png)

Para añadir un elemento a un sitio, selecciona un sitio del menú del panel lateral derecho. Puedes filtrar los sitios realizando una búsqueda en el campo situado en la parte superior del panel.

Si hay sitios que tienen activada la opción «asignar automáticamente nuevos elementos» en su configuración, puedes utilizar esta pestaña para eliminar este elemento de dichos sitios. Haz clic en el icono de la papelera situado a la derecha de la fila del sitio para eliminarlo.

### Avanzado
La pestaña «Avanzado» tiene dos opciones. Una te permite establecer una miniatura personalizada para el elemento. La otra te permite cambiar el usuario propietario del elemento.

#### Miniatura

Por defecto, Omeka S utilizará el archivo multimedia situado más arriba para generar una miniatura del elemento. Si deseas utilizar una imagen que no sea un archivo multimedia como miniatura de un elemento, puedes configurarla aquí.

![Pestaña «Avanzado» sin ningún recurso seleccionado. La pestaña muestra un mensaje sobre la creación de miniaturas y un botón para «seleccionar» un recurso](contentfiles/items_advtab.png)

Cuando se utiliza una miniatura de un recurso en lugar de subir un archivo multimedia, la miniatura del recurso no se muestra en la página pública del elemento. Esto hace que estas miniaturas sean útiles para elementos que no tienen archivos multimedia pero que se beneficiarían de una miniatura en la vista de exploración, o para elementos cuyos archivos multimedia no generan una miniatura elegante, como los archivos de audio o vídeo.

Los recursos que selecciones y subas como miniaturas en esta pestaña son los mismos que los creados para [los logotipos del sitio](../sites/site_theme.md#logo).

Para asignar un recurso como miniatura, haz clic en el botón «Seleccionar» en el área de trabajo principal de la pestaña. Esto abrirá un panel deslizante en el lado derecho.

![Panel deslizante de selección con opción de subir archivos y dos recursos, ambos imágenes.](contentfiles/items_thumbdrawer.png)

El panel ofrece dos opciones: subir un archivo mediante el navegador o seleccionar uno de los recursos existentes. Para seleccionar un recurso existente, basta con hacer clic en él y se asignará automáticamente al elemento.

Para eliminar un recurso que hayas asignado como miniatura, haz clic en el botón «Borrar» situado debajo de la imagen del recurso. Para sustituirlo, haz clic en «Seleccionar» y elige o sube un nuevo recurso de miniatura.

#### Propietario

La propiedad de un elemento suele asignarse a la cuenta de usuario que lo crea. Puedes utilizar este menú desplegable para reasignar la propiedad. El menú desplegable mostrará los nombres de usuario (no las direcciones de correo electrónico) de los usuarios de la instalación. Selecciona un nuevo usuario y guarda los cambios.

### Visibilidad
Utiliza el botón **Hacer público/privado** (icono de ojo) para establecer si el elemento es visible para el público o solo para los usuarios del sistema Omeka S.

El elemento es público: ![botón «Hacer público» con un icono de ojo](../content/contentfiles/item_public.png){style="display:inline;"}

El elemento es privado: ![botón «Hacer privado» que muestra un icono de ojo tachado con una barra diagonal](../content/contentfiles/item_private.png){style="display:inline;"}

Ten en cuenta que, si un elemento es privado, todos los archivos multimedia adjuntos también lo son; sin embargo, un elemento público puede tener archivos multimedia adjuntos que se hayan configurado como públicos o privados.

## Editar un elemento
Una vez creado un elemento, puedes editarlo en cualquier momento, ya sea haciendo clic en el icono de edición (botón del lápiz) o haciendo clic en el título del elemento y, a continuación, en el botón «Editar» situado en la esquina superior derecha de la pantalla.

Para cancelar la edición, haz clic en el botón «Cancelar» situado en la parte superior derecha de la pantalla.

Las opciones de edición son las mismas que al crear un nuevo elemento, con la novedad de que ahora puedes añadir cualquier archivo multimedia que se haya guardado en un elemento como propiedad.

### Archivos multimedia como propiedad
Una vez que hayas creado un elemento y le hayas añadido archivos multimedia, también tendrás la opción de utilizar los archivos multimedia **adjuntos a ese elemento** como propiedad.

![Un rectángulo con contorno azul resalta las opciones de recursos para elementos, conjuntos de elementos y archivos multimedia que se pueden utilizar como entrada para el elemento «Descripción»](contentfiles/items_addmediaresource.png)

Para utilizar un recurso multimedia como propiedad, selecciona la opción multimedia del elemento (1). El panel que se abre mostrará todos los archivos multimedia adjuntos al elemento. Selecciona el recurso multimedia que desees utilizar (2); esto hará que el panel se centre únicamente en ese recurso (segunda imagen). Haz clic en el botón «Seleccionar recurso» situado en la parte inferior del panel para completar el proceso (3).

![Amplitud de la zona de edición de una ventana para el elemento «Sentido y sensibilidad», con los elementos «Título» y «Descripción» visibles. En la parte derecha de la ventana, hay un rectángulo vertical (el panel) abierto que muestra cinco recursos multimedia asociados al elemento, entre los que se incluyen vídeos, imágenes y texto. Esta imagen muestra los pasos 1 y 2.](contentfiles/items_mediaresource1.png)

![La misma ventana que antes, pero ahora el panel de la derecha muestra una miniatura del archivo multimedia «Tráiler del DVD de Sentido y sensibilidad» con un botón gris oscuro etiquetado como «seleccionar recurso» en la parte inferior del área del panel. Esta imagen muestra el paso 3](contentfiles/items_mediaresource2.png)

### Eliminar un elemento

Para eliminar un elemento, puedes:

- Hacer clic en el icono de la papelera de la página de exploración de elementos. Esto abrirá un panel lateral a la derecha para confirmar la eliminación.
- Hacer clic en el título del elemento en la tabla de la página de exploración de elementos y, a continuación, hacer clic en el botón «Eliminar» situado en la parte superior derecha de la pantalla.
- Utilizar los métodos de eliminación por lotes que se describen a continuación para eliminar varios elementos a la vez.

## Acciones por lotes

Desde la página de exploración de elementos (`admin/item`) puedes editar elementos de forma masiva utilizando el menú desplegable situado a la izquierda, junto a los botones de paginación. Puedes seleccionar varios elementos utilizando las casillas de selección situadas a la izquierda de la fila de cada elemento.

![Una flecha roja señala el menú desplegable con las opciones de edición y eliminación en bloque](contentfiles/items_batch.png)

Los editores, supervisores y administradores globales pueden editar y eliminar en bloque todos los elementos de la instalación. Los usuarios con permisos de nivel de autor pueden editar o eliminar en bloque sus propios elementos, pero no los de otros usuarios. En este caso, al seleccionar todos los elementos de la página, o al seleccionar todos los elementos, solo se incluirán los elementos de los que sean propietarios. Los usuarios con nivel de «Revisor» no pueden eliminar en bloque todos los recursos, pero sí pueden eliminar en bloque los recursos seleccionados.

Las acciones en bloque son las siguientes:  

- Editar los seleccionados: edita solo los elementos que están seleccionados en la página
- Editar todo: edita todos los elementos devueltos por una búsqueda (por defecto, todos los elementos)
- Eliminar los seleccionados: elimina solo los elementos que están seleccionados en la página
- Eliminar todo: elimina todos los elementos devueltos por una búsqueda (por defecto, todos los elementos).

Puedes seleccionar fácilmente todos los elementos de la página utilizando la casilla de selección situada en la parte superior de la tabla «Elementos». El número de resultados por página se configura en la [configuración global de la instalación](../admin/settings.md#general).

!!! Nota
  Las actividades de edición por lotes a veces se muestran en el [Registro de tareas](../admin/jobs.md), que se encuentra en la barra de la izquierda, bajo el encabezado «Admin». Aquí solo aparecen las operaciones «Editar todo» o «Eliminar todo». La edición en bloque de solo los elementos seleccionados, incluso si se trata de una página completa de elementos, no aparecerá aquí.

Primero puedes utilizar el enlace «🔍 Búsqueda avanzada» para filtrar los elementos y seleccionar un subconjunto para editar. Por ejemplo, puedes utilizar la [Búsqueda avanzada](../search.md#item-advanced-search) para limitar la búsqueda a los elementos que no estén en ningún conjunto de elementos, o a los que pertenezcan a un usuario específico. En la imagen siguiente, la búsqueda está configurada para mostrar cualquier elemento que no tenga un valor en el campo «Fecha de creación».

![La pantalla de búsqueda avanzada de elementos, con un campo rellenado.](contentfiles/items_advSearch.png)

Si realizas una búsqueda o llegas a la página de exploración de elementos desde un conjunto de elementos u otro filtro, volverás a ver la página de exploración, con los parámetros seleccionados en la parte superior de la pantalla. Desde esta pantalla de exploración, puedes seleccionar elementos manualmente para la edición por lotes utilizando las casillas de selección de la izquierda, seleccionar todos los elementos de la página o utilizar el menú desplegable para editar todos los elementos que se encuentran actualmente en el subconjunto.

Si completas una acción por lotes desde la siguiente pantalla, volverás a este mismo subconjunto de elementos.

### Edición por lotes

La **edición por lotes** de elementos le lleva a una nueva página. Los elementos que se están editando se mostrarán en una columna a la derecha. Asegúrese de que el número de elementos que se están editando es correcto.

El formulario de edición por lotes le ofrece las siguientes opciones:  

- **Establecer visibilidad**: un botón de opción. Selecciona «público» o «no público» para que el elemento sea visible o no para los usuarios que no hayan iniciado sesión.
- **Establecer plantilla**: un menú desplegable. Selecciona una de las plantillas de recursos de la instalación. Puedes eliminar plantillas de los elementos seleccionados con la opción «[Desactivar plantilla]». En la parte superior del menú desplegable aparece una barra de búsqueda si deseas escribir algo para buscar.
- **Establecer clase**: un menú desplegable. Selecciona entre las clases de los vocabularios instalados. Puedes eliminar todas las clases de los elementos seleccionados con la opción «[Desactivar clase]». En la parte superior del menú desplegable aparece una barra de búsqueda si desea escribir algo para buscar.
- **Establecer miniatura**: haz clic en el botón «Seleccionar» para abrir la barra lateral de activos, donde puedes elegir un activo existente o subir uno nuevo, que servirá como miniatura para todos los elementos incluidos. Esto sustituirá cualquier miniatura generada automáticamente a partir de los archivos multimedia, así como cualquier miniatura elegida manualmente al editar elementos individuales. 
- **Establecer propietario**: un menú desplegable. Selecciona entre los usuarios de la instalación para elegir quién debe establecerse como propietario de los elementos seleccionados. La propiedad determina quién puede editar y eliminar esos elementos, al margen de los [niveles de permiso de usuario](../admin/users.md#roles-and-permissions) superiores.
- **Añadir al conjunto de elementos**: un menú desplegable y un campo de texto. Selecciona entre los conjuntos de elementos de la instalación, organizados por propietario, o escribe para buscar. Puedes añadir los elementos seleccionados a varios conjuntos de elementos: haz clic de nuevo en el campo de texto para ver las opciones restantes.
- **Eliminar del conjunto de elementos**: un menú desplegable y un campo de texto. Seleccione entre los conjuntos de elementos de la instalación, organizados por propietario, o escriba para buscar. Puede eliminar los elementos seleccionados de varios conjuntos de elementos: haga clic de nuevo en el campo de texto para ver las opciones restantes.
- **Añadir a sitios**: un menú desplegable y un campo de texto. Seleccione entre los sitios de la instalación o escriba un texto para buscar. Puede añadir los elementos seleccionados a varios sitios: haga clic de nuevo en el campo de texto para ver las opciones restantes.
- **Eliminar de los sitios**: un menú desplegable y un campo de texto. Selecciona entre los sitios de la instalación o escribe para buscar. Puedes eliminar los elementos seleccionados de varios sitios: haz clic de nuevo en el campo de texto para ver las opciones restantes.
- **Borrar valores de propiedad**: un menú desplegable y un campo de texto, con todas las propiedades de todos los vocabularios. Al seleccionar esta opción, se eliminarán todos los valores de esa propiedad en los elementos afectados. Puedes eliminar varios valores de propiedad a la vez: haz clic de nuevo en el campo de texto para ver las opciones restantes.
- **Establecer visibilidad del valor**: un menú desplegable y un campo de texto, con botones de opción. Establece la visibilidad de una o varias propiedades específicas como «pública» o «no pública». A diferencia de los botones de opción situados en la parte superior del formulario, esto solo afectará a uno o varios campos de metadatos, en lugar de a todo el elemento (por ejemplo, es posible que desees ocultar el valor «Creador» en algunos elementos públicos). Selecciona una propiedad en el campo de texto (escribe para iniciar la búsqueda) y, a continuación, elige el botón de opción «Público» o «No público» para esta opción. Puedes añadir varias propiedades haciendo clic de nuevo en el campo de texto, pero todas pasarán a ser «Públicas» o «No públicas».

![Formulario de edición por lotes de elementos, con las opciones descritas anteriormente.](contentfiles/items_batchedit.png)

Además, puede utilizar los botones situados en la parte inferior del formulario de edición por lotes para **convertir los valores existentes de cualquier propiedad de un tipo de datos a otro**, como por ejemplo, un valor de texto «1900-01-01» en una fecha. 

También puedes **añadir propiedades** a cada elemento:

- Añadir valor de texto
- Añadir valor de recurso
- Añadir valor URI.  

Al seleccionar cualquiera de estas opciones, se añadirá un bloque al formulario en el que podrás seleccionar una propiedad de los vocabularios instalados e introducir el valor de dicha propiedad.

![La imagen muestra únicamente el bloque «Añadir valor de texto» del formulario de edición por lotes, con un menú desplegable titulado «Seleccionar propiedad» situado encima de un campo de texto vacío](contentfiles/items_beproperty.png)

### Eliminación por lotes

Para las **acciones de eliminación**, se abrirá un panel deslizante en la parte derecha de la pantalla que te indicará el número de elementos que se eliminarán. No se eliminará nada a menos que hagas clic en el botón rojo «Confirmar eliminación». Esta acción no se puede deshacer. Para cancelar la eliminación de los elementos, haz clic en la «X» situada en la esquina superior derecha del panel de eliminación. Para confirmar esta acción, marca la casilla «¿Estás seguro?» (solo para «Eliminar todo», no para «Eliminar los seleccionados») y, a continuación, haz clic en «Confirmar eliminación».

![Primer plano de la advertencia, con el texto que describe el número de elementos que se van a eliminar en rojo.](contentfiles/items_batchdelwarn.png)

Los módulos individuales también pueden añadir acciones de edición por lotes. Dichas opciones se indican en la documentación de cada módulo.
