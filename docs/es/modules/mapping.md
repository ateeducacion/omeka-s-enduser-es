# Cartografía 

El [módulo de cartografía](https://omeka.org/s/modules/Mapping){target=_blank} te permite geolocalizar los elementos de Omeka S y mostrar mapas interactivos en tus sitios web públicos. Los mapas pueden incluir líneas de tiempo que te permiten desplazarte por los elementos del mapa en orden cronológico.

![Mapa con línea temporal](modulesfiles/Mapping_timelinePublic1.png)

El módulo de mapas añade: 

- una pestaña «Mapeo» al editar elementos, donde estos se pueden geolocalizar mediante marcadores y formas (líneas, polígonos, rectángulos), y cada mapa se puede personalizar
- opciones de edición por lotes para los elementos
- campos de búsqueda opcionales basados en la ubicación para las interfaces de administración y públicas, que se controlan sitio por sitio mediante [Configuración del sitio](../sites/site_settings.md#settings)
- tres bloques de página para [Páginas del sitio](../sites/site_pages.md) que pueden mostrar mapas y líneas de tiempo para su exploración: «Mapa por consulta», «Mapa por archivos adjuntos» y «Mapa por grupos»
- Una página de «Navegación por mapas» para cada sitio, que se encuentra en la [Configuración de navegación del sitio](../sites/site_navigation.md)
- [bloques de recursos para elementos y conjuntos de elementos](../sites/site_theme.md#select-regions-and-blocks) (no para archivos multimedia), que pueden reposicionarse dentro de las regiones que ofrece el tema de un sitio determinado. 

!!! Nota
	Los conjuntos de elementos no se pueden geolocalizar, pero pueden mostrar información cartográfica basada en los elementos que se les hayan asignado.

La cartografía cuenta con ajustes predeterminados para toda la instalación (selección de «mapas base» que se muestran, etc.),que prevalecen sobre los globales, y ajustes administrativos específicos del usuario que se aplican al editar. Los mapas individuales de las páginas, así como los asociados a elementos, pueden personalizarse para anular todos estos valores predeterminados. 

La función de mapas puede integrarse con el módulo [Collecting](collecting.md#prompts), permitiendo a los usuarios que rellenan el formulario de contribución proporcionar datos de geolocalización para sus envíos. Los usuarios hacen clic directamente en un mapa para colocar un marcador y, opcionalmente, pueden añadir una etiqueta de texto al marcador. Consulta la página del módulo Collecting para obtener más información.

La función de mapas puede integrarse con el módulo [Importación CSV](csvimport.md), lo que permite añadir datos de geolocalización de forma masiva. Consulta la [sección de integración de Importación CSV más abajo](#csv-import-integration) para obtener más información.

## Requisitos
 
La mayor parte del módulo funciona con cualquier base de datos compatible con Omeka S. El bloque de página «Mapa por grupos» requiere MySQL 8.0.24 o superior, o MariaDB 11.7 o superior, para la función espacial `ST_COLLECT`. En versiones anteriores, el bloque indica este requisito al configurarlo, y no muestra nada en la página.

## Cómo utilizar los mapas

En las páginas públicas, los visitantes del sitio utilizan el ratón o el trackpad para navegar por el mapa: se desplazan hacia arriba o hacia abajo para acercar o alejar la imagen, y hacen clic y arrastran para desplazarse por el mapa. El desplazamiento mediante la rueda del ratón es una opción que se puede activar o desactivar en los bloques de página de mapas. (No se puede configurar para mapas de elementos o conjuntos de elementos.) Se puede hacer clic en los elementos del mapa (marcadores o formas) para ver más información, y estos pueden proporcionar enlaces a elementos. 

Al editar un mapa en la interfaz de administración, unos pequeños botones cuadrados blancos situados a la izquierda del mapa te permiten navegar y editar los elementos del mapa. Pasa el ratón por encima de los botones para ver las descripciones emergentes.

![Botones de navegación del mapa tal y como se describen a continuación](modulesfiles/Mapping_JustButtons.png)

* **Acercar**: El pequeño cuadrado blanco con un signo más negro. Cada clic acerca el mapa un nivel (entre 0 y 19).
* **Alejar el zoom**: El cuadrado con el signo menos negro. Cada clic aleja el zoom un nivel (entre 0 y 19).
* **Pantalla completa**: El cuadrado con cuatro esquinas. Visualiza este mapa ampliado para que ocupe toda la pantalla de tu dispositivo.
* **Dibujar una polilínea**: El cuadrado con una línea diagonal. Crea una línea con dos o más puntos para indicar una zona relevante en el mapa, como una calle.
* **Dibujar un polígono**: El cuadrado con una forma de cinco lados. Crea una forma con tres o más lados para indicar una zona relevante en el mapa, como un estado o una provincia. 
* **Dibujar un rectángulo**: El cuadrado con un cuadrado negro. Crea una forma con cuatro lados para indicar una zona relevante en el mapa. 
* **Dibujar un marcador**: el cuadrado con un marcador de burbuja negro. Al hacer clic en el botón, el puntero se convierte en un marcador azul. Vuelve a hacer clic en el mapa para colocar el marcador.
* **Editar elemento**: el cuadrado con un recuadro negro y el icono de un lápiz. Esta opción solo está disponible después de haber añadido un marcador o una figura. Haz clic en el botón y aparecerá un recuadro rosa alrededor de cada marcador. Haz clic en un marcador para moverlo. Vuelve a hacer clic para colocarlo. Utiliza los botones grises para «Guardar» o «Cancelar».
* **Función de eliminación**: El cuadrado con el icono de una papelera. Esta opción solo está disponible después de haber añadido un marcador o una forma. Haz clic en el icono para seleccionar un marcador. Haz clic en el marcador que quieras eliminar y desaparecerá. Utiliza los botones grises para «Guardar» o «Cancelar» estos cambios, o para «Borrar todos» los marcadores que hay actualmente en el mapa.
* **Introducir dirección**: El cuadrado con el icono de una lupa negra. Haz clic para introducir una dirección en la barra de búsqueda.
* **Establecer la vista actual como vista predeterminada**: El cuadrado con el símbolo de una diana o una cruz. El mapa puede tener un nivel de zoom predeterminado según la configuración del sitio, o un nivel de zoom que incluya todos los marcadores existentes, si procede. Haz clic para establecer la vista actual como vista predeterminada para este elemento.
* **Ir a la vista predeterminada actual**: El cuadrado con un recuadro negro alrededor de un punto. Esta opción solo está disponible una vez que hayas establecido una vista predeterminada. Haz clic para desplazar y ampliar el mapa hasta la vista seleccionada para este elemento.
* **Borrar la vista predeterminada**: El cuadrado con una «X» negra. Esta opción solo está disponible una vez que hayas establecido una vista predeterminada. Haz clic para borrar las preferencias de desplazamiento y zoom y volver a la vista global inicial.

### Búsqueda de datos cartográficos

Los elementos con metadatos cartográficos (es decir, con marcadores o formas en el mapa) se pueden buscar mediante los campos que el módulo «Mapping» añade a los formularios de búsqueda avanzada. Los campos públicos son opcionales (desactivados por defecto) en [sitios individuales](../sites/site_settings.md#) en su [configuración del sitio](#site-wide-settings). Los campos del panel de administración se activan automáticamente cuando el módulo está activo. 

![Búsqueda basada en mapas en el panel de administración,.](modulesfiles/Mapping_advSearch.png)

La opción «Añadir ubicación geográfica a la búsqueda avanzada» añadirá los dos campos que se ven arriba. Los usuarios pueden:

- buscar todos los elementos, tanto si tienen datos cartográficos («elementos», es decir, marcadores y formas) como si no
- realizar búsquedas por ubicación: deben indicar una dirección, así como una distancia (en números) y una unidad (kilómetros o millas) dentro de la cual realizar la búsqueda.

## Geolocalizar elementos

El módulo de mapas añade campos de metadatos a cada elemento, a la mayoría de los cuales no se puede acceder directamente como se hace con un campo de texto. Esto incluye un par de coordenadas de latitud y longitud que crea marcadores en los mapas (un elemento puede tener más de un marcador), o una serie de coordenadas que definen formas en el mapa (líneas, polígonos y rectángulos). También hay ajustes de visualización predeterminados para el mapa de cada elemento: coordenadas mínimas de las esquinas que garantizan que el mapa contenga, como mínimo, esos puntos superior, inferior, izquierdo y derecho. 

Esta información se puede configurar manualmente mediante la pestaña «Mapeo» del elemento a través de una interfaz visual de mapas, o se puede añadir de forma masiva a los elementos mediante un archivo de texto utilizando la [importación CSV](#csv-import-integration).

### Añadir ubicaciones

La pantalla de visualización del elemento no mostrará la pestaña «Mapeo» a menos que ya existan metadatos de geolocalización, pero aparecerá al editar el elemento. Para añadir un mapa a un elemento, entra en el modo de edición y ve a la pestaña «Mapeo».

![La página de edición del elemento con la pestaña «Mapeo» seleccionada.](modulesfiles/Mapping_Item_Add.png)

Para desplazar el mapa hasta el lugar donde desees añadir una ubicación, puedes realizar una de las siguientes acciones:

* Amplía la imagen y arrastra el cursor para encontrar la ubicación.
* Introduce las coordenadas de latitud y longitud en el cuadro de búsqueda. Deben estar en formato decimal; por ejemplo, `38.897222, -77,064167`, no `38° 53′ 50″ N, 77° 3′ 51″ O`.
* Escribe el nombre del lugar en el cuadro de búsqueda (véase la imagen siguiente).
  * Las opciones aparecerán a medida que escribas, y no se buscarán ubicaciones que no se ajusten al formato de la función de búsqueda.

![Pestaña «Mapeo» con una búsqueda de «Roosevelt Island» en la vista de búsqueda. Debajo del campo de búsqueda aparecen varias ubicaciones sugeridas.](modulesfiles/Mapping_itemSearch.png)

Cuando hayas centrado el mapa en la ubicación deseada, podrás:

* Utilizar la herramienta de línea para trazar una línea a través del mapa. Esto puede servir, por ejemplo, para situar un elemento a lo largo de una frontera o una calle. Una línea tiene un punto de inicio y otro de fin, y tantos puntos o ángulos como se desee, pero no puede conectarse para formar una figura. 
* Utilizar la herramienta de polígono o rectángulo para definir una forma en el mapa. Esto puede servir, por ejemplo, para delimitar una zona aproximada de interés (como una ciudad o un país) o indicar un rango potencial de ubicaciones (por ejemplo, cuando se desconoce la ubicación exacta de una foto). 
* Haz clic en la herramienta de marcador; el cursor se convertirá en un marcador. Para fijar el punto, haz clic en el mapa.

A lo largo del resto de esta documentación, nos referiremos a estos diversos marcadores y formas como «elementos».

![Pestaña «Mapeo» con un marcador activo que se está dibujando. El marcador tiene una descripción emergente que dice «haz clic en el mapa para colocar el marcador»](modulesfiles/Mapping_drawMarker.png)

#### Editar elementos

Ahora puedes hacer clic en el marcador o en la forma para añadir una etiqueta que se mostrará en las [vistas públicas del mapa](#public-view) del elemento. Ten en cuenta que se mostrará con una fuente grande.

![Primer plano del mapa con un marcador seleccionado. Hay un campo para introducir la etiqueta del marcador.](modulesfiles/Mapping_addLabel.png)

También puedes añadir una imagen que se mostrará en el elemento al hacer clic en él en la [vista pública](#public-view). Solo puedes seleccionar imágenes que ya se hayan [adjuntado al elemento como archivo multimedia](../content/items.md#media). Para eliminar la imagen, selecciona «Sin imagen» en la barra lateral.

![Marcador seleccionado con imagen añadida. El archivo multimedia también es visible en la barra lateral, junto con la opción «Sin imagen»](modulesfiles/Mapping_addImage.png)

Ninguno de los dos campos es obligatorio, pero si eliges una imagen sin introducir una etiqueta, el título del archivo multimedia aparecerá en el campo de la etiqueta. Esto se puede eliminar. 

Para volver a editar la etiqueta o la imagen, haz clic en el elemento. Se abrirán las opciones para la etiqueta y la imagen, tal y como se ve arriba.

Para **mover un marcador o una forma**, utiliza el botón «Editar elemento» de la barra de herramientas de la izquierda (un pequeño cuadrado blanco con un recuadro negro y el icono de un lápiz). Cualquier elemento del mapa quedará resaltado con un contorno rojo de línea punteada. Haz clic y arrastra el elemento que quieras mover. Los rectángulos se pueden convertir en polígonos con esta herramienta, y los puntos individuales de las líneas y los polígonos se pueden eliminar haciendo clic en ellos sin arrastrar (un polígono requiere un mínimo de tres puntos). 

Para aplicar los cambios, haz clic en la opción «Guardar» que aparece al pulsar el botón «Editar elemento». Si no guardas los cambios, el marcador no se moverá.

![Movimiento de un marcador](modulesfiles/Mapping_moveMarker.png)

Para **eliminar un marcador**, primero haz clic en el botón «Eliminar elemento» de la barra de herramientas de la izquierda (icono de la papelera). Haz clic en el marcador o la forma que quieras eliminar; esto eliminará el elemento del mapa. Para que la eliminación sea definitiva, debes hacer clic en «Guardar» en el pequeño menú que se abre al pulsar el botón «Eliminar elemento».

Ten en cuenta que puedes utilizar el botón «Borrar todo» del menú que se abre al pulsar el botón «Eliminar elemento» para borrar todos los marcadores y formas del mapa.

![Marcador siendo eliminado.](modulesfiles/Mapping_deleteMarker.png)

#### Visualización del mapa

Puedes ajustar el nivel de zoom y el centro de cualquier mapa. Por defecto, el mapa se centra en un elemento y se amplía al máximo, o (si hay varios marcadores en el mapa) se aleja lo suficiente como para que todos los elementos quepan en la vista del mapa.

* **Establecer la vista actual como vista predeterminada**: el cuadrado con el símbolo de una diana o una cruz. El mapa mostrará por defecto una vista alejada (global). Haz clic para establecer la vista actual como vista predeterminada para este elemento.
* **Ir a la vista predeterminada actual**: El cuadrado con un recuadro negro alrededor de un punto. Esta opción solo está disponible después de haber establecido una vista predeterminada. Haz clic para desplazar y ampliar el mapa hasta la vista seleccionada para este elemento.
* **Borrar la vista predeterminada**: El cuadrado con una «X» negra. Esta opción solo está disponible una vez que hayas establecido una vista predeterminada. Haz clic para borrar las preferencias de desplazamiento y zoom y volver a la vista global inicial.

#### Edición por lotes de datos del mapa

Los usuarios pueden seleccionar varios elementos y realizar una [edición por lotes](../content/items.md#batch-editing) para crear y editar marcadores del mapa. Por el momento, no es posible añadir formas de forma masiva ni editar de forma masiva la configuración de visualización del mapa, pero sí se pueden añadir marcadores de forma masiva a partir de valores de latitud y longitud, así como editar de forma masiva las etiquetas e imágenes de todos los elementos. 

Las opciones son:

- **Eliminar elementos**: puedes eliminar de forma masiva todos los marcadores y formas existentes de varios elementos. 
- **Copiar coordenadas a los marcadores**: esto te permite tomar los datos de latitud y longitud de un valor de metadatos existente en cada elemento o de sus archivos multimedia asociados. Esto añadirá nuevos marcadores, sin sobrescribir ninguno de los ya existentes. Si hay varios valores en un elemento dentro de la propiedad seleccionada, se copiarán todos de forma masiva como múltiples marcadores. Puedes especificar:
  - Qué campos contienen cada uno de los valores o ambos (por ejemplo, si previamente introdujiste esta información en un campo de texto como `dcterms:spatial`)
  - Cómo están separados (la operación ignorará los espacios)
  - Si la longitud o la latitud va primero en el par. 
Si copias coordenadas desde un archivo multimedia adjunto, también puedes marcar una casilla para asignar el archivo como imagen del marcador. 
- **Actualizar características**: Los marcadores y las formas pueden tener [miniaturas y etiquetas personalizadas](#edit-features) en lugar de mostrar únicamente el título del elemento como enlace. Puedes editar de forma masiva la personalización de los marcadores:
  - Eliminando imágenes
  - Utilizando el archivo multimedia principal de los elementos como imágenes
  - Copiando etiquetas de un valor de metadatos existente (ya sea del elemento, del contenido multimedia principal o del contenido multimedia ya asignado al marcador)
  - Eliminar etiquetas (la primera entrada del menú desplegable).

Ten en cuenta que las etiquetas de los marcadores tienen un límite de 255 caracteres. Las etiquetas aparecerán truncadas si se copia texto de un campo que contenga valores de más de 255 caracteres.

Si el campo seleccionado en esta operación por lotes no contiene entradas válidas, los elementos se omitirán y no aparecerá ningún mensaje de error. [Las operaciones de edición por lotes](../content/items.md#batch-editing) no aparecen en el registro de tareas a menos que se trate de «Editar todo», por lo que, si has realizado una edición por lotes de elementos seleccionados, es posible que no puedas rastrear qué elementos se han modificado.

![El campo de edición por lotes específico para mapas, con algunas selecciones realizadas para mostrar los campos disponibles.](modulesfiles/Mapping_batchEdit.png)

Quizá te interese copiar tus coordenadas en una operación por lotes y, a continuación, actualizar esos marcadores con etiquetas e imágenes en una segunda operación por lotes. Ten en cuenta que, si un elemento tiene varios marcadores, todos ellos se actualizarán con imágenes y etiquetas idénticas. 

### Configuración global

Se pueden establecer ajustes predeterminados para todos los mapas de añadir/editar elementos de la instalación, con el fin de agilizar el trabajo de geolocalización. Los usuarios que hayan iniciado sesión pueden anular estos ajustes para sus propias tareas de mapeo. Estos ajustes solo surtirán efecto en el **panel de administración**. 

En «Admin», en la barra de la izquierda del panel de control administrativo, haz clic en «Configuración» y, a continuación, desplázate hacia abajo hasta la sección «Mapeo». 

![La sección «Mapeo» de la pestaña de configuración general de la instalación.](modulesfiles/Mapping_globalSettings.png)

En esta sección puedes configurar: 

- **Proveedor del mapa base**: Selecciona un mapa base en el menú desplegable para que se muestre al editar mapas de elementos en el **panel de administración**. Para ayudar a los visitantes con baja visión, considera utilizar **Esri.NatGeoWorldMap** u **OpenTopoMap**, que ofrecen un mayor contraste entre los elementos del mapa.
  - Algunos de los mapas requieren una clave de usuario o un token. 
!!! Nota
	Para utilizar mapas base de Stamen en cualquier mapa (público o administrativo) de la instalación, debes registrar tu dominio (no una URL de sitio específica) en su página web; no es necesario introducir ningún tipo de clave de acceso en tu(s) instalación(es) de Omeka para que funcionen. Si no te registras en Stamen, esos mapas mostrarán el valor predeterminado «OpenStreetMap.Mapnik».
- **Clave API de Carto**: Para utilizar mapas base de Carto en cualquier mapa (público o administrativo) de la instalación, necesitas una clave API. Introduce una clave de Carto ya existente o ve al enlace que aparece en la interfaz y solicita una clave de acceso para utilizar mapas base de Carto. Si seleccionas un mapa base de Carto en cualquier configuración de mapa, pero no tienes una clave API válida en este campo, esos mapas mostrarán el valor predeterminado «OpenStreetMap.Mapnik» por defecto.
- **Token de acceso de Mapbox**: Para utilizar mapas base de Mapbox en cualquier mapa (público o administrativo) de la instalación, necesitas una clave API. Introduce un token de Mapbox ya existente o accede al enlace que aparece en la interfaz y solicita una clave de acceso para utilizar mapas base de Mapbox. Si seleccionas un mapa base de Mapbox en cualquier configuración de mapa, pero no dispone de un token de acceso válido en este campo, dichos mapas mostrarán por defecto «OpenStreetMap.Mapnik». 
- **Nivel de zoom mínimo**: Establece un nivel de zoom mínimo para todos los mapas de elementos cuando se cargan por primera vez.  
- **Nivel de zoom máximo**: Establece un nivel de zoom máximo para todos los mapas de elementos cuando se cargan por primera vez.
- **Límites predeterminados**: Establece un área que siempre debe mostrarse en los mapas de elementos al cargarse por primera vez. Las coordenadas de las cuatro esquinas establecidas en este mapa se incluirán en cualquier mapa, mostrándose el exceso si las dimensiones del mapa así lo requieren. Esta configuración solo se aplicará a los nuevos mapas de elementos, es decir, a los elementos que no tengan datos cartográficos. 

### Configuración del usuario

Un usuario que haya iniciado sesión puede personalizar su propia configuración del mapa para agilizar el trabajo de geolocalización. Esta configuración solo surtirá efecto en el **área de administración**. Estos ajustes se pueden modificar o eliminar en cualquier momento, a medida que el usuario va trabajando con los elementos. 

Desde el enlace «Usuarios» de la barra lateral izquierda, utiliza la tabla de cuentas de usuario para editar un usuario. En la parte superior de la pantalla, selecciona la pestaña «Configuración del usuario». 

![La pestaña «Configuración del usuario» desplazada hacia abajo hasta la subsección «Cartografía».](modulesfiles/Mapping_user.png)

La subsección «Cartografía», añadida a la pestaña «Configuración del usuario», ofrece opciones para lo siguiente:

- **Proveedor de mapas base**: selecciona un mapa base en el menú desplegable para que se muestre al editar los mapas de los elementos en el panel de administración. Consulta la información anterior sobre proveedores de mapas base específicos y requisitos. Los usuarios de nivel inferior necesitarán la ayuda de un administrador global para introducir las claves de acceso a servicios específicos. 
- **Nivel de zoom mínimo**: Establece un nivel de zoom mínimo para todos los mapas de elementos cuando se carguen por primera vez.  
- **Nivel de zoom máximo**: Establece un nivel de zoom máximo para todos los mapas de elementos al cargarse por primera vez.
- **Límites predeterminados**: Establece un área que siempre debe mostrarse en los mapas de elementos al cargarse por primera vez. Las coordenadas de las cuatro esquinas establecidas en este mapa se incluirán dentro de cualquier mapa, mostrándose el exceso si las dimensiones del mapa así lo requieren. Esta configuración solo se aplicará a los nuevos mapas de elementos, es decir, a los elementos que no tengan datos cartográficos. 

### Integración con la importación CSV

La asignación es compatible con la [importación CSV](csvimport.md) al importar elementos (pero no al importar recursos mixtos).

Si ambos módulos están habilitados, el proceso de importación CSV contará con un nuevo menú desplegable «Asignación» en la barra lateral «Añadir asignación» cuando conectes una columna de la hoja de cálculo a una propiedad.

El menú desplegable «Asignación» incluye tres opciones para ubicar geográficamente el elemento: «Latitud», «Longitud» y «Latitud/Longitud». Asegúrate de que los valores de «Latitud/Longitud» estén separados por una barra (`/`). 

Todos estos valores deben introducirse como números, no en grados: escribe las latitudes del norte como números positivos y las del sur como números negativos (de «-90» a «90»); las longitudes del este como números positivos y las del oeste como números negativos (de «-180» a «180»).

!!! Nota 
  Los campos de latitud y longitud no admiten valores múltiples; es decir, no puedes importar de forma masiva dos o más marcadores para cada elemento utilizando estos campos. Tampoco puedes importar varias latitudes y longitudes utilizando el método «Añadir» en la importación CSV para importar varias filas de datos en el mismo elemento. Puedes añadir varios valores utilizando el campo «Latitud/Longitud». Este campo admite entradas en el formato `lat/long;lat/long`, donde el punto y coma es el separador de valores múltiples que se indica en la configuración de la importación CSV.

La opción «Límites predeterminados (sw_lng,sw_lat,ne_lng,ne_lat)» te permite establecer cuatro coordenadas de esquina para el mapa que se muestra para ese elemento, en el formato `sw_lng,sw_lat,ne_lng,ne_lat` (longitud inferior izquierda, latitud inferior izquierda, longitud superior derecha, latitud superior derecha). La anchura y la altura del mapa se muestran de forma dinámica en función de la página y la ventana del navegador, por lo que las cuatro coordenadas quedarán centradas dentro del mapa y el espacio sobrante se mostrará vertical u horizontalmente, según corresponda. **Asegúrate de indicar primero las longitudes y después las latitudes en los valores de los límites.**

!!! Nota
	El campo de límites predeterminados no admite varios valores. Se producirá un error en todo el proceso de importación de CSV si intentas añadir un segundo valor de límites predeterminados a un elemento. En este momento, también se producirá un error en todo el proceso si intentas modificar o actualizar un valor de límites predeterminados ya existente en un elemento; el mensaje de error no especificará qué filas se han procesado correctamente, pero el registro identificará el elemento en el que se detuvo el proceso mediante su ID único. Debes borrar manualmente los límites predeterminados de cada elemento por separado si deseas modificar esa configuración. Las propiedades de mapeo no aparecen en las opciones de edición masiva.

Por ejemplo, para fijar un elemento cerca de Madrid y establecer los límites del mapa en torno al país de España, podría proporcionar dos valores: una latitud y longitud del marcador de «40.79864618/-3.645817429» y unos límites predeterminados de «4.25300,43.95470,-12.12392,36.45605». 

Ten en cuenta que los límites predeterminados ignorarán cualquier marcador de ubicación. Por ejemplo, si estableces los límites en torno a España, pero el marcador de tu elemento está situado en la Antártida, el mapa mostrará España y los usuarios tendrán que buscar el marcador manualmente.

No es posible establecer etiquetas ni imágenes para los marcadores en la importación CSV. Tampoco es posible importar las coordenadas de las formas del mapa en la importación CSV. 

No es posible [editar por lotes](../content/items.md#batch-editing) los valores de asignación una vez que los elementos están en el sistema; solo se pueden editar manualmente uno por uno, o revisar por lotes los datos de asignación mediante la importación CSV.

## Añadir mapas a un sitio

### Configuración general del sitio

El módulo Mapping añade una sección a la pestaña «Configuración» de cada sitio, que se encuentra en «Administración del sitio». 

![La sección Mapping de la pestaña Configuración, tal y como se describe a continuación.](modulesfiles/Mapping_siteSettings.png)

- **Añadir la presencia de elementos a la búsqueda avanzada**: permite a los visitantes del sitio buscar en función de si un elemento tiene o no datos de ubicación. 
- **Añadir la ubicación geográfica a la búsqueda avanzada**: permite a los visitantes del sitio buscar con unas coordenadas específicas y un radio para incluir elementos cercanos. 
- **Desactivar la agrupación de elementos del mapa**: activa o desactiva la agrupación de elementos en los mapas de este sitio mediante una casilla de selección.
- **Proveedor del mapa base**: muestra el mismo mapa base para todos los mapas del sitio. Esto se puede anular mediante la configuración específica de cada mapa. 

### Página de exploración del mapa

![La página de exploración del mapa en el tema The Daily. Se muestra un mapa con un grupo y 5 marcadores individuales más, con los campos de búsqueda a continuación: «Buscar por ubicación geográfica» es una categoría, con los campos «Dirección», «Radio» y «Unidad».](modulesfiles/Mapping_mapBrowsePage.png)

Mapping crea una página de «Exploración de mapas» que se puede añadir a cada sitio web en su configuración de navegación. Este mapa tiene opciones de personalización mínimas y mostrará todos los elementos del sitio web que tengan una o más geolocalizaciones, así como algunos campos de búsqueda avanzada (incluida la búsqueda por dirección con un radio). Estos campos de búsqueda no se ven afectados por la configuración del sitio. El título de la página será «Mapa».

Ve a un sitio y, a continuación, ve a «Navegación». Verás, en «Añadir un enlace personalizado», la opción para añadir «Exploración del mapa». Cuando se añada a tu navegación, podrás cambiar la etiqueta que aparece en la navegación (por defecto es «Exploración del mapa») y el mapa base, haciendo clic en el icono del lápiz para editar la configuración de la página «Exploración del mapa». Ten en cuenta que, al cambiar el mapa base, se modificará la URL que se añade a la navegación: por ejemplo, `tusitio/map-browse?mapping_basemap_provider=OpenTopoMap`. 

### Bloques de la página de recursos

#### Elementos

[Los bloques de la página de recursos se pueden configurar en cada sitio](../sites/site_theme.md#select-regions-and-blocks) en función del tema que utilice tu sitio. Algunos sitios ofrecen varias regiones en las que se pueden colocar bloques. Los mapas no se añaden automáticamente a las páginas de elementos cuando el módulo está activo; debes mover manualmente el bloque «Mapping» a la ubicación deseada. 

#### Conjuntos de elementos

Los conjuntos de elementos no pueden geolocalizarse por sí mismos (anclados a un mapa), pero mostrarán mapas con los datos de geolocalización de todos sus elementos. Esto aparece en el panel de administración como una pestaña «Mapeo» en el conjunto de elementos, al igual que en los elementos individuales. Esta pestaña tiene fines meramente informativos, no se puede editar y desaparecerá cuando se acceda al modo de edición. 

En la parte pública, los conjuntos de elementos no mostrarán un mapa automáticamente. Debes [añadir manualmente el bloque de página de recursos «Mapping» a una región](../sites/site_theme.md#select-regions-and-blocks) que ofrezca el tema de tu sitio, para cada uno de los sitios que tengas. 

Las páginas de conjuntos de elementos, si añades el bloque de recursos «Mapping» a una región, mostrarán un mapa con todas las características de todos los elementos de ese conjunto. Este bloque de recursos de mapa no tiene configuración propia, pero puede modificarse mediante la [configuración general del sitio](#site-wide-settings).

### Bloques de página

Mapping crea tres bloques de página que puedes añadir a las páginas de tu sitio: 

- «Mapa por archivos adjuntos», donde añades manualmente recursos al bloque de mapa
- «Mapa por consulta», que te permite utilizar parámetros de búsqueda para añadir recursos al bloque de mapa
- «Mapa por grupos», donde puedes mostrar un único elemento del mapa (un marcador con punto central o una forma que lo contenga) para representar categorías de elementos, como los agrupados por sus clases.

Para añadir un mapa a una página, entra en el modo de edición de la página. A la derecha, en «Añadir nuevo bloque», haz clic en el bloque «Mapa por archivos adjuntos», «Mapa por consulta» o «Mapa por grupos». Al seleccionar uno de ellos, se añadirá el bloque de mapa al final de la página. Los bloques incluyen funciones personalizables para el mapa en paneles que se pueden contraer. Haz clic en los triángulos para expandir o contraer estos campos.

![Pantalla de edición de la página con los tres bloques de mapa añadidos: «Mapa por consulta», «Mapa por archivos adjuntos» y «Mapa por grupos». El bloque incluye las opciones de menú «Vista predeterminada», «Superposiciones» y «Archivos adjuntos».](modulesfiles/Mapping_Page_MapBlock1.png)

Los bloques «Mapa por archivos adjuntos» y «Mapa por consulta» tienen prácticamente la misma configuración, salvo por el método para añadir elementos al mapa. 

El bloque «Mapa por grupos» no dispone de opciones de línea de tiempo ni de superposiciones.

#### Vista predeterminada

Esta sección te permite configurar el aspecto y el nivel de zoom del mapa. Hay tres campos y un mapa de vista previa. Dentro del mapa de vista previa hay botones para configurar el zoom y la ubicación predeterminados del mapa. Si no se establece un zoom o una ubicación predeterminados, el mapa mostrará todos los recursos cuando se cargue por primera vez en la página pública.

![Bloque «Mapa por archivos adjuntos» abierto en la sección «Vista predeterminada». El mapa base es «Esri.WorldTopoMap», y los niveles de zoom son 3 y 17, respectivamente. El zoom con la rueda de desplazamiento está configurado en «Desactivado hasta que se haga clic en el mapa».](modulesfiles/Mapping_BlockDefaultView1.png)

**Proveedor del mapa base**: Selecciona uno de los mapas base del menú desplegable. Una vez seleccionado, el mapa de vista previa te mostrará el aspecto de ese mapa. El valor por defecto es «OpenStreetMap.Mapnik», o el mapa base de la configuración del sitio, si se ha elegido alguno. Estos proveedores externos se ofrecen «tal cual»; no hay garantía de servicio ni de velocidad. 

!!! Nota
  Algunos mapas no disponen de mosaicos a un nivel de zoom elevado; asegúrate de probar el mapa base elegido en las páginas de artículos, las páginas de conjuntos de artículos, la página de exploración de mapas y los bloques de página para asegurarte de que se adapta a tus necesidades. 

**Nivel de zoom mínimo**: Establece el zoom mínimo del mapa. El zoom mínimo (0) es el nivel más amplio. Consulta el mapa de vista previa que aparece a continuación para visualizar cada nivel de zoom y probar tu configuración y el mapa base.

**Nivel de zoom máximo**: Establece el nivel de zoom máximo posible. El máximo es 19. Algunos mapas base no funcionan a niveles superiores; asegúrate de establecer el máximo en un nivel en el que tu mapa base sea visible. Consulta el mapa de vista previa que aparece a continuación para visualizar cada nivel de zoom y comprobar tu configuración y tu mapa base.

**Zoom con la rueda del ratón**: Establece si los usuarios pueden hacer zoom con la rueda del ratón al pasar el cursor por encima del mapa, ya sea automáticamente al cargar la página o tras hacer clic dentro del mapa. Puedes desactivar por completo el desplazamiento con la rueda del ratón.

El mapa de vista previa de esta página de edición te permite establecer visualmente una vista predeterminada para este mapa. Es posible que las dimensiones del mapa en la página pública no coincidan con las que se muestran en esta vista previa, pero guardar aquí una vista predeterminada garantizará que los cuatro puntos de las esquinas se muestren en la página pública, añadiendo el exceso a los bordes exteriores si procede. 

Ten en cuenta que el texto situado encima del mapa de vista previa indica el nivel de zoom actual. 

Dentro del mapa de vista previa hay seis botones:

 * **Acercar**: el cuadrado con el signo más negro. Cada clic acerca la imagen un nivel (entre 0 y 19).
 * **Alejar**: el cuadrado con el signo menos negro. Cada clic aleja el zoom un nivel (entre 0 y 19).
 * **Pantalla completa**: Amplía el mapa a pantalla completa para su edición.
 * **Establecer la vista actual como vista predeterminada**: El cuadrado con el símbolo de una diana o una cruz. El mapa mostrará por defecto una vista global, es decir, una vista que contiene todos los elementos cartográficos de todos los elementos. Haz clic para establecer la vista actual como vista predeterminada. 
 * **Ir a la vista predeterminada actual**: El cuadrado con un punto rodeado por un recuadro negro. Haz clic para visualizar la configuración actual.
 * **Borrar la vista predeterminada**: El cuadrado con una «X» negra. Haz clic para volver al centro y al nivel de zoom predeterminados iniciales.

Las dos últimas opciones solo están disponibles después de haber establecido una vista predeterminada. 

Debes guardar tu vista predeterminada utilizando los botones del mapa y, a continuación, guardar la página. 

#### Superposiciones

Puedes añadir información complementaria a tus mapas utilizando las opciones de Superposiciones. 

![Un pequeño mapa con una superposición visible, un mapa histórico de España. El menú de superposiciones está abierto en el mapa y muestra que hay cuatro superposiciones disponibles.](modulesfiles/Mapping_overlays.png)

Omeka ofrece tres formatos para añadir superposiciones personalizadas o datos ajenos a Omeka: 

- [Servicio de mapas web (WMS)](https://mapserver.org/ogc/wms_server.html){target=_blank}
- [Servicio de mosaicos de mapas web (WMTS)](https://www.ogc.org/standards/wmts/){target=_blank}
- [Anotación de georreferencia del Marco Internacional de Interoperabilidad de Imágenes (IIIF)](https://iiif.io/api/extension/georef/){target=_blank}
- [GeoJSON](https://geojson.org/){target=_blank}.

Las superposiciones de WMS, WMTS y las superposiciones IIIF aparecen como capas visuales opcionales que los visitantes del sitio pueden mostrar u ocultar. A menudo, las superposiciones solo cubren una parte del mapa mundial: por ejemplo, un mapa histórico del norte de África que se ha digitalizado y cartografiado con precisión mediante coordenadas. Puedes tener varias capas configuradas para que estén visibles por defecto, independientemente de si se superponen entre sí o no. 

Las superposiciones GeoJSON son conjuntos de datos que permiten añadir elementos al mapa. En lugar de mostrar elementos de tu colección de Omeka, esta opción permite mostrar información en un mapa mediante marcadores y formas generadas a partir de datos con formato [GeoJSON](https://en.wikipedia.org/wiki/GeoJSON){target=_blank}]. Puedes añadir marcadores interactivos complementarios a los mapas de tu sitio web mediante esta herramienta; los marcadores no están vinculados a elementos de Omeka, pero pueden utilizarse para añadir contexto, como edificios importantes. Puedes crear manualmente archivos GeoJSON para tu propio uso, o copiar GeoJSON de otras fuentes. Consulta más abajo para obtener más información sobre GeoJSON.

En primer lugar, puedes establecer si deseas que las superposiciones se muestren de forma exclusiva (una a la vez) o inclusiva (varias al mismo tiempo). A continuación, elige uno de los tres formatos para comenzar a introducir información.

##### WMS, WMTS e IIIF

Hay cuatro campos disponibles para las **superposiciones WMS**: 

 * **Etiqueta**: Crea una etiqueta única y descriptiva para la superposición del mapa. Será visible para los visitantes y debe utilizarse para diferenciar entre las distintas superposiciones. (Obligatorio.)
 * **URL base**: Añade una superposición de mapa al mapa WMS mediante una URL. 
 * **Capas**: Cualquiera de las capas ofrecidas que desees utilizar, separadas por comas. Se trata de una cadena o cadenas proporcionadas por el servidor WMS.
 * **Estilos**: Cualquier estilo que desee utilizar, separados por comas. Se trata de una cadena o cadenas proporcionadas por el servidor WMS.

Hay cinco campos disponibles para las **superposiciones WMTS**: similares a los de WMS, pero todos los campos solo admiten un valor:

 * **Etiqueta**: Crea una etiqueta única y descriptiva para la superposición del mapa. Será visible para los visitantes y debe utilizarse para diferenciar entre superposiciones. (Obligatorio.)
 * **URL base**: Añade una superposición al mapa WMTS mediante una URL. 
 * **Capa**: La capa ofrecida que deseas utilizar. Se trata de una cadena de caracteres proporcionada por el servidor WMTS.
 * **Estilo**: El estilo que deseas utilizar. Se trata de una cadena de caracteres proporcionada por el servidor WMTS.
 * **Conjunto de matriz de mosaicos**: Un código procedente del servicio de mapas que apunta a mosaicos en diferentes formatos. Es posible que tengas que consultar el XML proporcionado por el mapa WMTS para encontrar los valores `<TileMatrixSet>`. 

Para encontrar el nombre de la «Capa», es posible que tengas que consultar el XML: busca, por ejemplo, `<Layer><ows:Title>`. Ten en cuenta que, en el caso de las superposiciones WMTS, el valor de «Estilo» suele ser «predeterminado». 

Hay dos campos disponibles para las **superposiciones IIIF**:

 * **Etiqueta**: Crea una etiqueta única y descriptiva para la superposición del mapa. Esta será visible para los visitantes y debe utilizarse para diferenciar entre superposiciones. (Obligatorio.)
 * **URL**: Introduce la URL del manifiesto IIIF. Puede tener el formato `website.org/manifests/123456789`.

Haz clic en «Guardar superposición» para crear la superposición. Haz clic en «Cancelar» para borrar todos los campos. Se pueden añadir varias superposiciones. Asegúrate de guardar cada superposición tras editarla y, a continuación, guarda la página. 

![Un bloque de página «Mapa por consulta» con la sección «Superposiciones» abierta. Ya existen cuatro superposiciones y una de ellas (una superposición WMS) está abierta para su edición.](modulesfiles/Mapping_pageOverlays.png)

Una vez que hayas añadido una superposición, aparecerá encima de los campos para añadir más superposiciones. Si deseas que una o varias de las superposiciones se muestren automáticamente al cargar la página, marca la casilla situada junto a ellas. Ten en cuenta que algunas superposiciones pueden ser de gran tamaño y tardar en cargarse en una página pública. 

Edita una superposición existente haciendo clic en el botón de edición con el lápiz rojo, o haz clic el icono rojo de la papelera para eliminar la superposición. Recuerda hacer clic en «Guardar superposición» y, a continuación, guardar la página cada vez que realices cambios en esta configuración. 

##### Superposiciones GeoJSON

GeoJSON proporciona elementos cartográficos, así como información de metadatos sobre cada elemento. Puedes utilizarlo para ilustrar áreas, como los límites históricos de un municipio, o añadir coordenadas relacionadas con el tema de tu sitio o página de Omeka. Puedes mostrar cualquier número de elementos cartográficos, de todo tipo (punto, línea y polígono). También puedes tener un conjunto de metadatos que haga referencia a varias áreas discretas del mapa: por ejemplo, mostrar el territorio continental de Estados Unidos, Alaska y Hawái como un único punto de datos con tres elementos poligonales independientes. Los elementos GeoJSON tienen el mismo aspecto que los elementos de los artículos de Omeka. 

![La interfaz de administración de una página en proceso de edición, en la que se muestra la sección «GeoJSON» rellenada con información.](modulesfiles/Mapping_geojsonAdmin.png)

Hay cinco campos disponibles para las superposiciones GeoJSON:

* **Etiqueta**: Crea una etiqueta única y descriptiva para la superposición del mapa. Esta será visible para los visitantes y debe utilizarse para diferenciar entre superposiciones. (Obligatorio.)
- **GeoJSON**: Introduce los datos GeoJSON completos. Deberían tener un aspecto similar al [ejemplo que se muestra a continuación](https://geojson.org/){target=_blank}:

```
{
  "type": "Feature",
  "geometry": {
    "type": "Point",
    "coordinates": [125.6, 10.1]
  },
  "properties": {
    "name": "Islas Dinagat"
  }
}
```
Al examinar estos datos para encontrar las propiedades disponibles (como «name» en el ejemplo anterior), puedes rellenar los campos «label» y «comment» si así lo deseas. 

* **Clave de la propiedad «label»**: Las ventanas emergentes del mapa pueden contener todos los metadatos que hayas pegado, o bien pueden mostrar un campo como etiqueta y otro como comentario (estos campos en los marcadores de elementos de Omeka suelen ser los de «título» y «descripción»). Si deseas que cada elemento del mapa muestre un valor como título emergente, introduce aquí el nombre de la propiedad. Consulta el código que has pegado en el campo «GeoJSON» para obtener esta información. Ten en cuenta que esto no incluirá el nombre de la propiedad junto al valor.
* **Clave de la propiedad «Comentario»**: Si deseas que un valor aparezca como texto emergente de cada elemento del mapa, introduce aquí el nombre de la propiedad. Busca esta información en el código que has pegado en el campo «GeoJSON». Ten en cuenta que esto no incluirá el nombre de la propiedad junto al valor.
* **¿Mostrar la lista de propiedades GeoJSON?**: Marca esta casilla si deseas que las ventanas emergentes muestren todos los metadatos disponibles que has pegado en el campo anterior. Si no la marcas, las ventanas emergentes solo mostrarán los campos de etiqueta o comentario que hayas elegido; dependiendo de la cantidad de información que hayas incluido, las ventanas emergentes pueden resultar bastante largas y ser necesario desplazarse por ellas. Ten en cuenta que esto replicará cualquier información que hayas introducido en los campos de etiqueta y comentario; si marcas esta casilla, quizá te convenga dejar esos campos en blanco.

Esta es una ventana emergente de mapa geoJSON con la etiqueta y el comentario seleccionados:
![El mapa público con la configuración que se muestra en la captura de pantalla anterior. La ventana emergente de un marcador del mapa muestra el título «Rishworth Sports Club» y el texto «Squash».](modulesfiles/Mapping_geojsonPublic1.png)

Y esta es una ventana emergente de mapa GeoJSON en la que se muestran todas las propiedades disponibles, sin ninguna etiqueta ni comentario seleccionados:
![El mapa público con la configuración de la captura de pantalla anterior, salvo que la casilla «¿Mostrar la lista de propiedades GeoJSON?» está marcada. La ventana emergente del marcador del mapa no muestra ningún título, sino una ubicación, una actividad deportiva, la latitud y la longitud. El texto reza «Proveedor de actividades del club: Cragg Vale Tennis Club», etc.](modulesfiles/Mapping_geojsonPublic2.png)

La interfaz de administración no mostrará una vista previa del mapa con tus datos GeoJSON ni antes ni después de guardar la superposición. Tendrás que ir a la vista pública de la página para ver los elementos resultantes de tu entrada.

Ten en cuenta que los datos GeoJSON no estarán disponibles en la línea de tiempo como fechas; si tu mapa incluye una línea de tiempo, los elementos añadidos mediante GeoJSON aparecerán en el mapa predeterminado, pero no se podrán visualizar cuando se utilice la línea de tiempo para la navegación.

Haz clic en «Guardar superposición» para crear la superposición. Haz clic en «Cancelar» para borrar todos los campos. Se pueden añadir varias superposiciones. Asegúrate de guardar cada modificación de la superposición y, a continuación, guarda la página. 

#### Línea de tiempo

La sección «Línea de tiempo» te permite añadir una visualización de línea de tiempo junto a la vista del mapa. Esta función requiere el módulo [Tipos de datos numéricos](numericdatatypes.md) y elementos con valores de marca de tiempo o intervalo (aplicados a través de la [plantilla de recursos](../content/resource-template.md)). El código y los temas de la línea temporal proceden de [TimelineJS](https://timeline.knightlab.com/){target=_blank}.

- **Título principal**: se muestra en la primera diapositiva de la línea temporal (véase [«Vista pública de la línea temporal»](#timeline-public-view) más abajo). Puedes utilizarlo para dar un nombre a la línea temporal.
- **Texto del título**: aparece debajo del título principal en la primera diapositiva de la línea temporal (véase [«Vista pública de la línea temporal»](#timeline-public-view) más abajo). Puedes utilizarlo para proporcionar contexto o una introducción narrativa a la línea temporal.
- **Ir a**: es un menú desplegable en el que puedes establecer el nivel de zoom para cada punto de la línea temporal en el mapa. Las opciones disponibles son la vista predeterminada o los niveles de zoom del 0 al 18 (solo números pares). Cuanto mayor sea el número, más ampliado aparecerá el mapa.
  - Ten en cuenta que la transición entre puntos es animada, por lo que, si tienes puntos muy distantes entre sí, el cambio entre ellos implicará un zoom out y un zoom in significativos.
- **Mostrar eventos contemporáneos**: establece cómo se muestran dos eventos con la misma marca de tiempo o intervalo. Si se marca esta opción, los eventos contemporáneos se mostrarán ambos en el mapa cuando estén activos en el control deslizante de la historia.
	- En el caso de las propiedades de marca de tiempo, si dos eventos tienen la fecha «1 de enero de 2000», ambos aparecerán en el mapa cuando cualquiera de ellos se encuentre en el control deslizante de la historia.
  - En el caso de las propiedades de intervalo, si un evento tiene un intervalo de «28 de julio de 1914/11 de noviembre de 1918» y otro tiene un intervalo de «enero de 1819/diciembre de 1920», ambos eventos aparecerán en el mapa cuando cualquiera de ellos se encuentre en el control deslizante de la historia.
  - Ten en cuenta que esta configuración solo funciona cuando «Ir a» esté configurado en «Vista predeterminada».
- **Tema de la línea de tiempo**: un menú desplegable que ofrece esquemas de color para la línea de tiempo de [TimelineJS](https://timeline.knightlab.com/){target=_blank}. Las opciones son Predeterminado (el único tema disponible en versiones anteriores de la línea temporal), un tema oscuro y un tema de contraste con colores que cumplen con los estándares de accesibilidad. Ten en cuenta que estas selecciones activan un archivo CSS que se aplicará a todas las líneas de tiempo de una misma página; las diferentes líneas de tiempo de una misma página no pueden tener temas distintos. Consulta las imágenes de ejemplo que aparecen a continuación en la sección [Vista pública de la línea de tiempo](#timeline-public-view) de esta página.
- **Posición de navegación de la línea de tiempo**: por defecto, la línea temporal se muestra con el control deslizante de historias a la izquierda del mapa. Mediante este menú desplegable, puedes cambiar la ubicación del control deslizante de historias. Las opciones son:
  - Ancho completo, debajo del control deslizante de historias y del mapa
  - Ancho completo, encima del control deslizante de historias y del mapa.
- **Propiedad**: un menú desplegable; selecciona la propiedad de marca de tiempo o de intervalo que se utilizará al rellenar la línea de tiempo. El menú desplegable mostrará las propiedades que se hayan definido en un tipo de recurso como de tipo numérico «Intervalo» o «Marca de tiempo».
	- Es recomendable que anotes qué propiedad y qué tipo de datos numéricos vas a utilizar antes de crear el bloque de mapa. El menú desplegable solo muestra el término y el tipo de datos, pero no a qué plantilla está asociado; por ejemplo, `Fecha de creación (numérico:marca de tiempo)`.
  - Ten en cuenta que solo puedes seleccionar *una* propiedad por línea de tiempo. No puedes mezclar datos de marca de tiempo e intervalo.

![Bloque de mapeo con todas las opciones ocultas excepto «Línea de tiempo», que muestra las opciones tal y como se ha descrito](modulesfiles/Mapping_timelineBlock.png)

Para eliminar la línea de tiempo de un bloque de mapa, haz clic en la «X» situada en el extremo derecho del menú desplegable «Propiedad».

Para ver cómo se muestran los distintos ajustes del bloque de línea de tiempo en la vista pública, consulta la sección [Vista pública de la línea de tiempo](#timeline-public-view) más abajo.

#### Archivos adjuntos (bloque «Mapa por archivos adjuntos»)

Con este bloque, los marcadores se añaden al mapa seleccionando elementos manualmente.

* Haz clic en «Añadir archivo adjunto» (1) para abrir el panel lateral derecho y seleccionar elementos de la lista (2). Nota: Esta lista solo se rellenará con elementos a los que se les haya añadido al menos una ubicación.
* Al hacer clic en un elemento, este se añade a la lista de la sección «Archivos adjuntos» (3).
* Arrastra y suelta los elementos de esta lista para reordenarlos.
* Para eliminar elementos de la lista, haz clic en la papelera roja.

![Un mapa con la opción «Añadir archivo adjunto» seleccionada. A la derecha hay una lista de elementos.](modulesfiles/Mapping_pageAttachments.png)

Para añadir varios elementos a la vez, haz clic en el control deslizante «Añadir rápidamente» situado justo encima de la lista de elementos en el panel de la derecha. Esto añadirá una casilla de selección a la izquierda de cada elemento. Marca las casillas de los elementos que desees añadir al mapa y, a continuación, haz clic en el botón «Añadir los seleccionados» situado en la parte inferior del panel.

![Panel lateral con la opción de añadir en bloque activada](modulesfiles/Mapping_bulkAttachments.png)

#### Consulta (bloque «Mapa por consulta»)

Este bloque te permite seleccionar un subconjunto de los recursos añadidos a tu sitio mediante una consulta de búsqueda, en lugar de añadir elementos manualmente. 

La consulta puede dejarse en blanco; en ese caso, el mapa mostrará todos los elementos añadidos al sitio que cuenten con datos de mapeo válidos.

Se pueden configurar consultas más complejas: conjuntos de elementos específicos, clases, plantillas, elementos de un intervalo de fechas o elementos con un recurso vinculado específico (como un elemento «Persona» concreto en el campo «Creador»), por ejemplo. 

![El bloque «Mapa por consulta» mostrando una consulta para las clases «Imagen fija» e «Imagen», con la barra lateral abierta en la interfaz de edición de la consulta de búsqueda.](modulesfiles/Mapping_blockquerysidebar.png)

También puedes realizar una búsqueda en tu sitio público y, desde la página de resultados de búsqueda, copiar todo lo que aparece en la barra de direcciones de tu navegador, desde el signo de interrogación hasta el final de la URL de búsqueda (a la derecha). Por ejemplo:

```
?fulltext_search=london&resource_class_id[]=33&has_media=1&has_features=1
```

![La barra de direcciones y la parte superior de una página de resultados de búsqueda.](modulesfiles/sitepg_bpquery.png)

Haz clic en el botón «Edición avanzada» y pega la cadena de la URL en el campo que aparece. 

![Un bloque «Mapa por consulta» abierto en la sección «Consulta». Hay una consulta pegada en el campo.](modulesfiles/Mapping_blockQuery.png)

Deberías ver cómo la consulta se transforma en sentencias estructuradas al hacer clic en el botón «Aplicar».

![Un bloque «Mapa por consulta» abierto en la sección «Consulta». Se muestran varios parámetros de búsqueda.](modulesfiles/Mapping_blockQuery2.png)

Ten en cuenta que la interfaz de administración no mostrará una vista previa del mapa con los elementos seleccionados. Tendrás que ir a la vista pública de la página para ver los elementos resultantes de tu consulta.

#### Grupos (bloque «Mapa por grupos»)

El bloque de página «Mapa por grupos» clasifica tus elementos en los grupos que elijas. Un grupo se mostrará como un único marcador en el mapa (en el centro de todas las ubicaciones de todos sus elementos), o como un polígono (que contiene todas las ubicaciones de todos sus elementos). Los usuarios pueden hacer clic en los grupos para ver únicamente los elementos de ese grupo. También hay un menú desplegable en la esquina inferior izquierda donde los usuarios pueden seleccionar uno de los grupos. 

Este bloque de página ofrece formas habituales de explorar elementos: por clases, por conjuntos de elementos o por valores comunes en un campo determinado, como los recursos vinculados utilizados en el mismo campo. 

Este bloque no tiene ajustes de línea de tiempo ni de superposición: solo la sección «Vista predeterminada», como se ha indicado anteriormente, y una sección «Grupos». 

![Un bloque «Mapa por grupos» en una página pública, con el título «Mapa por grupos», en el que se muestran 3 marcadores. Uno de los marcadores tiene una ventana emergente que refleja el grupo «.](modulesfiles/Mapping_groupPublic1.png)

El mapa público, al verlo por primera vez, muestra un elemento por cada grupo. En la imagen anterior, se ha desplegado el menú desplegable para mostrar las opciones disponibles en este mapa. Se ha seleccionado un marcador y se muestra su ventana emergente, con la información de agrupación y un botón que dice «Ver todos los resultados».  

Al hacer clic en este botón, el mapa se actualizará para mostrar elementos de cada elemento del grupo. Puede haber agrupaciones, marcadores y formas. En la parte inferior del mapa se añade un botón «Volver a los grupos», junto a los parámetros de navegación actuales (incluido el grupo y cualquier filtro aplicado):

![Un bloque de mapa por grupos con el contenido del grupo visible. Ahora hay un botón «Volver a los grupos» en la esquina inferior izquierda del mapa.](modulesfiles/Mapping_groupPublic2.png)

La sección «Grupos» cuenta con dos campos iniciales:

- **Agrupar por**: Selecciona el tipo de grupo: 
	- Conjuntos de elementos
  - Clases de recursos
  - Valores de propiedad (es exactamente)
  - Valores de propiedad (contiene)
  - Valores de propiedad (es un elemento con ID)
  - Propiedades (tiene cualquier valor).
- **Tipo de elemento**: Selecciona el tipo de elemento que representará cada grupo:
	- Polígono: una forma con límites alrededor de los elementos más externos.
  - Punto: el punto central de todas las ubicaciones de los elementos del grupo.

Una vez que el usuario selecciona una opción de «Agrupar por», el formulario se ampliará con más campos, en función de la selección. 

También se ofrecen opciones de filtrado: cuando se elige una opción de agrupación (como agrupar elementos por su clase), se puede optar por filtrar los elementos en función de las demás selecciones (como incluir únicamente elementos de un conjunto de elementos concreto). Estos filtros solo permiten una selección. 

##### Agrupar por conjuntos de elementos

- Filtrar por clase de recurso: incluye únicamente los elementos asignados a la clase de recurso seleccionada.
- Conjuntos de elementos: selecciona los conjuntos de elementos que se mostrarán como grupos en el mapa. Recuerda que cada conjunto de elementos se mostrará como un polígono o un punto que representa la ubicación de todos sus elementos; ten en cuenta que los elementos pueden pertenecer a más de un conjunto de elementos. 

##### Agrupar por clases de recursos

- Filtrar por conjunto de elementos: solo se incluyen los elementos asignados al conjunto de elementos seleccionado.
- Clases de recursos: selecciona las clases que se mostrarán como grupos en el mapa. Recuerda que los elementos solo pueden tener una clase. 

##### Agrupar por valores de propiedad (es exactamente)

Esta opción puede resultar útil si utilizas vocabularios controlados, por ejemplo, para encabezamientos de materia. 

- Filtrar por conjunto de elementos.
- Filtrar por clase de recurso.
- Propiedad: selecciona la propiedad de los valores que deseas agrupar. Puede dejar este campo en blanco para crear grupos a partir de los valores de texto proporcionados en todas las propiedades. 
- Valores: Introduzca los valores de texto (coincidencia exacta) que se mostrarán como grupos en el mapa, separados por líneas nuevas. Con esta opción, un elemento puede pertenecer potencialmente a más de un grupo.

##### Agrupar por valores de propiedad (contiene)

Esta opción te ofrece más flexibilidad que la opción «es exactamente». Puede resultar útil para agrupar elementos con metadatos de ubicación textuales, como en el formato «Ciudad, Estado»: introduce el texto de cada Estado en una nueva línea para ver tus elementos agrupados por su estado. 

- Filtrar por conjunto de elementos.
- Filtrar por clase de recurso.
- Propiedad: selecciona la propiedad de los valores que se van a agrupar. Puedes dejar este campo en blanco para crear grupos a partir de los valores de texto proporcionados en todas las propiedades.
- Valores: introduce los valores de texto (que coincidan con cualquier parte) que se mostrarán como grupos en el mapa, separados por líneas nuevas. 

![Un bloque «Mapa por grupos» en el panel de administración, con la opción «Agrupar por valores de propiedad (contiene)» seleccionada. Se ha elegido «Tema de Dublin Core» y los valores de tema se han introducido en el cuadro de texto de abajo, uno por línea.](modulesfiles/Mapping_groupBlock.png)

##### Agrupar por valores de propiedad (es un elemento con ID)

Esta opción te permite agrupar elementos que tienen un recurso vinculado en común. Introduce el ID del recurso utilizado como valor de metadatos en las descripciones de varios elementos. Puedes elegir una propiedad específica, o bien optar por agrupar todos los elementos que hagan referencia al mismo recurso en cualquier propiedad. Esta función requerirá datos enlazados complejos en tu colección. 

- Filtrar por conjunto de elementos.
- Filtrar por clase de recurso.
- Propiedad: Selecciona la propiedad de los valores que deseas agrupar. Puedes dejar este campo en blanco.
- Valores: Introduce los ID de los recursos que se mostrarán como grupos en el mapa, uno por línea. Es decir, introduce el recurso vinculado utilizado como valor en los metadatos de otros elementos, como un conjunto de elementos utilizado en el campo «Creador» de varios elementos.

##### Agrupar por propiedades (que tengan cualquier valor)

- Filtrar por conjunto de elementos.
- Filtrar por clase de recurso.
- Propiedades: Selecciona las propiedades (que tengan cualquier valor) que se mostrarán como grupos en el mapa. Cada propiedad seleccionada se convertirá en un grupo. 

### Vista pública

Un bloque de mapa se mostrará en una página pública, en la vista de un elemento o en la vista de un conjunto de elementos, ocupando toda la página o el ancho del bloque, según la configuración de diseño de la página. Si ha definido ajustes en la [vista predeterminada](#default-view) del bloque de mapa, o ha establecido [límites de mapa predeterminados para el elemento](#map-display), se aplicarán estos. De lo contrario, el mapa se ampliará para que todos los elementos queden visibles.

Los usuarios pueden ampliar o reducir el mapa utilizando la función de desplazamiento de su ordenador o los botones de ampliar/reducir situados en la parte izquierda del mapa. Puedes configurar si los usuarios pueden utilizar la rueda del ratón para desplazarse dentro de los bloques de la página del mapa (excepto en los mapas de elementos o en la página «Explorar mapa»). 

![Bloque de mapa con tres marcadores individuales y dos círculos de agrupación verdes de dos marcadores cada uno. El mapa muestra una parte del sur de Inglaterra.](modulesfiles/Mapping_public.png)

Cada elemento se mostrará como uno o más marcadores o formas en el mapa. Los elementos que estén muy próximos entre sí pueden mostrarse como un círculo de agrupación, con un número que indica cuántos elementos comparten esa ubicación. A medida que se amplía la imagen, estas agrupaciones se separarán. Dependiendo del tamaño de una forma, es posible que las formas no se agrupen, salvo en niveles de zoom muy bajos, o que no se agrupen en absoluto. Al hacer clic en un marcador, se mostrará la etiqueta correspondiente a dicho marcador. 

Las páginas de conjuntos de elementos, si [añades el bloque de recursos «Mapping» a una región](../sites/site_theme.md#select-regions-and-blocks), mostrarán un mapa con todos los elementos de ese conjunto. Este bloque de recursos no tiene configuración propia, pero se puede modificar mediante la [configuración general del sitio](#site-wide-settings).

Si no has añadido una etiqueta o una imagen a los marcadores, simplemente mostrarán «Elemento: [Título]». 

!!! nota
  Ten en cuenta que los elementos del mapa deben mostrar los metadatos de idioma adecuados según la configuración de idioma del sitio: por ejemplo, si un sitio tiene configurado el idioma como «francés» y el elemento tiene un(`fr`), ese título debería mostrarse en lugar de uno con otra etiqueta de idioma o sin etiqueta alguna. Si tienes problemas para cargar el idioma correcto en proyectos multilingües, comprueba la configuración de tu sitio y las etiquetas de idioma en los campos de metadatos de los elementos. 

Si has añadido una etiqueta, se mostrará la etiqueta, así como un recurso multimedia representativo y un enlace a dicho recurso si el marcador lo tiene.

Marcador de asignación de elementos solo con etiqueta:

![Ventana emergente del marcador de elemento que muestra el texto «Agujero negro de Calcuta», con una línea debajo que indica «Elemento: Historia de Paul Jones, el pirata». como enlace al elemento.](modulesfiles/Mapping_publicLabel.png)

Marcador de asignación de elementos con etiqueta e imagen:

![Ventana emergente del marcador de elemento que muestra la misma información que la anterior, con una imagen en miniatura y, debajo de «Elemento:», otra línea que dice «Recurso: Ilustración en la portada de un velero en el mar», como enlace al recurso.](modulesfiles/Mapping_publicLabelImg.png)

Marcador de ubicación de un elemento sin etiqueta ni imagen:

![Ventana emergente del marcador que muestra únicamente «Elemento: Historia de Paul Jones, el pirata».](modulesfiles/Mapping_publicNoLabel2.png)

#### Vista pública de la línea de tiempo

Las líneas de tiempo solo pueden aparecer en bloques de página. La ficha de la línea de tiempo se mostrará a la izquierda del mapa, o encima del mapa en las vistas para móviles. La barra de la línea de tiempo en sí misma se puede configurar para que aparezca encima o debajo del mapa y de la ficha. Cada elemento aparece tanto en el mapa como en la línea de tiempo (lo que significa que solo se mostrarán los elementos que tengan tanto fechas numéricas como marcadores en el mapa). 

En un bloque de mapa con una línea de tiempo, el bloque se carga inicialmente con el mapa en la vista predeterminada o ampliado para mostrar todos los marcadores. La línea de tiempo mostrará el título y el texto, como se ve a continuación. Esta imagen también muestra la línea de tiempo con el tema «Oscuro» seleccionado en la configuración:

![Bloque de mapa con línea de tiempo, mostrando la primera diapositiva de la línea de tiempo. La línea de tiempo se encuentra encima del mapa.](modulesfiles/Mapping_timelinePublic2.png)

El visor de la línea de tiempo cuenta con botones de zoom para controlar el nivel de detalle de la barra de la línea de tiempo (acercar para ver año por año, alejar para ver décadas de una sola vez). Las flechas situadas debajo de ellos permiten saltar al último elemento, o a la diapositiva de título.

Al pasar el ratón por encima de la línea de tiempo, el cursor se convierte en una flecha de cuatro direcciones. Los usuarios pueden mantener pulsado y arrastrar hacia la izquierda y la derecha para desplazarse por la línea de tiempo. También pueden navegar entre los elementos utilizando las flechas derecha e izquierda de la ficha que muestra cada elemento.

Al hacer clic en un marcador, se mostrarán el título, la descripción, la fecha o el intervalo de ese elemento, así como la imagen adjunta. El área de información cuenta con una barra de desplazamiento para los contenidos más largos. El título es un enlace a la página de presentación del elemento.

![Bloque de mapa con línea de tiempo, en el que se muestra un elemento. La línea de tiempo se encuentra debajo del mapa.](modulesfiles/Mapping_timelinePublic1.png)

Cada vez que se seleccione un elemento, su marcador en la línea de tiempo aparecerá resaltado para indicar que está activo.

##### Visualización de intervalos

Las propiedades de intervalo (campos con el tipo de datos `numeric:interval`) se muestran como una barra larga que recorre horizontalmente la línea de tiempo, con extremos que llegan hasta la línea de tiempo en las fechas de inicio y fin del intervalo. Los intervalos que se solapan se apilarán. En la imagen siguiente, la línea de tiempo presenta el tema «Contraste» seleccionado en la configuración:

![Línea de tiempo y mapa que muestran dos elementos superpuestos en la barra de la línea de tiempo. La barra de la línea de tiempo se encuentra encima del mapa.](modulesfiles/Mapping_timelinePublic3.png)

##### Visualización de marcas de tiempo

Las propiedades de marca de tiempo (campos con el tipo de datos `numeric:timestamp`) se muestran como un indicador en la línea de tiempo, con una barra que las fija a la línea de tiempo. Los elementos que se solapan, ya sea por la fecha o por un texto extenso, se apilarán. En la imagen siguiente, la línea temporal utiliza el tema «Predeterminado»:

![Línea temporal de marcas de tiempo con muchos elementos mostrados muy próximos entre sí. La barra de la línea temporal se encuentra debajo del mapa.](modulesfiles/Mapping_timelinePublic4.png)

##### Posición de navegación de la línea de tiempo

El menú desplegable «Posición de navegación de la línea de tiempo» te ofrece la opción de elegir entre «ancho completo, debajo del control deslizante de la historia y del mapa» o «ancho completo, encima del control deslizante de la historia y del mapa».

En las imágenes anteriores, puedes ver ejemplos de la barra de la línea de tiempo mostrada encima del mapa y de la ficha del elemento, y debajo del mapa y de la ficha del elemento. 

##### Mostrar eventos contemporáneos

Cuando se marca la casilla «Mostrar eventos contemporáneos», el mapa se amplía para mostrar todos los eventos que tienen lugar el mismo día.

En la imagen siguiente, la línea de tiempo utiliza datos por intervalos. El elemento «Cobertizo del jardín del Smithsonian» está resaltado y muestra un marcador en el mapa. El elemento «Estatua de la Libertad», que se superpone cronológicamente al primer elemento de la línea de tiempo, también muestra un marcador en el mapa. 

![imagen según la descripción](modulesfiles/Mapping_timelinePublic3.png)

## Solución de problemas

- **Problemas al eliminar**: si deseas eliminar la ubicación en el mapa de un elemento, debes borrar todas las modificaciones realizadas en el mapa. En primer lugar, elimina cada marcador (haz clic en el botón «Eliminar elemento», selecciona los marcadores y haz clic para guardar). A continuación, borra la configuración de la vista del mapa (haz clic en el botón «Borrar el centro y el nivel de zoom predeterminados»). El mapa volverá a una vista global. Guarda el elemento y comprueba que el mapa ya no aparece.
- **Problemas con los mosaicos del mapa**: Asegúrate de haber elegido un mapa base de nuestra lista de proveedores que ofrezca mosaicos con un alto nivel de zoom. Si no es así, elige otro mapa base o vuelve al proveedor predeterminado.
- **Problemas con las líneas de tiempo**: Asegúrate de que tienes instalado y activo el módulo «Tipos de datos numéricos» y de que el campo de metadatos de fecha seleccionado está formateado correctamente como un «Tipo de datos numéricos» mediante plantillas de recursos. No se mostrarán los elementos con datos de mapeo pero sin datos de fecha, ni los elementos con datos de fecha pero sin datos de mapeo, ya que los mapas con líneas de tiempo requieren ambos.
- **Elementos que no aparecen en tus mapas**: Asegúrate de que todos los elementos se hayan añadido a tu sitio en la pestaña «Recursos». Comprueba que los elementos tengan datos de mapeo válidos en sus respectivas pestañas de «Mapeo». Prueba la página «Explorar mapas», que se encuentra en `tu-sitio/mapping/index/browse`. Prueba un bloque de página sencillo de «Mapa por archivos adjuntos» con algunos elementos que sepas que están geolocalizados correctamente.
- **Mapas que no aparecen en las páginas de elementos o en las páginas de conjuntos de elementos**: Añade el bloque de página de recursos «Mapeo» a una región proporcionada por tu tema, yendo a [Sitio > Tema > Configurar páginas de recursos](../sites/site_theme.md#configure-resource-pages).
- **Problemas al guardar superposiciones**: Hay un botón «Guardar superposición» en el que hay que hacer clic al introducir o editar una superposición. Asegúrate de guardar cada modificación y, a continuación, guarda la página. 
- **Aparecen mapas base incorrectos**: Los mapas base son propiedades heredadas: la configuración global se aplica a los, que quedan anuladas por la configuración de edición específica del usuario y por los mapas individuales del lado administrativo. Los mapas públicos muestran su propia configuración personalizada y, a falta de esta, utilizan la configuración predeterminada de todo el sitio. Los mapas base para las páginas de exploración de mapas se configuran en la pantalla de navegación de cada sitio; los mapas base para los bloques de página se configuran al editar las páginas del sitio. Los mapas de las páginas de vista de elementos utilizan el mapa base predeterminado del sitio y no se pueden personalizar más. 
