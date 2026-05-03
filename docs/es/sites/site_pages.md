# Páginas del sitio

Las páginas conforman el contenido de tus [sitios](../sites/index.md). Un sitio puede tener una o varias páginas, y estas pueden [organizarse, mediante la navegación](site_navigation.md), en una secuencia lineal (como en el caso de las exposiciones virtuales) o en una estructura jerárquica en forma de árbol. 

Gestiona las páginas de un sitio accediendo a la sección Sitios en el panel de navegación de la izquierda del panel de administración. Selecciona el sitio cuyas páginas deseas gestionar y haz clic en el título o en el botón de edición (lápiz) para editar ese sitio. 

Una vez que estés editando el sitio, haz clic en el enlace Páginas en el panel de navegación de la izquierda.

Al crear un nuevo sitio, Omeka S añade automáticamente una página titulada «Bienvenida» con un único bloque HTML (véase más abajo). Puede editar esta página o eliminarla.

## Explorar páginas
La pestaña Páginas mostrará todas sus páginas en su orden de navegación. Las páginas secundarias se mostrarán debajo de la página principal con uno o más caracteres «-» (guión) antes del título de la página.

Cada página aparece en la lista con su título, botones para ver (cuadro con una flecha que sale de él), editar (lápiz) o eliminar (papelera) la página, el slug de la página y su fecha de última modificación. 

![Vista de exploración de páginas de un sitio, con las páginas listadas, algunas de las cuales son páginas secundarias de otras.](../sites/sitesfiles/sitepg_browse.png)

Utiliza la pantalla [Navegación](site_navigation.md) del sitio para establecer el orden de las páginas, incluyendo la configuración de páginas secundarias y principales.

## Añadir una página
Desde el sitio en el que estás trabajando, haz clic en el enlace Páginas de la barra lateral izquierda. A continuación, haz clic en el botón «Añadir nueva página» situado en la esquina superior derecha de la ventana.

Para añadir una página debes introducir un **Título**. También puedes introducir un **slug de URL**. Ambos se pueden editar más adelante. Es necesario un título para crear la página. Si no introduces un slug, Omeka S creará uno a partir del título de la página. Un slug es la parte de la URL correspondiente a la página y solo puede contener letras, números y guiones; no se permiten otros caracteres.

Además, hay una casilla de verificación para «Añadir a la navegación». Si se marca, la página se añadirá automáticamente al final de la [navegación](../sites/site_navigation.md) principal del sitio, en el nivel superior. Si no marca esta casilla, puede añadir manualmente la página a la navegación del sitio y organizarla desde la página Navegación.

![Vista de la página mostrando los campos para Añadir página](../sites/sitesfiles/sitepg_add.png)

El icono del ojo, a la izquierda de los botones «Cancelar» y «Añadir», es un conmutador para configurar la visibilidad de tu página. Si el conmutador está en público (sin línea), cualquiera puede ver la página. Si el conmutador está en privado (línea que atraviesa el icono del ojo), la página solo será visible para los usuarios que hayan iniciado sesión en la instalación de Omeka S y que tengan permisos del sitio (los supervisores y los administradores globales siempre podrán ver las páginas privadas). Esto incluye su aparición en la navegación. Las páginas son visibles por defecto. 

Al hacer clic o pulsar Intro en el icono del ojo, se alterna entre público y privado. 

La página es pública: ![botón para hacer pública que muestra un icono de ojo](../content/contentfiles/item_public.png){style="display:inline;"}

La página es privada: ![botón para hacer privada que muestra un icono de ojo tachado con una barra diagonal](../content/contentfiles/item_private.png){style="display:inline;"}

Una vez introducida esta información, haz clic en el botón «Añadir» situado en la esquina superior derecha de la ventana del navegador. Se te redirigirá automáticamente a la vista de edición de esa página (véase más abajo). 

## Editar una página  
Después de hacer clic en el enlace Páginas, selecciona la página que deseas editar haciendo clic en el nombre de la página o en el botón de edición (lápiz).

![Una página en la vista de edición, con un título de página, un bloque multimedia y un bloque HTML.](../sites/sitesfiles/sitepg_edit.png)

La vista de edición de una página mostrará el título de la página en la parte superior. En la esquina superior derecha se encuentra el conmutador público/privado (el icono del ojo) y los botones para ver la versión pública (en una nueva pestaña), eliminar la página, cancelar los cambios o guardar los cambios. Los cambios no se mostrarán en la parte pública de tu sitio hasta que se hayan guardado.

En la parte superior del área de trabajo se encuentran los campos para el título de la página y el slug de la URL. Puedes editarlos en cualquier momento, pero recuerda que el slug debe ser único dentro del sitio (por ejemplo, no puedes tener dos páginas con el slug «bienvenido» en el mismo sitio).

### Desde la vista pública
Si estás en la vista de administración y haces clic en «Ver» en la esquina superior derecha de una página, se te redirigirá a la vista pública de esa página. 

Mientras navegas por la parte pública de tu sitio, puedes editar la página que estás viendo si has iniciado sesión y la [opción de la barra de usuario está activada en la configuración del sitio](../sites/site_settings.md#general-settings). 

La barra de usuario, que aparece en la parte superior de la página, incluye un enlace para editar la página actual, marcado con un círculo rojo en la imagen siguiente. 

![Barra de usuario de una página del sitio Jane Austen, con «Editar página» marcado con un círculo rojo](sitesfiles/sitepg_edit_public.png)

Te recomendamos mantener abierta una pestaña con la página pública y actualizarla para comprobar los resultados de tus cambios. Recuerda ver tu página con diferentes alturas y anchuras de navegador para asegurarte de que los objetos fluyen y se ajustan como esperabas. Quizás también quieras comprobar cómo se ve tu página en un dispositivo móvil. 

### Modo de diseño
Hay dos opciones para distribuir los bloques en tu página: **Flujo normal** y **Cuadrícula**. 

**Flujo normal** ofrece una vista en la que los bloques se apilan uno tras otro para construir la página. Con este diseño, puedes configurar los bloques para que floten a la derecha y a la izquierda, ocupen todo el ancho o centren el contenido en todo el ancho. Cuando los bloques (como los de medios) flotan junto a un bloque HTML, el texto fluirá y se ajustará alrededor del bloque flotante. Los bloques flotantes ocupan como máximo un tercio del ancho total de la página. 

****Cuadrícula** es un sistema de columnas definido por el usuario, basado en [el diseño de cuadrícula CSS](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_grid_layout){target=_blank}, que permite al usuario ajustar con precisión la ubicación y el ancho de los bloques en una página. Con esta opción puedes definir el número de columnas con las que deseas trabajar en tu página, de 1 a 12; los bloques se pueden configurar para que ocupen una o más columnas, una al lado de otra en filas. 

#### Configuración
A continuación, tendrás la opción de aplicar ajustes de configuración a toda la página. Al hacer clic en el icono de engranaje se abrirá el menú de configuración del diseño de página. 

En **Flujo normal**, podrás: 

- seleccionar una [plantilla para la página](#page-templates) si el tema del sitio ofrece una. 
- añadir un valor para utilizarlo como la `clase` HTML en la propiedad `<body>` de la página. Puedes añadir varios valores separados por espacios. 

En **Cuadrícula**, verás un botón adicional. El botón Vista previa del diseño (un pequeño icono de una cuadrícula de bloques de 2x3) aparecerá junto al icono de engranaje. Esto mostrará una vista previa del diseño en el panel de la derecha, mostrándote todos los bloques que hay actualmente en la página y su ancho en función de las columnas que hayas establecido. También mostrará los grupos de bloques con un contorno adicional alrededor del contenido del grupo. 

El botón «Configurar diseño» (icono de engranaje) te permitirá además definir los espacios (en píxeles) entre las columnas y filas de bloques. Una vez que hayas realizado un cambio en el diseño de la cuadrícula, puedes restablecer la página a la versión guardada más recientemente haciendo clic en el botón «Restaurar» que aparece a la derecha del icono de engranaje y del icono de vista previa.

##### Plantillas de página

Los temas ofrecen la posibilidad de proporcionar atajos en el desarrollo de páginas. Al seleccionar una plantilla de página del menú desplegable del menú de configuración, puedes aplicar diferentes variaciones de diseño proporcionadas por los desarrolladores del tema. Lee la [documentación para desarrolladores](https://github.com/omeka/omeka-s/wiki/4.1-RC){target=_blank} para obtener más información sobre cómo ofrecer plantillas de página. 

Una vez que haya seleccionado un tema del sitio que incluya plantillas de página, como [Foundation](site_theme.md#foundation-theme-settings), puede seleccionar una página para editarla y utilizar el menú de configuración para ver las plantillas disponibles. Foundation ofrece actualmente una opción de plantilla de ancho fijo (predeterminada) o de ancho completo (visible cuando el menú de navegación se configura como un menú desplegable horizontal en lugar de una columna). 

![El panel de la derecha abierto para mostrar el menú de configuración de flujo Normal, con el menú desplegable Plantilla abierto para mostrar las dos opciones del tema Foundation: Predeterminada y Ancho completo.](sitesfiles/sitepg_template.png)

### Añadir bloques

Una vez que hayas elegido el diseño, estarás listo para añadir bloques a la página.

En el lado derecho, puedes elegir añadir un nuevo bloque a tu página seleccionando uno de los siguientes elementos que vienen con cada instalación de Omeka S:

- Recurso
- Vista previa de exploración
- HTML
- Elemento con metadatos
- Salto de línea
- Lista de páginas
- Lista de sitios
- Incrustación de medios
- oEmbed
- Fecha/hora de la página
- Título de la página
- Índice.

Los módulos pueden añadir más bloques a estas opciones. Por ejemplo, en función de los módulos instalados y activos, también puede disponer de algunos de los siguientes bloques de página:

- [Recopilación](../modules/collecting.md)
- [Visualización de datos](../modules/datavisualization.md)
- [Carrusel de elementos](../modules/itemcarouselblock.md)
- [Mapa por archivos adjuntos](../modules/mapping.md)
- [Mapa por consulta](../modules/mapping.md).

Algunos bloques incluyen configuraciones predeterminadas para facilitar la configuración y la vista previa. Por ejemplo, el bloque de fecha y hora de la página se configura automáticamente para mostrar la versión de detalle medio tanto de la fecha de creación como de la de modificación. 

Otros bloques requieren ajustes manuales inmediatamente al añadirlos a la página. Por ejemplo, no puedes añadir un bloque oEmbed sin introducir una URL inmediatamente; no se puede guardar la página con este campo en blanco. 

Consulte una explicación detallada de cada bloque en la sección [Bloques de página](#page-blocks).

#### Grupos de bloques

Como novedad en Omeka S 4.1, ahora puedes agrupar bloques de página. Esto te permite asignar ajustes de diseño al grupo, que se comportará como un bloque normal en el diseño de la página. Los grupos de bloques se pueden personalizar como los bloques, tal y como se muestra a continuación, con un color de fondo o una imagen que abarque todo su contenido, y con clases, relleno interno y alineaciones. 

En la parte superior del panel de la derecha, junto al título «Añadir nuevo bloque», verás un botón blanco que dice «Añadir grupo de bloques». 

Cuando se añade un grupo a una página, puedes arrastrar y soltar bloques dentro de él. A continuación, puedes mover el grupo de bloques como cualquier otro bloque. Para eliminar un bloque de un grupo, basta con arrastrarlo fuera o borrarlo. Al eliminar un grupo de bloques se eliminará todo su contenido. 

### Ajustes de bloques

En el flujo normal o en el diseño de cuadrícula, puedes configurar cada bloque con el icono de engranaje que aparece en su barra de título. Esto desplegará el menú de configuración del diseño del bloque en el panel de la derecha, que contiene las siguientes opciones:

**Plantilla**: Si tu tema ofrece una, puedes seleccionar una plantilla para aplicarla al bloque desde el menú desplegable. Por ejemplo, [el tema Foundation](site_theme.md#foundation-theme-settings) te permite configurar el bloque de vista previa de exploración con su propia visualización en lista o cuadrícula, ignorando la configuración del propio sitio. No todos los bloques de página tendrán plantillas disponibles. 

**Clase** te permite escribir una clase CSS específica para aplicar estilos al bloque. Utilízala junto con tus propias hojas de estilo o con el módulo Editor de CSS. 

**Alineación** incluye dos ajustes: Alineación del bloque y Alineación del texto. 

La alineación del bloque tiene diferentes opciones dependiendo de si se utiliza el diseño [Cuadrícula](#grid) o [Flujo normal](#normal-flow). Consulte las secciones siguientes para obtener más detalles. 

La alineación del texto puede ser:

- Predeterminada
- Izquierda
- Centrada
- Derecha 
- Justificada (completa).

La alineación del texto afectará al contenido del bloque, incluyendo imágenes, texto y enlaces. Por ejemplo, puede tener un bloque flotando a la izquierda de la página, con todo su texto y sus imágenes alineados a la derecha.

**Restricciones** le permite establecer un ancho máximo y/o una altura mínima para el bloque. 

**Relleno** le permite introducir valores numéricos para el relleno superior, izquierdo, derecho e inferior dentro del bloque. El valor predeterminado (un número sin unidades) está en píxeles; también puedes introducir valores en `em`, `rem`, `cm`, `ct`, `%`, etc. Es posible que desees utilizar esto al establecer una imagen o un color de fondo en un bloque lleno de texto; el fondo se extenderá a lo ancho completo del bloque, mientras que el relleno se puede usar para evitar que el texto toque los bordes.

**Fondo** te permite seleccionar un fondo para el bloque: ya sea un color ([utilizando un valor hexadecimal, con el carácter almohadilla (`#`), o un valor de palabra](https://www.w3schools.com/html/html_colors.asp){target=_blank}) o una imagen, de entre los recursos disponibles en la instalación. 

Si eliges una imagen, te resultarán útiles los tres menús desplegables que aparecen a continuación: 

- La posición de anclaje **Vertical** te permite seleccionar [Predeterminada, Superior, Centro o Abajo para el recurso de fondo](https://www.w3schools.com/cssref/pr_background-position.php){target=_blank}.
- La posición de anclaje **Horizontal** te permite seleccionar las opciones Predeterminado, Izquierda, Centro o Derecha para el recurso de fondo.
- **Tamaño** te permite seleccionar [Predeterminado, Portada o Contener para el recurso de fondo](https://www.w3schools.com/cssref/css3_pr_background-size.php){target=_blank}.

Una vez que hayas configurado el bloque, haz clic en «Aplicar cambios». Debes guardar la configuración del bloque y, a continuación, guardar la configuración de la página para que los cambios se vean en la vista pública. 

#### Flujo normal

![Una página de flujo normal en proceso de edición.](sitesfiles/sitepg_normalflow.png)

**La alineación del bloque**, en **flujo normal**, te permite elegir una de las cuatro posiciones del bloque: 

- Predeterminada
- Izquierda
- Derecha
- Centrada. 

Los bloques flotantes a la izquierda o a la derecha ocuparán como máximo un tercio de la página, y pueden ser más pequeños, dependiendo del contenido del bloque. Por ejemplo, un bloque de contenido multimedia incrustado con una miniatura de 200 píxeles y un título o pie de foto breve solo ocupará 200 píxeles más el relleno. Si el texto del bloque es más largo, el bloque ocupará todo el ancho permitido antes de ajustar el texto. 

Un bloque HTML situado justo debajo de un bloque flotante (es decir, el siguiente objeto de la página) ocupará el resto del ancho de la página y se ajustará alrededor del bloque flotante si procede. Esto es así tanto si el bloque flotante está alineado a la izquierda como a la derecha. 

Un bloque alineado al centro en flujo normal no permitirá flotantes a ninguno de los lados: ocupará todo el ancho de la página. Solo un bloque con alineación predeterminada se ajustará alrededor de otro bloque. 

![Una página de flujo normal en el lado público, con dos bloques flotantes y un bloque HTML.](sitesfiles/sitepg_normalPublicFloats.png)

La imagen anterior muestra, en orden:

- Un bloque de incrustación multimedia flotante a la izquierda, con texto alineado por defecto,
- Un bloque de incrustación multimedia flotante a la derecha, con texto alineado a la derecha,
- Un bloque HTML con alineación predeterminada, que se ajusta alrededor de los bloques multimedia, con texto justificado.

#### Cuadrícula

![Una página de cuadrícula en proceso de edición.](sitesfiles/sitepg_grid.png)

En el diseño de cuadrícula, puedes seleccionar la ubicación y el ancho de cada bloque en función del [número de columnas que hayas establecido para la página](#configuración). 

- Para cada bloque, puedes declarar su «Posición» inicial, es decir, el número de columna en la que comenzará el bloque. También puedes establecer la posición en «Auto», lo que significa que comenzará donde haya espacio para que quepa. Verás que el menú desplegable «Posición» refleja el número de columnas de tu página, menos el «Ancho» del bloque (su ancho). Por ejemplo, una página de 6 columnas con un bloque configurado para abarcar 3 columnas podrá comenzar en la columna 1, 2, 3 o 4. 
  
- Cada bloque tiene un ajuste de «Amplitud» que determina el ancho del bloque. El menú desplegable ofrecerá opciones desde «1» hasta el número de columnas establecido para la página. Si selecciona el número máximo de columnas, este bloque ocupará todo el ancho de la página; cualquier valor inferior dejará un espacio en blanco o permitirá que otro bloque ocupe la misma fila. 

Al utilizar estos dos ajustes, los bloques de su página se organizarán en filas según sus selecciones. Para que quepan dos elementos en una fila, configure cada uno de ellos para que ocupe un número que, sumado al resto, no supere el número de columnas de la página. Todos los bloques de una fila tendrán la misma altura; no hay ajuste de texto en el diseño de cuadrícula. 

Es posible que desee emplear una o más columnas vacías en cada fila como elemento de diseño, para crear un espacio en blanco intencionado. Combina esto con los ajustes de espacio entre columnas y entre filas para lograr la estética deseada. 

Para ver un esquema de cómo se posicionan tus bloques en la página, haz clic en el botón de vista previa del diseño (un icono de bloques en una cuadrícula), lo que mostrará una maqueta en el panel de la derecha.

Ten en cuenta que el ancho de cada bloque de página se calcula de la siguiente manera:

- Primero, calcula el ancho total de la ventana del navegador asignado al contenido de la página, restando cualquier barra lateral y teniendo en cuenta los anchos máximos determinados por tu tema.
- A continuación, divide ese valor entre el número de columnas. Por ejemplo, un contenedor de 1200 píxeles de ancho dividido entre 4 columnas dará 300 píxeles cada una.
- A continuación, ten en cuenta el ancho de los espacios entre columnas de la configuración de la página (el valor predeterminado es 10 píxeles) y el número de espacios entre bloques. Por ejemplo, un bloque de 2 columnas junto a otro bloque de 2 columnas en una cuadrícula de 4 columnas tendrá: 1200 píxeles, menos 30 por los 3 espacios entre columnas, dividido entre 4 columnas, multiplicado por 2 para un bloque de 2 columnas, más 10 píxeles para abarcar uno de los espacios, lo que da un ancho final de 595 píxeles cada uno.
- Un bloque calculará su ancho basándose en su propia configuración de extensión y tendrá en cuenta todos los posibles espacios entre columnas, independientemente de si hay otro contenido en la fila o no. Esto mantiene el diseño de la cuadrícula ordenado en la interfaz de usuario, independientemente del contenido de cada fila.
- Ten en cuenta que el espacio total disponible dependerá del dispositivo utilizado y del tamaño de la ventana del navegador. Los temas de Omeka tienen alternativas para anchos de pantalla móviles reducidos, lo que puede hacer que los bloques de tu página se muestren de uno en cada fila. 

También puede establecer la posición del contenido dentro de cada bloque con el menú desplegable **Alineación del bloque**, que se encuentra en **Alineación**. 

En el diseño de página **Cuadrícula**, la alineación del bloque le ofrece:

- Predeterminada
- Izquierda
- Derecha
- Centrada.

Esto determinará la posición del contenido del bloque dentro de su espacio. El título de una página, por ejemplo, está configurado para ocupar todo el ancho de la página de forma predeterminada, pero al elegir la alineación a la izquierda, a la derecha o al centro, el contenido se moverá al lugar designado, ajustando el contenedor estrechamente alrededor del contenido y dejando espacio en blanco en el resto del espacio. Esto se aprecia mejor cuando se utiliza un color de fondo o una imagen en los bloques. 

![Una página en cuadrícula en el lado público, con 4 bloques de título de página.](sitesfiles/sitepg_gridPublic.png)

La imagen anterior muestra, en orden:

- Un bloque de título de página con alineación predeterminada, extensión 4 (de 4 columnas), posición automática;
- Un bloque de título de página con alineación centrada, extensión 4, posición automática;
- Un bloque de título de página con alineación predeterminada y texto centrado, extensión 4, posición automática;
- Un bloque de título de página con alineación predeterminada, extensión 2, posición 2. 

Tenga en cuenta que el segundo título de página sigue ocupando las 4 columnas de la página y no se puede colocar nada a ninguno de sus lados. 

### Eliminar y reordenar bloques
Puede eliminar cualquiera de los bloques haciendo clic en el icono de la papelera situado en la esquina superior derecha del bloque. 

![El bloque «título de la página» está marcado para su eliminación y, por lo tanto, resaltado en rojo.](../sites/sitesfiles/sitepg_delblock.png)

Cambie el orden de los bloques haciendo clic en las tres líneas horizontales de la esquina superior izquierda de cualquier bloque y, a continuación, arrastrándolo y soltándolo en la ubicación deseada.

## Bloques de página

Los bloques de página están diseñados para ofrecer una variedad de herramientas de creación para cualquier tipo de página que estés escribiendo. Los módulos de terceros y los enviados por los usuarios pueden añadir otros bloques de página a los creados y mantenidos por el equipo de Omeka. 

### Recurso

Muestra archivos que no son archivos multimedia adjuntos a elementos (como un logotipo o un banner). Los usuarios pueden subir nuevos recursos o seleccionar entre los ya existentes.

![Bloque de activos con la barra lateral de selección de activos abierta, que incluye una opción para subir activos y otra para seleccionarlos](sitesfiles/sitepg_asset_selection.png)

Una vez seleccionado un activo, el usuario tiene la opción de incluir información adicional sobre el mismo:

- Enlace a la página: Selecciona una página dentro del sitio, de modo que el activo se convierta en un enlace a ella. El título de la página seleccionada también aparecerá como un enlace de texto encima o al lado del activo.
- Título alternativo del enlace: Si se ha establecido un enlace a la página anteriormente, aquí puedes controlar el texto que se muestra. Si no se introduce nada, el enlace mostrará por defecto el título de la página.
- Pie de foto: Texto que se mostrará debajo o cerca del recurso, sin enlace.

![Barra lateral de opciones del recurso con campos de entrada para el enlace a la página, el título alternativo del enlace y el pie de foto](sitesfiles/sitepg_asset_sidebar.png)

La visualización de estos elementos dependerá del tema y de las [plantillas](#block-settings) que estén disponibles. 

![Barra lateral de configuración de diseño del bloque de página «Recurso» con las plantillas de Foundation: Predeterminada, Tarjeta y Objeto multimedia](sitesfiles/sitepg_assetTemplate.png)

A continuación se muestra el bloque de página de activos con el mismo activo seleccionado y el mismo enlace establecido, con cada una de las tres opciones de configuración de plantillas de Foundation: Predeterminada, Tarjeta y Objeto multimedia:

![Las tres opciones de plantilla en una página pública.](sitesfiles/sitepg_assetTemplatePublic.png)

Haga clic en «Aplicar cambios» para guardar la configuración y, a continuación, guarde la página.

### Vista previa de exploración

Añade un bloque de recursos a una página, de forma idéntica a la página «Elementos» y otras páginas de exploración incluidas en su sitio Omeka.

![Bloque Vista previa de exploración con el elemento de consulta](sitesfiles/sitepg_browsepreview_query.png)

En el menú desplegable **Tipo de recurso**, elija el tipo de recurso que desea mostrar en el bloque: Elementos, Conjuntos de elementos o Multimedia. 

Utilizando la interfaz del elemento **Consulta de búsqueda**, seleccione su subconjunto de recursos o déjelo en blanco.

Haga clic en el botón «Editar» para mostrar la interfaz de búsqueda avanzada en el panel. Una vez que esté satisfecho con el subconjunto de recursos de su búsqueda, al hacer clic en el botón «Aplicar» se establecerá el subconjunto de recursos para el bloque de navegación.

![Panel de consulta de búsqueda avanzada](../sites/sitesfiles/sitepg_query_search.png)

Una vez establecida una consulta, puede hacer clic en «Editar» para actualizar el conjunto de recursos. Puede hacer clic en «Edición avanzada» para editar directamente la cadena de consulta. Por último, puede «Borrar» una consulta para empezar de nuevo. Si ha borrado una búsqueda por error, puede «Restaurarla».

![Bloque de exploración con el elemento de edición de consulta](sitesfiles/sitepg_query_update.png)

El campo **Límite** te permite establecer el número de recursos que se mostrarán en el bloque; se puede acceder a cualquier resultado adicional de tu consulta en una página de búsqueda enlazada desde el bloque (puedes establecer el texto del enlace en el campo **Texto del enlace** que aparece a continuación).

El campo **Componentes** te permite decidir qué mostrar en tu vista previa para cada recurso: el Título, el Cuerpo y/o la Miniatura. Si no se ha configurado en los [ajustes del sitio](site_settings.md#browse), el Título se establece por defecto en el título del recurso y el Cuerpo en la descripción del recurso.

El campo **Título de vista previa** establece el título que aparece encima de la sección de vista previa en la página.

El campo **Texto del enlace** establece el texto del enlace en la parte inferior del bloque; el bloque solo mostrará tantos resultados como hayas establecido en el campo **Límite** de arriba.

El bloque de vista previa de exploración tiene una opción de plantilla en algunos temas. Por ejemplo, el tema Foundation te permite anular la configuración del sitio para la exploración con las opciones de mostrar los recursos en una lista o en una cuadrícula en este bloque. 

### HTML

Crea un cuadro HTML en el que puedes añadir texto con formato y enlaces. Al hacer clic en el cuadro, aparecerá un menú de formato encima del campo de texto. 

Este es el bloque HTML básico tal y como aparece cuando se añade por primera vez a tu página: 

![Bloque de página para contenido HTML](sitesfiles/sitepg_html.png)

Y el bloque de página con el menú de formato abierto:

![Bloque de página para contenido HTML con campo activo, mostrando el menú de formato que incluye botones para estilos de párrafo, texto en negrita y cursiva, etc.](sitesfiles/sitepg_html2.png)

Puedes incrustar contenido de otros sitios de Internet utilizando iFrames u otros códigos de incrustación en el bloque HTML.

1. Haz clic en el área de contenido del bloque HTML para mostrar el menú de formato y, a continuación, haz clic en el botón «Fuente».  Esto abrirá un cuadro de diálogo donde podrás escribir contenido HTML.
1. Copia y pega el código de incrustación en el editor de código fuente. Por ejemplo, aquí está el código de incrustación de un screencast de Omeka alojado en Vimeo. 
![Cuadro de código fuente abierto con un breve párrafo de texto con formato HTML y un iFrame de Vimeo](sitesfiles/sitepg_htmlSource2.png)
1. Haz clic en el botón verde «Aceptar» situado en la parte inferior del editor. 
1. El material incrustado debería aparecer en el bloque HTML, ya sea como un rectángulo gris o como el contenido incrustado. 
![Bloque HTML que muestra un vídeo incrustado](sitesfiles/sitepg_htmlSource3.png)
1. Recuerda guardar la página con los cambios.

Si tienes instalado el [módulo Zotero Citations](../modules/zoterocitation.md), puedes insertar una bibliografía de Zotero en este campo. Busca el botón de Zotero en el menú de formato (una Z roja grande). 

### Imagen IIIF

Te permite insertar una URL a una imagen IIIF y mostrarla en tu página.

Un ejemplo de URL de imagen IIIF:

`https://media.nga.gov/iiif/public/objects/1/0/6/3/8/2/106382-primary-0-nativeres.ptif/info.json`

### Presentación IIIF

Te permite insertar una URL a una presentación IIIF y mostrarla en tu página.

Un ejemplo de URL de presentación IIIF:

`https://media.nga.gov/public/manifests/nga_highlights.json`

### Elemento con metadatos

Muestra un elemento junto con todos los metadatos asociados (introducidos al crear o editar el [elemento](../content/items.md)), de forma idéntica a la página de vista del elemento en tu tema. 

Añade archivos adjuntos de la misma manera que el bloque de página [incrustación de medios](site_pages.md#media-embed).

![Bloque «Elemento con metadatos» en la pantalla de edición de la página, con un elemento adjunto](sitesfiles/sitepg_iwm.png)

Muchos temas no mostrarán el medio principal en esta visualización, aunque algunos sí lo hacen. Aquí está el bloque de página en el tema Center Row:

![El mismo bloque «Elemento con metadatos» en la página pública, mostrando información del elemento adjunto](sitesfiles/sitepg_iwm2.png)

### Salto de línea

Añade un salto de línea transparente u opaco a la página. Selecciona si la línea es transparente u opaca en el menú desplegable.

![El bloque de salto de línea, con el menú desplegable seleccionado en opaco, además de su vista previa de diseño.](sitesfiles/sitepg_line.png)

En el diseño de flujo normal, el bloque de salto de línea borrará todos los bloques y elementos flotantes. 
En el diseño de cuadrícula, puede establecer la longitud de la línea utilizando la configuración de Span:

![El salto de línea en una página pública.](sitesfiles/sitepg_line2.png)

### Lista de páginas

Muestra una lista con viñetas de páginas enlazadas. Puede seleccionar entre las páginas que se encuentran dentro del sitio. Otros elementos de navegación, como las URL personalizadas y las páginas de exploración, no están disponibles.

Haga clic en el botón «Añadir páginas» del bloque para mostrar un panel que contiene todas las páginas del sitio. Haga clic en la página concreta para añadirla a la lista.

![Interfaz de edición de página con el bloque Lista de páginas activado para abrir el panel de selección de páginas](sitesfiles/sitepg_listPagesAdd.png)

Puede arrastrar y anidar páginas en cualquier orden.

![Bloque Lista de páginas con páginas anidadas](sitesfiles/sitepg_listPagesOrder.png)

### Lista de sitios

Muestra una lista de todos los sitios de su instalación de Omeka S, de forma similar a la página «Índice de sitios» que se puede mostrar en la raíz de su instalación. Este bloque tiene las siguientes opciones:

- Ordenar sitios por: Orden alfabético (A-Z); Los más antiguos primero; Los más recientes primero. Por defecto, está configurado en orden alfabético. 
- El número máximo de sitios le permite limitar el número de sitios que se muestran en el bloque. Si se deja en blanco, se mostrarán todos los sitios.
- Una casilla de verificación para permitir a los visitantes navegar por la lista completa de sitios, si se ha establecido un límite de visualización.
- Una casilla de verificación para mostrar resúmenes de los sitios.  
- Una casilla de verificación para mostrar miniaturas de los sitios.
- Una casilla de verificación para excluir el sitio actual de la lista. 

![Bloque Lista de sitios](../sites/sitesfiles/sitepg_slist1.png)

Este bloque puede resultar útil si designa un sitio como el sitio «principal» de su instalación, que contiene información general sobre la institución o su colección, y luego lo utiliza para dirigir a los visitantes a una colección de exposiciones digitales o ensayos basados en su colección. 

Aquí se muestra el bloque Lista de sitios tal y como aparece en el tema Papers, con paginación, resúmenes y miniaturas:

![Bloque Lista de sitios en la parte pública.](sitesfiles/sitepg_slistPublic.png)

### Incrustación de medios

Muestra uno o más elementos multimedia asociados a los elementos del conjunto de elementos del sitio. 

![bloque de medios sin ningún medio adjunto](../sites/sitesfiles/sitepg_media.png)

El bloque «Medios» tiene las siguientes opciones: 

- Diseño: elige entre diseño vertical u horizontal. Una fila horizontal de elementos contendrá un máximo de 4 antes de pasar a una nueva fila, dependiendo del ancho del bloque de página.
- Visualización de medios: elige mostrar los medios originales subidos o solo las miniaturas generadas por Omeka. Si incrustas medios, los vídeos, manifiestos IIIF y otros archivos enriquecidos se mostrarán en su tamaño original, al igual que los reproductores de audio, dependiendo del ancho del bloque de la página. Si eliges mostrar solo miniaturas, verás miniaturas de vídeo derivadas e imágenes de reserva para medios como el audio. Las imágenes siempre mostrarán una derivada, cuyo tamaño se selecciona de entre los tamaños de miniatura del siguiente menú desplegable. Ten en cuenta que solo puedes incrustar un visor de PDF utilizando este bloque si el [módulo PDF Embed está instalado y activo](https://omeka.org/s/modules/PdfEmbed/){target=_blank}; de lo contrario, se mostrará una imagen derivada.
- Tipo de imagen: elige entre tamaños de miniatura grandes, medianos y cuadrados para cualquier imagen que hayas añadido al conjunto. Estos tamaños se configuran [a nivel de instalación](../configuration.md#thumbnails), pero pueden parecer más pequeños dependiendo del ancho del bloque de la página.
- Establezca el título del archivo adjunto como:
  - título del elemento (título del elemento adjunto);
  - título del medio (título del medio específico que haya seleccionado del elemento); o
  - sin título.

Cada elemento añadido al bloque de incrustación de medios también puede tener un pie de foto de texto enriquecido que se muestra debajo del título. 

Para **añadir medios al bloque**, haga clic en el botón «Añadir archivo adjunto». 

Al cargarse, el panel mostrará una lista de tus elementos, ordenados por fecha, de más reciente a más antiguo. Puedes seleccionar desde la primera página, desplazarte utilizando las flechas de avance y retroceso, o buscar utilizando la barra de búsqueda. Puedes seleccionar desde la primera página, desplazarte utilizando las flechas de avance y retroceso, o buscar utilizando la barra de búsqueda. 

![Panel de selección de elementos](../sites/sitesfiles/sitepg_selectitem.png)
 
Si tiene un gran número de elementos entre los que navegar, o varios elementos con el mismo título, puede utilizar las opciones de «Filtrar búsqueda» haciendo clic en el botón triangular situado a la derecha de su etiqueta. 
 
Estas opciones son:

- Filtrar por clase: abre un menú desplegable para seleccionar entre todas las clases de los vocabularios de la instalación de Omeka.
- Filtrar por conjunto de elementos: abre un menú desplegable para seleccionar entre todos los conjuntos de elementos de la instalación (no solo los añadidos al sitio en el que estás trabajando).
- Filtrar por ID de elemento: puede introducir el ID específico de Omeka de un elemento. 

Una vez que haya aplicado los cambios al filtro, debe hacer clic en el botón de búsqueda (icono de la lupa) para aplicar los filtros y ejecutar la búsqueda.  

![Cajón de selección de elementos con opciones de filtro mostradas](../sites/sitesfiles/sitepg_selectitemFilter.png)

Una vez que haya seleccionado un elemento, el panel se desplazará a la información de ese elemento. Puede añadir un título y seleccionar qué medios (si hay más de uno) desea utilizar. Para volver a la lista de elementos, haga clic en el botón «Seleccionar elemento» en la parte superior del panel. Asegúrese de hacer clic en el botón «Aplicar cambios» en la parte inferior del panel. 

Si desea mostrar varios medios del mismo elemento, añade el mismo elemento al bloque de incrustación de medios varias veces y elige manualmente el medio para cada entrada. 

![Vista del elemento con la opción de aplicar cambios](../sites/sitesfiles/sitepg_applyitem.png)

Para añadir varios elementos a la vez, haz clic en el control deslizante «Añadir rápidamente» situado justo encima de la lista de elementos en el panel de la derecha. Esto añadirá una casilla de verificación a la izquierda de cada elemento. Marca las casillas de los elementos que quieras añadir al bloque y, a continuación, haz clic en el botón «Añadir seleccionados» situado en la parte inferior del panel.

![Panel de selección de elementos con la función de adición rápida activada: ahora todos los elementos de la vista tienen una casilla de verificación.](../sites/sitesfiles/sitepg_selectitemQuick.png)

!!! nota
  En el diseño de flujo normal (no en cuadrícula), si desea que los elementos multimedia aparezcan junto a un bloque de texto, coloque un bloque multimedia *por encima* de un bloque HTML y elija la alineación a la izquierda o a la derecha. En el ejemplo siguiente, el elemento multimedia tiene un tipo de miniatura «medio», la alineación «derecha» y el título del archivo adjunto es el «título del elemento»: 

  ![Un bloque de texto lorem ipsum con un elemento alineado a la derecha incrustado en la parte superior del párrafo](../sites/sitesfiles/sitepg_mediaalign.png)

	Colocar un bloque multimedia *después* de un bloque HTML en el diseño de flujo normal hará que el contenido multimedia aparezca debajo del final del contenido del bloque HTML.

  En el  diseño de cuadrícula, puedes colocar un bloque multimedia antes o después de un bloque HTML y determinar la ubicación en función del span y la posición que le asignes.

### oEmbed

Te permite incrustar contenido multimedia de sitios web de terceros, como Flickr, Vimeo, YouTube, SoundCloud y muchos más. Normalmente puedes introducir la URL directamente desde tu navegador o el enlace proporcionado por la función para compartir del sitio que hayas elegido. 

Por ejemplo, los enlaces en estos formatos deberían funcionar todos: 

- https://vimeo.com/381092531
- https://www.youtube.com/watch?v=W8r-tXRLazs
- https://youtu.be/W8r-tXRLazs?feature=shared

No puedes guardar la página sin ninguna URL en el bloque oEmbed, una vez que hayas añadido el bloque a la página.

![Campo de entrada para la URL de oEmbed](sitesfiles/sitepg_oEmbed.png)

Después de guardar la URL, puedes ver la configuración avanzada, que incluye información sobre el formato del oEmbed (no editable) y una casilla de verificación para actualizar el oEmbed. También puedes sustituir la entrada existente por una nueva URL. 

![La configuración avanzada de oEmbed incluye la información de formato y la opción de actualizar](sitesfiles/sitepg_oEmbedadvanced.png)

La fuente del contenido multimedia enviará un tamaño fijo que no se puede modificar, salvo colocando el oEmbed en un contenedor más pequeño. En el diseño Normal, la ubicación del oEmbed vendrá determinada por el flotante. En el diseño de cuadrícula, abarcará el número de columnas que elijas.

Dependiendo del sitio del que proceda la incrustación, habrá diferentes funciones disponibles dentro de la visualización del contenido multimedia. Algunos ejemplos son:

- Flickr: incluye botones para compartir en Facebook, Tumblr, X y Pinterest, o para llevarte al contenido multimedia en Flickr. También se muestran el pie de foto, el autor y la atribución.
- Vimeo: incluye botones para dar «Me gusta», añadir a «Ver más tarde» y compartir. Además de los controles de reproducción y volumen, hay opciones para activar los subtítulos, ver una transcripción, ver la configuración, poner el vídeo a pantalla completa o ver el vídeo en Vimeo.
- YouTube: incluye botones para poner el vídeo a pantalla completa y ver el vídeo en YouTube.

Puede que te resulte útil [la lista de proveedores de oEmbed](https://oembed.com/providers.json){target=_blank}. Omeka está diseñado específicamente para reconocer más fácilmente las URL compatibles con oEmbed procedentes de diversas fuentes; puedes ver [esta lista en el código fuente](https://github.com/omeka/omeka-s/blob/develop/application/config/module.config.php#L893){target=_blank}. 

!!! nota
  Puedes incrustar contenido multimedia de muchos de los sitios compatibles con oEmbed de otras formas, lo que puede ofrecerte más control sobre el estilo y la personalización. Por ejemplo, puedes añadir un vídeo de YouTube a un elemento y luego mostrarlo con el bloque de incrustación de medios, o pegar el código de incrustación que ofrecen Vimeo o Flickr en un bloque de página HTML.

### Fecha y hora de la página

Muestra la fecha de creación de la página y/o la fecha de la última modificación, con o sin marca de tiempo precisa.

![Cuadro de configuración de fecha y hora de la página con botones de opción.](sitesfiles/sitepg_pageDateTime.png)

Tienes la opción de mostrar la fecha de creación, la de modificación o ambas, así como de configurar el formato de las fechas y horas. Si eliges mostrar tanto la fecha como la hora, aparecerá con «a las» entre los dos valores:

```
<p>Página creada: 6 de septiembre de 2022 a las 19:17:35 GMT</p>

<p>Página modificada: 7 de septiembre de 2022 a las 21:38:39 GMT</p>
```

Opciones de formato de fecha:

- Ninguna
- Corto (`7/6/22`)
- Medio (`6 de septiembre de 2022`)
- Largo (`6 de septiembre de 2022`)
- Completo (`Martes, 6 de septiembre de 2022`).

Opciones de formato de hora:

- Ninguna
- Corto (`7:17 p. m.`)
- Medio (`7:17:35 p. m.`)
- Largo (`7:17:35 p. m. GMT`)
- Completo (`7:17:35 p. m. GMT`).

### Título de la página

Muestra el título de la página. Este bloque se añade por defecto a cada página nueva, pero se puede eliminar o reorganizar. El título de la página se muestra dentro de una etiqueta `<h2>`. 

### Índice
Si la página tiene páginas secundarias, puedes añadir un bloque de índice para esas páginas. No se trata de un índice para todo el sitio, sino solo para los elementos que se encuentran debajo de la página actual. 

Si el tema de Omeka ya muestra un índice de forma predeterminada, al insertar este bloque en tu página se sustituirá esa visualización. Por ejemplo, el tema Papers mostrará todas las páginas secundarias de la página actual justo debajo de la ruta de navegación; si se añade el bloque de índice a la página, esa barra desaparecerá. En Thanks Roy, la subnavegación del índice aparece en una columna a la izquierda del contenido de la página; si se añade el bloque de índice a la página, esa columna desaparecerá y el contenido de la página ocupará más ancho de pantalla. 

La opción Profundidad te permite establecer cuántos niveles de páginas secundarias deseas mostrar. El valor predeterminado es 1. Introduce un número entero. No puedes dejar este campo en blanco. 

![Bloque de índice con la opción de profundidad establecida en 3.](sitesfiles/sitepg_toc.png)

Añade y organiza páginas utilizando la configuración de [Navegación del sitio](site_navigation.md). Si deseas mostrar páginas de todo el sitio o en un orden personalizado, utiliza el [bloque Lista de páginas](#list-of-pages). 

Ten en cuenta que puedes activar o desactivar la subnavegación de páginas en la [configuración del sitio](site_settings.md#general-settings). 

### Otros bloques
Para bloques específicos de módulos, como [Recopilación](../modules/collecting.md) o [Mapeo](../modules/mapping.md), consulta la documentación de ese módulo.

## Eliminar una página
Para eliminar una página, ve a la sección Páginas del sitio correspondiente. Haz clic en el botón de eliminar (papelera) situado en el extremo derecho de la fila de esa página. 

Se abrirá un panel en el lado derecho de la página pidiéndole que confirme que desea eliminar la página, con el nombre de la página mostrado debajo del botón de confirmación. Para continuar, haga clic en el botón «Confirmar eliminación». De lo contrario, haga clic en la «X» en la esquina superior derecha del panel para cancelar.

![Panel de eliminación de la página Novelas](sitesfiles/sitepg_delete.png)

