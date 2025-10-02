# Búsqueda

Existen funciones de búsqueda tanto en el lado administrativo como en el público de las instalaciones y sitios de Omeka S.

## Interfaz de administración

### Búsqueda básica

Hay un campo de búsqueda cerca de la parte superior del menú izquierdo, justo debajo de la información del usuario. Este campo de búsqueda funciona como una búsqueda por palabra clave en todas las propiedades de los recursos.

![Opción de búsqueda en la barra lateral azul.](files/search1.png)

Por defecto, esta búsqueda opera sobre los elementos de su instalación. Sin embargo, puede usar los puntos suspensivos (tres puntos) para abrir un menú y cambiar el tipo de recurso que se busca, seleccionando entre Elementos, Conjuntos de elementos o Medios.

![Primer plano de las opciones de búsqueda, mostrando el menú expandido de los puntos suspensivos con opciones de selección para Elementos, Conjuntos de elementos o Medios.](files/search2.png)

### Búsqueda avanzada de elementos

La búsqueda avanzada solo para elementos está disponible en la página de [Elementos](content/items.md), desde el enlace "Búsqueda Avanzada" que se encuentra sobre la tabla de elementos.

![Botón de Búsqueda Avanzada indicado con una flecha roja.](files/search_advanced.png)

La búsqueda avanzada se carga en una nueva página y tiene las siguientes opciones:

- **Búsqueda de texto completo**: ejecuta una búsqueda de texto completo en todo el texto de cada elemento de la instalación.
- **Búsqueda por valor**: busca un término o frase que usted introduzca.
	- El primer selector le permite especificar una propiedad para la búsqueda.
	- El segundo selector le permite establecer la relación que la propiedad tiene con el valor. Las opciones son:
		- es exactamente,
		- no es exactamente,
		- contiene,
		- no contiene,
		- es recurso con ID,
		- no es recurso con ID,
		- tiene cualquier valor (hay algo en la propiedad), y
		- no tiene ningún valor.
	- Finalmente, hay un campo de texto para que introduzca el valor que desea que tenga la propiedad. Para encontrar un ID de recurso, vaya al recurso y mire la URL en la barra de direcciones de su navegador. Los números al final de la URL son el ID del recurso.
- **Búsqueda por clase**: seleccione una clase para la búsqueda en el menú desplegable.
- **Búsqueda por plantilla**: seleccione una plantilla de recursos en el menú desplegable. Las plantillas están organizadas por propietario y luego alfabéticamente.
- **Búsqueda por conjunto de elementos**: Seleccione si los resultados deseados están incluidos o excluidos del conjunto de elementos indicado. Elija un conjunto de elementos del menú desplegable o escriba para buscar. Puede añadir múltiples parámetros; estos acotarán la búsqueda (es decir, devolverá todos los elementos que no están en el conjunto X Y tampoco en el conjunto Y; todos los elementos que están en el conjunto X Y también en el conjunto Y; todos los elementos que están en el conjunto X Y también excluidos del conjunto Y).
- **Búsqueda por sitio**: seleccione un sitio del menú desplegable de sitios en la instalación. Tenga en cuenta que solo puede buscar elementos de un sitio a la vez.
- **Búsqueda por presencia de medios**: seleccione si los resultados tienen medios o no los tienen.
- **Búsqueda por propietario**: seleccione un usuario del menú desplegable de usuarios en la instalación.
- **Búsqueda por visibilidad**: seleccione si los resultados son elementos públicos o privados.
- **Búsqueda por ID**: introduzca un valor de identificador de elemento específico, o una lista de identificadores separados por comas (por ejemplo, "1, 5, 9, 12, 43, 44, 45"). Solo funciona para coincidencias exactas, no con comodines o rangos.

También puede seleccionar cómo ordenar los resultados de su búsqueda.

![Página de opciones de búsqueda avanzada de elementos.](files/search_advanced2.png)

Otros campos de búsqueda pueden ser introducidos por módulos que añaden nuevos campos de metadatos a sus elementos.

Las búsquedas por valor, clase, plantilla y conjunto de elementos le permiten buscar por más de una entrada; use los iconos grandes de signo más para añadir más parámetros. Estos términos de búsqueda son acumulativos: buscar dos conjuntos de elementos devolverá todos los elementos que se encuentren en cualquiera de los dos conjuntos, en lugar de solo aquellos que estén en ambos. Puede eliminar esas búsquedas usando el icono rojo de la papelera a la derecha de cada línea.

Puede restablecer sus términos de búsqueda en cualquier momento usando el botón "Restablecer" en la esquina superior derecha, junto al botón "Buscar".

### Búsqueda avanzada de medios
La búsqueda avanzada de medios se accede desde la página de exploración de [Medios](content/media.md), desde el enlace **Búsqueda Avanzada** sobre la tabla de medios.

![Botón de Búsqueda Avanzada indicado con una flecha roja.](files/search_mediaadvanced1.png)

La búsqueda avanzada se carga en una nueva página y tiene las siguientes opciones:

- **Búsqueda de texto completo**: ejecuta una búsqueda de texto completo en todo el texto de cada recurso de medios en la instalación.
- **Búsqueda por valor**: busca un término o frase que usted introduzca.
	- El primer selector le permite especificar una propiedad para la búsqueda.
	- El segundo selector le permite establecer la relación que la propiedad tiene con el valor. Las opciones son:
		- es exactamente,
		- no es exactamente,
		- contiene,
		- no contiene,
		- es recurso con ID,
		- no es recurso con ID,
		- tiene cualquier valor (hay algo en la propiedad), y
		- no tiene ningún valor.
	- Finalmente, hay un campo de texto para que introduzca el valor que desea que tenga la propiedad.
	- Para encontrar un ID de recurso, vaya al recurso y mire la URL en la barra de direcciones de su navegador. Los números al final de la URL son el ID del recurso.
	- Puede eliminar búsquedas por valor usando el icono rojo de la papelera a la derecha.
- **Búsqueda por clase**: seleccione una clase para la búsqueda en el menú desplegable.
- **Búsqueda por plantilla**: seleccione una plantilla de recursos en el menú desplegable. Las plantillas están organizadas por propietario y luego alfabéticamente.
- **Búsqueda por tipo MIME**: puede especificar el tipo de medio para la búsqueda. Por ejemplo, para encontrar todas las imágenes tiff, introduciría `image/tiff`.
- **Búsqueda por propietario**: seleccione un usuario del menú desplegable de usuarios en la instalación.
- **Búsqueda por visibilidad**: seleccione si los resultados son medios públicos o privados.
- **Búsqueda por ID**: introduzca un valor de identificador de medio específico, o una lista de identificadores separados por comas (por ejemplo, "1, 5, 9, 12, 43, 44, 45"). Solo funciona para coincidencias exactas, no con comodines o rangos.

También puede seleccionar cómo ordenar los resultados de su búsqueda.

![Formulario de opciones de búsqueda avanzada de medios, con los campos descritos arriba.](files/search_mediaadvanced2.png)

Las búsquedas por valor, clase y plantilla le permiten buscar por más de una entrada; use los iconos grandes de signo más para buscar con más de un valor. Estos términos de búsqueda son acumulativos: buscar dos plantillas devolverá todos los medios que usen cualquiera de las dos plantillas.

Puede eliminar búsquedas por valor y conjunto de elementos usando el icono rojo de la papelera a la derecha de esas opciones.

Puede restablecer sus términos de búsqueda en cualquier momento usando el botón "Restablecer" en la esquina superior derecha, junto al botón "Buscar".

### Búsqueda avanzada de conjuntos de elementos

La búsqueda avanzada solo para conjuntos de elementos se accede desde la página de [Conjuntos de elementos](content/item-sets.md), desde el enlace "Búsqueda Avanzada" sobre la tabla de conjuntos de elementos.

![Botón de Búsqueda Avanzada indicado con una flecha roja.](files/search_advancedis1.png)

La búsqueda avanzada se carga en una nueva página y tiene las siguientes opciones:

- **Búsqueda de texto completo**: ejecuta una búsqueda de texto completo en todo el texto de cada conjunto de elementos en la instalación.
- **Búsqueda por valor**: busca un término o frase que usted introduzca.
	- El primer selector le permite especificar una propiedad para la búsqueda.
	- El segundo selector le permite establecer la relación que la propiedad tiene con el valor. Las opciones son:
		- es exactamente,
		- no es exactamente,
		- contiene,
		- no contiene,
		- es recurso con ID,
		- no es recurso con ID,
		- tiene cualquier valor (hay algo en la propiedad), y
		- no tiene ningún valor.
	- Finalmente, hay un campo de texto para que introduzca el valor que desea que tenga la propiedad.
	- Para encontrar un ID de recurso, vaya al recurso y mire la URL en la barra de direcciones de su navegador. Los números al final de la URL son el ID del recurso.
	- Puede eliminar búsquedas por valor usando el icono rojo de la papelera a la derecha.
- **Búsqueda por clase**: seleccione una clase para la búsqueda en el menú desplegable.
- **Búsqueda por plantilla**: seleccione una plantilla de recursos en el menú desplegable. Las plantillas están organizadas por propietario y luego alfabéticamente.
- **Búsqueda por propietario**: seleccione un usuario del menú desplegable de usuarios en la instalación.
- **Búsqueda por visibilidad**: seleccione si los resultados son conjuntos de elementos públicos o privados.
- **Búsqueda por ID**: introduzca un valor de identificador de conjunto de elementos específico, o una lista de identificadores separados por comas (por ejemplo, "1, 2, 5, 9"). Solo funciona para coincidencias exactas, no con comodines o rangos.

También puede seleccionar cómo ordenar los resultados de su búsqueda.

![Formulario de opciones de búsqueda avanzada de conjuntos de elementos, con los campos descritos arriba.](files/search_advancedis2.png)

Las búsquedas por valor, clase y plantilla le permiten buscar por más de una entrada; use los iconos grandes de signo más para buscar con más de un valor. Estos términos de búsqueda son acumulativos: buscar dos plantillas devolverá todos los medios que usen cualquiera de las dos plantillas.

Otros campos de búsqueda pueden ser introducidos por módulos que añaden nuevos campos de metadatos a sus conjuntos de elementos.

Puede restablecer sus términos de búsqueda en cualquier momento usando el botón "Restablecer" en la esquina superior derecha, junto al botón "Buscar".

## Vistas públicas

La apariencia exacta de la interfaz de búsqueda variará según el [tema](sites/site_theme.md) seleccionado. El funcionamiento de la búsqueda es consistente independientemente del tema.

### Búsqueda básica
Hay una barra de búsqueda cerca del menú de cada sitio. En el tema por defecto, se encuentra justo debajo del menú principal, como se muestra en la imagen siguiente.

![Página de inicio del sitio de Jane Austen, con una flecha azul apuntando a la barra de búsqueda debajo del menú de navegación principal.](files/search_public1.png)

Esta barra de búsqueda funciona como una búsqueda de texto completo para todo el sitio. Buscará en todos los elementos, conjuntos de elementos y medios, así como en el contenido de cada página publicada en el sitio. Los resultados se ordenan por tipo, agrupando los resultados de páginas y los de elementos o conjuntos de elementos. Desde la página de resultados inicial, puede ver todos los resultados para ese tipo (página, elemento) usando el enlace "ver todos los resultados".

![Resultados de búsqueda para "Cassandra" mostrando una página y tres elementos.](files/search_public2.png)

### Búsqueda avanzada de elementos
Los visitantes del sitio pueden acceder a una búsqueda avanzada de elementos desde la página de Explorar Elementos, si tiene esa página accesible. Hay un enlace para Búsqueda Avanzada entre la paginación y las opciones de ordenación en la parte superior de la tabla de exploración de elementos.

Puede controlar los ajustes de búsqueda avanzada para cada sitio desde la [pestaña de Ajustes del Sitio](sites/site_settings.md#search). Esto incluirá los campos de búsqueda avanzada introducidos por los módulos.

![La página de Elementos del sitio de Jane Austen, con una flecha azul apuntando al enlace de Búsqueda Avanzada.](files/search_publicitems1.png)

Al hacer clic, se carga una nueva página con cuatro opciones de búsqueda:

- **Búsqueda de texto completo**: ejecuta una búsqueda de texto completo en todo el texto de cada elemento del sitio.
- **Búsqueda por valor**: busca un término o frase usando múltiples opciones.
	- El primer selector le permite especificar una propiedad para la búsqueda.
		- Tenga en cuenta que si ha [configurado el sitio](sites/site_settings.md#search) para restringir la búsqueda a plantillas, aquí solo se mostrarán las propiedades usadas por esas plantillas.
	- El segundo selector le permite establecer la relación que la propiedad tiene con el valor. Las opciones son:
		- es exactamente,
		- no es exactamente,
		- contiene,
		- no contiene,
		- es recurso con ID,
		- no es recurso con ID,
		- tiene cualquier valor (hay algo en la propiedad), y
		- no tiene ningún valor.
	- Finalmente, hay un campo de texto para que introduzca el valor que desea que tenga la propiedad.
	- Para encontrar un ID de recurso, vaya al recurso y mire la URL en la barra de direcciones de su navegador. Los números al final de la URL son el ID del recurso.
- **Búsqueda por clase**: seleccione una o más clases para la búsqueda en el menú desplegable.
- **Búsqueda por conjunto de elementos**: seleccione uno o más conjuntos de elementos del menú desplegable. Los resultados mostrarán los elementos dentro de uno o más de los conjuntos que eligió.
- **Búsqueda por presencia de medios**: seleccione si los resultados tienen medios o no los tienen.
- **Búsqueda por ID**: introduzca uno o más valores de identificador de elemento. Los usuarios pueden proporcionar una lista de identificadores separados por comas (por ejemplo, "1, 5, 9, 12, 43, 44, 45"). Solo funciona para coincidencias exactas, no con comodines o rangos.

Los usuarios también pueden seleccionar cómo ordenar los resultados de su búsqueda.

Aquí está el formulario de búsqueda avanzada por defecto en dos temas: Thanks, Roy y The Daily:

![Campos de búsqueda avanzada de elementos como se ha descrito.](files/search_publicitems2.png)

![Campos de búsqueda avanzada de elementos como se ha descrito.](files/search_publicitems3.png)

Las búsquedas por valor, clase y conjunto de elementos permiten a un visitante buscar por más de una entrada; pueden usar los botones "Añadir nuevo" (signo más) para buscar con más de un término de búsqueda. Estos términos de búsqueda son acumulativos: buscar dos conjuntos de elementos devolverá todos los elementos que se encuentren en cualquiera de los dos conjuntos, en lugar de solo aquellos que estén en ambos.

Los visitantes del sitio pueden eliminar las búsquedas por valor, clase y conjunto de elementos usando el icono rojo de la papelera a la derecha de esas opciones.

### Búsqueda avanzada de conjuntos de elementos

Los visitantes del sitio pueden acceder a una búsqueda avanzada de conjuntos de elementos desde la página de Explorar Conjuntos de Elementos, si tiene esa página accesible. Hay un enlace para Búsqueda Avanzada cerca de la parte superior de la página de Conjuntos de Elementos.

![Página de conjuntos de elementos para el sitio de Jane Austen. Una flecha azul apunta al enlace de búsqueda avanzada.](files/search_publicitemsets1.png)

Al hacer clic en el enlace de búsqueda avanzada se carga una nueva página con tres opciones de búsqueda:

- **Búsqueda de texto completo**: ejecuta una búsqueda de texto completo en todo el texto de cada conjunto de elementos del sitio.
- **Búsqueda por valor**: busca un término o frase usando múltiples opciones.
	- El primer selector le permite especificar una propiedad para la búsqueda.
		- Tenga en cuenta que si ha [configurado el sitio](sites/site_settings.md#search) para restringir la búsqueda a plantillas, aquí solo se mostrarán las propiedades usadas por esas plantillas.
	- El segundo selector le permite establecer la relación que la propiedad tiene con el valor. Las opciones son:
		- es exactamente,
		- no es exactamente,
		- contiene,
		- no contiene,
		- es recurso con ID,
		- no es recurso con ID,
		- tiene cualquier valor (hay algo en la propiedad), y
		- no tiene ningún valor.
	- Finalmente, hay un campo de texto para que introduzca el valor que desea que tenga la propiedad.
	- Para encontrar un ID de recurso, vaya al recurso y mire la URL en la barra de direcciones de su navegador. Los números al final de la URL son el ID del recurso.
- **Búsqueda por clase**: seleccione una o más clases para la búsqueda en el menú desplegable.
- **Búsqueda por ID**: introduzca un valor de identificador de conjunto de elementos específico, o una lista de identificadores separados por comas (por ejemplo, "1, 2, 5, 9"). Solo funciona para coincidencias exactas, no con comodines o rangos.

Los usuarios también pueden seleccionar cómo ordenar los resultados de su búsqueda.

![Opciones de búsqueda avanzada de conjuntos de elementos como se ha descrito.](files/search_publicitemsets2.png)

Las búsquedas por valor y clase permiten a un visitante buscar por más de una entrada; pueden usar los botones "Añadir nuevo" (signo más) para buscar con más de un término. Estos términos de búsqueda son acumulativos: buscar dos clases devolverá todos los conjuntos de elementos que tengan cualquiera de las dos clases, en lugar de solo los que tengan ambas.

Los visitantes del sitio pueden eliminar las búsquedas de valor y conjunto de elementos usando el icono rojo de la papelera a la derecha de esas opciones.

Puede modificar estos órdenes de clasificación por defecto para las páginas públicas de los sitios en los [Ajustes del sitio](sites/site_settings.md#settings), y para las páginas administrativas por usuario en los [Ajustes de usuario](admin/users.md#admin-browse-defaults).

## Ordenación

Todas las vistas de exploración públicas y administrativas y todos los resultados de búsqueda pueden ordenarse de varias maneras. En la parte superior derecha de cada tabla de exploración o resultados hay dos menús desplegables y un botón de "Ordenar". Uno le permite seleccionar un campo, y el otro determina el orden en que se clasificarán.

La forma predeterminada en que se ordenan la mayoría de los recursos es por la fecha de creación del recurso (Creado), en orden cronológico inverso (Descendente). Esto es así para elementos, medios y conjuntos de elementos. Los sitios, vocabularios y plantillas de recursos se ordenan por defecto por Título o Etiqueta en orden Ascendente. Los usuarios se ordenan por defecto por Correo Electrónico en orden Ascendente.

Ascendente significa A-Z alfabéticamente para campos de texto, del más antiguo al más reciente para campos con formato de fecha como Creado (la fecha y hora de creación interna del elemento) y Modificado (la fecha y hora de la última modificación del elemento), y del menor al mayor para números como los Identificadores. Tenga en cuenta que algunos campos (como Fecha de Dublin Core) pueden tener formato de texto para incluir información como "circa" y se ordenarán alfabéticamente en lugar de como números (como "1800-01-01") o fechas. Es posible que esté utilizando módulos como [Tipos de Datos Numéricos](modules/numericdatatypes.md) que pueden modificar estos ajustes.

Tanto en orden ascendente como descendente, los campos vacíos aparecerán al final.