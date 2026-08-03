---
título: Visualización de datos
---
# Visualización de datos

El [módulo de visualización de datos](https://omeka.org/s/modules/Datavis){target=_blank} permite a los administradores del sitio generar conjuntos de datos y crear diagramas que reflejen la complejidad de sus colecciones. Una vez instalado y activado en la sección «Módulos» del panel de administración, el módulo de visualización de datos se gestiona de forma individual para cada sitio. Puedes añadir tus diagramas de datos a las páginas del sitio utilizando bloques de página.

![Diagrama generado por una visualización titulada «Recuento de valores de propiedad en una serie temporal», utilizando la opción de visualización de líneas MonotoneX. El título es «Temas a lo largo del tiempo» y la descripción es «Elementos organizados por fecha, que muestran los encabezados temáticos con los que están etiquetados». Al pasar el ratón por encima de una fecha, aparece un cuadro emergente con el texto «1870» y una lista de temas con el recuento de elementos que utilizan cada uno de ellos.](modulesfiles/dataviz_countPropertyValuesTime-display.png)

Algunas visualizaciones permiten a los usuarios interactuar y navegar por los elementos o conjuntos; otras son representaciones estáticas de la información del sitio. Algunas requerirán que reformatees o conviertas tus metadatos para que sean legibles por la Visualización de datos. 

Todas las visualizaciones basadas en la fecha y la hora requieren que los [tipos de datos numéricos](numericdatatypes.md) estén instalados y activos en tu instalación, y que los valores de fecha tengan el formato correcto. También te pueden resultar útiles los módulos [Limpieza de datos](datacleaning.md) y [Navegación por facetas](facetedbrowse.md) para detectar y corregir inconsistencias en tus datos, con el fin de obtener mejores visualizaciones.

Las visualizaciones de datos pueden ser creadas y modificadas por [administradores globales y supervisores](../admin/users.md), así como por usuarios designados como [gestores en sitios individuales](../sites/site_users.md). Los creadores de sitios pueden ver los diagramas de visualización y los conjuntos de datos, pero no pueden crear ni modificar visualizaciones.

## Visualizaciones de datos por sitio

Las visualizaciones de datos se generan a partir de los elementos añadidos a un sitio concreto. No es posible visualizar información sobre todos los recursos de una instalación. 

En el menú de la barra lateral de cada sitio aparecerá una sección dedicada a la visualización de datos. Al hacer clic en este enlace, se accederá a una lista de todas las visualizaciones creadas para el sitio. 

![La pantalla de administración que muestra la sección «Visualización de datos» en la barra lateral y tres conjuntos de datos creados para un sitio.](modulesfiles/dataviz_browse.png)

Puede ordenar las visualizaciones por fecha o por título, en orden ascendente o descendente. No es posible editar visualizaciones de forma masiva, ni siquiera eliminarlas de forma masiva, ni duplicar visualizaciones existentes, ni copiarlas a otros sitios.

## Añadir una visualización de datos

Después de hacer clic en el enlace «Visualización de datos» debajo de un sitio, haz clic en el botón «Añadir nueva visualización».

A continuación, seleccione lo que desea visualizar. Las opciones incluyen:

1. **Recuento de elementos con clases**, que visualiza el recuento de elementos que son instancias de las clases de recursos seleccionadas.
1. **Recuento de elementos en conjuntos de elementos**, que visualiza el recuento de elementos asignados a los conjuntos de elementos seleccionados.
1. **Recuento de elementos con propiedades**, que muestra el número de elementos que tienen las propiedades seleccionadas.
1. **Recuento de elementos con valores de propiedad**, que muestra el número de elementos que tienen los valores seleccionados de una propiedad determinada.
1. **Recuento de valores de propiedad**, que muestra el número de valores de una propiedad seleccionada.
1. **Recuento de elementos con valores de propiedad en una serie temporal**, que muestra el número de elementos que tienen los valores seleccionados de una propiedad seleccionada durante un periodo de tiempo seleccionado.
1. **Recuento de elementos en una serie temporal**, que muestra el recuento de elementos a lo largo de un periodo de tiempo seleccionado.
1. **Recuento de valores de propiedad**, que muestra el recuento de valores de una propiedad seleccionada de los elementos.
1. **Relaciones entre elementos**, que muestra las relaciones entre los elementos a través de los valores de sus recursos.

Una vez que hayas seleccionado lo que deseas visualizar, haz clic en el botón «Siguiente». A continuación, podrás describir y configurar esta visualización.

- Cada visualización requiere un título.
- Puedes añadir una descripción en prosa de la visualización. Esto aparecerá debajo del título en la página de la visualización y en el bloque de la página. Puede incluir código HTML en este campo, incluidos enlaces. 
- Utilice la interfaz de consulta de búsqueda para establecer el conjunto de recursos que se van a visualizar. Si decide dejarlo en blanco, la visualización incluirá todos los elementos asignados a ese sitio.
    - Si seleccionas «Editar», se abrirá una barra lateral que te permitirá realizar búsquedas de texto completo, por valor, por clase, por plantilla, por conjunto de elementos y/o por propietario. Puedes combinar varios parámetros con «Y» o «O». Puedes «Previsualizar», «Restablecer» o «Aplicar» la búsqueda seleccionando el botón correspondiente en la parte inferior de la barra lateral de búsqueda.
    - Si seleccionas «Edición avanzada», puedes editar o pegar una cadena de búsqueda procedente de una URL (que puedes crear buscando tus elementos en la interfaz de usuario del sitio).

![Formulario de visualización de datos que incluye título, descripción, consulta de búsqueda y opciones de configuración de datos para una visualización de «Recuento de elementos con valores de propiedad»](modulesfiles/dataviz_editVisualization.png)

### Configuración de datos

Las opciones para configurar tu conjunto de datos reflejarán el tipo que hayas seleccionado inicialmente y es posible que debas modificarlas en función del diagrama que desees mostrar:

#### Recuento de elementos con clases

Esta selección te ofrece la opción de elegir entre un gráfico de barras, un gráfico de columnas o un gráfico circular (consulta la [Configuración del diagrama](#diagram-configuration) más abajo).

Selecciona las clases haciendo clic dentro del menú desplegable «Clases» y añadiendo una a una las clases disponibles (consulta la [pestaña «Vocabularios»](../content/vocabularies.md) para ver las clases instaladas). Si no completas este paso, aparecerá un error al intentar generar tu conjunto de datos; debes seleccionar todas las clases si deseas mostrarlas todas. 

![Visualización de las clases de elementos, ordenadas alfabéticamente, en un gráfico de barras.](modulesfiles/dataviz_classes.png)

#### Recuento de elementos en conjuntos de elementos

Esta selección te ofrece la opción de elegir entre un gráfico de barras, un gráfico de columnas o un gráfico circular.

Selecciona uno o más conjuntos de elementos haciendo clic dentro del cuadro de conjuntos de elementos y seleccionando una opción del menú desplegable. Puedes añadir más de un conjunto de elementos. Si no completas este paso, aparecerá un error al intentar generar tu conjunto de datos; debes seleccionar todos los conjuntos de elementos si deseas mostrarlos todos.

![Visualización del recuento de conjuntos de elementos, ordenados de menor a mayor, en un gráfico de columnas.](modulesfiles/dataviz_itemsets.png)

##### Recuento de elementos con propiedades

Esta selección te ofrece la opción de elegir entre un gráfico de barras, un gráfico de columnas o un gráfico circular.

Selecciona una o más propiedades haciendo clic dentro del cuadro «Propiedad» y seleccionando una opción del menú desplegable. Puedes añadir más de una propiedad. Si no completas este paso, aparecerá un error al intentar generar tu conjunto de datos.

![Visualización de los elementos con las cuatro propiedades seleccionadas, en un gráfico circular. Al pasar el ratón por encima de una porción, se muestra el recuento correspondiente a esa porción.](modulesfiles/dataviz_properties.png)

#### Recuento de elementos con valores de propiedad

Esta selección te ofrece la opción de elegir entre un gráfico de barras, un gráfico de columnas o un gráfico circular.

Hay dos campos que debes rellenar en «Configuración del conjunto de datos» al crear un recuento de elementos con propiedades: «Propiedad de valor» y «Valores». En primer lugar, debes utilizar el menú desplegable para seleccionar una propiedad. A continuación, puedes introducir los valores específicos, separados por líneas nuevas, en el cuadro de texto.

Puede resultarte útil copiar los valores de esta lista desde el [módulo de navegación por facetas](facetedbrowse.md), ya que este puede cargar todos los valores disponibles de una propiedad facetada determinada.

#### Recuento de elementos con valores de propiedad en una serie temporal

Esta selección dará lugar a un gráfico de líneas y visualiza el recuento de elementos que tienen los valores seleccionados de una propiedad dentro de un intervalo de tiempo especificado. El [módulo «Tipos de datos numéricos»](numericdatatypes.md) debe estar instalado y activado; los valores utilizados para la fecha y la hora deben tener el formato correcto según la norma ISO 8601 para valores de fecha. 

![Diagrama generado con la siguiente configuración, utilizando la opción de visualización de líneas MonotoneX. El título es «Temas a lo largo del tiempo» y la descripción es «Elementos organizados por fecha, mostrando los encabezados temáticos con los que están etiquetados». El cursor del ratón se encuentra sobre una fecha, mostrando un cuadro emergente con el texto «1870» y una lista de temas con el recuento de elementos que utilizan cada uno.](modulesfiles/dataviz_countPropertyValuesTime-display.png)

Introduce los valores deseados en una lista. Puede resultarte útil copiar los valores de esta lista desde el [módulo de navegación por facetas](facetedbrowse.md), ya que este puede cargar todos los valores disponibles de una propiedad facetada determinada.

Cada entrada de la lista de valores tendrá un color distinto. El gráfico mostrará las instancias de cada valor en cada intervalo de fechas de la «frecuencia de muestreo» (por ejemplo, cada año o cada periodo de diez años). Al pasar el ratón por encima de un intervalo de fechas, aparecerá un cuadro emergente que mostrará los recuentos exactos de cada valor, en el orden establecido en la configuración. Esta visualización no proporciona enlaces a elementos ni a resultados de búsqueda. 

![Configuración del administrador del diagrama anterior.](modulesfiles/dataviz_countPropertyValuesTime.png)

#### Recuento de elementos en una serie temporal

Esta selección te ofrece la opción de elegir entre un histograma o un gráfico de líneas, y visualiza el recuento de elementos a lo largo de un periodo de tiempo seleccionado. El [módulo «Tipos de datos numéricos»](numericdatatypes.md) debe estar instalado y activado; los valores utilizados para la fecha y la hora deben tener el formato correcto según la norma ISO 8601 para valores de fecha. 

![Una visualización de datos de series temporales que muestra un histograma con elementos desde 1700 hasta 2024. El título es «La colección por fecha» y el párrafo dice: «Consulta el intervalo de fechas y la frecuencia actuales de la colección. Esto solo incluye elementos cuya fecha se conoce y está formateada correctamente...»"](modulesfiles/dataviz_timeSeries.png)

Esta visualización no proporciona enlaces a los elementos incluidos en ella; solo muestra el recuento de los elementos dentro de un intervalo determinado. 

##### Recuento de valores de propiedad

Esta selección te ofrece la opción de elegir entre un gráfico de barras, un gráfico de columnas o un gráfico circular.

![Pantalla de administración que muestra la configuración de un gráfico circular de «recuento de valores de propiedad». La consulta de búsqueda es «Tipo tiene cualquier valor» y la propiedad de valor es «Dublin Core: Tipo». El mínimo está fijado en 10; el máximo no está fijado.](modulesfiles/dataviz_countPropertyValues.png)

Al configurar tu conjunto de datos para contar los valores de las propiedades, debes seleccionar una propiedad del menú desplegable. Si no completas este paso, recibirás un error al intentar generar tu conjunto de datos. Hay otros dos campos de configuración opcionales: «Recuento mínimo» y «Recuento máximo». Puede establecer estos valores escribiéndolos o aumentando o disminuyéndolos con las flechas.

![Vista pública del diagrama generado por la configuración anterior. El párrafo dice: «Todos los elementos del sitio, por tipo. Solo se muestran los tipos de elementos con más de 10 elementos». Los tipos incluyen baladas y canciones, biografía, poesía y folclore.](modulesfiles/dataviz_countPropertyValues-display.png)

#### Relaciones entre elementos

Esta opción visualiza las relaciones entre los elementos a través de los valores de sus recursos. Se basa en los [recursos vinculados](../content/items.md#linked-resources) que hayas establecido entre elementos utilizando sus campos de metadatos (por ejemplo, estableciendo el elemento «William Shakespeare» como valor de «Creador» en el elemento «Mucho ruido y pocas nueces»). 

Estas visualizaciones no mostrarán enlaces entre elementos y conjuntos de elementos, ni enlaces con archivos multimedia. 

Al igual que en otros diagramas, primero debes seleccionar un subconjunto de elementos del sitio mediante una consulta de búsqueda. A continuación, debes especificar qué propiedades vinculadas deseas mostrar. Si eliges mostrar un subconjunto concreto de elementos (como los elementos con la clase «Persona»), el diagrama mostrará los enlaces salientes de esos elementos hacia otros elementos del mismo subconjunto. 

Puede utilizar el selector de propiedades para especificar qué vínculos (como «Cónyuge de») desea mostrar. Si deja el selector de propiedades en blanco, el diagrama mostrará todos los vínculos entre los elementos incluidos. 

Las relaciones entre elementos pueden visualizarse en uno de estos dos diagramas: el gráfico de red, una representación en «árbol» con nodos movibles, o el de arcos, en el que todos los elementos aparecen en una lista vertical y se dibujan arcos entre los elementos que tienen vínculos. Ambos diagramas incluyen ventanas emergentes con más información sobre cada elemento, así como enlaces en los que se puede hacer clic para explorar dichos elementos. La siguiente imagen muestra el diagrama de arcos:

![El diagrama de arcos que muestra las relaciones entre elementos. El párrafo dice: «Las relaciones que se muestran incluyen cónyuges, padres e hijos». Los elementos son nombres como Abigail, Betty, Clara, Hannah y Jenny.](modulesfiles/dataviz_arc.png)

Y el diagrama de red:

![El diagrama de red que muestra las relaciones entre los elementos. El párrafo dice: «Este diagrama muestra a las personas casadas y sus relaciones. Los hombres aparecen en azul y las mujeres en naranja». El gráfico muestra un gran número de pares o tríos de puntos de colores.](modulesfiles/dataviz_network.png)

### Configuración del diagrama

!!! nota
	Si realizas cambios en cualquiera de los ajustes situados por encima de esta sección, tendrás que volver a generar tu conjunto de datos para poder ver los resultados en tu diagrama. Los cambios realizados por debajo de este punto en la página de configuración no requieren actualizar el conjunto de datos. Sin embargo, al visualizar el diagrama resultante, te recomendamos que actualices la página pública de forma manual para asegurarte de que los cambios se cargan correctamente.

En «Configuración del diagrama», podrás seleccionar el tipo de diagrama que deseas generar para tu visualización y, a continuación, especificar colores, dimensiones y otros ajustes visuales. 

#### Diagramas de «Recuento de»

Para los diagramas de «Recuento de», las opciones son gráfico de barras, gráfico de columnas y gráfico circular.

En estos diagramas no hay enlaces que permitan a los usuarios navegar por la colección. 

Si seleccionas **gráfico de barras** o **gráfico de columnas**, se te pedirá que introduzcas el ancho y la altura de tu visualización, así como los márgenes superior, derecho, inferior e izquierdo. Además, podrás utilizar un menú desplegable para ordenar los datos por valor (ascendente), por valor (descendente), por etiqueta (ascendente) o por etiqueta (descendente).

Si seleccionas **gráfico circular**, solo se te pedirá que introduzcas el ancho, la altura y los márgenes. Los gráficos circulares son siempre círculos; las porciones se ordenan siempre de mayor a menor, en el sentido de las agujas del reloj. 

La imagen siguiente muestra la pantalla de administración para configurar un gráfico de columnas:

![Formulario de configuración de un gráfico de columnas.](modulesfiles/dataviz_diagramConfig.png)

En el caso de los gráficos de barras y de columnas, puedes elegir un único color para todo el diagrama introduciendo un código de color hexadecimal de seis dígitos. Para los gráficos circulares, puedes elegir una combinación de colores que ofrezca varios colores complementarios en el menú desplegable. Utiliza [el enlace del texto de ayuda (que se despliega al hacer clic en la flecha situada junto a «Esquema de colores») para ver las opciones](https://d3js.org/d3-scale-chromatic/categorical){target=_blank}. 

![Algunas de las combinaciones de colores disponibles para los gráficos circulares; captura de pantalla de la página de D3 enlazada en el texto. Para obtener más información, visita esa página.](modulesfiles/dataviz_diagramColors.png)

#### Diagramas basados en fechas

##### Histogramas

Los histogramas están disponibles para los conjuntos de datos de «Recuento de elementos en una serie temporal». 

Los histogramas son similares a los gráficos de columnas: el eje horizontal representa un intervalo de tiempo y el eje vertical, el recuento de tu conjunto de datos. 

En este diagrama no hay enlaces que permitan a los usuarios explorar la colección. 

![Visualización de datos de una serie temporal, que muestra un histograma con elementos desde 1700 hasta 2024.  El título es «La colección por fecha» y el párrafo dice: «Consulta el intervalo de fechas y la frecuencia actuales de la colección. Esto solo incluye elementos cuya fecha se conoce y está formateada correctamente...»](modulesfiles/dataviz_timeSeries.png)

##### Gráficos de líneas agrupados (series temporales)

Los gráficos de líneas están disponibles para los conjuntos de datos «Recuento de valores de propiedades en una serie temporal» y «Recuento de elementos en una serie temporal». [Consulta las capturas de pantalla anteriores para ver las opciones de los conjuntos de datos y la configuración de los diagramas](#count-of-items-with-property-values-in-a-time-series).

Los gráficos de líneas son similares a los gráficos de columnas y a los histogramas, pero con una representación más compleja para mostrar los cambios a lo largo del tiempo. En el caso de «Recuento de elementos en una serie temporal», el gráfico de líneas mostrará un solo color. En el caso de «Recuento de valores de propiedad en una serie temporal», el gráfico de líneas mostrará un color diferente para cada valor de propiedad incluido. Los colores vienen predeterminados con sus opciones de visualización y no se pueden personalizar.

Puedes elegir mostrar, para cada valor con un recuento: una línea (sin puntos en cada intervalo de fecha), puntos en cada intervalo de fecha (sin línea de conexión) o tanto la línea como sus puntos.

Las opciones de línea son:

- Lineal
- MonotoneX
- Natural
- Escalonado
- Escalonado posterior
- Escalonado anterior.

En la imagen anterior, en la sección [Recuento de elementos con valores de propiedad a lo largo del tiempo](#count-of-items-with-property-values-in-a-time-series), se puede ver la opción MonotoneX. Las cuatro opciones siguientes son Lineal, Natural (las dos superiores), Step y StepAfter (las dos inferiores).

![Cuatro de las opciones de línea anteriores mostradas en una página pública: Lineal, Natural, Por pasos y Por pasos posteriores.](modulesfiles/dataviz_countPropertyValuesTime-lines.png)

En estos diagramas no hay enlaces que permitan a los usuarios explorar la colección. 

#### Diagramas de relaciones

##### Diagramas de arcos

![Un diagrama de arcos, como el anterior, con un elemento resaltado que muestra su ventana emergente. El texto dice: «Las relaciones que se muestran incluyen cónyuges, padres e hijos». La persona «Poll» está resaltada, mostrando enlaces a «Abigail» y «David», que también están resaltados. Una ventana emergente junto a «Poll» muestra el texto en azul «mujer» y las relaciones con David («Cónyuge») y Abigail («Progenitora»).](modulesfiles/dataviz_arc-highlight.png)

Los diagramas de arcos muestran los elementos en una columna situada en el lado izquierdo del diagrama, y las relaciones entre dichos elementos se representan mediante grandes semicírculos arqueados que conectan dos elementos. Un elemento puede tener varios arcos. 

Los elementos se colorean en función del «Grupo» asignado en tu configuración (ya sea la clase o la plantilla del elemento, o un valor de propiedad que hayas seleccionado), y los arcos tienen el color del elemento cuyo recurso vinculado saliente se indica en un valor de propiedad.

Por ejemplo, si se mostrara la relación entre los creadores y sus creaciones, utilizando plantillas de recursos (por ejemplo, «Personas» y «Libros») como grupos, las personas aparecerían en naranja y los libros en azul, con arcos azules que conectaran los libros con las personas indicadas en sus campos «Creador». Si los elementos tienen relaciones recíprocas (inversas) entre sí, es posible que veas lo que parece un único arco con el color combinado de los dos arcos. 

Si los elementos no pertenecen al grupo elegido (por ejemplo, si se agrupan por clase y algunos elementos no tienen clase), se incluirán en un grupo «nulo». Los grupos nulos siempre se mostrarán en primer lugar.

Este diagrama proporciona enlaces que permiten a los usuarios explorar los elementos incluidos. 

Puedes establecer el ancho del diagrama; la altura se ajusta automáticamente en función del número de elementos del diagrama, así como del tamaño del texto y el espaciado. Los arcos se dibujan automáticamente y pueden desbordar el ancho del diagrama si hay muchos elementos (y si el arco se dibuja entre un elemento cercano al principio y otro cercano al final de la lista). 

También puede establecer los márgenes superior e inferior, que son el espacio que queda por encima del centro del primer elemento y por debajo del centro del último elemento. Si establece estos valores en «0», verá que el texto queda cortado en la parte superior e inferior del diagrama.

Establecer el margen izquierdo significa dejar espacio dentro del ancho total del diagrama, desde el borde izquierdo, para mostrar los nombres de los elementos. Dado que los títulos de los elementos pueden ser muy largos y el diagrama no añade saltos de línea para las etiquetas largas, es posible que algunas etiquetas queden cortadas por el lado izquierdo del diagrama, por lo que debes ajustar este valor para compensar la etiqueta más larga de tu diagrama. Es posible que también tengas que aumentar el ancho total del diagrama para adaptarlo a este cambio.

Puedes elegir ordenar tus elementos según el conjunto de agrupación establecido anteriormente o alfabéticamente por el título del elemento. 

Puede establecer el tamaño del texto (desde extra-extra-pequeño hasta extra-extra-grande) y el espacio entre el texto (en píxeles). Dependiendo del número de elementos que haya en tu diagrama, o del tamaño total generado por los arcos, es posible que observes un cambio en el tamaño del texto al modificar la configuración del diagrama. Utiliza el ajuste «Tamaño de fuente de las etiquetas» para compensarlo según sea necesario. El espaciado es un ajuste numérico que no se verá afectado por otros cambios, pero debe ajustarse al mismo tiempo que se modifica el tamaño del texto. Ajusta también los márgenes superior e inferior si el cambio en el tamaño del texto hace que las etiquetas superior e inferior de los elementos queden cortadas.

Puedes elegir una combinación de colores que ofrezca varios colores complementarios en el menú desplegable. Utiliza [el enlace del texto de ayuda (que se despliega al hacer clic en la flecha situada junto a «Combinación de colores») para ver las opciones](https://d3js.org/d3-scale-chromatic/categorical){target=_blank}. 

##### Diagramas de grafos de red

![Un diagrama de red, como el anterior, con un elemento resaltado que muestra su ventana emergente. La persona «Patrick Hawkins» tiene un cuadro emergente con la palabra «hombre» en azul, con enlaces a «Letty Hawkins» («Cónyuge») y «Kitty Hawkins» («Cónyuge»).](modulesfiles/dataviz_network-highlight.png)

Los diagramas de grafos de red muestran elementos con enlaces entre sí en una visualización en árbol. 

Los elementos se muestran como pequeños círculos y se colorean según el «Grupo» asignado en tu configuración (ya sea la clase o la plantilla del elemento, o un valor de propiedad que hayas seleccionado). Los enlaces entre elementos son de color gris.

Si los elementos no pertenecen al grupo que hayas elegido (por ejemplo, si estás agrupando por clase y algunos elementos no tienen clase), se incluirán en un grupo «nulo». 

Al hacer clic en un elemento, su círculo se resaltará con un borde negro y sus enlaces pasarán a ser negros. Aparecerá un cuadro emergente que mostrará el nombre del elemento en la parte superior, el nombre de su grupo debajo y los recursos vinculados que se incluyen en el diagrama. Los usuarios pueden arrastrar los nodos por la pantalla para ver sus relaciones. 

Este diagrama proporciona enlaces que permiten a los usuarios explorar los elementos incluidos. 

Al seleccionar un diagrama de grafo de red, tendrás la opción de establecer el ancho y la altura de tu diagrama. Los elementos se agruparán automáticamente en un círculo alrededor del punto central de tu diagrama, dentro del diámetro especificado por tu dimensión más pequeña, por lo que te recomendamos mantener unas dimensiones cuadradas. 

Puede elegir una combinación de colores que ofrezca varios colores complementarios en el menú desplegable. Utilice [el enlace del texto de ayuda (que se despliega al hacer clic en la flecha situada junto a «Combinación de colores») para ver las opciones](https://d3js.org/d3-scale-chromatic/categorical){target=_blank}. 

### Genera tu visualización

Una vez que hayas configurado tu visualización, haz clic en el botón «Guardar y...», marca la casilla «Generar conjunto de datos» y haz clic en «Permanecer en esta visualización».

![Menú «Guardar» con la opción «Generar conjunto de datos» marcada](modulesfiles/dataviz_saveGenerate.png)

No verás el botón «Ver» hasta que haya finalizado la generación del conjunto de datos. Comprueba el estado de la tarea antes de intentar ver los resultados. Una vez completada la visualización, puedes hacer clic en el botón «Ver...» y seleccionar «Conjunto de datos» o «Diagrama».

Si seleccionas «Conjunto de datos», se abrirá una nueva pestaña del navegador que mostrará tu conjunto de datos en formato JSON. Puede resultarte útil hacer clic en «Expandir todo» en la parte superior de la página para examinar rápidamente los valores cargados.

Si seleccionas «Diagrama», se abrirá una nueva pestaña del navegador con una nueva página pública en tu sitio web que contiene tu diagrama. Esta página seguirá estando disponible públicamente en tu sitio web mientras exista la visualización, pero no es necesario que incluyas un enlace a ella desde ningún sitio. En su lugar, puedes insertar tus visualizaciones como bloques de página (véase más abajo).

Puedes guardar tu trabajo y seleccionar «Volver a las visualizaciones», lo que te llevará a una lista de todas tus visualizaciones, donde podrás ver el diagrama o el conjunto de datos, o editar la visualización.

![Menú de visualización con «Conjunto de datos» y «Diagrama»](modulesfiles/dataviz_viewMenu.png)

Si editas tu visualización para cambiar la configuración del diagrama después de que se haya generado la visualización inicial, perderás tu configuración actual del diagrama.

Solo puedes generar un diagrama por conjunto de datos; si deseas presentar varios diagramas con la misma información, crea más visualizaciones con las mismas consultas y ajustes.

### Solución de problemas

Es posible que observes que el ancho y la altura de tu diagrama no muestran los resultados adecuadamente. Los diagramas se generan mediante SVG, lo que significa que algunos elementos (como las líneas verticales del histograma) se dibujan con un ancho inferior a 1 píxel en relación con los tamaños y parámetros proporcionados, o que los arcos quedan recortados por el lado derecho. Puedes solucionar esto ampliando el diagrama, reduciendo los parámetros en cualquiera de los ejes (como el intervalo de fechas), ampliando los intervalos o reduciendo el número de elementos. Considera la posibilidad de dibujar varios diagramas y colocarlos en una sola página si hay demasiados detalles para mostrarlos adecuadamente en un solo diagrama.

!!! Nota
  El diagrama debe dibujarse con la anchura y la altura deseadas en el contexto de la página en la que finalmente se vaya a mostrar. Quizá te interese crear una versión preliminar de la página y actualizarla cada vez que realices cambios en la configuración del diagrama. Algunos diagramas pueden resultar inadecuados en función del diseño de página que tengas previsto, como por ejemplo si pretendes mostrar un diagrama alto y estrecho junto al texto de la página. No todas las opciones de diagrama disponen de ajustes que permitan una visualización flexible.

Si el texto queda apretado en los ejes de tu gráfico, vuelve atrás y ajusta los márgenes. Las etiquetas de texto no disponen de opciones de desbordamiento ni de ajuste de línea, por lo que algunos títulos largos pueden quedar cortados. Puedes ajustar el tamaño de la fuente en algunos diagramas (desde extra-extra-pequeño hasta extra-extra-extra-grande), pero puede verse limitado por el ancho máximo del diagrama, que a su vez dependerá del diseño de la página y del tema de tu sitio Omeka. 

## Publica tu visualización

Las visualizaciones de datos se publican principalmente añadiéndolas a las páginas del sitio como bloques de página. 

Mientras editas una página nueva o ya existente, añade un bloque de «Visualización de datos». En el nuevo bloque, utiliza el menú desplegable para seleccionar la visualización que deseas añadir a la página. A continuación, guarda los cambios realizados en la página. Recuerda añadir la página a la navegación de tu sitio, si es nueva.

![Bloque de visualización de datos en una página](modulesfiles/dataviz_block.png)

También puedes utilizar los botones «Ver diagrama» de cada visualización para obtener una URL directa a una página que contenga el título, la descripción y la visualización. 

Puedes añadir estas páginas a la navegación de tu sitio en la configuración de «Navegación». Busca la opción «Visualización de datos +» en la barra lateral derecha. 
