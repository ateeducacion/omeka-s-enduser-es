# Búsqueda por facetas

El [módulo de búsqueda por facetas](https://omeka.org/s/modules/FacetedBrowse){target=_blank} te permite crear páginas de «exploración de recursos» con facetas (funciones de filtrado y ordenación) que los visitantes del sitio pueden utilizar para explorar tus colecciones. Las páginas de navegación por facetas pueden crearse para elementos, conjuntos de elementos o medios. 

Con este módulo, los administradores del sitio configuran las páginas de búsqueda por facetas en función de los recursos específicos del sitio. A continuación, los usuarios finales pueden navegar por esos recursos y utilizar las facetas para acotar los resultados de forma lógica e intuitiva. Esta funcionalidad es similar a las opciones de filtrado de muchos sitios web y debería resultar fácil de manejar para los usuarios, siempre que se utilice un lenguaje claro.

La sección [vista pública](#public-views) que aparece a continuación muestra cómo se muestran estas facetas en páginas de una sola categoría y de varias categorías.

Las [páginas](../sites/site_pages.md) de navegación por facetas se pueden añadir a la [navegación](../sites/site_navigation.md) de un sitio. Puedes [añadir la navegación por facetas a una página como un bloque](#faceted-browse-preview-page-block) que mostrará una vista previa de la página de navegación por facetas, pero sin todas sus funcionalidades. 

El contenido de la navegación por facetas se puede establecer como la vista de búsqueda predeterminada cuando un usuario escribe en la barra de búsqueda situada en la parte superior de un sitio de Omeka S. 

Una vez activada, la navegación por facetas se configura para cada sitio individualmente.

## Terminología

Estos son los términos que utilizamos para los aspectos de una página de navegación por facetas:

- Categoría: un grupo de recursos (elementos, conjuntos de elementos o archivos multimedia) al que se aplican facetas en una página específica. Puedes utilizar una consulta para filtrar los recursos disponibles, o dejarlo en blanco para mostrar todos los recursos de ese tipo. Las categorías se configuran en el panel de administración. Debes añadir una categoría a cada página que crees. 
- Faceta: un aspecto de un recurso (normalmente parte de los metadatos) que permite a los usuarios filtrar los recursos de la categoría. La navegación por facetas funciona mejor cuando se dispone de vocabularios controlados en los valores de los metadatos, o cuando los valores únicos pueden clasificarse en grupos (como las fechas ordenadas por siglo). Las facetas se ofrecen como posibles filtros de navegación en la parte pública. 
- Columna: Información que se mostrará para cada recurso en los resultados. Las columnas son opcionales. Una vez que hayas configurado al menos una columna, los elementos se mostrarán en forma de tabla (no de cuadrícula). Cuando no se configuren columnas, se mostrará la navegación predeterminada de tu sitio (por ejemplo, título, miniatura y descripción de cada recurso).
- Selección: cuando una faceta es navegable, debes ofrecer a tus visitantes los medios más adecuados para ordenar o buscar en dichas facetas. Puedes permitirles, por ejemplo, excluir o incluir cadenas de caracteres en los resultados, o buscar coincidencias exactas con valores completos. O bien, si los tipos de datos numéricos están activos, puedes agrupar los valores en categorías que tú mismo establezcas (como décadas, para elementos con fechas más específicas). 

![Página de navegación por facetas con una lista de eventos que tuvieron lugar en el National Mall. En la parte izquierda de la imagen hay una lista de opciones con casillas de selección.](modulesfiles/FacetedBrowse_publicView-basic.png)

En la vista pública del ejemplo anterior: 

- el título «Explorar elementos» se utiliza para la apariencia de la página en la navegación.
- «Filtrar por tipo» es el nombre de la categoría en la barra lateral izquierda de la página.
- Las facetas de la categoría incluyen «Clase», «Plantilla utilizada» y «Colección».
- En estos ejemplos, la opción de selección utilizada es «Múltiple (lista)», lo que da lugar a casillas de selección para cada opción, y las opciones visibles se truncan a 4.

## Crear páginas de navegación por facetas

![Administrador del sitio mostrando la página de inicio de la navegación por facetas.](modulesfiles/FacetedBrowse_1.png)

Una vez activado el módulo de navegación por facetas, aparecerá un enlace a la navegación por facetas en el menú contextual de cada sitio. Al hacer clic en este enlace, accederás a una lista de todas tus páginas de navegación por facetas para ese sitio.

Los administradores del sitio deben crear páginas de navegación por facetas antes de poder añadirlas a la navegación del sitio.

Crea una nueva página haciendo clic en el botón «Añadir nueva página». Esto te llevará a una nueva página donde podrás añadir la información básica de la página y empezar a añadir categorías. 

![Interfaz de creación de página que muestra el menú desplegable para guardar la página](modulesfiles/FacetedBrowse_AddPage.png)

El **título de la página** es obligatorio; se mostrará en las pestañas del navegador y se incluirá en los metadatos de la página. Puedes establecer una etiqueta diferente en la navegación del sitio. La mayoría de los temas no mostrarán este título de forma visible en la página. Cuando una página solo tiene una categoría, su título aparecerá en la página; cuando se establecen dos o más categorías, el encabezado «Explorar» aparecerá encima de los enlaces de categorías en la barra lateral (véase [la captura de pantalla siguiente](#multiple-categories-on-one-page) para ver cómo se mostrará). 

Utiliza el menú desplegable **tipo de recurso** para seleccionar el tipo de recurso que deseas que los usuarios puedan explorar en esta página: Elementos, Conjuntos de elementos o Archivos multimedia. Esto no se puede editar una vez creada la página.

A continuación, elige las **miniaturas** que mostrará esta página de navegación por facetas. Puedes elegir [miniaturas cuadradas (recortadas) o miniaturas medianas (sin recortar, con la proporción original)](../content/media.md#media-thumbnails) para los elementos y conjuntos de elementos que se muestran en la tabla. Si lo dejas en «Predeterminado», se mostrarán las miniaturas que prefiera el tema de tu sitio web. 

Selecciona «Guardar y... Permanecer en esta página» para continuar creando las categorías de navegación por facetas.

También puedes guardar tus cambios y salir sin trabajar en las categorías ni en las facetas seleccionando «Guardar y... Volver a las páginas».

### Categorías

Una vez creada la página, debes crear una categoría. Aquí es donde se configuran las facetas y los filtros utilizados para acotar el conjunto de recursos de dichas facetas. Puedes utilizar varias categorías para ofrecer a los usuarios diferentes subconjuntos de recursos desde los que iniciar su navegación, o bien crear una sola categoría y proporcionar a tus usuarios el conjunto máximo de recursos para explorar.

Por ejemplo, quizá quieras añadir una página general de «Explorar elementos» a tu navegación y, dentro de ella, ofrecer una categoría para navegar únicamente por imágenes, otra categoría para navegar únicamente por eventos y una última categoría que permita a los usuarios explorar todos los elementos del sitio, incluidas imágenes y eventos. O bien, podrías crear páginas de navegación por facetas independientes para añadirlas a tu navegación (una para cada clase de elemento) y, dentro de cada página, ofrecer categorías para restringir aún más los recursos según otro valor. 

Haz clic en el botón «Añadir categoría» para acceder a una nueva interfaz. 

Asigna a tu categoría un **nombre** que se mostrará al público. Este aparecerá en la parte superior de la página de navegación por facetas si es la única categoría, y aparecerá en el menú de selección de la página si hay varias categorías. Este es el único campo obligatorio de esta sección. 

Utiliza la interfaz de **consulta de búsqueda** para definir el conjunto de recursos que los usuarios podrán explorar. Puedes dejar la consulta en blanco para incluir todos los recursos del sitio de ese tipo. El botón «Editar» abre un panel a la derecha de la ventana que funciona exactamente igual que los [formularios de búsqueda avanzada](../search.md#item-advanced-search) para elementos, medios y conjuntos de elementos. El botón «Edición avanzada» te permite introducir una cadena de consulta manualmente. 

Puedes establecer un método de **ordenación predeterminado** que se utilizará cuando un visitante del sitio comience a navegar utilizando esta categoría. Esto se aplicará a la lista predeterminada de recursos o a la [tabla FB que hayas personalizado con columnas](#columns). El menú desplegable mostrará inicialmente «Creado» y «Título», pero se actualizará para reflejar las columnas que personalices más abajo en la página. Tendrás que guardar la configuración de las columnas y volver a esta página para ver el menú actualizado. Ten en cuenta que no puedes establecer una ordenación predeterminada según una columna de un conjunto de elementos. 

![Formulario de añadir categoría que muestra las opciones](modulesfiles/FacetedBrowse_SearchQuery.png)

También puedes incluir algún **texto de ayuda** para guiar a tus usuarios sobre cómo navegar por la página de navegación por facetas. Este texto aparecerá en la barra lateral izquierda junto con tus facetas de esta categoría. Hay un botón para contraer el texto (que está expandido por defecto); el botón dice «Instrucciones» por defecto, pero puedes cambiar esta etiqueta. Si no añades ningún texto de ayuda, este botón y el área de texto no aparecerán. 

Por último, esta área incluye la configuración del comportamiento de las **facetas de valor**: «Coincidir con cualquiera» y «Coincidir con todas». Si utilizas facetas de valor (esta configuración no es aplicable a las facetas de clase, plantilla, conjunto de elementos o texto completo), la opción «Coincidir con cualquiera» ampliará los resultados, mientras que «Coincidir con todas» los reducirá. Por ejemplo, si tienes una faceta de valor para encabezados de materia, el usuario puede seleccionar un encabezado de materia para ver todos los elementos que coincidan con él. Si añade otro encabezado temático, verá los elementos que coincidan con **cualquiera de** las dos selecciones si la categoría está configurada en «Coincidir con cualquiera», o solo los elementos que coincidan con **ambas** selecciones si la categoría está configurada en «Coincidir con todos». Esto también se aplica a una selección de cada una de dos facetas de valor independientes. Ten en cuenta que esta configuración se aplica a todas las facetas de valor de la categoría: no puedes establecer este comportamiento para cada faceta de valor de forma individual. 

!!! nota
  Si utilizas facetas de valor, te recomendamos que utilices el campo «Texto de ayuda» para explicar a tus usuarios el comportamiento esperado.

Tras configurar la categoría, puedes crear facetas y configurar columnas para tu vista de navegación. Una vez que hayas terminado de crear tus facetas y de configurar tus columnas de visualización, guarda tu categoría.

Puedes tener más de una categoría por página. Consulta [Varias categorías en una página](#multiple-categories-on-one-page) para ver cómo funciona esto en la vista pública.

### Facetas

Las facetas funcionan dentro de las categorías que hayas creado. Puedes tener una o más facetas para cada categoría. Se trata de las opciones que utilizarán los visitantes del sitio para filtrar la lista de elementos.

Puedes crear facetas a partir de las siguientes opciones: 

- Valor
- Clase de recurso
- Plantilla de recurso
- Conjunto de elementos (solo para elementos)
- Texto completo.

Los módulos pueden añadir más opciones. La principal es «Tipos de datos numéricos»; consulta la sección más abajo en esta página para obtener más información.

![Menú desplegable «Tipo de faceta» que muestra las opciones](modulesfiles/FacetedBrowse_SelectFacetType.png)

Una vez seleccionado el tipo, haz clic en el botón «Añadir». Se abrirá un panel deslizante en la parte derecha de la ventana del navegador para configurar la faceta. Los nombres de las facetas son siempre obligatorios y se mostrarán en la interfaz pública. 

No olvides hacer clic en el botón «Establecer faceta» para guardar tu trabajo y, a continuación, guarda la categoría.

##### **Valor** 

Las facetas de valor corresponden a los [valores](../content/items.md#values) dentro de una propiedad específica de cada elemento.

La imagen siguiente muestra algunas de las opciones del panel deslizante para la faceta de valor:

![Configurar el panel deslizante de la faceta de tipo «Valores».](modulesfiles/FacetedBrowse_configurefacet1.png)

!!! nota
  Ten en cuenta que la configuración «Modo de faceta de valor», situada en la parte superior de la interfaz de edición de la categoría, se aplicará a todas las facetas de valor que añadas a esta categoría. La opción «Coincidir con cualquiera» permitirá a los usuarios ampliar sus resultados añadiendo más selecciones, mientras que «Coincidir con todos» reducirá los resultados cuando se añadan más criterios.

Es obligatorio introducir un título; este será el encabezado público que se mostrará a los usuarios, y puede utilizarlo para explicar cómo funciona la faceta (por ejemplo, «Buscar en las descripciones» o «Seleccionar encabezados temáticos»). 

Utiliza el menú desplegable para seleccionar qué propiedad se va a utilizar para la faceta. Por ejemplo, quizá desees seleccionar el campo de descripción y permitir a los usuarios buscar dentro de esos textos descriptivos (con el tipo de selección «Entrada de texto» y el tipo de consulta «Contiene»). O quizá prefiera seleccionar su campo de materia y permitir a los usuarios ver todos los valores controlados que utiliza como encabezados de materia. Puede dejar este campo en blanco para ofrecer opciones de búsqueda o navegación por todas las propiedades de los recursos.

Configure el «Tipo de selección» para la faceta de navegación. Esto determina cómo interactúan los visitantes del sitio con las opciones del campo:

- Única (lista). Los visitantes solo pueden seleccionar una opción; las opciones se muestran en una lista de botones de opción. En la parte superior aparece la opción «Todas», que está seleccionada al cargar la página; los usuarios pueden seleccionar otra opción y, a continuación, desmarcarla seleccionando de nuevo «Todas». 
- Múltiple (lista). Los visitantes pueden seleccionar varias opciones; estas se muestran en una lista de casillas de selección. Las selecciones múltiples realizadas por los visitantes del sitio **restringirán** (Opción 1 Y Opción 2) los resultados de la búsqueda, independientemente del comportamiento del valor «Coincidir con cualquiera»/«Coincidir con todos» establecido en la categoría. 
- Única (menú desplegable). Los visitantes solo pueden seleccionar una opción; todas las opciones se muestran en un menú desplegable. En la parte superior aparece la opción «Seleccionar una...», que está seleccionada al cargarse la página; los usuarios pueden elegir otra opción y, a continuación, desmarcar esa elección haciendo clic de nuevo en «Seleccionar una...».
- Introducción de texto. Los visitantes pueden escribir texto para incluir o excluir recursos que contengan ese texto en sus valores.

![Configura el dibujo de la faceta para el tipo de faceta «Valores», tal y como se indica en la sección siguiente.](modulesfiles/FacetedBrowse_configurefacet2.png)

En el caso de **listas o menús desplegables**, puedes establecer un **tipo de consulta** (las consultas solo están disponibles para facetas de valor; no para clases, plantillas, conjuntos de elementos, etc.). Las opciones son:

- «Es exactamente»: los visitantes eligen un valor que coincide exactamente con el valor de la propiedad. 
	- Por ejemplo, los visitantes pueden marcar una casilla junto a un valor de «Asunto» disponible y ver todos los elementos que tengan ese valor exacto en la propiedad «Asunto». El texto exacto no distingue entre mayúsculas y minúsculas.
- «No es exactamente»: los visitantes eligen un valor que coincida exactamente con los elementos que deben excluirse de los resultados. 
	- Por ejemplo, los visitantes pueden marcar una casilla junto a un valor de «asunto» disponible y ver todos los elementos que no tengan ese valor exacto en su propiedad «asunto».
- «Contiene»: los visitantes pueden seleccionar un valor que aparezca en cualquier parte del valor de la propiedad.
- «No contiene»: Los visitantes pueden seleccionar un valor que deba excluirse de cualquier parte del valor de la propiedad.
- «Es un recurso con ID»: Los visitantes seleccionarán un recurso vinculado a los elementos disponibles en el campo indicado (por ejemplo, todos los elementos con el mismo recurso indicado en el campo «Creador»). Los recursos se muestran por su título, no por su ID. 
  - Si a continuación se selecciona «Añadir todos los valores disponibles», los visitantes verán una lista de recursos que se [utilizan como valores en otros elementos (es decir, recursos vinculados)](../content/items.md#linked-resources). Puedes utilizar esta opción sin seleccionar ninguna propiedad; en ese caso, se incluirán todos los valores de recursos vinculados. Ten en cuenta que los ID no aparecerán en la interfaz pública, aunque sí se muestren en el panel de administración: en las opciones públicas solo se mostrarán los títulos.
-  «No es un recurso con el ID»: Los visitantes seleccionarán un recurso que se vaya a excluir. 
	- Si a continuación se selecciona «Añadir todos los valores disponibles», los visitantes verán una lista de recursos que se utilizan como valores en otros elementos. Se puede emplear esta opción sin seleccionar ninguna propiedad; en ese caso, se incluirán todos los valores de los recursos vinculados. Tenga en cuenta que los ID no se mostrarán en la interfaz pública, aunque sí se muestran en el panel de administración.
-  «Tiene algún valor»: Los visitantes seleccionarán la propiedad. Se mostrarán todos los elementos con esa propiedad no vacía.  
  - Esto borrará la propiedad que hayas elegido en los pasos anteriores. Si a continuación seleccionas «Añadir todos los valores disponibles», los visitantes verán una lista de propiedades que contienen valores (en el formato «Dublin Core: Idioma»). 
-  «No tiene valores»: Los visitantes seleccionarán la propiedad. 
  - Esto borrará la propiedad que hayas elegido en los pasos anteriores. Si a continuación «Añades todos los valores disponibles», los visitantes verán una lista de propiedades que tienen valores vacíos (en el formato «Dublin Core: Idioma»). 

En el campo de texto «Seleccionar tipo», puede establecer una propiedad específica para la búsqueda o dejarlo en blanco para buscar en todas las propiedades. El texto exacto no distingue entre mayúsculas y minúsculas. Las opciones son:

- «Es exactamente»: los visitantes introducen un valor que coincide exactamente con el valor completo de la propiedad. 
- «No es exactamente»: los visitantes introducen un valor exacto que debe excluirse de los valores de la propiedad.
- «Contiene»: los visitantes introducen un valor que coincide con cualquier parte del valor de la propiedad. Por ejemplo, pueden buscar en las descripciones de los elementos un apellido o un lugar, o realizar una búsqueda de texto en todos los campos de metadatos disponibles.
- «No contiene»: los visitantes introducen un valor que debe excluirse de cualquier parte del valor de la propiedad. Por ejemplo, pueden excluir todos los artículos que mencionen un nombre de pila o un lugar concretos.

No se puede dejar la consulta en blanco. Es posible que desee proporcionar varios tipos de consultas de selección para el mismo campo, con el fin de ofrecer más detalle a los visitantes del sitio.

En los tipos de selección «Única (lista)» y «Múltiple (lista)», los creadores de páginas pueden optar por **truncar los valores mostrados** en la lista visible para el visitante del sitio, estableciendo un número en la opción «Truncar valores». Si se deja el campo en blanco, se mostrarán todos los valores. Si se introduce un número, solo se mostrarán ese número de valores, en orden, junto con un enlace «Ver más (X)» que indicará el número de valores adicionales.

A continuación, introduce los valores que compondrán la faceta. Cada valor debe aparecer en una línea separada. El formato de la entrada de valores dependerá del tipo de consulta seleccionado anteriormente. Si el tipo de consulta es:

-  «Es exactamente»: introduce un valor que coincida exactamente con el valor de la propiedad.
-  «Contiene»: introduce un valor que coincida con cualquier parte del valor de la propiedad.
-  «Es un recurso con ID»: introduce el ID del recurso seguido de cualquier valor (normalmente el título del recurso), separados por un solo espacio.
-  «Tiene cualquier valor»: introduce el ID de la propiedad seguido de cualquier valor (normalmente la etiqueta de la propiedad), separados por un solo espacio.

![La tabla «Valores disponibles» ordenada por frecuencia de aparición en la propiedad seleccionada.](modulesfiles/FacetedBrowse_AllValuesCount.png)

Puedes marcar la casilla «Mostrar todos los valores disponibles» para hacerte una idea de los datos que se pueden introducir. Esto mostrará los valores existentes en la propiedad que hayas seleccionado anteriormente o en todas las propiedades. Puedes ordenar esa tabla por los valores más comunes o por orden alfabético, utilizando los triángulos de ordenación que aparecen en la parte superior de la tabla. A continuación, puede hacer clic en el botón «Añadir todo» para rellenar la lista de valores.

El orden de los valores disponibles (de más a menos frecuentes, alfabéticamente, etc.) no se mantendrá al utilizar el botón «Añadir todo». Los valores de las propiedades se reorganizarán según un orden interno, al igual que las plantillas de recursos, las clases y los recursos por ID. El orden que aparece en el campo del panel de administración es el que se mostrará en la página pública. 

Por ejemplo, es posible que desees cargar todos los valores de la propiedad «Tema» y permitir a los usuarios explorar los elementos utilizando los encabezados temáticos actualmente en uso. Si seleccionas «Mostrar todos los valores disponibles», verás una lista de los temas actualmente en uso, ordenados de más a menos frecuentes. Ten en cuenta que quizá te interese limpiar tus datos y consolidar valores similares, o corregir errores tipográficos y variaciones, para que la navegación por facetas resulte más útil. Puedes utilizar el [módulo Value Suggest](valuesuggest.md) junto con la navegación por facetas para ver y limpiar datos desordenados.

Cuando estés satisfecho con tu configuración, asegúrate de hacer clic en el botón «Establecer faceta» antes de guardar la página.

!!! Nota
	Ten en cuenta que las facetas de «Todos los valores disponibles» no se actualizan dinámicamente cuando se añaden nuevos valores al corpus o cuando se editan valores. Debes recargar las opciones utilizando «Mostrar todos los valores disponibles» y «Añadir todo» en la faceta para actualizar el contenido de la lista de navegación. Recomendamos hacerlo con regularidad cuando se añadan nuevos elementos.

Así es como aparecerá la faceta de valores del ejemplo anterior en una página pública de navegación por facetas: 

![Configurar el dibujo de la faceta para el tipo de faceta «Valores», tal y como se indica en la sección siguiente.](modulesfiles/FacetedBrowse_facetpublic2.png)

##### **Clase de recurso** 

Permite a los visitantes filtrar los elementos según su clase de recurso.

Establece el tipo de selección para la faceta de navegación. Con la opción «Múltiple (lista)», las selecciones múltiples realizadas por los visitantes del sitio **ampliarán** (Opción 1 O Opción 2) los resultados de la búsqueda. 

Selecciona las clases que compondrán las facetas en el menú desplegable.  Si lo deseas, puedes recortar visualmente las listas.

![Configurar el panel de facetas para el tipo de faceta «Valores».](modulesfiles/FacetedBrowse_facetClass.png)

Marca la casilla «Mostrar todas las clases disponibles» para hacerte una idea de los datos que se pueden introducir. El orden de los valores disponibles (de más a menos frecuente, o alfabéticamente, etc.) no se mantendrá al utilizar el botón «Añadir todo». Las clases se reorganizarán según un orden interno. El orden que aparece en el campo del panel de administración es el que aparecerá en la página pública. 

##### **Plantilla de recurso** 

Permite a los visitantes filtrar los elementos según su [plantilla de recurso](../content/resource-template.md).

Establece el tipo de selección para la faceta de navegación. Para la opción «Múltiple (lista)», las selecciones múltiples realizadas por los visitantes del sitio **ampliarán** (Opción 1 O Opción 2) los resultados de la búsqueda. 

Selecciona las plantillas de recursos que compondrán las facetas. Puedes recortar visualmente las listas si lo deseas. 

Marca la casilla «Mostrar todas las plantillas disponibles» para hacerte una idea de los datos que se pueden introducir. El orden de los valores disponibles (de más a menos frecuentes, por orden alfabético, etc.) no se mantendrá cuando utilices el botón «Añadir todo». Los valores de las plantillas se reorganizarán según un orden interno. El orden que aparece en el campo del panel de administración es el que aparecerá en la página pública. 

##### **Conjunto de elementos** 

Permite a los visitantes filtrar los elementos mediante [conjuntos de elementos](../content/item-sets.md).

Establece el tipo de selección para la faceta de navegación. Con la opción «Múltiple (lista)», las selecciones múltiples realizadas por los visitantes del sitio **ampliarán** (Opción 1 O Opción 2) los resultados de la búsqueda. 

Selecciona los conjuntos de elementos que compondrán las facetas.  Si lo deseas, puedes recortar visualmente las listas.

![Configurar el panel de facetas para el tipo de faceta «Valores».](modulesfiles/FacetedBrowse_facetItemSet.png)

Marca la casilla «Mostrar todos los conjuntos de elementos disponibles» para hacerte una idea de los datos que se pueden introducir. El orden de los valores disponibles (de más a menos frecuentes, alfabéticamente, etc.) no se mantendrá cuando utilices el botón «Añadir todo». Los conjuntos de elementos se reorganizarán según su ID interno. El orden que aparece en el campo del panel de administración es el que se mostrará en la página pública. 

##### **Texto completo** 

Añade una barra de búsqueda de texto que filtrará los resultados en función de lo que introduzca el visitante. Esto incluirá todos los valores, como el título, la descripción, la clase y cualquier texto extraído. Solo puedes tener una barra de búsqueda de texto completo en una categoría. 

### Integración de «Numeric Data Types»

Si utilizas el [módulo «Numeric Data Types»](numericdatatypes.md), dispondrás de tipos de facetas adicionales con los que trabajar, entre los que se incluyen «Fecha posterior a», «Fecha anterior a», «Valor mayor que», «Valor menor que», «Duración mayor que», «Duración menor que» y «Fecha en intervalo».

![Menú desplegable de tipos de faceta que muestra opciones que incluyen tipos de datos numéricos de fecha](modulesfiles/FacetedBrowse_NumericDataTypesSelect.png)

Una vez seleccionado un tipo de faceta, podrás configurar la faceta para que funcione con las propiedades que utilicen un tipo de datos numérico. Solo se mostrarán en el menú desplegable las propiedades con el tipo de datos exacto establecido (Número, Fecha, Duración o Intervalo).

En la vista pública, la faceta se controlará mediante un menú desplegable.

![Página de navegación por facetas pública con botones de opción para seleccionar una lista de valores de «Estado» y un menú desplegable «Fecha de nacimiento anterior a» en la columna de la izquierda. En la columna de la derecha hay una tabla de elementos con información sobre el «Título», la «Ubicación» y el «Cónyuge»](modulesfiles/FacetedBrowse_DatesPublic.png)

### Columnas

Los elementos de la página pública se mostrarán inicialmente en forma de lista (independientemente de la configuración del tema de tu sitio). La lista incluye filas con el título, la descripción y la miniatura de cada recurso. Estas filas pueden aparecer truncadas (el texto excesivamente largo se ocultará), en función de la configuración del tema de tu sitio web.

Puedes configurar la información que se muestra sobre los resultados añadiendo columnas de metadatos a la visualización. Esto convertirá la visualización en una tabla con una fila para cada recurso de los resultados. Las columnas se configuran categoría por categoría. Si tu página solo tiene una categoría, la visualización inicial mostrará sus columnas de forma predeterminada; si tienes varias categorías, se mostrará el formato de lista predeterminado.

En la vista pública de una búsqueda por facetas, los usuarios pueden ordenar por una columna seleccionándola en el menú desplegable. Cada columna se puede ordenar en orden ascendente o descendente. Si deseas impedir que los usuarios ordenen por una columna determinada, puedes marcar la casilla «Excluir ordenación por» al configurar dicha columna para excluirla del menú desplegable.

!!! Nota
	Si un valor es muy largo, como el título o la descripción de un recurso, es posible que las filas de la tabla resulten muy altas, con el campo más grande ocupando la columna más ancha y el resto de columnas reducidas para compensar. Puedes utilizar el [módulo Editor CSS](csseditor.md) para implementar un truncamiento que oculte el texto que se salga de la columna.

Selecciona un tipo de columna para añadir desde el menú desplegable: 

- Título (enlace al recurso) 
- Valor
- Clase de recurso
- Plantilla de recurso 
- Conjunto de elementos 
- ID.

Una vez seleccionado el tipo, haz clic en el botón «Añadir». Se abrirá un panel con opciones para configurar la columna. 

Cada columna debe tener un título, que se mostrará en el encabezado de la tabla. También puedes impedir que los visitantes del sitio puedan ordenar cada columna. A continuación se describen otros ajustes.

Recuerda hacer clic en el botón «Establecer columna» y, a continuación, guardar la página; de lo contrario, tu trabajo no se guardará.

![Página de navegación por facetas pública con columnas visibles](modulesfiles/FacetedBrowse_columns.png)

#### **Valor**

Selecciona una propiedad que se vaya a mostrar (obligatorio). 

A continuación, establece el número máximo de valores para esa propiedad. Para mostrar todos los valores, deja el campo en blanco. Esto puede provocar que las filas de la tabla sean muy altas, si los elementos tienen varios valores para la propiedad seleccionada o si algunos valores son muy largos. 

#### **Conjunto de elementos**

Establece el número máximo de conjuntos de elementos que se mostrarán. Para mostrar todos los valores, deja el campo en blanco. Esto puede provocar que las filas de tu tabla sean muy altas, si los elementos pertenecen a varios conjuntos de elementos. 

Los conjuntos de elementos se mostrarán con pequeñas miniaturas y enlaces a los mismos. 

## Añadir páginas de navegación por facetas a tu navegación

Haz clic en la [pestaña Navegación](../sites/site_navigation.md) de tu sitio. En la lista «Añadir un enlace personalizado» de la barra lateral de la página, selecciona la opción «Navegación por facetas».

![La pantalla de navegación muestra el menú desplegable para añadir la página de navegación por facetas, abierto para ver las páginas disponibles](modulesfiles/FacetedBrowse_AddPageNav.png)

Asigna una etiqueta a tu enlace personalizado (opcional) y selecciona una opción de la lista desplegable de páginas de navegación por facetas (obligatorio). Si la etiqueta está en blanco, se utilizará el título de la página.

Puedes añadir tantos enlaces personalizados de navegación por facetas como desees.

Arrastra y suelta tus páginas en el lugar deseado de la navegación de tu sitio y, a continuación, guarda los cambios.

## Vistas públicas

Las vistas públicas de las páginas de navegación por facetas incluyen la página base, en la que puede haber una o más categorías en las que hacer clic, y luego las páginas específicas de cada categoría, que muestran las columnas elegidas para esa vista. Los recursos disponibles se mostrarán en una lista si no se ha seleccionado ninguna columna para su visualización.

![Página de navegación por facetas con una lista de eventos que tuvieron lugar en el National Mall. En la parte izquierda de la imagen hay una lista de épocas con botones de opción.](modulesfiles/FacetedBrowse_publicView.png)

En esta imagen, la faceta es «Época», que se muestra como una lista de selección única. Los elementos de esta página se muestran en columnas con el título y la época de cada elemento.

Dependiendo de la configuración de las columnas en cada categoría, es posible que haya más columnas de las que pueda albergar la ventana del navegador del usuario. Si es así, solo verá el número de columnas que quepan en la página sin desbordarse, y verá unas flechas a la izquierda y a la derecha, situadas en la esquina superior derecha de la tabla, para desplazar las columnas ocultas y poder verlas. Ten en cuenta que el texto de las columnas que no se muestran en la página no aparecerá si el usuario realiza una búsqueda de texto en la página.

![Página de navegación por facetas con la tabla de resultados, en la que se muestran flechas a la izquierda y a la derecha para ver las columnas que no son visibles con el ancho actual de la página.](modulesfiles/FacetedBrowse_publicView2.png)

### Varias categorías en una misma página

Cuando hay varias categorías en una página, esta se carga mostrando todos los recursos de todas las categorías y muestra enlaces a las categorías disponibles en un submenú.

![Página de navegación por facetas con dos categorías. Las categorías aparecen resaltadas en un recuadro rojo con la etiqueta «Categorías»](modulesfiles/FacetedBrowse_multiCatView1.png)

Cuando un usuario hace clic en una categoría, la lista de recursos cambia para mostrar únicamente los recursos de esa categoría, la disposición de columnas que hayas configurado y sus facetas en el submenú. Los usuarios pueden utilizar el botón «Atrás» de la página para volver a la lista completa de categorías y borrar sus filtros.

![Una página de navegación por facetas con las facetas visibles. El encabezado de la categoría aparece encima de las facetas. Encima de este hay un botón con la etiqueta «Atrás». Las anotaciones indican el botón, la categoría y los encabezados de las facetas.](modulesfiles/FacetedBrowse_multiCatView2.png)

### Bloque de página «Vista previa de la navegación por facetas»

Puedes añadir un bloque de página «Vista previa de la navegación por facetas» a las páginas de los sitios de Omeka. Este bloque de página mostrará los primeros elementos que aparecen en la página completa de navegación por facetas, sin ninguna de las facetas de la barra lateral ni las herramientas de navegación disponibles en la página. 

![Bloque de página de vista previa de la navegación por facetas en la configuración de administración, con los ajustes que se indican a continuación. Se ha seleccionado una categoría de página, el «Límite» está fijado en 6, el «Título de la vista previa» está fijado en «Explorar por tipo» y el «Texto del enlace» está fijado en «Explorar todo».](modulesfiles/FacetedBrowse_previewpageblock.png)

El bloque de página incluye los siguientes ajustes:

* Categoría de página: selecciona en el menú desplegable que muestra cada página de FB y todas sus categorías. Solo puedes elegir una categoría para mostrar por bloque de página, pero puedes tener varios bloques de página. 
* Límite: elige el número máximo de elementos que se mostrarán de entre los resultados predeterminados de la categoría de Facebook. Consulta la propia página de Facebook para ver qué elementos se mostrarán según su configuración actual. 
* Título de vista previa: introduce un título que se mostrará en la parte superior del bloque de página. 
* Texto del enlace: Introduce el texto que se mostrará en un botón situado en la parte inferior del bloque de página. Esto redirigirá a los usuarios a la página completa de Facebook. 

![El bloque de página de vista previa de Facebook tal y como aparece en el tema «The Daily».](modulesfiles/FacetedBrowse_previewpageblock2.png)

## Búsqueda predeterminada con «Faceted Browse»

Puedes dirigir a tus usuarios a una página de «Faceted Browse» directamente desde la barra de búsqueda que aparece en el encabezado o en el menú de tu sitio web. 

Ve a la página de Ajustes de tu sitio y busca la sección «Faceted Browse». Verás un menú desplegable que te permite seleccionar una de tus categorías para que se muestre cuando se realice una búsqueda de texto en la barra de búsqueda de todo el sitio. 

![Sección «Navegación por facetas» en la configuración del sitio](modulesfiles/FacetedBrowse_sitewideSetting.png)

Ten en cuenta que solo aparecerán las categorías con una faceta de búsqueda de texto. 

Cuando un usuario realice una búsqueda de texto en tu sitio web, se le redirigirá a la categoría de «Navegación por facetas» y verá su búsqueda de texto completada en la faceta de texto completo de la barra lateral. Desde allí, podrá acotar o ampliar aún más su búsqueda. 

![Una búsqueda de texto de «william» ha cargado la página de «Navegación por facetas», y «william» también aparece en la faceta de texto completo de la barra lateral.](modulesfiles/FacetedBrowse_sitewide.png)
