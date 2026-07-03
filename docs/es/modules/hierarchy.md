# Jerarquía

El [módulo «Jerarquía»](https://omeka.org/s/modules/Hierarchy){target=_blank} permite organizar los conjuntos de elementos de Omeka S en árboles. Este módulo es similar al [Árbol de colecciones](https://omeka.org/classic/plugins/CollectionTree/){target=_blank} de Omeka Classic: permite crear sistemas de organización ordenados o de varios niveles.

![Una jerarquía en acción en una página pública.](modulesfiles/hierarchy_public.png)

En el módulo se puede crear cualquier número de agrupaciones; un elemento principal puede tener cualquier número de elementos secundarios. Puedes elegir que las agrupaciones de nivel superior reflejen el número total de elementos de todos los conjuntos de elementos incluidos en los niveles inferiores. 

Las jerarquías se muestran en cada sitio mediante [bloques de página de recursos](../sites/site_theme.md#configure-resource-pages) para elementos y conjuntos de elementos, y mediante un [bloque de página «Jerarquía»](../sites/site_pages.md#page-blocks). Las jerarquías se pueden añadir a sitios individuales para su visualización y se pueden configurar sitio por sitio.

Los usuarios con los niveles de «Supervisor» y «Administrador global» pueden crear jerarquías. Las jerarquías se muestran [en sitios individuales a los usuarios con permiso](../sites/site_users.md) para modificar los bloques de página de recursos y con permiso para editar páginas. 

## Planifica tus agrupaciones

Un elemento de Omeka S puede pertenecer a varios conjuntos de elementos, según tus necesidades. Sin embargo, los conjuntos de elementos no pueden contener otros conjuntos de elementos. Las jerarquías no cambian esto, sino que son una forma complementaria de indicar una relación entre conjuntos de elementos. 

Por ejemplo, si organizas tus elementos por creador (en un conjunto de elementos «Shakespeare, William», un conjunto de elementos «Marlowe, Christopher», y así sucesivamente), estos conjuntos de elementos podrían considerarse «hermanos» entre sí: conceptos equivalentes, pero sin orden específico. Puedes utilizar una jerarquía para ordenar estos conjuntos de elementos cronológicamente según los períodos de vida de los autores, de mayor a menor número de elementos, alfabéticamente o según cualquier otro sistema que elijas. 

También podrías organizarlos en grupos por país de origen, por el idioma utilizado en sus obras u otras categorías. Si tienes un conjunto de elementos «Obras en alemán», que contiene elementos diversos, así como elementos que también se encuentran en el conjunto de elementos «Mann, Thomas», podrías anidar los conjuntos de elementos de autores alemanes bajo el conjunto de elementos «Obras en alemán» como forma de indicar esa relación.

Otro ejemplo podría ser organizar los elementos por tipo de objeto: pinturas, esculturas, hallazgos arqueológicos, documentos, fotografías. Estos conjuntos de elementos no se modificarán, pero pueden complementarse añadiendo categorías más amplias, como «Obras de arte», «Elementos en papel» y «Objetos tridimensionales», para agrupar los conjuntos de elementos pertinentes. Una jerarquía puede contener el mismo conjunto de elementos más de una vez, por lo que se puede tener una jerarquía como la siguiente:

- Obras de arte
  - Pinturas
  - Esculturas
  - Fotografías
- Objetos tridimensionales
  - Esculturas
  - Hallazgos arqueológicos
- Elementos en papel
	- Documentos
  - Fotografías.

Recuerda que los conjuntos de elementos, las clases de recursos y las plantillas también pueden ayudarte a proporcionar múltiples puntos de organización y contexto para tus elementos. 

Las jerarquías se pueden configurar de diferentes maneras en función de la configuración del sitio que tengas previsto utilizar para ellas: tanto si deseas crear solo una agrupación por conjunto de elementos, enlazando directamente con las páginas de los conjuntos de elementos, como si las agrupaciones se utilizarán para mostrar una combinación de todos los elementos de sus agrupaciones secundarias. Te recomendamos que consultes la sección de configuración del sitio, más abajo, mientras planificas tus colecciones. 

Una jerarquía en Omeka S no añade relaciones de metadatos a los conjuntos de elementos (por ejemplo, valores de `relation` o `hasPart`). La información creada en una jerarquía se almacena únicamente en los datos del módulo y no modifica los propios conjuntos de elementos.

## Crear una jerarquía

En la sección «Módulos» de la barra lateral, busca la página «Jerarquía». Haz clic en el botón «Añadir jerarquía» para crear tu primera jerarquía.

![Añadiendo una nueva jerarquía en la página «Jerarquía». De arriba abajo: el título de la página es «Jerarquía». Hay un botón para «Añadir jerarquía». Hay un campo para introducir una «Etiqueta de jerarquía». Hay un botón para «Añadir agrupación». Se ha añadido una agrupación vacía, que cuenta con un campo para la «Etiqueta» y un menú desplegable para seleccionar un conjunto de elementos.](modulesfiles/hierarchy_add.png)

Si lo deseas, puedes asignar una etiqueta a tu nueva jerarquía o dejarla en blanco. 

Las jerarquías se crean organizando y reordenando agrupaciones en árboles. Haz clic en el botón «Añadir agrupación» para añadir tu primera agrupación. Si lo deseas, puedes asignarle una etiqueta o dejarla en blanco. También puedes, si lo prefieres, configurar tu agrupación para que sea equivalente a un conjunto de elementos ya existente. 

Si deja en blanco la etiqueta de la agrupación, se mostrará el nombre del conjunto de elementos. Si rellena la etiqueta, se mostrará esta en su lugar, siempre que aparezca la jerarquía. 

!!! Nota
  Si no rellenas la etiqueta de la agrupación ni eliges un conjunto de elementos, la agrupación aparecerá en el árbol como «[Sin título]». Te recomendamos que utilices al menos una de las dos opciones. 

A continuación, arrastra y suelta tus agrupaciones en el orden o la estructura de árbol que desees. Las agrupaciones se pueden arrastrar para convertirlas en subordinadas de otras agrupaciones, o ordenarlas para que sean equivalentes entre sí. Al arrastrar una agrupación, fíjate en las pequeñas flechas que indican dónde soltarla: para que sea equivalente a otra agrupación (una flecha debajo) o para que sea subordinada de la agrupación (una flecha en el centro). 

Añade tantos grupos como necesites, rellenando las etiquetas y seleccionando conjuntos de elementos cuando sea necesario. Combina esto con la creación de nuevos conjuntos de elementos y añádeles elementos según sea necesario. 

Por ejemplo, quizá quieras crear un sistema de organización de archivos de cinco niveles como el siguiente:

- Una colección [la jerarquía]
	- Serie 1
  - Serie 2
  - Serie 3
    - Subserie 3.1
 -  Carpeta 3.1.1 [asignada a un conjunto de elementos]
 - [Elementos]

Cada entrada de la lista anterior es una agrupación con una etiqueta pero sin conjunto de elementos, excepto el nivel más bajo, que está vinculado al conjunto de elementos que contiene los elementos pertinentes en Omeka. 

![Se muestra un ejemplo de pantalla de jerarquía completada. La primera jerarquía se denomina «Sala 1» y tiene una agrupación, llamada «Estantería 1». La segunda jerarquía se denomina «Sala 2» y contiene «Estantería 5», que a su vez contiene «Estantería superior» y «Estantería central». El «Estante central» contiene «Caja 1» y «Caja 2». «Caja 2» contiene «Carpeta 1» y «Carpeta 2». La «Carpeta 2» está vinculada a un conjunto de elementos llamado «Correspondencia 1933-1937» y se muestra que contiene 62 elementos. Las agrupaciones principales de la «Carpeta 2» (la «Caja 2», el «Estante central» y el «Estante 5») también contienen 62 elementos, lo que indica que el resto de agrupaciones aún no se han asignado a conjuntos de elementos que contengan elementos.](modulesfiles/hierarchy_admin.png)

Puedes crear tantas jerarquías como desees, con tantos niveles como sea necesario, y reutilizar tus conjuntos de elementos donde quieras. De esta forma, puedes crear múltiples puntos de acceso a tus colecciones, según diferentes temas o métodos de navegación. 

Si eliminas una agrupación (el icono de la papelera situado a la derecha), sus elementos secundarios no se eliminarán con ella. En su lugar, ascenderán al nivel de la agrupación eliminada. 

Recuerda guardar los cambios antes de salir de la página del módulo. 

## Añadir una jerarquía a un sitio

En la pestaña «Sitios» del menú de navegación de la izquierda, selecciona un sitio y, a continuación, elige «Jerarquía» en la lista.

![Añadir jerarquías por nombre a un sitio.](modulesfiles/hierarchy_site.png)

Todas tus jerarquías aparecen en la lista de la derecha. Añádelas a cada sitio según desees. El orden en que aparecen las jerarquías en esta página es el orden en que se mostrarán en este sitio; una vez añadidas, puedes arrastrarlas y soltarlas. A continuación, guarda la página. 

## Configuración del sitio

En la página de administración del sitio, selecciona la pestaña «Configuración» y desplázate hacia abajo hasta la sección «Jerarquía». 

![Se muestra una pantalla de configuración de ejemplo, con los campos que se enumeran a continuación rellenados. Las tres primeras opciones están marcadas y las tres últimas, desmarcadas.](modulesfiles/hierarchy_siteSettings.png)

El módulo Jerarquía cuenta con seis opciones de configuración para cada sitio:

- **Enlace directo al conjunto de elementos**: si está marcado, la jerarquía no enlazará las agrupaciones a sus propias páginas públicas personalizadas; la estructura de enlaces de la jerarquía enviará a los usuarios directamente a las páginas de conjuntos de elementos.
    - Esto desactivará la opción «Combinar recursos de jerarquía» que aparece más abajo. 
 - Si eliges enlazar directamente a los conjuntos de elementos en la jerarquía, no habrá enlaces públicos disponibles a las páginas de agrupaciones, aunque dichas páginas seguirán existiendo en el sitio. Los visitantes del sitio pueden acceder a las páginas de agrupación creadas por este módulo si les facilitas esos enlaces de alguna otra forma (por ejemplo, en tu navegación). Por lo tanto, la opción «Mostrar metadatos del conjunto de elementos» puede resultar redundante, ya que solo afecta a las páginas de agrupación. Quizás también te interese desactivar la opción «Mostrar conjuntos de elementos debajo de la jerarquía».
- **Mostrar etiqueta de jerarquía**: si se marca, la etiqueta asignada a la jerarquía se mostrará como encabezado de la jerarquía en las páginas públicas. Si no se marca, la jerarquía se mostrará sin etiqueta. También puede dejar en blanco las etiquetas de jerarquías individuales. Esto solo se aplica a los encabezados de jerarquía; las etiquetas de las agrupaciones individuales no se ven afectadas por esta configuración. 
- **Mostrar recuentos de recursos de la jerarquía**: Si se marca, las etiquetas de agrupación de la jerarquía irán seguidas, entre paréntesis, del número de recursos que hay dentro del conjunto de elementos asignado actualmente.
- **Combinar recursos de la jerarquía**: Si se marca, las agrupaciones mostrarán los recursos de todas las agrupaciones secundarias en los recuentos de recursos y en las páginas de exploración de agrupaciones. Si muestra el recuento de recursos para cada nivel de su jerarquía y, además, combina dichos recuentos, verá el número total de elementos de cada agrupación y de sus agrupaciones secundarias. Si esos elementos se encuentran en más de un conjunto de elementos incluido, no se contarán dos veces. 
- **Mostrar conjuntos de elementos debajo de la jerarquía**: si se marca, aparecerá un párrafo debajo de la jerarquía con una lista de todos los conjuntos de elementos que se han añadido a las agrupaciones de la jerarquía. Esta es una forma de proporcionar enlaces directos a las páginas de visualización de los conjuntos de elementos, independientemente de la propia estructura de enlaces de la jerarquía. 
- **Mostrar metadatos del conjunto de elementos en las páginas de agrupación**: Si se marca, el título, la descripción y la imagen del conjunto de elementos asignado se mostrarán en la página de exploración de cada agrupación. No se mostrará la información del conjunto de elementos de las agrupaciones secundarias, sino solo la del conjunto de elementos vinculado a la agrupación en cuestión.

Ten en cuenta que, en la siguiente imagen, la etiqueta de la agrupación se muestra en la jerarquía de la izquierda, mientras que el título completo del conjunto de elementos aparece en el área de la derecha, junto con la descripción y la miniatura del conjunto de elementos. 

![Una página de agrupación que muestra información sobre el conjunto de elementos asociado.](modulesfiles/hierarchy_groupingPage.png)

!!! nota
  Una agrupación jerárquica asignada a un conjunto de elementos, si se marca la opción «Vincular directamente» anterior, se vinculará incluso a conjuntos de elementos que estén vacíos. Esto puede resultar útil si tus conjuntos de elementos contienen muchos metadatos; por ejemplo, si utilizas el [ArchivesSpace Connector](archivesspaceconnector.md) para importar muchos objetos de contenedores de archivo con información descriptiva sobre su organización, es posible que tengas 4 conjuntos de elementos vacíos por encima de un conjunto de elementos de nivel «carpeta» que contenga elementos. Estos enlaces siempre mostrarán conjuntos de elementos con 0 elementos. Dependiendo del tema (como el predeterminado), los elementos (o la ausencia de ellos) contenidos en el conjunto de elementos pueden mostrarse de forma destacada. Te recomendamos que busques un tema que se adapte a las colecciones de tu sitio. Considera también eliminar los conjuntos de elementos de la jerarquía si no deseas que se muestren cuando no contengan elementos. Puedes añadirlos más tarde, una vez que hayas añadido elementos a ellos. 

## Mostrar jerarquías en un sitio

Las páginas públicas mostrarán la jerarquía en forma de árbol. Las agrupaciones que contengan elementos aparecerán como enlaces; las que no contengan ningún elemento se mostrarán en texto sin formato. 

Dependiendo de la configuración de tu sitio, cada enlace de la jerarquía apuntará a una página pública, con el formato `tuinstalación.org/s/tu-sitio/jerarquía/01`. De este modo, se mostrará la jerarquía seleccionada a la izquierda y todos los elementos contenidos en la agrupación en cuestión a la derecha (ya sean todos los elementos del conjunto de elementos asociado o, según la configuración de tu sitio, incluidos todos los elementos secundarios). 

Dependiendo de la configuración de tu sitio, debajo de la jerarquía en estas páginas aparecerá una lista de todos los conjuntos de elementos incluidos en la jerarquía completa, para que los usuarios puedan navegar hasta ellos si es necesario. (Consulta la imagen en la parte superior de esta página para ver un ejemplo). En los bloques de las páginas del sitio y en los recursos (elementos y conjuntos de elementos), esta sección no se mostrará. 

!!! Nota
  La visualización pública dependerá de si los conjuntos de elementos incluidos se añaden al sitio como recursos. Si un conjunto de elementos está incluido en una jerarquía pero no se ha añadido al sitio, aparecerá el texto «(Privado)» después de la etiqueta, y aparecerá sin vincular y sin recuento de recursos. En la imagen anterior, «Carpeta 2» es un conjunto de elementos público que no está incluido en el sitio. Los conjuntos de elementos cuya visibilidad esté configurada como «privada» no estarán disponibles para los usuarios que no hayan iniciado sesión; además, se mostrarán sin vincular y con «(Privado)» después de la etiqueta. Aparecerán con normalidad para los usuarios que hayan iniciado sesión, así como en las jerarquías de la interfaz de administración. 

Puedes mostrar las jerarquías de dos formas en tus sitios: 

- Añadiendo bloques de página de recursos a las páginas de vista de elementos y conjuntos de elementos
- Añadiendo bloques de página a las páginas del sitio. 

Recuerda que todas las jerarquías mostradas en un sitio determinado se formatearán de acuerdo con la configuración general del sitio. Por ejemplo, no puedes mostrar recuentos combinados de recursos en una zona de tu sitio y recuentos específicos de agrupaciones en otras zonas. 

### Bloques de recursos

![Configuración de la página de vista de elementos en el panel de administración, con el bloque «Jerarquía» incluido.](modulesfiles/hierarchy_resource.png)

Selecciona un sitio y, a continuación, selecciona la pestaña «Tema» en la barra lateral izquierda. Haga clic en el botón «Configurar páginas de recursos» situado junto a «Editar configuración del tema». 

#### Páginas de elementos

En las páginas de elementos, puede añadir el bloque de recursos «Jerarquía» a cualquier región que ofrezca su tema. De este modo se mostrarán todas las jerarquías que se aplican al elemento, limitadas a las jerarquías añadidas al sitio. Si un elemento pertenece a más de un conjunto de elementos, se mostrarán todas las jerarquías de dichos conjuntos (en función de las jerarquías y los conjuntos de elementos añadidos al sitio como recursos) en el orden especificado en la configuración específica del sitio. 

![Una página de vista de un elemento público con la jerarquía mostrando varias agrupaciones resaltadas en negrita.](modulesfiles/hierarchy_publicItem2.png)

Ten en cuenta que el elemento puede pertenecer a más de un conjunto de elementos, y cualquiera de esos conjuntos de elementos que estén incluidos en tu jerarquía se mostrará en negrita. En la imagen anterior, puedes ver una página de vista de elemento con una jerarquía mostrada. Hay más de una agrupación resaltada en negrita, lo que indica que el elemento se encuentra en todas esas agrupaciones o conjuntos de elementos. 

#### Páginas de conjuntos de elementos

![La configuración de la página de vista de un conjunto de elementos en el panel de administración, con el bloque «Jerarquía» incluido.](modulesfiles/hierarchy_resource2.png)

En las páginas de conjuntos de elementos, puedes añadir el bloque de recursos «Jerarquía» a cualquier región que ofrezca tu tema. Esto mostrará todas las jerarquías que se aplican al conjunto de elementos (si las jerarquías se han añadido al sitio).

![Una página de vista de conjunto de elementos con la jerarquía en la parte superior.](modulesfiles/hierarchy_publicItemSet.png)

### Bloques de página

![Una página que se está editando en el panel de administración y que muestra dos bloques de página de jerarquía, configurados para mostrar las jerarquías «Sala 1» y «Sala 2».](modulesfiles/hierarchy_pageBlock.png)

Al añadir el bloque de página «Jerarquía» a una página, puedes seleccionar una jerarquía cada vez para mostrarla. Puedes añadir varios bloques de página. 

![Vista pública de las jerarquías «Sala 1», «Sala 2» y «Sala 3» como tres bloques de página, con un bloque de página multimedia a la derecha.](modulesfiles/hierarchy_public2.png)
