# Búsqueda

Las instalaciones y los sitios de Omeka S cuentan con funciones de búsqueda tanto en el panel de administración como en la interfaz pública.

## Interfaz administrativa

### Búsqueda básica

Hay un campo de búsqueda cerca de la parte superior del menú de la izquierda, justo debajo de la información del usuario. Este campo de búsqueda funciona como una búsqueda por palabra clave en todas las propiedades de los recursos.

![Opción de búsqueda en la barra lateral azul.](files/search1.png)

De forma predeterminada, esta búsqueda se aplica a los elementos de tu instalación. Sin embargo, puedes utilizar los tres puntos (... ) para abrir un menú y cambiar el tipo de recurso que se busca, seleccionando entre Elementos, Conjuntos de elementos o Medios.

![Primer plano de las opciones de búsqueda, mostrando el menú desplegado de los puntos suspensivos con opciones de selección para Elementos, Conjuntos de elementos o Medios.](files/search2.png)

### Búsqueda avanzada de elementos

La búsqueda avanzada solo para elementos está disponible en la página [Elementos](content/items.md), desde el enlace «Búsqueda avanzada» situado encima de la tabla de elementos.

![Botón de búsqueda avanzada indicado con una flecha roja.](files/search_advanced.png)

La búsqueda avanzada se carga en una nueva página y cuenta con las siguientes opciones:

- **Ordenar**: puedes configurar cómo se muestran los resultados, basándote en las columnas específicas de cada recurso que hayas configurado en tu cuenta de usuario. Puedes ordenar cada selección de forma ascendente o descendente.
- **Búsqueda de texto completo**: realiza una búsqueda de texto completo en todo el texto de cada elemento de la instalación.
- **Búsqueda por valor**: busca un término o frase que introduzcas.
  - El primer selector te permite especificar una propiedad en la que buscar.
	- El segundo selector le permite establecer la relación que tiene la propiedad con el valor. Las opciones son:
    - es exactamente,
    - no es exactamente,
    - contiene,
    - no contiene,
    - es un recurso con ID,
    - no es un recurso con ID,
		- tiene cualquier valor (hay algo en la propiedad),
    - no tiene valores,
    - tiene tipo de datos, o
    - no tiene tipo de datos.
	- Introduzca el valor que desea que tenga la propiedad. Para encontrar un ID de recurso, vaya al recurso y observe la URL en la barra de direcciones de su navegador. Los números al final de la URL son el ID del recurso.
- **Buscar por clase**: seleccione una clase del menú desplegable.
- **Buscar por plantilla**: seleccione una plantilla de recurso del menú desplegable. Las plantillas se ordenan por propietario y, a continuación, alfabéticamente. 
- **Buscar por conjunto de elementos**: seleccione si los resultados deseados se incluyen o se excluyen del conjunto de elementos dado. Elija un conjunto de elementos del menú desplegable o escriba lo que desee buscar. Puede añadir varios parámetros; estos reducirán la búsqueda (es decir, mostrarán todos los elementos que no estén en el conjunto X Y que tampoco estén en el conjunto Y; todos los elementos que estén en el conjunto X Y que también estén en el conjunto Y; todos los elementos que estén en el conjunto X Y que tampoco estén en el conjunto Y).
- **Buscar por sitio**: seleccione un sitio del menú desplegable de sitios de la instalación. Tenga en cuenta que solo puede buscar elementos de un sitio a la vez.
- **Buscar por presencia de medios**: seleccione si los resultados tienen medios o no tienen medios.
- **Búsqueda por propietario**: seleccione un usuario de un menú desplegable de usuarios de la instalación.
- **Búsqueda por visibilidad**: seleccione si los resultados son elementos públicos o privados.
- **Buscar por ID**: introduzca un valor de identificador de elemento específico, o una lista de identificadores separados por comas (por ejemplo, «1, 5, 9, 12, 43, 44, 45»). Solo funciona para coincidencias exactas, no con comodines ni rangos.

![Página de opciones de búsqueda avanzada de elementos.](files/search_advanced2.png)

Es posible que se introduzcan otros campos de búsqueda con módulos que añadan nuevos campos de metadatos a tus elementos.

Las búsquedas por valor, clase, plantilla y conjunto de elementos te permiten buscar por más de un criterio: utiliza los iconos rojos grandes con el signo más para añadir más parámetros. Estos términos de búsqueda se combinan: si buscas dos conjuntos de elementos, se mostrarán todos los elementos de cualquiera de los dos conjuntos, en lugar de solo aquellos que estén en ambos. Puedes eliminar esas búsquedas utilizando el icono de la papelera roja situado a la derecha de las líneas.

Puedes restablecer tus términos de búsqueda en cualquier momento utilizando el botón «Restablecer» situado en la parte superior derecha, junto al botón «Buscar».

### Búsqueda avanzada de medios
Se accede a la búsqueda avanzada de medios desde la página de exploración [Medios](content/media.md), a través del enlace **Búsqueda avanzada** situado encima de la tabla de conjuntos de elementos.

![Botón de búsqueda avanzada indicado con una flecha roja.](files/search_mediaadvanced1.png)

La búsqueda avanzada se carga en una nueva página y ofrece las siguientes opciones:

- **Ordenar**
- **Búsqueda de texto completo**
- **Búsqueda por valor**
- **Búsqueda por clase**
- **Buscar por plantilla**
- **Buscar por tipo MIME**: puede especificar el tipo de medio para la búsqueda. Por ejemplo, para encontrar todas las imágenes TIFF, debe introducir `image/tiff`.
- **Buscar por propietario**
- **Buscar por visibilidad**
- **Búsqueda por ID**: introduce un valor de identificador de medio específico, o una lista de identificadores separados por comas (por ejemplo, «1, 5, 9, 12, 43, 44, 45»). Solo funciona para coincidencias exactas, no con comodines ni rangos.

### Búsqueda avanzada de conjuntos de elementos

Se accede a la búsqueda avanzada solo para conjuntos de elementos en la página [Conjuntos de elementos](content/item-sets.md), desde el enlace «Búsqueda avanzada» situado encima de la tabla de conjuntos de elementos.

![Botón de búsqueda avanzada indicado con una flecha roja.](files/search_advancedis1.png)

La búsqueda avanzada se carga en una nueva página y ofrece las siguientes opciones:

- **Ordenar**
- **Búsqueda de texto completo**
- **Búsqueda por valor**
- **Búsqueda por clase**
- **Búsqueda por plantilla**
- **Búsqueda por propietario**
- **Buscar por visibilidad**
- **Buscar por ID**: introduce un valor de identificador de conjunto de elementos específico, o una lista de identificadores separados por comas (por ejemplo, «1, 2, 5, 9»). Solo funciona para coincidencias exactas, no con comodines ni rangos.


## Vistas públicas

El aspecto exacto de la interfaz de búsqueda variará en función del [tema](sites/site_theme.md) seleccionado. El funcionamiento de la búsqueda es el mismo independientemente del tema.

### Búsqueda básica
Hay una barra de búsqueda cerca del menú de cada sitio. En el tema predeterminado, se encuentra justo debajo del menú principal, como se muestra en la imagen siguiente.

![Página de inicio del sitio de Jane Austen, con una flecha azul que señala la barra de búsqueda situada debajo del menú de navegación principal](files/search_public1.png)

Esta barra de búsqueda funciona como una búsqueda de texto completo para todo el sitio. Buscará en todos los elementos, conjuntos de elementos y archivos multimedia, así como en el contenido de todas las páginas publicadas en el sitio. Los resultados se ordenan por tipo, agrupando los resultados de páginas y los resultados de elementos o conjuntos de elementos. Desde la página de resultados inicial, puede ver todos los resultados de ese tipo (página, elemento) utilizando el enlace «ver todos los resultados».

![Resultados de búsqueda para «Cassandra» que muestran una página y tres elementos](files/search_public2.png)

### Búsqueda avanzada de elementos
Los visitantes del sitio pueden acceder a una búsqueda avanzada de elementos desde la página «Explorar elementos», si dicha página está disponible. Hay un enlace a «Búsqueda avanzada» entre la paginación y las opciones de ordenación en la parte superior de la tabla de exploración de elementos.

Puede controlar la configuración de la búsqueda avanzada para cada sitio individualmente, desde la [pestaña Configuración del sitio](sites/site_settings.md#search). Esto incluirá los campos de búsqueda avanzada introducidos por los módulos.

![La página «Elementos» del sitio de Jane Austen, con una flecha azul que señala el enlace de «Búsqueda avanzada»](files/search_publicitems1.png)

Al hacer clic en este enlace, se carga una nueva página con cuatro opciones de búsqueda:

- **Ordenar**
- **Búsqueda de texto completo**: realiza una búsqueda de texto completo en todo el texto de cada elemento del sitio.
- **Buscar por valor**
  - Ten en cuenta que si has configurado el [sitio](sites/site_settings.md#search) para restringir la búsqueda a las plantillas, solo se mostrarán las propiedades utilizadas por dichas plantillas.
- **Buscar por clase**
- **Buscar por conjunto de elementos**: los resultados mostrarán los elementos que se encuentran dentro de uno o varios de los conjuntos que hayas elegido.
- **Buscar por presencia en medios**
- **Buscar por ID**.

Aquí tienes el formulario de búsqueda avanzada predeterminado en dos temas: Thanks, Roy y The Daily:

![Campos de búsqueda avanzada de elementos tal y como se describe](files/search_publicitems2.png)

![Campos de búsqueda avanzada de elementos tal y como se describe](files/search_publicitems3.png)

### Búsqueda avanzada de conjuntos de elementos

Los visitantes del sitio pueden acceder a una búsqueda avanzada de conjuntos de elementos desde la página «Explorar conjuntos de elementos», si dicha página está disponible. Hay un enlace para la búsqueda avanzada cerca de la parte superior de la página «Conjuntos de elementos».

![Página de conjuntos de elementos del sitio de Jane Austen. Una flecha azul señala el enlace de búsqueda avanzada](files/search_publicitemsets1.png)

Al hacer clic en el enlace de búsqueda avanzada se carga una nueva página con tres opciones de búsqueda:

- **Ordenar**
- **Búsqueda de texto completo**
- **Buscar por valor**
  - Ten en cuenta que si tienes la [configuración del sitio](sites/site_settings.md#search) para restringir la búsqueda a plantillas, esto solo mostrará las propiedades utilizadas por esas plantillas.
- **Buscar por clase**
- **Buscar por ID**.

![Opciones de búsqueda avanzada de conjuntos de elementos tal y como se describe](files/search_publicitemsets2.png)

### Estilizar las vistas públicas

Puede estilizar, ocultar y resaltar los campos de búsqueda utilizando CSS. Cada entrada tiene un identificador personalizado, como el `div` con «has_media_field», dentro del `div` de la clase «advanced-search-content». Puedes aplicar estilos a estas opciones utilizando el [módulo Editor CSS](modules/csseditor.md) o modificando el código de tu instalación.  

## Ordenación

Todas las vistas de navegación públicas y administrativas, así como todos los resultados de búsqueda, se pueden ordenar de varias formas. En la parte superior derecha de cada tabla de navegación o de resultados hay dos menús desplegables y un botón «Ordenar». Uno te permite seleccionar un campo y el otro determina el orden en el que se ordenarán.

Puede modificar estos órdenes de clasificación predeterminados para las páginas públicas de los sitios en [Configuración del sitio](sites/site_settings.md#settings), y para las páginas administrativas de forma individual por usuario en [Configuración del usuario](admin/users.md#admin-browse-defaults).

La forma predeterminada en que se ordenan la mayoría de los recursos es por el identificador interno de Omeka (ID), en orden cronológico inverso (descendente). Esto se aplica a los elementos, los medios y los conjuntos de elementos. Los sitios, los vocabularios y las plantillas de recursos se ordenan de forma predeterminada por título o etiqueta en orden ascendente. Los usuarios se ordenan de forma predeterminada por correo electrónico en orden ascendente. 

Cuando se realiza una búsqueda de texto completo, los resultados se muestran por relevancia, en orden descendente (los resultados más relevantes primero). 

«Ascendente» significa de la A a la Z en orden alfabético para los campos de texto, de más antiguo a más reciente para los campos con formato de fecha, como «Creado» (es decir, la fecha y hora internas de creación del elemento) y «Modificado» (la fecha y hora en que se modificó por última vez el elemento), y de menor a mayor para los números, como los identificadores. Ten en cuenta que algunos campos (como «Fecha de Dublin Core») pueden tener formato de texto para incluir información como «circa» y se ordenarán alfabéticamente en lugar de como números (como «1800-01-01») o fechas. Es posible que esté utilizando módulos como [Tipos de datos numéricos](modules/numericdatatypes.md) que pueden modificar esta configuración.

Tanto en orden ascendente como descendente, los campos vacíos aparecerán al final.
