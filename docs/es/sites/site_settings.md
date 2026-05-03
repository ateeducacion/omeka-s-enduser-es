# Administración del sitio

La página de administración del sitio te permite gestionar la configuración principal del sitio en el que estás trabajando. Los cambios solo se aplicarán a este sitio y no modificarán la configuración de otros sitios.

En el menú de navegación de la izquierda, una vez que hayas seleccionado un sitio en la página «Sitios», es el primer enlace que aparece debajo del título del sitio, representado con un icono de engranaje.

La página de administración del sitio tiene dos pestañas: Información y Configuración.

## Información
La configuración de información del sitio para un sitio Omeka S es donde puedes cambiar la información básica del sitio, la misma información que introdujiste al crear el sitio. Puedes cambiar:

* **Título**: un campo de texto, con un máximo de 190 caracteres.
* **Slug**: la URL de tu sitio, que se generará automáticamente a partir del título si dejas este campo en blanco.
* **Resumen**: una breve descripción de la temática de tu sitio, que aparecerá en la página de inicio de tu instalación y en la [lista de sitios](../sites/site_pages.md#list-of-sites).
* **Miniatura**: una pequeña imagen para tu sitio, que aparecerá en la página de inicio de tu instalación y en la [lista de sitios](../sites/site_pages.md#list-of-sites). Se subirá y seleccionará de los recursos de tu instalación. Recomendamos utilizar una imagen pequeña, de no más de 240 píxeles de ancho (el tamaño máximo en el que se mostrará, en la página de inicio). También puedes [configurar un favicon para tu sitio](#general-settings) en la pestaña de configuración.

![Pantalla de información de un sitio Omeka S con una miniatura y un resumen.](../sites/sitesfiles/sites_siteinfo.png)

En la esquina superior derecha de la ventana de esta pestaña, puede utilizar los botones para:

- Establecer su sitio como público o privado utilizando el icono del ojo
- Eliminar el sitio
- Cancelar los cambios
- Guardar los cambios.

El botón **hacer público/privado** (icono del ojo) se utiliza tanto para indicar como para establecer si el sitio es visible para el público o solo para los usuarios de esta instalación de Omeka S.

El sitio es público: ![botón «Hacer público» que muestra un icono de ojo](../content/contentfiles/item_public.png){style="display:inline;"}

El sitio es privado: ![botón «Hacer privado» que muestra un icono de ojo tachado con una barra diagonal](../content/contentfiles/item_private.png){style="display:inline;"}

## Configuración

La página de configuración se divide en varias secciones; se pueden añadir más secciones mediante módulos, como [Recopilación](../modules/collecting.md), [Mapeo](../modules/mapping.md) y [Compartir](../modules/sharing.md). 

Para aplicar los cambios que realices, haz clic en «Guardar» en la parte superior derecha de la ventana del navegador cuando hayas terminado. Para salir sin guardar los cambios, haz clic en «Cancelar».

### Configuración general

![Configuración general del sitio, con las opciones predeterminadas al crear un nuevo sitio.](../sites/sitesfiles/sites_settingsgen.png)

**Asignar automáticamente nuevos elementos**: una casilla de verificación que establece si los nuevos elementos se añaden automáticamente a este sitio. Si está marcada, cada nuevo elemento se añadirá al sitio, independientemente del propietario del elemento. Ten en cuenta que los propietarios de los elementos pueden desasignar sus elementos del sitio en cualquier momento, en las páginas de edición de los elementos.

**Tipo de enlace de los archivos adjuntos**: establece el destino de los enlaces de los archivos adjuntos que añadas a los [bloques de página del sitio](../sites/site_pages.md#page-blocks) (por ejemplo, en el [bloque de incrustación de medios](../sites/site_pages.md#media-embed)). Ofrece un menú desplegable con las siguientes opciones:

- Página del elemento: al hacer clic en el archivo adjunto, los usuarios acceden a la página del elemento asociada al medio adjunto.
- Página del medio: al hacer clic en el archivo adjunto, los usuarios acceden a la página del medio.
- Enlace directo al archivo: al hacer clic en el archivo adjunto, el usuario accede únicamente al archivo.

**Mostrar paginación de la página**: cuando está marcado, los enlaces «Anterior» y «Siguiente» se mostrarán en la parte inferior de cada página del sitio, permitiéndole avanzar en la navegación. Si no está marcada, estos enlaces no se mostrarán.

**Mostrar barra de usuario en vistas públicas**: establece si hay una barra en la parte superior de las páginas públicas del sitio que permite a los usuarios acceder a la parte de administración del sitio.

Cuando los usuarios han iniciado sesión, la barra de usuario tiene las siguientes opciones:

- Título de la instalación: te lleva de vuelta a la administración de la instalación.
- Título del sitio: te lleva de vuelta a la página de inicio para gestionar el sitio (site/show).
- Vista de recursos: dependiendo de lo que estés viendo, este es un enlace a la gestión del panel de administración para [Páginas](../sites/site_pages.md), [Elementos](../content/items.md) o [Conjuntos de elementos](../content/item-sets.md).
- Enlace de edición para esa página, conjunto de elementos o elemento.
- Nombre de usuario: te lleva a tu página de usuario.
- Cerrar sesión: cierra la sesión del usuario actual.

![Una barra azul en la parte superior de la imagen muestra las siguientes palabras en texto azul claro, indicando un enlace: Stackable Sandbox, Jane Austen, Páginas, Editar página, Iniciada sesión como Megan, y un botón para Cerrar sesión.](../sites/sitesfiles/sites_userbarin.png)

Si optas por mostrar siempre la barra de usuario, cuando cualquier visitante que no haya iniciado sesión navegue por tu sitio, aparecerá la barra de usuario y mostrará una opción de inicio de sesión.

![Una barra azul en la parte superior de la imagen solo tiene un pequeño botón que dice «Iniciar sesión». Debajo de este, el título del sitio «A Tin Box» se muestra en texto negro sobre fondo blanco.](../sites/sitesfiles/sites_userbarout.png)

Las opciones para esta configuración son:

- Nunca
- Cuando se identifique (al iniciar sesión)
- Siempre.

**Desactivar la incrustación de JSON-LD**: Marca esta casilla para desactivar la incrustación de JSON-LD en las páginas de exploración de recursos y de visualización de este sitio. Esto también está disponible como [configuración global a nivel de instalación](../admin/settings.md).

**Favicon**: Elige entre tus recursos o sube un archivo para que aparezca en el pequeño espacio del icono de la ventana o pestaña del navegador. Un [favicon](https://www.w3schools.com/html/html_favicon.asp){target=_blank} debe ser una imagen pequeña de unos 32x32 píxeles subida específicamente para este fin. Los favicons se pueden [configurar a nivel de instalación](../admin/settings.md#general) así como en cada sitio individual.

**Visualización de la subnavegación de la página**: Se puede navegar por las páginas de arriba abajo según el orden utilizado en la pestaña [navegación](site_navigation.md), utilizando los botones «Anterior» y «Siguiente» que aparecen en la parte inferior de cada página. Algunos temas también pueden mostrar una ruta de navegación en la parte superior de cada página. 

Cuando las páginas están organizadas jerárquicamente en la navegación, también se muestra una subnavegación para ayudar a los visitantes a desplazarse de las páginas principales a las secundarias, y entre páginas del mismo nivel. Cuando se muestra, la subnavegación mostrará las páginas secundarias de la página actual, si las hay. Cuando una página secundaria (o una «página hoja», como las hojas de un árbol) muestra la subnavegación, esta se mostrará en contexto con sus páginas del mismo nivel. 

Puedes optar por:

- Mostrar la subnavegación en todas las páginas
- Ocultarla en las páginas hoja (la configuración predeterminada)
- Ocultar la subnavegación dondequiera que aparezca.

Es posible que desee utilizar el [bloque de página «Índice»](site_pages.md#table-of-contents) o el [bloque de página «Lista de páginas»](site_pages.md#list-of-pages) para ayudar a los usuarios a navegar por su sitio.  

### Idioma

**Configuración regional** es un menú desplegable para seleccionar el código de idioma de este sitio. De forma predeterminada, se establecerá igual que la configuración regional global de toda la instalación de Omeka S. Para cambiarlo, seleccione un idioma en el menú desplegable.

**Filtrar valores según la configuración regional del sitio** es una casilla de verificación para restringir los valores visibles a aquellos que coincidan con la configuración de idioma del sitio y a aquellos que no tengan un ID de configuración regional. Cuando está marcada, sus recursos solo mostrarán propiedades y valores en los que los valores tengan la misma configuración de idioma, o ningún idioma. Esto le permite, por ejemplo, tener un sitio en inglés y otro en francés en los que cada uno muestre únicamente los valores respectivos en inglés o francés asignados a los mismos elementos. 

**Mostrar etiquetas de idioma para los valores** es una casilla de verificación que controla la visibilidad de la etiqueta de idioma para cada valor en las páginas públicas de los recursos.

### Explorar

![Configuración de exploración, todo vacío o en su valor predeterminado.](../sites/sitesfiles/sites_settingsbrowse.png)

**Restringir la exploración a elementos adjuntos** es una casilla de verificación. Si se marca, las funciones de exploración de su sitio solo mostrarán los elementos que se hayan añadido a un bloque de página. Si no se marca, las páginas y bloques de exploración de su sitio incluirán todos los elementos del conjunto de elementos.

**Resultados por página** establece el número de resultados por página en las páginas de exploración introduciendo un número. Si se deja en blanco, el sitio utilizará el valor predeterminado de la [configuración global](../admin/settings.md).

Dependiendo del [tema del sitio](../sites/site_theme.md), es posible que desee establecer este valor como un múltiplo de 4 para obtener una visualización más elegante. Ten en cuenta que el uso de números muy grandes (50, 75, 100) puede hacer que las páginas de navegación se carguen lentamente.

**Propiedad del encabezado de navegación** establece qué propiedad se utilizará como encabezado para cada recurso en una página de navegación. Por defecto, es Dublin Core: Título. El menú desplegable te permite seleccionar entre todos los vocabularios disponibles e incluye una barra de búsqueda para encontrar rápidamente la propiedad deseada.

![La opción de propiedad de encabezado de navegación está abierta. La selección actual, Dublin Core: Título, se encuentra en la parte superior. Justo debajo hay una barra de búsqueda, indicada por un símbolo de lupa. Debajo de esa barra se muestran algunas propiedades del vocabulario «amigo de un amigo».](../sites/sitesfiles/sites_setbrowseprop.png)

**Propiedad del cuerpo de la navegación** establece qué propiedad se utilizará como texto del cuerpo para cada recurso en una página de navegación. Por defecto, es Dublin Core: Descripción. El menú desplegable te permite seleccionar entre todos los vocabularios disponibles e incluye una barra de búsqueda para encontrar rápidamente la propiedad deseada.

**Valores predeterminados de exploración de elementos** le permiten personalizar la exploración predeterminada y la ordenación de los resultados de búsqueda de su sitio. Por defecto, los elementos se ordenan por «Creado» «Descendente», lo que significa que los elementos añadidos más recientemente aparecen en la parte superior de las exploraciones y búsquedas. Tenga en cuenta que los usuarios siempre pueden cambiar estos métodos de ordenación en las páginas públicas. Aquí puede establecer un valor predeterminado alternativo, como por orden alfabético por Título, o por orden alfabético por Clase de recurso. 
También puede elegir una propiedad de su instalación para utilizarla como método de ordenación predeterminado personalizado, aunque esta propiedad no se mostrará en la entrada de cada elemento en los resultados de navegación y búsqueda. Seleccione «[Ordenación personalizada por]» e introduzca la propiedad en el campo de texto, con el formato `vocabulario:propiedad`; por ejemplo, `dcterms:format`. También puede utilizar `id` y `modified`. 
Esta entrada personalizada será el método de ordenación activo en todas las tablas de elementos de su sitio. Tenga en cuenta que aparecerá como «Personalizado (dcterms:format)» en los menús desplegables públicos. 
Consulte la [sección «Ordenación» de la página de búsqueda](../search.md#sorting) para obtener más información sobre los comportamientos de ordenación. 

### Mostrar

![Configuración de «Mostrar», con algunas personalizaciones: «Anotaciones de valor» está configurado en «Mostrar anotaciones de valor (expandidas)» y «Excluir recursos que no están en el sitio» está marcado.](../sites/sitesfiles/sites_settingShow.png)

**Mostrar páginas adjuntas**: Cuando esta casilla está marcada, las páginas del sitio a las que está adjunto un elemento se mostrarán en la vista pública de dicho elemento.

**Información de la etiqueta de la propiedad**: Cuando se muestran los metadatos, los visitantes del sitio ven una etiqueta legible para el término de vocabulario utilizado (como «Título» para `dcterms:title`). Puedes elegir incluir también el término completo, o el nombre del vocabulario, entre paréntesis después de cada etiqueta; por ejemplo, para mostrar «Descripción (dcterms:description)» o «Descripción (Dublin Core)» en lugar de solo «Descripción». 

**Anotaciones de valor**: Cuando se utilizan [anotaciones](../content/items.md#value-annotation), puede optar por ocultarlas siempre en este sitio, mostrar un icono que se expanda al hacer clic en él, o mostrarlas expandidas por defecto con un icono disponible para contraerlas. Recuerde que las anotaciones de valor se aplican a nivel de recurso y, por lo tanto, están disponibles en toda la instalación, no sitio por sitio.

**Excluir recursos que no están en el sitio**: Cuando esta casilla está marcada, el sitio no mostrará [recursos Omeka vinculados](../content/items.md#linked-resources) que no se hayan [añadido como recursos al sitio](site_resources.md).

**Incrustar medios en las páginas de elementos (heredado)**: Marque esta casilla cuando los temas no muestren los medios de un elemento en la página de vista del elemento de forma predeterminada. 

### Búsqueda

![La sección de configuración de búsqueda, todo configurado con los valores predeterminados excepto en «Buscar recursos», donde también está marcada la opción «conjuntos de elementos»; por defecto, solo están marcadas «Páginas del sitio» y «elementos».](../sites/sitesfiles/sites_settingssearch.png)

**Tipo de búsqueda** es un menú desplegable que le permite establecer desde qué sitio(s) genera resultados la barra de búsqueda:

- Este sitio: solo devuelve resultados de este sitio.
- Todos los sitios: devuelve resultados de todos los sitios de la instalación.

**Buscar recursos** es una serie de casillas de verificación que le permiten seleccionar qué tipos de recursos se buscan desde el campo de búsqueda principal del sitio. Seleccione entre: páginas del sitio, elementos y conjuntos de elementos. Puede seleccionar todos si lo desea.

**Miembros del vocabulario de búsqueda avanzada** le permite limitar las opciones de búsqueda a propiedades y clases. Puede elegir mostrar solo las propiedades y clases utilizadas en este sitio, o en toda la instalación de Omeka, en lugar de todas las propiedades y clases proporcionadas por todos los vocabularios instalados actualmente en la plataforma.

**Plantillas** le permite limitar las propiedades para la búsqueda avanzada de elementos o conjuntos de elementos a solo las propiedades incluidas en una o varias plantillas. Cuando este campo está vacío, la opción «Buscar por valor» de la búsqueda avanzada mostrará todas las propiedades de todos los vocabularios de la instalación de Omeka S. Aplicar una plantilla no solo limita las opciones del menú desplegable, sino que también incluye sus etiquetas alternativas para las propiedades:

![Vista detallada de un menú desplegable para la opción «Buscar por valor». Los valores cargados incluyen Creador:Autor, Fecha: Fecha de publicación y Descripción.](../sites/sitesfiles/sites_settingtemp.png)

Haga clic en el campo para añadir una plantilla; puede añadir más de una plantilla haciendo clic de nuevo en el campo.

**Restringir a plantillas** limitará los resultados de la búsqueda únicamente a aquellos elementos que utilicen las plantillas seleccionadas.

### Visor IIIF

Omeka S incluye el [visor Mirador](https://projectmirador.org/){target=_blank} para mostrar imágenes y presentaciones IIIF. Los siguientes ajustes solo afectan al visor de presentaciones (para múltiples imágenes). 

**Mostrar barra lateral**: cuando está marcada, cualquier visor Mirador del sitio mostrará la barra lateral de información de forma predeterminada. Los usuarios pueden ocultarla o mostrarla en cualquier momento. 

**Tema**: dependiendo del diseño de su sitio, es posible que desee utilizar el tema claro u oscuro de Mirador para el visor IIIF. 

El visor con el tema oscuro, con la barra lateral visible:

![El visor IIIF con el tema oscuro y la barra lateral visible, mostrando un autorretrato de Van Gogh e información de la Galería Nacional de Arte sobre su presentación IIIF, denominada «Lo más destacado de la colección».](../sites/sitesfiles/sites_iiifdark.png)

El visor con el tema claro, sin la barra lateral visible:

![La misma colección de imágenes con el mismo título, pero sin la información de la barra lateral y con el tema claro.](../sites/sitesfiles/sites_iiiflight.png)

### Secciones añadidas por módulos

Si ves secciones adicionales en esta página añadidas por módulos, ve a la página del módulo específico en este manual de usuario para obtener más información sobre la configuración. 
