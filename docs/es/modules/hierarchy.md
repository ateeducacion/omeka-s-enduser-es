# Jerarquía

El [módulo Jerarquía](https://omeka.org/s/modules/Hierarchy){target=_blank} permite organizar los conjuntos de elementos de Omeka S en árboles. Este módulo es similar al [Árbol de colecciones](https://omeka.org/classic/plugins/CollectionTree/){target=_blank} de Omeka Classic: permite crear sistemas de organización ordenados o de varios niveles.

![Una jerarquía en acción en una página pública.](modulesfiles/hierarchy_public.png)

Se puede crear cualquier número de agrupaciones en el módulo; un elemento principal puede tener cualquier número de elementos secundarios. Puedes elegir que las agrupaciones de nivel superior reflejen el número total de elementos de todos los conjuntos de elementos incluidos en los niveles inferiores. 

Las jerarquías se muestran en cada sitio mediante [bloques de página de recursos](../sites/site_theme.md#configure-resource-pages) para elementos y conjuntos de elementos, y mediante un [bloque de página «Jerarquía»](../sites/site_pages.md#page-blocks). Las jerarquías se pueden añadir a sitios individuales para su visualización y se pueden configurar sitio por sitio.

Los usuarios con permisos de Supervisor y Administrador global pueden crear jerarquías. Las jerarquías se muestran [en sitios individuales por parte de usuarios con permiso](../sites/site_users.md) para modificar los bloques de página de recursos y con permiso para editar páginas. 

## Planifica tus agrupaciones

Un elemento de Omeka S puede pertenecer a muchos conjuntos de elementos, según sus necesidades. Sin embargo, los conjuntos de elementos no pueden contener otros conjuntos de elementos. Las jerarquías no cambian esto; más bien, son una forma complementaria de indicar una relación entre conjuntos de elementos. 

Por ejemplo, si organizas tus elementos por creador (en un conjunto de elementos «Shakespeare, William», un conjunto de elementos «Marlowe, Christopher», y así sucesivamente), estos conjuntos de elementos podrían considerarse «hermanos» entre sí: conceptos equivalentes, pero sin orden. Puedes utilizar una jerarquía para ordenar estos conjuntos de elementos cronológicamente según la vida de los creadores, o de mayor a menor número de elementos, o alfabéticamente, o cualquier otro sistema que elijas. 

También podrías organizarlos en grupos por país de origen, el idioma utilizado en sus obras u otras categorías. Si tiene un conjunto de elementos «Obras en alemán», que contiene elementos diversos, así como elementos que también se encuentran en el conjunto de elementos «Mann, Thomas», podría anidar los conjuntos de elementos de autores alemanes bajo el conjunto de elementos «Obras en alemán» como forma de indicar esa relación.

Otro ejemplo podría ser organizar los elementos por tipo de objeto: pinturas, esculturas, hallazgos arqueológicos, documentos, fotografías. Estos conjuntos de elementos no se modificarán, pero pueden complementarse añadiendo categorías más amplias, como «Obras de arte», «Elementos en papel» y «Objetos tridimensionales», para agrupar los conjuntos de elementos pertinentes. Una jerarquía puede contener el mismo conjunto de elementos más de una vez, por lo que puede tener una jerarquía como la siguiente:

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

Recuerde que los conjuntos de elementos, las clases de recursos y las plantillas también pueden ayudarle a proporcionar múltiples puntos de organización y contexto para sus elementos. 

Las jerarquías se pueden configurar de diferentes maneras dependiendo de la configuración del sitio que planees utilizar para ellas: si deseas crear solo una agrupación por conjunto de elementos, enlazando directamente a las páginas de los conjuntos de elementos, o si las agrupaciones se utilizarán para mostrar una combinación de todos los elementos de sus agrupaciones secundarias. Recomendamos consultar la sección de configuración del sitio, más abajo, mientras planifica sus colecciones. 

Una jerarquía en Omeka S no añade relaciones de metadatos a los conjuntos de elementos (por ejemplo, valores `relation` o `hasPart`). La información creada en una jerarquía se almacena únicamente en los datos del módulo y no modifica los conjuntos de elementos en sí.

## Crear una jerarquía

En la sección «Módulos» de la barra lateral, busca la página «Jerarquía». Haz clic en el botón «Añadir jerarquía» para iniciar tu primera jerarquía.

![Añadiendo una nueva jerarquía en la página Jerarquía. De arriba abajo: el título de la página es «Jerarquía». Hay un botón para «Añadir jerarquía». Hay un campo para introducir una «Etiqueta de jerarquía». Hay un botón para «Añadir agrupación». Se ha añadido una agrupación vacía, que tiene un campo para la «Etiqueta» y un menú desplegable para elegir un conjunto de elementos.](modulesfiles/hierarchy_add.png)

Opcionalmente, puedes asignar una etiqueta a tu nueva jerarquía o dejarla en blanco. 

Las jerarquías se crean organizando las agrupaciones en árboles. Haz clic en el botón «Añadir agrupación» para añadir tu primera agrupación. Opcionalmente, puedes asignarle una etiqueta o dejarla en blanco. También puedes, si lo deseas, configurar tu agrupación para que sea equivalente a un conjunto de elementos existente. 

Si deja la etiqueta de la agrupación en blanco, se mostrará el nombre del conjunto de elementos. Si rellena la etiqueta, se mostrará esta en su lugar, siempre que aparezca la jerarquía. 

!!! nota
  Si no rellenas la etiqueta de agrupación ni eliges un conjunto de elementos, la agrupación aparecerá en el árbol como «[Sin título]». Te recomendamos que utilices al menos una de las dos opciones. 

A continuación, arrastra y suelta tus agrupaciones en el orden o la estructura de árbol que desees. Las agrupaciones se pueden arrastrar para convertirlas en subordinadas de otras agrupaciones, o ordenarlas para que sean equivalentes entre sí. Al arrastrar una agrupación, busque las flechas pequeñas que indican dónde soltarla: para que sea equivalente a otra agrupación (una flecha debajo) o para que sea subordinada de la agrupación (una flecha en el centro). 

Añada tantos grupos como necesite, rellenando las etiquetas y seleccionando conjuntos de elementos cuando sea necesario. Combine esto con la creación de nuevos conjuntos de elementos y añada elementos a ellos según sea necesario. 

Por ejemplo, es posible que desee crear un sistema de organización de archivos de cinco niveles como el siguiente:

- Una colección [la jerarquía]
	- Serie 1
  - Serie 2
  - Serie 3
    - Subserie 3.1
 -  Carpeta 3.1.1 [asignada a un conjunto de elementos]
 - [Elementos]

Cada entrada de la lista anterior es una agrupación con una etiqueta pero sin conjunto de elementos, excepto el nivel más bajo, que está configurado como el conjunto de elementos que contiene los elementos relevantes en Omeka. 

![Se muestra un ejemplo de pantalla de jerarquía completada. La primera jerarquía se llama «Sala 1» y tiene una agrupación, llamada «Estante 1». La segunda jerarquía se llama «Habitación 2» y contiene «Estante 5», que a su vez contiene «Estante superior» y «Estante central». El Estante central contiene «Caja 1» y «Caja 2». «Caja 2» contiene «Carpeta 1» y «Carpeta 2». La Carpeta 2 está configurada en un conjunto de elementos llamado «Correspondencia 1933-1937» y se muestra que contiene 62 elementos. Las agrupaciones principales de la Carpeta 2 (Caja 2, Estante central y Estante 5) también contienen 62 elementos, lo que indica que otras agrupaciones aún no están configuradas como conjuntos de elementos que contengan elementos.](modulesfiles/hierarchy_admin.png)

Puede crear tantas jerarquías como desee, con tantos niveles como sea necesario, y reutilizar sus conjuntos de elementos donde quiera. De esta forma, puede crear múltiples puntos de acceso a sus colecciones, según diferentes temas o métodos de navegación. 

Si elimina una agrupación (el icono de la papelera a la derecha), sus elementos secundarios no se eliminarán con ella. En su lugar, ascenderán al nivel de la agrupación eliminada. 

Recuerde guardar los cambios antes de salir de la página del módulo. 

## Añadir una jerarquía a un sitio

En la pestaña Sitios del menú de navegación de la izquierda, selecciona un sitio y, a continuación, elige «Jerarquía» en la lista.

![Añadiendo jerarquías por nombre a un sitio.](modulesfiles/hierarchy_site.png)

Todas tus jerarquías aparecen en la lista de la derecha. Añádelas a cada sitio como desees. El orden en que se organizan las jerarquías en esta página es el orden en que se mostrarán en este sitio; una vez añadidas, puedes arrastrarlas y soltarlas. A continuación, guarda la página. 

## Configuración del sitio

En la página de administración del sitio, selecciona la pestaña «Configuración» y desplázate hacia abajo hasta la sección «Jerarquía». 

![Se muestra una pantalla de configuración de ejemplo, con los campos que se enumeran a continuación rellenados. Las tres primeras opciones están marcadas y las tres últimas, desmarcadas.](modulesfiles/hierarchy_siteSettings.png)

El módulo Jerarquía tiene seis opciones de configuración para cada sitio:

- **Enlazar directamente al conjunto de elementos**: si está marcado, la jerarquía no enlazará las agrupaciones a sus propias páginas públicas personalizadas; la estructura de enlaces de la jerarquía enviará a los usuarios directamente a las páginas de conjuntos de elementos.
    - Esto desactivará la configuración «Combinar recursos de jerarquía» que aparece a continuación. 
 - Si eliges enlazar directamente a conjuntos de elementos en la jerarquía, no habrá enlaces públicos disponibles a las páginas de agrupaciones, aunque esas páginas seguirán existiendo en el sitio. Los visitantes del sitio pueden acceder a las páginas de agrupación creadas por este módulo si les proporciona esos enlaces de alguna otra forma (por ejemplo, en su navegación). Por lo tanto, la configuración «Mostrar metadatos del conjunto de elementos» puede resultar redundante, ya que solo afecta a las páginas de agrupación. Es posible que también desee desactivar la configuración «Mostrar conjuntos de elementos debajo de la jerarquía».
- **Mostrar etiqueta de jerarquía**: si se marca, la etiqueta asignada a la jerarquía se mostrará como encabezado de la jerarquía en las páginas públicas. Si no se marca, la jerarquía se mostrará sin etiqueta. También puede dejar en blanco las etiquetas de jerarquías individuales. Esto solo se aplica a los encabezados de jerarquía; las etiquetas de las agrupaciones individuales no se ven afectadas por esta configuración. 
- **Mostrar recuentos de recursos de la jerarquía**: si se marca, las etiquetas de agrupación de la jerarquía irán seguidas del número de recursos dentro del conjunto de elementos asignado actualmente, entre paréntesis.
- **Combinar recursos de la jerarquía**: si se marca, las agrupaciones mostrarán los recursos de todas las agrupaciones secundarias en los recuentos de recursos y en las páginas de exploración de agrupaciones. Si muestra el recuento de recursos para cada nivel de su jerarquía y, además, combina dichos recuentos, verá el número total de elementos de cada agrupación y sus subagrupaciones. Si esos elementos se encuentran en más de un conjunto de elementos incluido, no se contarán dos veces. 
- **Mostrar conjuntos de elementos debajo de la jerarquía**: si se marca, aparecerá un párrafo debajo de la jerarquía con una lista de todos los conjuntos de elementos que se han añadido a las agrupaciones de la jerarquía. Esta es una forma de proporcionar enlaces directos a las páginas de vista de los conjuntos de elementos, independientemente de la propia estructura de enlaces de la jerarquía. 
- **Mostrar metadatos del conjunto de elementos en las páginas de agrupación**: Si se marca, el título, la descripción y la imagen del conjunto de elementos asignado se mostrarán en la página de exploración de cada agrupación. Esto no mostrará la información del conjunto de elementos de las agrupaciones secundarias, solo la del conjunto de elementos vinculado a la agrupación en cuestión.

Tenga en cuenta que en la siguiente imagen, la etiqueta de la agrupación se muestra en la jerarquía de la izquierda, mientras que el título completo del conjunto de elementos se muestra en el área de la derecha, junto con la descripción y la miniatura del conjunto de elementos. 

![Una página de agrupación que muestra información sobre el conjunto de elementos adjunto.](modulesfiles/hierarchy_groupingPage.png)

!!! nota
  Una agrupación jerárquica asignada a un conjunto de elementos, si la opción «Enlazar directamente» anterior está marcada, enlazará incluso a conjuntos de elementos que estén vacíos. Esto puede resultar útil si sus conjuntos de elementos contienen muchos metadatos; por ejemplo, si utiliza el [ArchivesSpace Connector](archivesspaceconnector.md) para importar muchos objetos de contenedores de archivo con información descriptiva sobre su organización, es posible que tenga 4 conjuntos de elementos vacíos por encima de un conjunto de elementos de nivel «carpeta» que contenga elementos. Estos enlaces siempre mostrarán conjuntos de elementos con 0 elementos. Dependiendo del tema (como el predeterminado), los elementos (o la ausencia de ellos) contenidos en el conjunto de elementos pueden mostrarse de forma destacada. Recomendamos buscar un tema que se adapte a las colecciones de su sitio. Considere también eliminar los conjuntos de elementos de la jerarquía si no desea que se muestren cuando no contienen elementos. Puede añadirlos más tarde, después de añadirles elementos. 

## Mostrar jerarquías en un sitio

Las páginas públicas mostrarán la jerarquía en forma de árbol. Las agrupaciones que contengan elementos aparecerán como enlaces; las agrupaciones sin elementos se mostrarán en texto sin formato. 

Dependiendo de la configuración de tu sitio, cada enlace de la jerarquía apuntará a una página pública, con el formato `tuinstalación.org/s/tu-sitio/jerarquía/01`. Esto mostrará la jerarquía elegida a la izquierda y todos los elementos contenidos en la agrupación dada a la derecha (ya sean todos los elementos del conjunto de elementos adjunto o incluyendo todos los elementos secundarios según la configuración de tu sitio). 

Dependiendo de la configuración de su sitio, debajo de la jerarquía en estas páginas aparecerá una lista de todos los conjuntos de elementos incluidos en la jerarquía completa, para que los usuarios puedan navegar a ellos si es necesario. (Vea la imagen en la parte superior de esta página como ejemplo). En los bloques de la página del sitio y en los recursos (elementos y conjuntos de elementos), esta sección no se mostrará. 

!!! nota
  La visualización pública dependerá de si los conjuntos de elementos incluidos se añaden al sitio como recursos. Si un conjunto de elementos está incluido en una jerarquía pero no se ha añadido al sitio, aparecerá el texto «(Privado)» después de la etiqueta, y aparecerá desvinculado sin recuento de recursos. En la imagen anterior, «Carpeta 2» es un conjunto de elementos público que no está incluido en el sitio. Los conjuntos de elementos con la visibilidad establecida en «privado» no estarán disponibles para los usuarios que no hayan iniciado sesión; además, se mostrarán como desvinculados y con «(Privado)» después de la etiqueta. Aparecerán con normalidad para los usuarios que hayan iniciado sesión, así como en las jerarquías de la interfaz administrativa. 

Puedes mostrar jerarquías de dos maneras en tus sitios: 

- Añadiendo bloques de página de recursos a las páginas de vista de elementos y conjuntos de elementos
- Añadiendo bloques de página a las páginas del sitio. 

Recuerda que todas las jerarquías mostradas en un sitio determinado se formatearán de acuerdo con la configuración de todo el sitio. Por ejemplo, no puede mostrar recuentos de recursos combinados en una zona de su sitio y recuentos específicos de agrupaciones en otras zonas. 

### Bloques de recursos

![La configuración de la página de vista de elementos en el panel de administración, con el bloque Jerarquía incluido.](modulesfiles/hierarchy_resource.png)

Seleccione un sitio y, a continuación, seleccione la pestaña «Tema» en la barra lateral izquierda. Haga clic en el botón «Configurar páginas de recursos» junto a «Editar configuración del tema». 

#### Páginas de elementos

En las páginas de elementos, puede añadir el bloque de recursos «Jerarquía» a cualquier región que ofrezca su tema. Esto mostrará todas las jerarquías que se aplican al elemento, limitadas a las jerarquías añadidas al sitio. Si un elemento se encuentra en más de un conjunto de elementos, se mostrarán todas las jerarquías de los conjuntos de elementos (según qué jerarquías y qué conjuntos de elementos se hayan añadido al sitio como recursos) en el orden especificado en la configuración específica del sitio. 

![Una página de vista de un elemento público con la jerarquía mostrando varias agrupaciones resaltadas en negrita.](modulesfiles/hierarchy_publicItem2.png)

Tenga en cuenta que el elemento puede estar en más de un conjunto de elementos, y cualquiera de esos conjuntos de elementos que estén incluidos en su jerarquía se mostrará en negrita. En la imagen anterior, puede ver una página de vista de elementos con una jerarquía mostrada. Más de una agrupación está resaltada en negrita, lo que indica que el elemento está en todas esas agrupaciones/conjuntos de elementos. 

#### Páginas de conjuntos de elementos

![Configuración de la página de vista de conjuntos de elementos en el panel de administración, con el bloque Jerarquía incluido.](modulesfiles/hierarchy_resource2.png)

En las páginas de conjuntos de elementos, puede añadir el bloque de recursos «Jerarquía» a cualquier región que ofrezca su tema. Esto mostrará todas las jerarquías que se aplican al conjunto de elementos (si las jerarquías se han añadido al sitio).

![Una página de vista de conjunto de elementos con la jerarquía en la parte superior.](modulesfiles/hierarchy_publicItemSet.png)

### Bloques de página

![Una página que se está editando en el panel de administración y que muestra 2 bloques de página de jerarquía, configurados para mostrar las jerarquías «Sala 1» y «Sala 2».](modulesfiles/hierarchy_pageBlock.png)

Al añadir el bloque de página «Jerarquía» a una página, puedes seleccionar una jerarquía cada vez para mostrarla. Puedes añadir varios bloques de página. 

![Vista pública de las jerarquías «Sala 1», «Sala 2» y «Sala 3» como 3 bloques de página, con un bloque de página multimedia a la derecha.](modulesfiles/hierarchy_public2.png)
