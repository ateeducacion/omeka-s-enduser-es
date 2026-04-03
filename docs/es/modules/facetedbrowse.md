# Búsqueda por facetas

El [módulo de búsqueda por facetas](https://omeka.org/s/modules/FacetedBrowse){target=_blank} te permite crear páginas de «exploración de recursos» con facetas —funciones de filtrado y ordenación— que los visitantes del sitio pueden utilizar para explorar tus colecciones. Las páginas de búsqueda por facetas se pueden crear para elementos, conjuntos de elementos o archivos multimedia. 

Con este módulo, los administradores del sitio pueden configurar páginas de búsqueda por facetas y añadirlas a la [navegación](../sites/site_navigation.md) de su sitio. Los usuarios finales pueden entonces navegar por los recursos y utilizar las facetas para acotar los resultados de una manera lógica e intuitiva. Esta funcionalidad es similar a las opciones de filtrado de muchos sitios web y debería ser fácil de gestionar para los usuarios siempre que el lenguaje sea claro.

La sección [vista pública](#public-views) que aparece a continuación muestra cómo se muestran estas facetas en páginas de una sola categoría y de varias categorías.

Las páginas de navegación por facetas existen como [páginas](../sites/site_pages.md) independientes. Puedes [añadir la navegación por facetas a una página como un bloque](#faceted-browse-preview-page-block) que mostrará una vista previa de la página de navegación por facetas, pero sin toda su funcionalidad. 

Una vez activada, la navegación por facetas se configura para cada sitio web individualmente.

## Terminología

Guía de los términos utilizados para describir los aspectos de una página de navegación por facetas:

- Categoría: un grupo de recursos (elementos, conjuntos de elementos o medios) a los que se aplican facetas en una página específica. Puedes utilizar una consulta para filtrar los recursos, o dejarla en blanco para mostrar todos los recursos de ese tipo. 
- Faceta: un aspecto de un recurso —normalmente parte de los metadatos— que se convierte en una forma de filtrar los recursos de la categoría. La navegación por facetas funciona mejor cuando se dispone de vocabularios controlados en los valores de los metadatos, o cuando los valores únicos se pueden clasificar en grupos (como fechas ordenadas por siglo). 
- Columna: información que se mostrará para cada recurso en los resultados. Las columnas son opcionales. Una vez que haya establecido al menos una columna, los elementos se mostrarán en forma de tabla (no de cuadrícula). Cuando no se establezca ninguna columna, se mostrará la navegación predeterminada de su sitio (por ejemplo, título, miniatura y descripción de cada recurso).
- Seleccionar: cuando una faceta es navegable, debe ofrecer a sus visitantes los medios más adecuados para ordenar o buscar en esas facetas. Puede permitirles, por ejemplo, excluir o incluir cadenas en los resultados, buscar coincidencias exactas de valores completos o, con tipos de datos numéricos, agrupar los valores en categorías que usted establezca. 

![Página de navegación por facetas con una lista de eventos que tuvieron lugar en el National Mall. En la parte izquierda de la imagen hay una lista de opciones con casillas de selección.](modulesfiles/FacetedBrowse_publicView-basic.png)

En la vista pública de ejemplo anterior, el título «Explorar elementos» se utiliza para la apariencia de la página en la navegación; «Filtrar por tipo» es el nombre de la categoría en la barra lateral izquierda de la página. Las facetas de la categoría incluyen «Clase», «Plantilla utilizada» y «Colección». En estos ejemplos, la opción de selección utilizada es «Múltiple (lista)», lo que da como resultado casillas de verificación para cada opción, y las opciones visibles se truncan en 4.

## Crear páginas de navegación por facetas

![Administrador del sitio mostrando la página de inicio de la navegación por facetas.](modulesfiles/FacetedBrowse_1.png)

Una vez que el módulo de navegación por facetas esté activo, aparecerá una pestaña para la navegación por facetas en el menú contextual de cada sitio. Al hacer clic en esta pestaña, accederás a una lista de todas tus páginas de navegación por facetas para ese sitio.

Los administradores del sitio deben crear páginas de navegación por facetas antes de que puedan añadirse a la navegación del sitio.

### Añadir una página de navegación por facetas

Cree una nueva página haciendo clic en el botón «Añadir una página». Esto le llevará a una nueva página donde podrá añadir la información básica de la página y empezar a añadir categorías. 

![Interfaz de creación de página mostrando el menú desplegable para guardar la página](modulesfiles/FacetedBrowse_AddPage.png)

El **título de la página** es obligatorio y se mostrará en las pestañas del navegador y se enviará en los metadatos de la página. Puede establecer una etiqueta independiente en la navegación del sitio. La mayoría de los temas no mostrarán este título de forma visible en la página. Cuando se utiliza una sola categoría, su título aparecerá en la página; cuando se configuran dos o más categorías, el encabezado «Explorar» se mostrará encima de los enlaces de categorías en la barra lateral (consulte [la captura de pantalla siguiente](#multiple-categories-on-one-page) para ver cómo se mostrará). 

Utilice el menú desplegable **tipo de recurso** para seleccionar el tipo de recurso que desea que los usuarios puedan explorar en esta página: Elementos, Conjuntos de elementos o Medios. Esto no se puede editar una vez creada la página.

A continuación, elija las **miniaturas** que mostrará esta página de navegación por facetas. Puede elegir [miniaturas cuadradas (recortadas) o miniaturas medianas (sin recortar, con relación de aspecto original)](../content/media.md#media-thumbnails) para los elementos y conjuntos de elementos que se muestran en la tabla. Si deja esta opción en «Predeterminado», se mostrarán las miniaturas que prefiera su tema. 

Seleccione «Guardar y... Permanecer en esta página» para continuar creando la navegación por facetas.

También puede guardar sus cambios y salir sin trabajar en las categorías y facetas seleccionando «Guardar y... Volver a las páginas».

### Categorías

Una vez creada la página, debe crear una categoría. Aquí es donde se crean las facetas, y también puede utilizar filtros para reducir el conjunto de recursos que se pueden explorar con esas facetas. Puede utilizar varias categorías para proporcionar diferentes subconjuntos de recursos con los que los usuarios puedan comenzar su exploración.

Por ejemplo, es posible que desee añadir una página general de «Explorar elementos» a su navegación y proporcionar dentro de ella una categoría para navegar solo por imágenes, otra categoría para navegar solo por eventos y una última categoría que permita a los usuarios explorar todos los elementos del sitio, incluidas imágenes y eventos. O bien, podría crear páginas de navegación por facetas independientes para añadir a su navegación —una para cada clase de elemento— y, dentro de cada página, proporcionar categorías para restringir aún más los recursos mediante otro valor. 

Haga clic en el botón «Añadir categoría» para acceder a una nueva interfaz. 

Asigne a su categoría un **nombre** que se mostrará al público. Este aparecerá en la parte superior de la página de navegación por facetas si es la única categoría, y aparecerá en el menú de selección de la página si hay varias categorías. Este es el único campo obligatorio de esta sección. 

Utilice la interfaz de **consulta de búsqueda** para establecer el conjunto de recursos que los usuarios podrán explorar. El botón «Editar» abre un panel en el lado derecho de la ventana del navegador que funciona exactamente igual que los [formularios de búsqueda avanzada](../search.md#item-advanced-search) para elementos, medios y conjuntos de elementos. El botón «Edición avanzada» te permite introducir una cadena de consulta. Puedes dejar la consulta en blanco para incluir todos los recursos del sitio de ese tipo. 

Puede establecer un método de **ordenación predeterminado** que se utilizará cuando un visitante del sitio comience a navegar utilizando esta categoría. Esto se aplicará a la lista predeterminada de recursos o a la [tabla FB que haya personalizado con columnas](#columns). El menú desplegable mostrará inicialmente «Creado» y «Título», pero se actualizará para reflejar las columnas que personalice más abajo en la página. Deberá guardar la configuración de las columnas y volver a esta página para ver el menú actualizado. Tenga en cuenta que no puede establecer una ordenación predeterminada por una columna de conjunto de elementos. 

![Formulario de añadir categoría mostrando las opciones](modulesfiles/FacetedBrowse_SearchQuery.png)

También puede incluir un **texto de ayuda** para guiar a los usuarios sobre cómo navegar por la página de navegación por facetas. Este texto aparecerá en la barra lateral izquierda junto con las facetas de esta categoría. Hay un botón para contraer el texto (que está expandido por defecto); el botón dice «Instrucciones» por defecto, pero puede cambiar esta etiqueta. Si no añade ningún texto de ayuda, este botón y el área de texto no aparecerán. 

Por último, esta área incluye la configuración del comportamiento de las **facetas de valor**: «Coincidir con cualquiera» y «Coincidir con todas». Si utiliza facetas de valor (esta configuración no es aplicable a facetas de clase, plantilla, conjunto de elementos o texto completo), puede utilizarla para garantizar que los usuarios puedan ampliar sus resultados con «coincidir con cualquiera» o reducirlos con «coincidir con todas». Por ejemplo, si tienes una faceta de valor para encabezados de materia, el usuario puede seleccionar un encabezado de materia para ver todos los elementos que coincidan con él. Si añade además otro encabezado de materia, verá los elementos que coincidan con cualquiera de las selecciones si la categoría está configurada en «Coincidir con cualquiera», o solo los elementos que coincidan con ambas selecciones si la categoría está configurada en «Coincidir con todos». Esto también se aplica a una selección de cada una de dos facetas de valor separadas. Tenga en cuenta que esta configuración se aplica a todas las facetas de valor de la categoría; no puede establecer este comportamiento para cada faceta de valor individualmente. 

!!! nota
  Si la selección del «Modo de facetas de valor» aquí afecta al comportamiento de su página de navegación por facetas (es decir, si está utilizando facetas de valor en esta categoría), es posible que desee utilizar el campo «Texto de ayuda» para explicar el comportamiento esperado a sus usuarios.

Una vez configurada la categoría, puede crear facetas y establecer columnas para la visualización de la navegación. Cuando haya terminado de crear las facetas y de configurar las columnas de visualización, guarde la categoría.

Puede tener más de una categoría por página. Consulte [Varias categorías en una página](#multiple-categories-on-one-page) para ver cómo funciona esto en la vista pública.

### Facetas

Las facetas funcionan dentro de las categorías que haya creado. Puede tener una o más facetas para cada categoría. Estas son las selecciones que los visitantes del sitio utilizarán para filtrar la lista de elementos.

Puede crear facetas a partir de las siguientes opciones: 

- Valor
- Clase de recurso
- Plantilla de recurso
- Conjunto de elementos (solo para elementos)
- Texto completo.

![Menú desplegable de tipo de faceta mostrando opciones](modulesfiles/FacetedBrowse_SelectFacetType.png)

Una vez seleccionado el tipo, haga clic en el botón «Añadir». Se abrirá un panel deslizante en el lado derecho de la ventana del navegador con opciones para configurar la faceta. Los nombres de las facetas son siempre obligatorios y se mostrarán en la interfaz pública. 

A continuación se describen otras opciones de facetas.

La imagen siguiente muestra las opciones del panel deslizante para la faceta Valor:

![Panel de configuración de la faceta para el tipo de faceta «Valores», tal y como se indica en la sección siguiente.](modulesfiles/FacetedBrowse_ConfigureFacetV.png) 

Para los tipos de selección Única (lista) y Múltiple (lista), los creadores de la página pueden optar por truncar los valores de la lista que ven los visitantes del sitio, estableciendo un número en la opción «Truncar valores». Si se deja el campo en blanco, se mostrarán todos los valores. Al introducir un número, solo se mostrarán ese número de facetas, en orden, con un enlace «Ver más (X)» que muestra el número de facetas adicionales. 

No olvide hacer clic en el botón «Establecer faceta» para guardar su trabajo y, a continuación, guarde la categoría.

##### **Valor** 

Las facetas de valor corresponden a los [valores](../content/items.md#values) dentro de una propiedad específica de cada elemento.

!!! nota
  Ten en cuenta que la configuración «Modo de faceta de valor» en la parte superior de la interfaz de edición de categorías se aplicará a todas las facetas de valor que añadas a esta categoría. «Coincidir con cualquiera» permitirá a los usuarios ampliar sus resultados añadiendo más selecciones, mientras que «Coincidir con todos» reducirá los resultados cuando se añadan más criterios.

Utilice el menú desplegable para seleccionar qué propiedad utilizar para la faceta. Por ejemplo, es posible que desee seleccionar el campo de descripción y permitir a los usuarios buscar dentro de esos textos descriptivos. O tal vez desee seleccionar el campo de tema y permitir a los usuarios ver todos los valores controlados que está utilizando como encabezados de tema. Puede dejar este campo en blanco para ofrecer opciones de búsqueda o navegación en todas las propiedades de los recursos.

Establezca el Tipo de selección para la faceta de navegación. Esto determina cómo interactúan los visitantes del sitio con las opciones del campo:

- Única (lista). Los visitantes pueden seleccionar solo una; todas las opciones se muestran en una lista de botones de opción.
- Múltiple (lista). Los visitantes pueden seleccionar varias; todas las opciones se muestran en una lista de casillas de verificación. Las selecciones múltiples de los visitantes del sitio reducirán (Opción 1 Y Opción 2) los resultados de la búsqueda. 
- Único (menú desplegable). Los visitantes pueden seleccionar solo una opción; todas las opciones se muestran en un menú desplegable.
- Entrada de texto. Los visitantes pueden escribir texto para incluir o excluir recursos que incluyan ese texto en sus valores.

Para los tipos de selección que incluyen una lista o un menú desplegable, puede establecer un tipo de consulta (las consultas solo están disponibles para facetas de valor; no para clases, plantillas, conjuntos de elementos, etc.). Las opciones son:

- «Es exactamente»: los visitantes eligen un valor que coincide exactamente con el valor de la propiedad. 
  - Por ejemplo, los visitantes pueden marcar una casilla junto a un valor de tema disponible y ver todos los elementos que tengan ese valor exacto en su propiedad de tema. El texto exacto no distingue entre mayúsculas y minúsculas.
- «No es exactamente»: los visitantes eligen un valor que coincide exactamente con los elementos que se deben excluir de los resultados. 
	- Por ejemplo, los visitantes pueden marcar una casilla junto a un valor de tema disponible y ver todos los elementos que no tengan ese valor exacto en su propiedad de tema.
- «Contiene»: Los visitantes pueden seleccionar un valor que aparezca en cualquier parte del valor de la propiedad.
- «No contiene»: Los visitantes pueden seleccionar un valor que se excluya de cualquier parte del valor de la propiedad.
-  «Es un recurso con ID»: Los visitantes seleccionarán un recurso que se incluirá. 
  - Si a continuación se selecciona «Añadir todos los valores disponibles», los visitantes verán una lista de recursos que se [utilizan como valores en otros elementos (es decir, recursos vinculados)](../content/items.md#linked-resources). Puede emplear esta opción sin seleccionar ninguna propiedad; en ese caso, se incluirán todos los valores de recursos vinculados. Tenga en cuenta que los ID no se mostrarán en la interfaz pública, aunque sí se muestran en la parte administrativa.
-  «No es un recurso con ID»: Los visitantes seleccionarán un recurso que se excluirá. 
	- Si a continuación «Añade todos los valores disponibles», los visitantes verán una lista de recursos que se utilizan como valores en otros elementos. Puede emplear esta opción sin seleccionar ninguna propiedad; en ese caso, se incluirán todos los valores de recursos vinculados. Tenga en cuenta que los ID no se mostrarán en la interfaz pública, aunque sí se muestran en el panel de administración.
-  «Tiene cualquier valor»: Los visitantes seleccionarán la propiedad. 
	- Esto borrará la propiedad que haya elegido en los pasos anteriores. Si a continuación selecciona «Añadir todos los valores disponibles», los visitantes verán una lista de propiedades que contienen valores (en el formato «Dublin Core: Idioma»). 
-  «No tiene valores»: Los visitantes seleccionarán la propiedad. 
	- Esto borrará la propiedad que haya elegido en los pasos anteriores. Si a continuación selecciona «Añadir todos los valores disponibles», los visitantes verán una lista de propiedades que tienen valores vacíos (en el formato «Dublin Core: Idioma»). 

Para el tipo de selección de entrada de texto, puede establecer una propiedad específica para buscar, o dejarlo en blanco para buscar en todas las propiedades. El texto exacto no distingue entre mayúsculas y minúsculas. Las opciones son:

- «Es exactamente»: Los visitantes introducen un valor que coincide exactamente con el valor completo de la propiedad. 
- «No es exactamente»: Los visitantes introducen un valor exacto que debe excluirse de los valores de la propiedad.
- «Contiene»: Los visitantes introducen un valor que coincide con cualquier parte del valor de la propiedad. Por ejemplo, pueden buscar en las descripciones de los elementos un apellido o un lugar.
- «No contiene»: los visitantes introducen un valor que debe excluirse de cualquier parte del valor de la propiedad. Por ejemplo, pueden excluir todos los artículos que mencionen un nombre de pila o un lugar específicos.

No se puede dejar la consulta en blanco. Es posible que desee proporcionar varios tipos de consultas de selección para el mismo campo, con el fin de ofrecer más granularidad a los visitantes del sitio.

Para los tipos de selección Única (lista) y Múltiple (lista), los creadores de páginas pueden optar por truncar los valores disponibles en esta lista que es visible para el visitante del sitio estableciendo un número en la opción «Truncar valores». Si se deja el campo en blanco, se mostrarán todos los valores. Al introducir un número, solo se mostrarán ese número de facetas, en orden, con un enlace «Ver más (X)» que muestra el número de facetas adicionales.

A continuación, introduzca los valores que compondrán las facetas. Cada valor debe estar en una línea separada.

Marque la casilla «Mostrar todos los valores disponibles» para hacerse una idea de los datos que se pueden introducir. Esto mostrará los valores existentes en la propiedad que haya seleccionado anteriormente, o de todas las propiedades. Puede hacer clic en el botón «Añadir todo» para rellenar la lista de valores. 

El orden de los valores disponibles (de más a menos frecuentes) no se mantendrá al utilizar el botón «Añadir todo». Las propiedades se reorganizarán según un orden interno, al igual que las plantillas de recursos, las clases y los recursos por ID. 

El formato de la entrada de valores dependerá del tipo de consulta seleccionado anteriormente. Si el tipo de consulta es

-  «Es exactamente»: introduzca un valor que coincida exactamente con el valor de la propiedad.
-  «Contiene»: introduzca un valor que coincida con cualquier parte del valor de la propiedad.
-  «Es un recurso con ID»: introduzca el ID del recurso seguido de cualquier valor (normalmente el título del recurso), separados por un solo espacio.
-  «Tiene cualquier valor»: introduzca el ID de la propiedad seguido de cualquier valor (normalmente la etiqueta de la propiedad), separados por un solo espacio.

Cuando esté satisfecho con su configuración, haga clic en el botón «Establecer faceta».

Por ejemplo, es posible que desee cargar todos los valores de la propiedad «Tema» y permitir a los usuarios explorar elementos utilizando los encabezados de tema actualmente en uso. Si selecciona «Mostrar todos los valores disponibles», verá una lista de los temas actualmente en uso, ordenados de más frecuentes a menos. Tenga en cuenta que es posible que desee limpiar sus datos y consolidar valores similares, o corregir errores tipográficos y variaciones, para que la navegación por facetas resulte más útil. Puede utilizar el [módulo Value Suggest](../modules/valuesuggest.md) junto con la navegación por facetas para ver y limpiar datos desordenados.

!!! nota
  Tenga en cuenta que las facetas de «Todos los valores disponibles» no se actualizan dinámicamente cuando se añaden nuevos valores al corpus o cuando se editan valores. Debe volver a cargar las opciones utilizando «Mostrar todos los valores disponibles» y «Añadir todo» en la faceta para actualizar el contenido de la lista de navegación. Recomendamos hacerlo con regularidad cuando se añadan nuevos elementos.

##### **Clase de recurso** 

Permite a los visitantes filtrar los elementos por su clase de recurso.

Establezca el Tipo de selección para la faceta de navegación. Para la opción «Múltiple (lista)», las selecciones múltiples realizadas por los visitantes del sitio ampliarán (Opción 1 O Opción 2) los resultados de la búsqueda. 

Seleccione las clases que compondrán las facetas en el menú desplegable.

Marque la casilla «Mostrar todas las clases disponibles» para hacerse una idea de los datos que están disponibles para introducir.

##### **Plantilla de recurso** 

Permite a los visitantes filtrar los elementos por su [plantilla de recurso](../content/resource-template.md).

Establezca el tipo de selección para la faceta de navegación. Con la opción «Múltiple (lista)», las selecciones múltiples de los visitantes del sitio ampliarán (Opción 1 O Opción 2) los resultados de la búsqueda. 

Seleccione las plantillas de recurso que compondrán las facetas.

Marque la casilla «Mostrar todas las plantillas disponibles» para hacerse una idea de los datos que se pueden introducir.

##### **Conjunto de elementos** 

Permite a los visitantes filtrar los elementos por [conjuntos de elementos](../content/item-sets.md).

Establezca el tipo de selección para la faceta de navegación. Con la opción «Múltiple (lista)», las selecciones múltiples de los visitantes del sitio ampliarán (Opción 1 O Opción 2) los resultados de la búsqueda. 

Seleccione los conjuntos de elementos que compondrán las facetas.

Marque la casilla «Mostrar todos los conjuntos de elementos disponibles» para hacerse una idea de los datos que se pueden introducir.

##### **Texto completo** 

Añade una barra de búsqueda de texto que filtrará los resultados en función de lo que introduzca el visitante. Esto incluirá todos los valores, como el título, la descripción, la clase y cualquier texto extraído. 

### Integración de tipos de datos numéricos

Si utiliza el [módulo Tipos de datos numéricos](../modules/numericdatatypes.md), dispondrá de tipos de facetas adicionales con los que trabajar, entre ellos: Fecha posterior a, Fecha anterior a, Valor mayor que, Valor menor que, Duración mayor que, Duración menor que y Fecha en intervalo.

![Menú desplegable de tipos de facetas que muestra opciones que incluyen tipos de datos numéricos de fecha](../modules/modulesfiles/FacetedBrowse_NumericDataTypesSelect.png)

Una vez seleccionado un tipo de faceta, podrá configurar la faceta para que funcione con las propiedades que utilicen un tipo de datos numérico. Solo se mostrarán en el menú desplegable las propiedades con el tipo de datos exacto establecido (Número, Fecha, Duración o Intervalo).

En la vista pública, la faceta se controlará a través de un menú desplegable.

![Página de navegación por facetas pública con botones de opción para seleccionar una lista de valores de Estado y un menú desplegable «Fecha de nacimiento anterior a» en la columna izquierda. En la columna derecha hay una tabla de elementos con información sobre Título, Ubicación y Cónyuge](modulesfiles/FacetedBrowse_DatesPublic.png)

### Columnas

Los elementos de la página pública se mostrarán inicialmente en una lista, incluyendo el título, la descripción y la miniatura de cada recurso. Estas filas pueden quedar truncadas (el texto excesivamente largo se ocultará).

Puede configurar la información que se muestra sobre los resultados añadiendo columnas de metadatos a la visualización de su búsqueda por facetas. Esto convertirá la visualización en una tabla con una fila para cada recurso de los resultados. Las columnas se configuran categoría por categoría. Dependiendo de si su página tiene una o varias categorías, la visualización de la página inicial puede cambiar.

En la vista pública de una búsqueda por facetas, los usuarios pueden ordenar por una columna seleccionándola en el menú desplegable. Cada columna se puede ordenar en orden ascendente o descendente. Si desea impedir que los usuarios ordenen por una columna determinada, puede marcar la casilla «Excluir ordenación por» al configurar esa columna para excluirla del menú desplegable.

!!! nota
  Si un valor es muy largo, como el título o la descripción del recurso, es posible que las filas de la tabla resulten muy altas, con el campo más grande ocupando la columna más ancha y las demás columnas reducidas para compensar. Puede utilizar el [módulo Editor CSS](csseditor.md) para implementar un truncamiento que oculte el texto que sobresalga.

Seleccione un tipo de columna para añadir desde el menú desplegable: 

- Título (enlace al recurso) 
- Valor
- Clase de recurso
- Plantilla de recurso 
- Conjunto de elementos 
- ID.

Una vez seleccionado el tipo, haga clic en el botón «Añadir». Se abrirá un panel con opciones para configurar la columna. 

Para cada columna, se requiere un título, que se mostrará en el encabezado de la tabla. También puede excluir cada columna para que los visitantes del sitio no puedan ordenarla. A continuación se describen otros ajustes.

Recuerde hacer clic en el botón «Establecer columna» o su trabajo no se guardará.

![Página de navegación por facetas pública con columnas visibles](modulesfiles/FacetedBrowse_columns.png)

#### **Valor**

Seleccione una propiedad que se vaya a mostrar (obligatorio). 

A continuación, establezca el número máximo de valores para esa propiedad. Para mostrar todos los valores, deje el campo en blanco. Esto puede provocar que las filas de la tabla sean muy altas, si los elementos tienen varios valores para la propiedad seleccionada o si algunos valores son muy largos. 

#### **Conjunto de elementos**

Establezca el número máximo de conjuntos de elementos que se mostrarán. Para mostrar todos los valores, deje el campo en blanco. Esto puede provocar filas muy altas en su tabla, si los elementos se encuentran en varios conjuntos de elementos. 

Los conjuntos de elementos se mostrarán con pequeñas miniaturas y enlaces a los conjuntos de elementos. 

## Añadir páginas de navegación por facetas a la navegación

Haga clic en la [pestaña Navegación](../sites/site_navigation.md) de su sitio. En la lista «Añadir un enlace personalizado» de la barra lateral de la página, seleccione la opción «Navegación por facetas».

![La pantalla de navegación mostrando el menú desplegable para añadir la página de navegación por facetas abierto para ver las páginas disponibles](modulesfiles/FacetedBrowse_AddPageNav.png)

Asigne una etiqueta a su enlace personalizado (opcional) y seleccione de la lista desplegable las páginas de navegación por facetas (obligatorio). Si la etiqueta está en blanco, se utilizará el título de la página.

Puede añadir tantos enlaces personalizados de navegación por facetas como desee.

Arrastre y suelte sus páginas en el lugar deseado de la navegación de su sitio y, a continuación, guarde su trabajo.

## Vistas públicas

Las vistas públicas de las páginas de navegación por facetas incluyen la página base, donde puede haber una o más categorías en las que hacer clic, y luego páginas específicas de cada categoría, que muestran las columnas elegidas para esa vista. Las facetas de navegación se mostrarán en una lista si no se selecciona ninguna columna para mostrar; no se incluirán encabezados de columna, pero los elementos de la página se pueden ordenar como de costumbre.

![Página de navegación por facetas con una lista de eventos que tuvieron lugar en el National Mall. En el lado izquierdo de la imagen hay una lista de épocas con botones de opción.](modulesfiles/FacetedBrowse_publicView.png)

En esta imagen, la faceta es Época, mostrada como una lista de selección única. Los elementos de esta página se muestran en columnas con el título y la época de cada elemento.

Dependiendo de la configuración de columnas de cada categoría, es posible que haya más columnas de las que puede albergar la ventana del navegador del usuario. Si es así, solo verá el número de columnas que quepan en la página sin desbordarse, y verá flechas a la izquierda y a la derecha en la esquina superior derecha de la tabla para desplazar las columnas ocultas y verlas. Tenga en cuenta que el texto de las columnas que no se muestran en la página no aparecerá si el usuario realiza una búsqueda de texto en la página.

![Página de navegación por facetas con la tabla de resultados mostrando flechas a la izquierda y a la derecha para ver las columnas que no son visibles con el ancho actual de la página.](modulesfiles/FacetedBrowse_publicView2.png)

### Varias categorías en una página

Cuando hay varias categorías en una página, esta se cargará mostrando todos los recursos de todas las categorías y mostrará enlaces a las categorías disponibles en un submenú.

![Página de navegación por facetas con dos categorías. Las categorías están resaltadas en un cuadro de anotación rojo etiquetado como «Categorías»](modulesfiles/FacetedBrowse_multiCatView1.png)

Una vez que el usuario hace clic en una categoría, la lista de recursos cambiará para mostrar solo los recursos de esa categoría, la visualización de columnas que haya configurado y sus facetas en el submenú. Los usuarios pueden utilizar el botón «Atrás» de la página para volver a la lista completa de categorías y borrar sus filtros.

![Una página de navegación por facetas con las facetas visibles. El encabezado de la categoría aparece encima de las facetas. Encima de este hay un botón con la etiqueta «Atrás». Las anotaciones indican los encabezados del botón, la categoría y las facetas.](modulesfiles/FacetedBrowse_multiCatView2.png)

### Bloque de página de vista previa de navegación por facetas

Puede añadir un bloque de página de «Vista previa de navegación por facetas» a las páginas de los sitios Omeka. Este bloque de página mostrará los primeros elementos que aparecen en la página completa de navegación por facetas, sin ninguna de las facetas de la barra lateral ni las herramientas de navegación disponibles en la página. 

![Bloque de página de vista previa de la navegación por facetas en la configuración de administración, con los ajustes que se indican a continuación. Se ha seleccionado una categoría de página, el límite se ha establecido en 6, el título de la vista previa se ha establecido en «Explorar por tipo» y el texto del enlace se ha establecido en «Explorar todo».](modulesfiles/FacetedBrowse_previewpageblock.png)

El bloque de página incluye los siguientes ajustes:

* Categoría de página: Seleccione en el menú desplegable que muestra cada página de Facebook y todas sus categorías. Solo puede elegir una categoría para mostrar por bloque de página, pero puede tener varios bloques de página. 
* Límite: Elija el número máximo de elementos que se mostrarán de los resultados predeterminados de la categoría de Facebook. Compruebe la propia página de Facebook para ver qué elementos se mostrarán según su configuración actual. 
* Título de vista previa: Introduce un título que se mostrará en la parte superior del bloque de página. 
* Texto del enlace: Introduce el texto que se mostrará en un botón en la parte inferior del bloque de página. Esto enlazará a los usuarios con la página completa de Facebook. 

![El bloque de página de vista previa de Facebook tal y como aparece en el tema The Daily.](modulesfiles/FacetedBrowse_previewpageblock2.png)

## Búsqueda predeterminada con Faceted Browse

Puedes dirigir a tus usuarios a una página de Faceted Browse directamente desde la barra de búsqueda que aparece en el encabezado o el menú de tu sitio. 

Ve a la página de configuración de tu sitio y busca la sección «Faceted Browse». Verás un menú desplegable que te permite seleccionar una de tus categorías para que se muestre cuando se realice una búsqueda de texto en la barra de búsqueda de todo el sitio. 

![Sección de Faceted Browse en la configuración del sitio](modulesfiles/FacetedBrowse_sitewideSetting.png)

Ten en cuenta que solo aparecerán las categorías con una faceta de búsqueda de texto. 

Cuando un usuario realice una búsqueda de texto en tu sitio, se le redirigirá a la categoría de Navegación por facetas y verá su búsqueda de texto completada en la faceta de texto completo de la barra lateral. Desde allí, podrá restringir o ampliar aún más sus búsquedas. 

![Una búsqueda de texto de «william» ha cargado la página de navegación por facetas, y «william» también aparece en la faceta de texto completo de la barra lateral.](modulesfiles/FacetedBrowse_sitewide.png)
