# Importación de CSV

El [módulo de importación de CSV](https://omeka.org/s/modules/CSVImport){target=_blank} te permite importar elementos, conjuntos de elementos, archivos multimedia y usuarios a tu instalación de Omeka S desde un archivo CSV (valores separados por comas), TSV (valores separados por tabulaciones) u ODS (hoja de cálculo OpenDocument). Este módulo solo está disponible para [usuarios con roles de administrador global y supervisor](../admin/users.md).

La importación CSV requiere que tu instalación de Omeka S [tenga PHP en funcionamiento para poder ejecutar tareas de importación en segundo plano](../install.md#test-and-set-the-php-path). Antes de utilizar la importación CSV, debes comprobar que PHP se reconoce en la [página de información del sistema](../admin-dashboard.md#system-information). 

## Prepara tu archivo CSV

La mayoría de los editores de hojas de cálculo (incluidos Microsoft Excel, Google Sheets y Apple Numbers) pueden exportar a formato CSV, TSV u ODS. 

!!! Nota
  Los archivos CSV para la importación **deben estar codificados en UTF-8**, por lo que, al exportar o guardar un nuevo documento, asegúrate de comprobar que la codificación sea UTF-8.

La mayoría de las opciones de importación de CSV se basan en que solo importes un tipo de datos: una lista de elementos, una lista de conjuntos de elementos, una lista de medios, etc. Existe la opción de [importación de recursos mixtos](#mixed-resource-import), que requiere una columna que identifique el tipo de cada fila.

Si la hoja de cálculo ya está creada, piensa qué columnas quieres que se correspondan con qué [propiedades del vocabulario](../content/vocabularies.md). Tu archivo CSV **debe tener una fila de encabezado** para que el módulo lo procese correctamente, por lo que es posible que tengas que añadir una fila en la parte superior con los nombres de las columnas.

Si tienes varias entradas para una misma propiedad, puedes separarlas con un **separador de valores múltiples** secundario. Por ejemplo, una obra con varios autores (E.B. White y William Strunk Jr.) en la que la columna «Creador» contenga «E.B. White;William Strunk Jr.» tiene un punto y coma (;) como separador de valores múltiples. Al importarla a Omeka S, cada una de estas entradas aparecería como una entrada independiente en la propiedad (Creador: «E.B. White» y Creador: «William Strunk Jr.»). Ten en cuenta que la importación será la misma tanto si dejas un espacio después del separador (como en «E.B. White; William Strunk Jr) o no. 

### Nombres de las columnas

Puedes asignar manualmente cada columna a su propiedad correspondiente, y es obligatorio asignar manualmente las columnas que no sean de metadatos, como la URL del archivo para su subida. El módulo asignará automáticamente las columnas de metadatos según los nombres proporcionados en la fila de encabezado, siempre que se ajusten a los términos de las propiedades de los [vocabularios](../content/vocabularies.md) en el formato `prefijo:propiedad`. Por ejemplo, un archivo CSV con un encabezado de columna «dcterms:title» se asignaría automáticamente a la propiedad «Título» de Dublin Core al cargar el CSV para la asignación. Puedes modificar estas columnas asignadas automáticamente antes de la importación.

Para encontrar los términos que debes utilizar para los encabezados de tus columnas, ve a la pestaña «Vocabularios» desde el panel de administración. Haz clic en el número de propiedades del vocabulario que desees utilizar (por ejemplo, «Dublin Core» en la imagen siguiente).

En la tabla de propiedades del vocabulario, hay una columna denominada **Término**. Utiliza el «Término» como encabezado de columna para la propiedad que desees asignar automáticamente en la importación CSV. Por ejemplo, «dcterms:abstract» se asignaría automáticamente a la propiedad «Abstract» de Dublin Core y «foaf:firstName» se asignaría automáticamente a la propiedad «firstName» de Friend of a Friend.

![La flecha señala la columna «Término» de las propiedades de Dublin Core.](../modules/modulesfiles/csvimport_automap2.png)

En la configuración inicial de la importación hay una opción para realizar la asignación automática con etiquetas simples; esto funcionará con columnas cuyos nombres coincidan con una etiqueta del vocabulario, por ejemplo, «title» o «abstract», sin necesidad de especificar el término. Ten en cuenta que esta opción utiliza por defecto Dublin Core (`dcterms:title` y `dcterms:abstract`) antes de pasar a otros vocabularios instalados.

Si los nombres de tus columnas no coinciden exactamente y la función de asignación automática no los reconoce, deberías asignarles un nombre que resulte útil para puedas asignarlas manualmente durante la importación.

Si tienes previsto importar por lotesimportar por lotes metadatos o propiedades que vienen con un módulo (como la latitud y la longitud del módulo Mapping) o utilizar vocabularios estructurados procedentes de módulos (como los tipos de datos del módulo Value Suggest), instala y configura primero esos módulos para asegurarte de que los campos existen en el modelo de datos de tu sitio, antes de intentar introducir información en dichos campos. Se podrían perder datos si desinstalas esos módulos más adelante.

## Configuración inicial de la importación

Inicia una importación haciendo clic en la pestaña «Importación CSV» del menú de navegación de la izquierda. Se abrirá la página inicial «Configuración de la importación». Para la mayoría de las hojas de cálculo exportadas directamente desde un programa de software en el formato correcto, puedes dejar estos ajustes en sus valores predeterminados.

- Utiliza el botón «Elegir archivo» para seleccionar una hoja de cálculo de tu ordenador.
- En el menú desplegable **Delimitador de columnas CSV**, elige entre las siguientes opciones (debe coincidir con el formato de tu archivo) el carácter que separa los distintos valores de una fila:
	- coma (por defecto)
  - punto y coma
  - dos puntos
  - tabulación
  - retorno de carro
  - espacio
  - barra vertical (`|`).

- En el menú desplegable **Delimitador de columnas CSV**, elige la opción que delimita el texto largo en tu archivo, si procede:
	- comillas dobles (predeterminado)
  - comillas
  - almohadilla (`#`).

- En el menú desplegable **Tipo de importación**, selecciona lo que vas a importar:
	- Elementos
  - Conjuntos de elementos
  - Archivos multimedia (se requiere una columna que asocie los archivos multimedia a elementos ya existentes)
  - Recursos mixtos (la hoja de cálculo puede incluir conjuntos de elementos, elementos y archivos multimedia; se requiere una columna que identifique el tipo de cada fila)
  - Usuarios.

- Marca la casilla para **Asignación automática con etiquetas simples**. La importación CSV asignará automáticamente los encabezados de columna con formato especial (en «prefijo:propiedad»); si marcas esta casilla, también asignará automáticamente cualquier encabezado de columna que coincida con las etiquetas de propiedades del vocabulario existentes (como «Título»). 

- Los **comentarios** aparecerán en la página «Importaciones anteriores»; esto puede resultarte útil para anotar qué se está importando y cualquier configuración que hayas elegido en esta página, por ejemplo, si estás trabajando por lotes o si deseas deshacer una importación más adelante.

![Configuración de importación tal y como se describe, sin entradas](../modules/modulesfiles/csvimport_settings.png)

Haz clic en el botón «Siguiente» para continuar con el proceso de importación.

## Importar elementos
Para importar elementos, selecciona «Elementos» en «Tipo de importación» en la primera página.

Al hacer clic en «Siguiente», se cargará la página con las siguientes pestañas:

### Asignar a datos de Omeka S 

Esta pestaña muestra una tabla con las columnas de tu hoja de cálculo como filas. Cada fila muestra:

- Una casilla de selección
- El encabezado de la columna de la hoja de cálculo
- Un botón con el símbolo «+» para añadir o modificar una asignación
- Un botón con el símbolo de una llave inglesa para acceder a las opciones de la columna de la hoja de cálculo
- Una columna que muestra las propiedades asignadas, ya sea de forma automática o manual
- Una papelera para eliminar las asignaciones existentes
- Una columna que muestra las opciones concretas seleccionadas (como si se deben buscar separadores de valores múltiples o la visibilidad de esa columna).

![Asignaciones para una hoja de cálculo con diez columnas. Algunas de las columnas, como las denominadas «Descripción» y «Título», se han asignado automáticamente a propiedades de Dublin Core.](../modules/modulesfiles/csvimport_itemsMap1.png)

#### Opciones de asignación

Para asignar el encabezado de una columna a una propiedad del vocabulario, haz clic en el botón con el símbolo más. Esto abrirá un panel deslizante en la parte derecha de la pantalla.

El panel deslizante ofrece varias opciones de asignación:

**Propiedades** te permite seleccionar una propiedad a la que asignar los datos de la columna, de cualquiera de los vocabularios instalados. Utiliza el campo «Filtro» para buscar una propiedad específica.

![Opción «Propiedades» abierta, mostrando todos los vocabularios instalados para la instalación de Omeka S: Dublin Core, Ontología Bibliográfica, Friend of a Friend, Scripto y Ontología OWL-Time.](../modules/modulesfiles/csvimport_itemsMapProp.png)

**Datos específicos del elemento** cuenta con un menú desplegable para establecer un conjunto de elementos según la propiedad seleccionada. Si tienes una columna que identifica un conjunto de elementos al que deseas añadir cada elemento (en lugar de colocar todos los elementos importados en los mismos conjuntos de elementos de la pestaña «Configuración básica»), puedes definir cómo se asignan mediante este menú desplegable. Puedes utilizar el ID interno del conjunto de elementos o cualquiera de sus propiedades (como el título).

![menú desplegable tal y como se describe](../modules/modulesfiles/csvimport_itemsMapISD.png)

**Los datos genéricos** también cuentan con un menú desplegable en el que puedes seleccionar una de estas cuatro opciones:

- **Plantilla de recurso (por etiqueta)**: Establece la plantilla de un elemento por su nombre. El nombre de la plantilla tal y como se ha introducido en la hoja de cálculo y el nombre de la plantilla en Omeka S deben coincidir exactamente.
- **Clase de recurso (por término)**: Establece la clase de recurso de un elemento. El término de la clase que figura en la hoja de cálculo y en la instalación de Omeka S debe coincidir exactamente; consulta la pestaña «Vocabularios» de tu instalación. Por ejemplo, introduce «dctype:Dataset», «dcterms:Location», «bibo:Interview» o «foaf:Person» con dos puntos que separen el prefijo del vocabulario y el término, sin espacios.
- **Propietario (por dirección de correo electrónico)**: Establece el propietario de un elemento mediante su dirección de correo electrónico. Debe ser la dirección de correo electrónico asociada a la cuenta del usuario en la instalación de Omeka S.
- **Visibilidad pública/privada**: Establece la visibilidad del elemento. Utiliza «privado» o «público» en la hoja de cálculo.

![Menú desplegable tal y como se describe](../modules/modulesfiles/csvimport_itemsMapgeneric.png)

**Fuente multimedia** te permite importar [archivos multimedia](../content/media.md#add-media-to-an-item) junto con tus elementos, seleccionando el método de origen en el menú desplegable:

- HTML
- Imagen IIIF (enlace)
- Presentación IIIF (enlace)
- oEmbed (enlace)
- URL
- YouTube (enlace).

Pueden aparecer aquí otras opciones en función de los módulos activos, como «Carga lateral de archivos». 

Asegúrate de hacer clic en «Aplicar cambios» en la parte inferior del panel; de lo contrario, no se guardará nada de lo que hayas configurado aquí.

Para eliminar una asignación, haz clic en el icono de la papelera en la fila correspondiente a esa asignación de datos. Esto eliminará *únicamente* la asignación, no los datos de la columna. 

Si tienes datos en una columna de tu archivo CSV que no deseas importar a tu instalación de Omeka S, simplemente no asignes esa columna a ninguna propiedad ni tipo de datos.

#### Opciones de columna

Las opciones de columna son independientes de las asignaciones. Si añades opciones sin asignar también los datos de la columna a un recurso, un medio u otros datos, no se importará nada. Si tienes varias asignaciones configuradas para una misma columna de tus datos, estas opciones se aplicarán a todas ellas.

Para acceder a las opciones de una columna de tu CSV (representada por una fila en la tabla de importación), haz clic en el icono de la llave inglesa situado junto al encabezado de esa columna.

![ventana deslizante con las opciones que se describen a continuación](../modules/modulesfiles/csvimport_ItemColOpt.png)

Esto abrirá un panel deslizante en la parte derecha de la ventana del navegador con las siguientes opciones:

- **Usar separador de valores múltiples**: Marca esta casilla para utilizar el separador de valores múltiples en los datos de esta columna. El separador de valores múltiples se configura en la página inicial de importación, pero puedes cambiarlo en la pestaña «Configuración básica».  
- **Idioma**: Establece el idioma de esta columna utilizando la [etiqueta de idioma de la IETF](https://en.wikipedia.org/wiki/IETF_language_tag){target=_blank} correspondiente al idioma en el que está escrito el texto. Esto anulará lo que hayas introducido en la configuración básica.
- **Importar valores como privados**: Marca esta casilla para establecer como privados todos los valores de las propiedades *de esta columna*.
- **Tipo de datos**: Un menú desplegable con al menos tres opciones, que se corresponden con los [valores](../content/items.md#values) que se pueden utilizar al añadir propiedades a un elemento:
	- Importar como texto (predeterminado).
  - Importar como referencia URI. Puedes establecer la etiqueta de una URI incluyendo el texto deseado tras un espacio, por ejemplo: `http://example.com El texto de la etiqueta va aquí`.
  - Importar como recurso Omeka S. Esto creará [recursos enlazados](../content/items.md#linked-resources). Si seleccionas esta opción, deberás elegir qué valores de propiedad deben coincidir para encontrar el recurso de Omeka deseado en tu instalación, en el siguiente menú desplegable **Propiedad identificadora del recurso**. Debe ser una propiedad única, por lo que «Título» puede que no sea una buena opción. 
 - Puedes utilizar el ID interno de Omeka. El ID de un recurso es la secuencia numérica que aparece al final de la URL en la página de visualización o edición; así, para `/admin/item/11576`, el ID es 11576. También puedes ver el ID del recurso en el panel de la derecha de lapágina de visualización del recurso. Los elementos, los conjuntos de elementos y los archivos multimedia tienen todos un ID.
		- Puedes incluir recursos que se estén creando en el mismo archivo CSV, siempre y cuando los recursos a los que se enlaza ya se hayan creado en filas anteriores y se puedan localizar mediante el valor de propiedad único indicado aquí. Si deseas hacerlo, te recomendamos establecer un número de lote bajo (incluso 1) en la pestaña «Configuración avanzada», para garantizar que los recursos estén se hayan creado por completo antes de que otro recurso nuevo intente vincularse a ellos. 
  - Si tienes instalados determinados módulos, como [Tipos de datos numéricos](../modules/numericdatatypes.md), es posible que dichos módulos ofrezcan opciones adicionales de tipos de datos.

Asegúrate de hacer clic en el botón «Aplicar cambios» situado en la parte inferior del panel para guardar los cambios. Para eliminar una configuración de opción de columna, haz clic de nuevo en el icono de la llave inglesa y deshaz los cambios manualmente.

#### Edición por lotes
Cuando selecciones una o más filas de la tabla (columnas de tu archivo CSV), puedes utilizar el botón «Opciones de edición por lotes» para aplicar las opciones de columna descritas anteriormente —separador de valores múltiples, idioma, tipo de datos y privacidad de las propiedades— a varias columnas del CSV a la vez.

![Captura de pantalla de la pestaña «Asignación», con dos casillas de columna marcadas. En la parte derecha de la pantalla, un panel desplegable ofrece opciones para modificar la configuración.](modulesfiles/csvimport_batchOptions.png)

Asegúrate de hacer clic en el botón «Aplicar cambios» situado en la parte inferior del panel para guardar los cambios.

### Pestaña «Configuración básica»

Esta configuración se aplica a todo el archivo CSV que estás importando. Ten en cuenta que estas opciones pueden ser anuladas por las opciones de columna de la pestaña «Asignar a datos de Omeka S». Si una columna está asignada a una plantilla, clase o propietario, esos valores prevalecerán sobre esta configuración; lo mismo ocurrirá con la configuración de las columnas de idioma y privacidad.

![La página «Configuración de importación de elementos», en la que se muestra la pestaña «Configuración básica», con las opciones que se enumeran a continuación. La visibilidad está establecida en «Pública» y el separador de valores múltiples es «;»; las demás opciones están vacías.](../modules/modulesfiles/csvimport_itemsbasic.png)

- **Plantilla de recurso**: Selecciona una [plantilla de recurso](../content/resource-template.md) del menú desplegable para aplicarla a los elementos importados. Puedes utilizar el campo de búsqueda situado en la parte superior del menú desplegable para filtrar los resultados o encontrar una plantilla concreta. Ten en cuenta que las plantillas de recursos pueden tener campos obligatorios, y los elementos no se importarán si no se rellenan todos los campos obligatorios de la plantilla seleccionada. Por ejemplo, si tu hoja de cálculo contiene entradas sin un valor `dcterms:title` y la plantilla de recursos requiere títulos, esas filas no se importarán y aparecerán errores en el registro.
- **Clase**: Selecciona una clase en el menú desplegable para aplicarla a los elementos importados. Puede utilizar el campo de búsqueda situado en la parte superior del menú desplegable para filtrar los resultados o buscar una clase concreta.
- **Propietario**: Establezca el propietario de los elementos seleccionando un usuario del menú desplegable. Puede utilizar el campo de búsqueda situado en la parte superior del menú desplegable para filtrar los resultados o buscar un usuario concreto.
- **Visibilidad**: Establece la visibilidad de los elementos importados como pública o privada.
- **Conjuntos de elementos**: Añade los elementos importados a uno o varios conjuntos de elementos específicos mediante el menú desplegable.
- **Sitios**: Añade los elementos importados al sitio o sitios especificados. Aquí aparecerán preseleccionados los sitios predeterminados globales y específicos del usuario.
- **Separador de valores múltiples**: Introduce aquí el carácter separador de valores múltiples, si has utilizado alguno.
 - Las columnas de datos de tu archivo CSV deben estar separadas por comas; sin embargo, dentro de esas columnas puedes añadir un carácter especial para crear entradas múltiples, por ejemplo, un punto y coma. Aquí es donde puedes especificar varios creadores, varios temas u otros usos habituales.
- **Idioma**: Establece el idioma de los valores de la hoja de cálculo utilizando la [etiqueta de idioma de la IETF](https://en.wikipedia.org/wiki/IETF_language_tag){target=_blank} adecuada.

!!! Nota
	Si vas a subir datos en diferentes formatos (por ejemplo, algunos nombres de creadores en formato de texto y otros enlaces de creadores basados en URI) en el mismo campo (`dcterms:creator`, en este caso), utiliza dos columnas (con nombres descriptivos como «dcterms:creator-text» y «dcterms:creator-uri») y, al importarlas, asigna esas dos columnas a tipos de datos diferentes. Utiliza el icono de la llave inglesa para abrir la configuración de asignación de columnas y selecciona el tipo de datos correcto para cada columna.

### Pestaña «Configuración avanzada»

Hay dos opciones en la pestaña «Configuración avanzada».

![Página de configuración avanzada en la que solo se muestran el menú desplegable «Acción» y el campo para el número de filas a procesar.](../modules/modulesfiles/csvimport_ItemsAdvanced.png)

La configuración «Acción» te permite cambiar la acción del proceso, pasando de una importación directa a una de las siguientes opciones:

- **Crear un nuevo recurso**: Opción predeterminada. Cada fila del CSV se convertirá en un nuevo recurso.
- **Añadir datos al recurso**: Añade nuevos datos al recurso, basándose en un identificador de un recurso existente. (No se puede deshacer.) Esta opción te permite proporcionar varios valores para el mismo elemento; cada fila se añadirá (es decir, puede añadir un título a un elemento en una fila y añadir otro título al mismo elemento en otra fila). Ten en cuenta que no puedes proporcionar plantillas de recursos ni asignaciones de clases en las filas de tu CSV con un proceso de «Añadir»; se producirá un error. 
- **Revisar los datos del recurso**: Sustituye los datos existentes del recurso por los datos del CSV, *excepto si* la celda correspondiente del CSV está vacía. (No se puede deshacer.)
- **Actualizar los datos del recurso**: sustituye los datos existentes del recurso por los datos del CSV, *incluso cuando* la celda correspondiente del CSV esté vacía. (No se puede deshacer.)
- **Sustituir todos los datos del recurso**: Elimina todas las propiedades del recurso y rellénalas con la nueva información de la hoja. (No se puede deshacer.)
- **Eliminar el recurso**: Elimina todos los recursos coincidentes. (No se puede deshacer.)

Si seleccionas una de estas opciones en el menú desplegable, aparecerán tres ajustes adicionales en la pestaña. Estos ajustes ayudan al proceso a determinar sobre qué recursos se debe actuar.

- **Columna de identificador de recurso**: Selecciona en un menú desplegable una de las columnas de tu archivo CSV. Se trata de los datos de tu hoja de cálculo que identifican los elementos existentes en tu instalación de Omeka S. Elige un identificador único (por ejemplo, podrías utilizar la columna «Título» de tu CSV).  No es necesario asignar esta columna en la otra pestaña.
- **Propiedad identificadora del recurso**: Selecciona de un menú desplegable entre todas las propiedades de tu instalación de Omeka S. Debe ser la propiedad equivalente en tu instalación de Omeka S a la columna que has seleccionado anteriormente (por ejemplo, `dcterms:title`). Esto solo funcionará con coincidencias exactas. Si tienes más de un recurso con datos coincidentes, solo se aplicará la acción al recurso más antiguo.
- **Acción sobre recursos no identificados**: Esta opción determina qué hacer cuando no existe ningún recurso coincidente en la instalación de Omeka S, siempre que la acción seleccionada se aplique a un recurso existente («Añadir», «Revisar», «Actualizar» o «Reemplazar»). Esta opción no se utiliza cuando la acción principal es «Crear» o «Eliminar». Las opciones disponibles son:
  - Saltar la fila e ignorar su contenido
  - Crear un nuevo recurso con la información proporcionada.

Además de lo anterior, la pestaña «Configuración avanzada» incluye una opción para establecer el número de filas que se procesarán por lote. Por defecto, está fijado en 20. Sin embargo, si se producen errores durante una importación, es posible que desee establecerlo en 5 o incluso en 1 para solucionar el problema y determinar el origen del error.

!!! Nota
	Ten en cuenta que la opción «Añadir datos» te permitirá proporcionar varias filas con el mismo identificador; los valores de cada fila se añadirán junto a los anteriores.

	La revisión, actualización y sustitución de datos **borrarán** los datos proporcionados en filas anteriores de tu archivo CSV, si las filas posteriores utilizan el mismo identificador. Si deseas importar varios valores (por ejemplo, dos valores de «Creador») en estos procesos, puedes: colocarlos en dos columnas de la misma fila, asignados a la misma propiedad; o bien, colocarlos en una sola celda y utilizar separadores de valores múltiples. No olvides especificar tu separador de valores múltiples en la pestaña «Configuración básica» y marcar la casilla «Usar separador de valores múltiples» en las opciones (icono de la llave inglesa) de cada columna.

### Finalizar la importación
Una vez que hayas completado las asignaciones, las opciones de las columnas y la configuración, haz clic en el botón «Importar» situado en la esquina superior derecha de la ventana del navegador. Esto debería iniciar la importación y redirigirte a la pestaña «Importaciones anteriores». Deberías ver un mensaje de confirmación en verde en la parte superior de la pantalla que dice «Importando con ID de tarea [número]».


## Importar conjuntos de elementos
Para importar conjuntos de elementos, selecciona «Conjunto de elementos» en «Tipo de importación» en la primera página.

Al hacer clic en «Siguiente», se cargará la página con las siguientes pestañas:

### Asignar a datos de Omeka S
Esta pestaña muestra una tabla con las columnas de tu hoja de cálculo como filas. Cada fila muestra:

- una casilla de selección
- el encabezado de la columna de la hoja de cálculo
- un botón con el símbolo «+» para añadir o modificar una asignación
- un botón con el símbolo de una llave inglesa para las opciones de las columnas de la hoja de cálculo
- una columna que muestra las propiedades asignadas, ya sea de forma automática o manual
- una papelera para eliminar las asignaciones existentes
- una columna que muestra las opciones concretas seleccionadas.

![Asignaciones para una hoja de cálculo con cuatro columnas, todas ellas asignadas automáticamente](../modules/modulesfiles/csvimport_ItemSet1.png)

#### Opciones de asignación

Para asignar un encabezado de columna a una propiedad del vocabulario, haz clic en el botón con el símbolo «+» situado a la izquierda del encabezado de la columna. Esto abrirá un panel deslizante en la parte derecha de la pantalla.

El panel deslizante ofrece varias opciones de asignación:

**Propiedades**: Selecciona una propiedad a la que asignar los datos de la columna, de cualquiera de los vocabularios instalados. Utiliza el campo «Filtro» para buscar una propiedad específica entre las disponibles.

![Opción «Propiedades» abierta, mostrando todos los vocabularios instalados para la instalación de Omeka S: Dublin Core, Ontología Bibliográfica, Friend of a Friend, Scripto y OWL-Time Ontology.](../modules/modulesfiles/csvimport_itemsMapProp.png)

**Datos específicos del conjunto de elementos** es una casilla de selección para «Abierto a adiciones». Márcala para permitir que otros usuarios editen o añadan elementos al conjunto. Déjala sin marcar para que el conjunto de elementos solo sea editable por su creador, los administradores del sitio y los administradores globales.

![Añadir el panel de asignación que muestra la sección «Datos específicos del conjunto de elementos». Debajo del encabezado de la sección hay una única casilla de selección desmarcada con la etiqueta «Abierto a nuevas entradas».](../modules/modulesfiles/csvimport_itemSetSD.png)

**Datos genéricos** también cuenta con un menú desplegable en el que puedes seleccionar una de estas cuatro opciones:

- **Plantilla de recurso (por etiqueta)**: Establece la plantilla de un conjunto de elementos por su nombre. El nombre de la plantilla tal y como se ha introducido en la hoja de cálculo y el nombre de la plantilla en Omeka S deben coincidir exactamente.
- **Clase de recurso (por término)**: Establece la clase de recurso para un conjunto de elementos. El término de la clase en la hoja de cálculo y en la instalación de Omeka S debe coincidir exactamente; consulta la pestaña «Vocabularios» de tu instalación. Por ejemplo, introduce «dctype:Dataset», «dcterms:Location», «bibo:Interview» o «foaf:Person», separando el prefijo del vocabulario y el término con dos puntos, sin espacios.
- **Propietario (por dirección de correo electrónico)**: Establece el propietario de un conjunto de elementos mediante su dirección de correo electrónico. Debe ser la dirección de correo electrónico asociada a la cuenta del usuario en la instalación de Omeka S.
- **Visibilidad pública/privada**: Establece la visibilidad del conjunto de elementos. Utiliza «privado» o «público» en la hoja de cálculo.

![Menú desplegable tal y como se describe](../modules/modulesfiles/csvimport_itemsMapgeneric.png)

Asegúrate de hacer clic en «Aplicar cambios» en la parte inferior del panel; de lo contrario, no se guardará nada de lo que hayas configurado aquí.

Para eliminar una asignación, haz clic en el icono de la papelera en la fila correspondiente a esa asignación de datos. Se eliminará *únicamente* la asignación, no los datos de la columna.

Si tienes datos en una columna de tu CSV que no deseas importar a tu instalación de Omeka S, simplemente no asignes esa columna a ninguna propiedad ni tipo de datos.

#### Opciones de columna

Las opciones de columna son complementarias a las asignaciones. Si añades opciones sin asignar también los datos de la columna a un recurso, un medio u otros datos, no se importará nada.

Para acceder a las opciones de los datos de una columna de tu archivo CSV (representada por una fila en la tabla de importación), haz clic en el icono de la llave inglesa situado junto al encabezado de esa columna.

Esto abrirá un panel deslizante en la parte derecha de la ventana del navegador con las siguientes opciones:

- **Usar separador de valores múltiples**: Marca esta casilla para utilizar el separador de valores múltiples para los datos de esta columna. El separador de valores múltiples se configura en la página de importación inicial, pero puede cambiarlo en la pestaña «Configuración básica».  
- **Idioma**: Establece el idioma de esta columna utilizando la [etiqueta de idioma de la IETF](https://en.wikipedia.org/wiki/IETF_language_tag){target=_blank} para el idioma en el que está escrito el texto. Esto anulará lo que hayas introducido en la configuración básica.
- **Importar valores como privados**: Marca esta casilla para establecer como privados todos los valores de propiedad *de esta columna*.
- **Tipo de datos**: Un menú desplegable con al menos tres opciones, que se corresponden con los [valores](../content/items.md#values) que se pueden utilizar al añadir propiedades a un elemento:
	- Importar como texto (predeterminado).
  - Importar como referencia URL. Puedes establecer la etiqueta para el URI incluyendo el texto deseado tras un espacio, por ejemplo:  `http://example.com This Is The Label`
  - Importar como recurso Omeka S. Esto creará [recursos vinculados](../content/item-sets.md#linked-resources). Si seleccionas esta opción, debes elegir qué valores de propiedad deben coincidir para encontrar el recurso de Omeka deseado en tu instalación, en el siguiente menú desplegable **Propiedad identificadora del recurso**. Debe ser una propiedad única, por lo que «Título» puede no ser una buena opción. 
		- Puedes utilizar el ID interno de Omeka. El ID de un recurso es la secuencia numérica que aparece al final de la URL en la página de visualización o edición; así, para `/admin/item/11576` el ID es 11576. También puedes ver el ID del recurso en el panel lateral derecho de la página de visualización del recurso. Los elementos, los conjuntos de elementos y los archivos multimedia tienen todos un ID.
		- Puedes incluir recursos que se estén creando en el mismo archivo CSV, siempre y cuando los recursos a los que se enlaza ya se hayan creado en filas anteriores y se puedan encontrar mediante el valor de propiedad único indicado aquí. Si deseas hacerlo, te recomendamos establecer un número de lote bajo (incluso 1) en la pestaña «Configuración avanzada», para garantizar que los recursos se hayan creado por completo antes de que otro recurso nuevo intente vincularse a ellos. 
  - Si tienes instalados determinados módulos, como «Tipos de datos numéricos», puede que haya opciones adicionales de tipos de datos proporcionadas por dichos módulos.

Asegúrate de hacer clic en el botón «Aplicar cambios» situado en la parte inferior del panel para guardar los cambios. Para eliminar la configuración de una opción de columna, vuelve a hacer clic en el icono de la llave inglesa y deshaz los cambios manualmente.

#### Edición por lotes
Cuando selecciones una o más filas de la tabla (columnas de tu archivo CSV), puedes utilizar el botón «Opciones de edición por lotes» para aplicar las opciones de columna descritas anteriormente a varias columnas del CSV a la vez.

![Un panel desplegable ofrece opciones para modificar la configuración por lotes.](../modules/modulesfiles/csvimport_batchOptions2.png)

Asegúrate de hacer clic en el botón «Aplicar cambios» situado en la parte inferior del panel para guardar los cambios.

### Importación de conjuntos de elementos: pestaña «Configuración básica»

Esta configuración se aplica a todo el archivo CSV que estás importando. Ten en cuenta que esta configuración puede ser sobrescrita por las opciones de columna de la pestaña «Asignar a datos de Omeka S». Si una columna está asignada a una plantilla, clase o propietario, esos valores prevalecerán sobre esta configuración; al igual que los ajustes de las columnas de idioma y privacidad.

![La página «Configuración de importación para conjuntos de elementos», en la que se muestra la pestaña «Configuración básica», con las opciones que se enumeran a continuación. La visibilidad está establecida en «Pública» y el separador de valores múltiples es «;»; las demás opciones están vacías.](../modules/modulesfiles/csvimport_ItemSetBasic.png)

- **Plantilla de recurso**: Selecciona una plantilla de recurso del menú desplegable para aplicarla a los conjuntos de elementos importados. Puedes utilizar el campo de búsqueda situado en la parte superior del menú desplegable para filtrar los resultados o encontrar una plantilla concreta.
- **Clase**: Selecciona una clase del menú desplegable para aplicarla a los conjuntos de elementos importados. Puedes utilizar el campo de búsqueda situado en parte superior del menú desplegable para filtrar los resultados o encontrar una clase concreta.
- **Propietario**: Establece el propietario de los conjuntos de elementos seleccionando un usuario del menú desplegable. Puedes utilizar el campo de búsqueda situado en la parte superior del menú desplegable para filtrar los resultados o encontrar un usuario concreto.
- **Visibilidad**: Establece la visibilidad de los conjuntos de elementos importados como pública o privada.
- **Abierto/cerrado a nuevas entradas**: Establece si los usuarios que no sean el propietario (ni los administradores del sitio ni los globales) podrán añadir o editar los conjuntos de elementos.
- **Separador de valores múltiples**: Introduce aquí el carácter separador de valores múltiples, si has utilizado alguno.
 - Las columnas de datos de tu archivo CSV deben estar separadas por comas; sin embargo, dentro de esas columnas puedes añadir un carácter especial para crear entradas múltiples, por ejemplo, un punto y coma.
- **Idioma**: Establece el idioma de los valores de la hoja de cálculo utilizando la [etiqueta de idioma de la IETF](https://en.wikipedia.org/wiki/IETF_language_tag){target=_blank}.

### Pestaña «Configuración avanzada» de la importación de conjuntos de elementos

La pestaña «Configuración avanzada» incluye una opción para establecer el número de filas que se procesarán por lote. Por defecto, está configurado en 20. Sin embargo, si se producen errores durante una importación, es posible que desee establecerlo en 5 o incluso en 1 para solucionar el problema y determinar el origen del error.

![Página de configuración avanzada en la que solo se muestran el menú desplegable «Acción» y el campo para el número de filas a procesar. ](../modules/modulesfiles/csvimport_ItemSetAdv.png)

#### Acción

Esta configuración te permite cambiar la acción del proceso de una importación directa a una de las siguientes opciones:

- **Crear un nuevo recurso**: Opción predeterminada. Cada fila del CSV se convertirá en un nuevo recurso.
- **Añadir datos al recurso**: Añade nuevos datos al recurso, basándose en el identificador de un recurso existente. (No se puede deshacer.) Esta opción te permite proporcionar varios valores para el mismo conjunto de elementos; cada fila se añadirá (es decir, puedes añadir un título a un conjunto de elementos en una fila y añadir otro título al mismo conjunto de elementos en otra fila).
- **Modificar los datos del recurso**: Sustituye los datos existentes del recurso por los datos del archivo CSV, *excepto si* la celda correspondiente del CSV está vacía. (No se puede deshacer.)
- **Actualizar los datos del recurso**: Sustituye los datos existentes del recurso por los datos del archivo CSV, *incluso cuando* la celda correspondiente del CSV esté vacía. (No se puede deshacer.)
- **Sustituir todos los datos del recurso**: Eliminar todas las propiedades del recurso y rellenarlas con la nueva información de la hoja. (No se puede deshacer.)
- **Eliminar el recurso**: Eliminar todos los recursos coincidentes. (No se puede deshacer.)

Si seleccionas una de estas opciones en el menú desplegable, aparecerán tres ajustes adicionales en la pestaña. Estos ajustes ayudan al proceso a determinar sobre qué recursos se debe actuar.

![Pestaña «Opciones avanzadas» con las opciones que se describen a continuación](../modules/modulesfiles/csvimport_itemSetAdvAct.png)

- **Columna de identificador de recurso**: Selecciona de un menú desplegable las columnas de tu archivo CSV. Se trata de los datos de tu hoja de cálculo que se asignan a datos existentes en tu instalación de Omeka S. No es necesario asignar esta columna en la otra pestaña.
- **Propiedad de identificador de recurso**: Selecciona de un menú desplegable entre todas las propiedades de tu instalación de Omeka S. Debe ser la propiedad en la que ya tengas datos y que hayas utilizado para crear los datos de la columna anterior.
  - Ejemplo: si los datos de la columna «Identificador de recurso» son «Título», y la primera fila de datos tiene por título «Un estudio en escarlata», y configura la propiedad «Identificador de recurso» como «Dublin Core: Título», las acciones se aplicarán a un recurso que ya se encuentre en tu instalación de Omeka S y cuya propiedad dc:title sea «Un estudio en escarlata».
	- Esto solo funcionará con coincidencias exactas.
  - Si tienes más de un recurso con datos coincidentes, solo se aplicará la acción al recurso más antiguo.
- **Acción sobre recursos no identificados**: Esta opción determina qué hacer cuando no existe ningún recurso coincidente en la instalación de Omeka S, pero la acción seleccionada solo se aplica a un recurso existente («Añadir», «Revisar», «Actualizar» o «Sustituir»). Esta opción no se utiliza cuando la acción principal es «Crear» o «Eliminar». Las opciones disponibles son dos botones de opción:
  - Omitir la fila
  - Crear un nuevo recurso.

!!! Nota
	Ten en cuenta que al «Añadir» datos podrás introducir varias filas con el mismo identificador; los valores de cada fila se añadirán junto a los anteriores.

  Al «Revisar», «Actualizar» y «Sustituir» datos, se **borrarán** los datos introducidos en filas anteriores de tu CSV, si las filas posteriores utilizan el mismo identificador. Si deseas importar varios valores (por ejemplo, dos valores de «Creador») en estos procesos, puedes: colocarlos en dos columnas de la misma fila, asignados a la misma propiedad; o bien, colocarlos en una sola celda y utilizar separadores de valores múltiples. No olvides especificar tu separador de valores múltiples en la pestaña «Configuración básica» y marcar la casilla «Usar separador de valores múltiples» en las opciones (icono de llave inglesa) de cada columna.

### Finalizar la importación
Una vez que hayas completado las asignaciones, las opciones de las columnas y cualquier otra configuración, haz clic en el botón «Importar» situado en la esquina superior derecha de la ventana del navegador. Esto debería iniciar la importación y redirigirte a la pestaña «Importaciones anteriores». Deberías ver un mensaje de confirmación que diga «Importando en ID de tarea [número]».

## Importar archivos multimedia
Para importar archivos multimedia, selecciona «Archivos multimedia» en «Tipo de importación» en la primera página.

Para importar archivos multimedia, debes tener una columna en el archivo CSV que se corresponda con los datos de los elementos. Los archivos multimedia no pueden existir a menos que estén asociados a un elemento mediante un identificador único (ID de elemento de Omeka, título, etc.). Ten en cuenta que, si estás ejecutando una tarea avanzada, como una actualización o sustitución, no es necesario que haya una columna con datos de elementos asociados, sino solo una forma de hacer coincidir las filas con los archivos multimedia que ya existen.

Al hacer clic en «Siguiente», se cargará la página con las siguientes pestañas:

### Asignar a datos de Omeka S
Esta pestaña muestra una tabla con las columnas de tu hoja de cálculo como filas. Cada fila muestra:

- una casilla de selección
- el encabezado de la columna de la hoja de cálculo
- un botón con el símbolo «+» para añadir o modificar una asignación
- un botón con el símbolo de una llave inglesa para acceder a las opciones de las columnas de la hoja de cálculo
- una columna que muestra las propiedades asignadas, ya sea de forma automática o manual
- una papelera para eliminar las asignaciones existentes
- una columna que muestra las opciones concretas seleccionadas.

![Asignaciones para una hoja de cálculo con diez columnas. Algunas de las columnas, como las denominadas «Descripción» y «Título», se han asignado automáticamente a propiedades de Dublin Core.](../modules/modulesfiles/csvimport_mediaMap1.png)

#### Opciones de asignación

Para asignar el encabezado de una columna a una propiedad del vocabulario, haz clic en el botón con el símbolo de más situado a la izquierda del encabezado de la columna. Esto abrirá un panel deslizante en la parte derecha de la pantalla.

El panel desplegable ofrece varias opciones de asignación:

**Propiedades**: Selecciona una propiedad a la que asignar los datos de la columna, de cualquiera de los vocabularios instalados. Utiliza el campo «Filtro» para buscar una propiedad específica entre las disponibles.

![Opción «Propiedades» abierta, mostrando todos los vocabularios instalados para la instalación de Omeka S: Dublin Core, Ontología Bibliográfica, Friend of a Friend, Scripto y Ontología OWL-Time.](../modules/modulesfiles/csvimport_itemsMapProp.png)

**Datos específicos de los archivos multimedia** cuenta con un menú desplegable para seleccionar el elemento al que se debe añadir el medio. Puedes utilizar el ID interno del elemento o buscar coincidencias con cualquiera de sus propiedades únicas (título, descripción). El ID de un elemento es la secuencia numérica que aparece al final de la URL en la página de visualización o edición; así, para `/admin/item/11576`, el ID es 11576. También puedes ver el ID del elemento en el panel lateral derecho de la página de visualización del elemento.

![Datos específicos de los medios con menú desplegable](../modules/modulesfiles/csvimport_mediaMapData.png)

Los **datos genéricos** también cuentan con un menú desplegable en el que puedes seleccionar una de estas cuatro opciones:

- **Plantilla de recurso (por etiqueta)**: Establece la plantilla para el recurso multimedia por su nombre. El nombre de la plantilla tal y como se ha introducido en la hoja de cálculo y el nombre de la plantilla en Omeka S deben coincidir exactamente.
- **Clase de recurso (por término)**: Establece la clase de recurso para el material multimedia. El término de la clase que figure en la hoja de cálculo y en la instalación de Omeka S debe coincidir exactamente; consulta la pestaña «Vocabularios» de tu instalación. Por ejemplo, introduce «dctype:Dataset», «dcterms:Location», «bibo:Interview» o «foaf:Person», separando con dos puntos el prefijo del vocabulario y el término, sin espacios.
- **Propietario (por dirección de correo electrónico)**: Establece el propietario del recurso multimedia mediante su dirección de correo electrónico. Debe ser la dirección de correo electrónico asociada a la cuenta del usuario en la instalación de Omeka S.
- **Visibilidad pública/privada**: Establece la visibilidad del archivo multimedia. Utiliza «privado» o «público» en la hoja de cálculo.

![Menú desplegable tal y como se describe](../modules/modulesfiles/csvimport_itemsMapgeneric.png)

**Origen del archivo multimedia**: Para la columna de tu hoja de cálculo que hace referencia al archivo multimedia que estás creando, selecciona de qué tipo de archivo multimedia se trata en el menú desplegable:

- HTML
- Imagen IIIF (enlace)
- Presentación IIIF (enlace)
- oEmbed (enlace)
- URL
- YouTube (enlace).

Pueden aparecer aquí otras opciones en función de los módulos activos, como «Carga lateral de archivos». 

Asegúrate de hacer clic en «Aplicar cambios» en la parte inferior del panel; de lo contrario, no se guardará nada de lo que hayas configurado aquí.

Para eliminar una asignación, haz clic en el icono de la papelera en la fila correspondiente a esa asignación de datos. Esto eliminará *únicamente* la asignación, no los datos de la columna.

Si tienes datos en una columna de tu archivo CSV que no deseas importar a tu instalación de Omeka S, simplemente no asignes esa columna a ninguna propiedad ni tipo de datos.

#### Opciones de columna

Las opciones de columna son independientes de las asignaciones. Si añades opciones sin asignar también los datos de la columna a un recurso, un medio u otros datos, no se importará nada.

Para acceder a las opciones de los datos de una columna de tu archivo CSV (representada por una fila en la tabla de importación), haz clic en el icono de la llave inglesa situado junto al encabezado de esa columna.

![menú desplegable con las opciones que se describen a continuación](../modules/modulesfiles/csvimport_mediaColOpt.png)

Esto abrirá un panel deslizante en la parte derecha de la ventana del navegador con las siguientes opciones:

- **Usar separador de valores múltiples**: marca esta casilla para utilizar el separador de valores múltiples para los datos de esta columna. El separador de valores múltiples se configura en la página de importación inicial, pero puedes cambiarlo en la pestaña «Configuración básica».  
- **Idioma**: Establece el idioma de esta columna utilizando la [etiqueta de idioma de la IETF](https://en.wikipedia.org/wiki/IETF_language_tag){target=_blank} correspondiente al idioma en el que está escrito el texto. Esto anulará lo que hayas introducido en la configuración básica.
- **Importar valores como privados**: Marca esta casilla para establecer como privados todos los valores de las propiedades *de esta columna*.
- **Tipo de datos**: Un menú desplegable con al menos tres opciones, que se corresponden con los [valores](../content/items.md#values) que se pueden utilizar al añadir propiedades a un elemento:
  - Importar como texto (por defecto).
  - Importar como referencia URL. Puedes establecer la etiqueta para el URI incluyendo el texto deseado tras un espacio, por ejemplo:  `http://example.com This Is The Label`.
  - Importar como recurso Omeka S. Esto creará [recursos enlazados](../content/media.md#omeka-resource). Si seleccionas esta opción, debes elegir qué valores de propiedad deben coincidir para encontrar el recurso de Omeka deseado en tu instalación, en el siguiente menú desplegable **Propiedad identificadora del recurso**. Debe ser una propiedad única, por lo que «Título» puede no ser una buena opción. 
 - Puedes utilizar el ID interno de Omeka. El ID de un recurso es la secuencia numérica que aparece al final de la URL en la página de visualización o edición; así, para `/admin/item/11576`, el ID es 11576. También puedes ver el ID del recurso en elde la página de visualización del recurso. Los elementos, los conjuntos de elementos y los archivos multimedia tienen todos un ID.
		- Puedes incluir recursos (elementos o conjuntos de elementos) que se estén creando en el mismo archivo CSV, siempre que los recursos a los que se va a enlazar ya se hayan creado en filas anteriores y puedan localizarse mediante el valor de propiedad único indicado aquí. Si deseas hacerlo, te recomendamos establecer un número de lote bajo (incluso 1) en la pestaña «Configuración avanzada», para garantizar que los recursos se hayan creado por completo antes de que otro recurso nuevo intente vincularse a ellos. 
  - Si tienes instalados determinados módulos, como «Tipos de datos numéricos», es posible que dichos módulos ofrezcan opciones adicionales de tipos de datos.

Recuerda hacer clic en el botón «Aplicar cambios». Para eliminar la configuración de una opción de columna, vuelve a hacer clic en el icono de la llave inglesa y deshaz los cambios manualmente.

#### Edición por lotes
Cuando selecciones una o más filas de la tabla (columnas de tu archivo CSV), puedes utilizar el botón «Opciones de edición por lotes» para aplicar las opciones de columna descritas anteriormente a varias columnas del CSV a la vez.

![Un panel desplegable ofrece opciones para modificar la configuración de forma masiva.](../modules/modulesfiles/csvimport_batchOptions2.png)

Asegúrate de hacer clic en el botón «Aplicar cambios» situado en la parte inferior del panel desplegable para guardar los cambios.

### Ajustes básicos de importación de archivos multimedia
Estos ajustes se aplican a todo el archivo CSV que estás importando. Ten en cuenta que estos ajustes pueden ser sobrescritos por las opciones de columna de la pestaña «Asignar a datos de Omeka S». Si una columna está asignada a una plantilla, clase o propietario, esos valores prevalecerán sobre estos ajustes; lo mismo ocurrirá con los ajustes de columna para el idioma y la privacidad.

- **Plantilla de recurso**: Selecciona una plantilla de recurso en el menú desplegable para aplicarla a los archivos multimedia importados. Puedes utilizar el campo de búsqueda situado en la parte superior del menú desplegable para filtrar los resultados o encontrar una plantilla concreta. 
- **Clase**: Selecciona una clase en el menú desplegable para aplicarla a los archivos multimedia importados. Puede utilizar el campo de búsqueda situado en la parte superior del menú desplegable para filtrar los resultados o encontrar una clase concreta. 
- **Propietario**: Establezca el propietario de los archivos multimedia seleccionando un usuario del menú desplegable. Puede utilizar el campo de búsqueda situado en la parte superior del menú desplegable para filtrar los resultados o encontrar un usuario concreto. 
- **Visibilidad**: Establece la visibilidad de los archivos multimedia importados como pública o privada.
- **Separador de valores múltiples**: Introduce aquí el carácter separador de valores múltiples, si has utilizado alguno.
      - Las columnas de datos de tu archivo CSV deben estar separadas por comas; sin embargo, dentro de esas columnas puedes añadir un carácter especial para crear entradas múltiples, por ejemplo, un punto y coma.
- **Idioma**: Establece el idioma de los valores de la hoja de cálculo utilizando la [etiqueta de idioma IETF](https://en.wikipedia.org/wiki/IETF_language_tag){target=_blank}.

### Ajustes avanzados de importación de medios
En esta pestaña hay dos opciones destinadas exclusivamente a usuarios avanzados.

El ajuste «Acción» te permite cambiar la acción del proceso de una importación directa a una de las siguientes opciones:

- **Crear un nuevo recurso**: Opción predeterminada. Cada fila del CSV se convertirá en un nuevo recurso.
- **Añadir datos al recurso**: Añade nuevos datos al recurso. 
- **Revisar los datos del recurso**: sustituye los datos existentes en el recurso por los del archivo CSV, salvo si están vacíos.
- **Actualizar los datos del recurso**: sustituye los datos existentes en el recurso por los del archivo CSV, incluso cuando la celda esté vacía.
- **Sustituir todos los datos del recurso**: Elimina todas las propiedades del recurso y rellénalas con la nueva información de la hoja.
- **Eliminar el recurso**: Elimina todos los recursos que coincidan.

Si seleccionas una de estas opciones en el menú desplegable, aparecerán tres ajustes adicionales en la pestaña. Estos ajustes ayudan al proceso a determinar sobre qué recursos se debe actuar.

![Opciones descritas a continuación](../modules/modulesfiles/csvimport_mediaAdvAct.png)

- **Columna de identificador de recurso**: Selecciona de un menú desplegable una de las columnas de tu archivo CSV. Se trata de los datos de tu hoja de cálculo que se asignan a los datos existentes en tu instalación de Omeka S. No es necesario asignar esta columna en la otra pestaña.
- **Propiedad de identificador de recurso**: Selecciona de un menú desplegable entre todas las propiedades de tu instalación de Omeka S. Debe ser la propiedad en la que ya tengas datos y que hayas utilizado para crear los datos de la columna anterior.
	- Ejemplo: si los datos de la columna «Identificador de recurso» son «Título», y la primera fila de datos tiene por título «Un estudio en escarlata», y configuras la propiedad «Identificador de recurso» como «Dublin Core: Título», las acciones se aplicarán a un recurso que ya se encuentre en su instalación de Omeka S y cuya propiedad `dcterms:title` sea «Un estudio en escarlata».
  - Esto solo funcionará con coincidencias exactas.
  - Si tienes más de un recurso con datos coincidentes, solo se aplicará la acción al recurso más antiguo.
- **Acción sobre recursos no identificados**: Esta opción determina qué hacer cuando no existe ningún recurso coincidente en la instalación de Omeka S, pero la acción seleccionada solo se aplica a un recurso existente («Añadir», «Revisar», «Actualizar» o «Reemplazar»). Esta opción no se utiliza cuando la acción principal es «Crear» o «Eliminar». Las opciones disponibles son dos botones de opción:
  - Omitir la fila
  - Crear un nuevo recurso.

Además de lo anterior, la pestaña «Configuración avanzada» cuenta con una opción para establecer el número de filas que se procesarán por lote. Por defecto, está configurado en 20. Sin embargo, si se producen errores durante una importación, es posible que desee establecerlo en 5 o incluso en 1 para solucionar el problema y determinar el origen del error.

!!! Nota
	Ten en cuenta que la opción «Añadir datos» te permitirá introducir varias filas con el mismo identificador; los valores de cada fila se añadirán junto a los anteriores.

  Las opciones «Revisar», «Actualizar» y «Sustituir» **borrarán** los datos introducidos en filas anteriores de tu archivo CSV, si las filas posteriores utilizan el mismo identificador. Si deseas importar varios valores (por ejemplo, dos valores de «Creador») en estos procesos, puedes: colocarlos en dos columnas de la misma fila, asignados a la misma propiedad; o bien, colocarlos en una sola celda y utilizar separadores de valores múltiples. No olvides especificar tu separador de valores múltiples en la pestaña «Configuración básica» y marcar la casilla «Usar separador de valores múltiples» en las opciones (icono de la llave inglesa) de cada columna.

### Finalizar la importación
Una vez que hayas completado las asignaciones, las opciones de las columnas y cualquier otra configuración, haz clic en el botón «Importar» situado en la esquina superior derecha de la ventana del navegador. Esto debería iniciar la importación y redirigirte a la pestaña «Importaciones anteriores». Deberías ver un mensaje de confirmación que diga «Importando con ID de tarea [número]».

## Importación de recursos mixtos
Esta opción de recursos te permite importar una hoja de cálculo con una combinación de tipos de recursos: elementos, conjuntos de elementos y archivos multimedia.

### Asignar a datos de Omeka S
Esta pestaña muestra un menú desplegable inicial sobre una tabla en la que las columnas de tu hoja de cálculo aparecen como filas. Cada fila muestra:

- una casilla de selección
- el encabezado de la columna de la hoja de cálculo
- un botón con el símbolo «+» para añadir o modificar una asignación
- un botón con el símbolo de una llave inglesa para las opciones de las columnas de la hoja de cálculo
- una columna que muestra las propiedades asignadas, ya sea de forma automática o manual
- una papelera para eliminar las asignaciones existentes
- una columna para mostrar las opciones concretas seleccionadas.

![Asignaciones para una hoja de cálculo con nueve columnas.](../modules/modulesfiles/csvimport_mixedR1.png)

El menú desplegable situado encima de la tabla es donde se establece qué columna del archivo CSV indica si los datos de esa fila corresponden a un elemento, un conjunto de elementos o un recurso multimedia. No es necesario asignar estos datos en la tabla de esta pestaña. Los valores de esta columna pueden ser `item` o `items`, «conjunto de elementos» o «conjuntos de elementos», o «conjuntos de elementos», o «conjuntos de elementos», o «contenido multimedia». Otros valores, o los campos vacíos, harán que la fila no se importe.

Las filas con «contenido multimedia» en la columna de tipo de recurso deben indicar a qué elemento se van a adjuntar, tal y como se indica en la [sección Contenido multimedia anterior](#import-media), y requieren que se incluya una fuente multimedia.

#### Opciones de asignación

Para asignar un encabezado de columna a una propiedad del vocabulario, haz clic en el botón con el símbolo más situado a la izquierda del encabezado de la columna. Esto abrirá un panel deslizante en la parte derecha de la pantalla.

El panel deslizante ofrece varias opciones de asignación:

**Propiedades** selecciona una propiedad a la que asignar los datos de la columna, de cualquiera de los vocabularios instalados. Utiliza el campo «Filtro» para buscar una propiedad específica entre las disponibles.
![Opción «Propiedades» abierta, mostrando todos los vocabularios instalados para la instalación de Omeka S: Dublin Core, Ontología Bibliográfica, Friend of a Friend, Scripto y OWL-Time Ontology.](../modules/modulesfiles/csvimport_itemsMapProp.png)

**Los datos específicos del elemento** cuentan con un menú desplegable para establecer el conjunto de elementos según la propiedad seleccionada. Si tienes una columna con datos de un conjunto de elementos al que deseas añadir el elemento, puedes configurar cómo se asigna mediante este menú desplegable. Puede utilizar el ID interno del conjunto de elementos o cualquiera de sus propiedades (título, descripción).

![menú desplegable tal y como se describe](../modules/modulesfiles/csvimport_itemsMapISD.png)

**Datos específicos del conjunto de elementos**: es una casilla de selección para «Abierto a nuevas incorporaciones». Márcala para permitir que otros usuarios editen o añadan elementos al conjunto de elementos. Déjala sin marcar para que el conjunto de elementos solo pueda ser editado por su creador, los administradores del sitio y los administradores globales.

![Panel de asignación que muestra la sección «Datos específicos del conjunto de elementos». Debajo del encabezado de la sección hay una única casilla de selección sin marcar con la etiqueta «Abierto a nuevas incorporaciones».](../modules/modulesfiles/csvimport_itemSetSD.png)

**Datos específicos del medio** cuenta con un menú desplegable para seleccionar el elemento al que se debe añadir el medio. Puedes utilizar el ID interno del elemento o cualquiera de sus propiedades (título, descripción). El ID de un elemento es la secuencia numérica que aparece al final de la URL en la página de visualización o edición; así, para `/admin/item/11576`, el ID es 11576. También puedes ver el ID del elemento en el panel de la derecha de la página de visualización del mismo.

![Datoscon menú desplegable](../modules/modulesfiles/csvimport_mediaMapData.png)

**Datos genéricos** cuenta con un menú desplegable en el que puedes seleccionar una de estas cuatro opciones:

- **Plantilla de recurso (por etiqueta)**: Establece la plantilla para el recurso multimedia por su nombre. El nombre de la plantilla tal y como se ha introducido en la hoja de cálculo y el nombre de la plantilla en Omeka S deben coincidir exactamente.
- **Clase de recurso (por término)**: Establece la clase de recurso para el recurso multimedia. El término de la clase en la hoja de cálculo y en la instalación de Omeka S debe coincidir exactamente.
- **Propietario (por dirección de correo electrónico)**: Establece el propietario del archivo multimedia mediante su dirección de correo electrónico. Debe ser la dirección de correo electrónico asociada a la cuenta del usuario en la instalación de Omeka S.
- **Visibilidad pública/privada**: Establece la visibilidad del archivo multimedia. Utiliza «privada» o «pública» en la hoja de cálculo.

![Menú desplegable tal y como se describe](../modules/modulesfiles/csvimport_itemsMapgeneric.png)

**Fuente del recurso multimedia** Para las columnas de la hoja de cálculo que hacen referencia al recurso multimedia, selecciona para cada columna una de las siguientes opciones del menú desplegable:

- HTML
- Imagen IIIF (enlace)
- Presentación IIIF (enlace)
- oEmbed (enlace)
- URL
- YouTube (enlace).

Pueden aparecer aquí otras opciones en función de los módulos activos, como «Carga lateral de archivos». 

Asegúrate de hacer clic en «Aplicar cambios» en la parte inferior del panel; de lo contrario, no se guardará nada de lo que hayas configurado aquí.

Para eliminar una asignación, haz clic en el icono de la papelera en la fila correspondiente a esa asignación de datos. Esto eliminará *únicamente* la asignación, no los datos de la columna.

Si tienes datos en una columna de tu archivo CSV que no deseas importar a tu instalación de Omeka S, simplemente no asignes esa columna a ninguna propiedad ni tipo de datos.

#### Opciones de columna

Las opciones de columna son independientes de las asignaciones. Si añades opciones sin asignar también los datos de la columna a un recurso, un medio u otros datos, no se importará nada.

Para acceder a las opciones de los datos de una columna de tu archivo CSV (representada por una fila en la tabla de importación), haz clic en el icono de la llave inglesa situado junto al encabezado de esa columna.

Esto abrirá un panel deslizante en la parte derecha de la ventana del navegador con las siguientes opciones:

- **Usar separador de valores múltiples**: Marca esta casilla para utilizar el separador de valores múltiples para los datos de esta columna. El carácter separador de valores múltiples se configura en la página de importación inicial, pero puede modificarse en la pestaña «Configuración básica».
- **Idioma**: Establece el idioma de esta columna utilizando la [etiqueta de idioma de la IETF](https://en.wikipedia.org/wiki/IETF_language_tag){target=_blank} correspondiente al idioma en el que está escrito el texto. Esto anulará lo que hayas introducido en la configuración básica.
- **Importar valores como privados**: Marca esta casilla para establecer como privados todos los valores de las propiedades *de esta columna*.
- **Tipo de datos**: Un menú desplegable con al menos tres opciones, que se corresponden con los [valores](../content/items.md#values) que se pueden utilizar al añadir propiedades a un elemento:
  - Importar como texto (predeterminado).
	- Importar como referencia URL. Puedes establecer la etiqueta para el URI incluyendo el texto deseado tras un espacio, por ejemplo: `http://example.com This Is The Label`.
	- Importar como recurso de Omeka S. Esto creará [recursos vinculados](../content/items.md#linked-resources). Si seleccionas esta opción, debes elegir qué valores de propiedad deben coincidir para encontrar el recurso de Omeka deseado en tu instalación, en el siguiente menú desplegable **Propiedad identificadora del recurso** . Debe ser una propiedad única, por lo que «Título» puede no ser una buena opción. 
 - Puedes utilizar el ID interno de Omeka. El ID de un recurso es la secuencia numérica que aparece al final de la URL en la página de visualización o edición; así, para `/admin/item/11576` el ID es 11576. También puedes ver el ID del recurso en el panel de la derecha de la página de visualización del recurso. Los elementos, los conjuntos de elementos y los archivos multimedia tienen todos un ID.
		- Puedes incluir recursos que se estén creando en el mismo archivo CSV, siempre y cuando los recursos a los que se enlaza ya se hayan creado en filas anteriores y se puedan localizar mediante el valor de la propiedad única indicado aquí. Si deseas hacerlo, te recomendamos establecer un número de lote bajo (incluso 1) en la pestaña «Configuración avanzada», para garantizar que los recursos se hayan creado por completo antes de que otro recurso nuevo intente vincularse a ellos. 
  - Si tienes instalados determinados módulos, como «Tipos de datos numéricos», es posible que dichos módulos ofrezcan opciones adicionales de tipos de datos.

Asegúrate de hacer clic en el botón «Aplicar cambios» situado en la parte inferior del panel. Para eliminar la configuración de una opción de columna, vuelve a hacer clic en el icono de la llave inglesa y deshaz los cambios manualmente.

#### Edición por lotes
Cuando selecciones una o más filas de la tabla (columnas de tu archivo CSV), puedes utilizar el botón «Opciones de edición por lotes» para aplicar las opciones de columna descritas anteriormente a varias columnas del CSV a la vez.

![Un panel ofrece opciones para modificar la configuración de forma masiva.](../modules/modulesfiles/csvimport_batchOptions2.png)

Asegúrate de hacer clic en el botón «Aplicar cambios» situado en la parte inferior del panel para guardar los cambios.

### Configuración básica de la importación de recursos mixtos

Esta configuración se aplica a todo el archivo CSV que estás importando. Ten en cuenta que esta configuración puede ser sobrescrita por las opciones de columna de la pestaña «Asignar a datos de Omeka S». Si una columna está asignada a una plantilla, clase o propietario, esos valores prevalecerán sobre esta configuración; lo mismo ocurrirá con la configuración de columna para el idioma y la privacidad.

![opciones tal y como se describen a continuación](../modules/modulesfiles/csvimport_mixedRBasic.png)

- **Plantilla de recurso**: Selecciona una plantilla de recurso en el menú desplegable para aplicarla a los conjuntos de elementos importados. Puedes utilizar el campo de búsqueda situado en la parte superior del menú desplegable para filtrar los resultados o encontrar una plantilla concreta.
- **Clase**: Selecciona una clase del menú desplegable para aplicarla a los conjuntos de elementos importados. Puedes utilizar el campo de búsqueda situado en la parte superior del menú desplegable para filtrar los resultados o encontrar una clase concreta.
- **Propietario**: Establece el propietario de los conjuntos de elementos seleccionando un usuario del menú desplegable. Puedes utilizar el campo de búsqueda situado en la parte superior del menú desplegable para filtrar los resultados o buscar un usuario concreto.
- **Visibilidad**: Establece la visibilidad de los conjuntos de elementos importados como pública  o privada.
- **Conjuntos de elementos abiertos/cerrados a nuevas incorporaciones**: Establece si los usuarios que no sean el propietario (ni los administradores del sitio ni los globales) podrán añadir o editar los conjuntos de elementos.
- **Conjunto de elementos para los elementos**: Selecciona uno de los conjuntos de elementos existentes en el menú desplegable.
- **Sitios para los elementos**: Selecciona uno o varios de tus sitios existentes para añadir nuevos elementos como recursos.
- ****Separador de valores múltiples**: Introduce aquí el carácter separador de valores múltiples, si has utilizado alguno.
 - Las columnas de datos de tu archivo CSV deben estar separadas por comas; sin embargo, dentro de esas columnas puedes añadir un carácter especial para crear entradas múltiples, por ejemplo, un punto y coma.
- **Idioma**: Establece el idioma de los valores de la hoja de cálculo utilizando la [etiqueta de idioma de la IETF](https://en.wikipedia.org/wiki/IETF_language_tag){target=_blank} adecuada.

### Configuración avanzada de la importación de recursos mixtos

La configuración «Acción» te permite cambiar la acción del proceso de una importación directa a una de las siguientes opciones:

- **Crear un nuevo recurso**: Opción predeterminada. Cada fila del archivo CSV se convertirá en un nuevo recurso.
- **Añadir datos al recurso**: Añade nuevos datos al recurso.
- **Modificar los datos del recurso**: sustituye los datos existentes en el recurso por los del archivo CSV, salvo si están vacíos.
- **Actualizar los datos del recurso**: sustituye los datos existentes en el recurso por los del archivo CSV, incluso cuando la celda esté vacía.
- **Sustituir todos los datos del recurso**: Elimina todas las propiedades del recurso y rellénalas con la nueva información de la hoja.
- **Eliminar el recurso**: Elimina todos los recursos que coincidan.

Si seleccionas una de estas opciones en el menú desplegable, aparecerán tres ajustes adicionales en la pestaña. Estos ajustes ayudan al proceso a determinar sobre qué recursos se debe actuar.

![Opciones descritas a continuación](../modules/modulesfiles/csvimport_mixedRAdvAct.png)

- **Columna de identificador del recurso**: Selecciona de un menú desplegable las columnas de tu CSV. Se trata de los datos de tu hoja de cálculo que se asignan a los datos existentes en tu instalación de Omeka S.
- **Propiedad de identificador de recurso**: Selecciona de un menú desplegable entre todas las propiedades de tu instalación de Omeka S. Debe ser la propiedad en la que ya tengas datos y que hayas utilizado para crear los datos de la columna anterior.
  - Ejemplo: si los datos de la columna «Identificador de recurso» son «Título», y la primera fila de datos tiene por título «Un estudio en escarlata», y configuras la propiedad «Identificador de recurso» como «Dublin Core: Título», las acciones se aplicarán a un recurso que ya se encuentre en tu instalación de Omeka S y cuya propiedad dc:title sea «Un estudio en escarlata».
  - Esto solo funcionará con coincidencias exactas.
  - Si tienes más de un recurso con datos coincidentes, solo se aplicará la acción al recurso más antiguo.
- **Acción sobre recursos no identificados**: esta opción determina qué hacer cuando no existe ningún recurso coincidente en la instalación de Omeka S, pero la acción seleccionada solo se aplica a un recurso existente («Añadir», «Revisar», «Actualizar» o «Reemplazar»). Esta opción no se utiliza cuando la acción principal es «Crear» o «Eliminar». Las opciones disponibles son dos botones de opción:
  - Omitir la fila
  - Crear un nuevo recurso.

Además de lo anterior, la pestaña «Configuración avanzada» incluye una opción para establecer el número de filas que se procesarán por lote. Por defecto, está configurado en 20. Sin embargo, si se producen errores durante una importación, es posible que desees establecerlo en 5 o incluso en 1 para solucionar el problema y determinar el origen del error.

!!! Nota
	Ten en cuenta que la opción «Añadir datos» te permitirá introducir varias filas con el mismo identificador; los valores de cada fila se añadirán junto a los anteriores.

	La revisión, actualización y sustitución de datos **borrarán** los datos introducidos en filas anteriores de tu archivo CSV, si las filas posteriores utilizan el mismo identificador. Si deseas importar varios valores (por ejemplo, dos valores de «Creador») en estos procesos, puedes: colocarlos en dos columnas de la misma fila, asignados a la misma propiedad; o bien, colocarlos en una sola celda y utilizar separadores de valores múltiples. No olvides especificar tu separador de valores múltiples en la pestaña «Configuración básica» y marcar la casilla «Usar separador de valores múltiples» en las opciones (icono de la llave inglesa) de cada columna.

### Finalizar la importación
Una vez que hayas completado las asignaciones, las opciones de las columnas y cualquier otra configuración, haz clic en el botón «Importar» situado en la esquina superior derecha de la ventana del navegador. Esto debería iniciar la importación y redirigirte a la pestaña «Importaciones anteriores». Deberías ver un mensaje de confirmación que diga «Importando en ID de tarea [número]».

## Importar usuarios
Al importar usuarios, solo puedes importar datos relacionados con la tabla de usuarios de Omeka S: el correo electrónico del usuario, el nombre para mostrar y el rol. No se importarán los datos adicionales que contenga tu archivo CSV. Ninguna de estas propiedades puede ser multivalor.

Esta pestaña muestra un menú desplegable inicial situado encima de una tabla en la que las columnas de tu hoja de cálculo aparecen como filas. Cada fila muestra:

- Una casilla de selección
- Un encabezado de columna de la hoja de cálculo
- Un botón con el símbolo «+» para añadir o modificar una asignación
- Una papelera para eliminar asignaciones
- Una columna para mostrar las opciones seleccionadas.

![Tabla tal y como se ha descrito anteriormente, con filas para las columnas del CSV tituladas «correo electrónico», «nombre de visualización» y «rol».](../modules/modulesfiles/csvimport_users.png)

Para asignar un encabezado de columna a la información de un usuario, haz clic en el botón con el símbolo «+» situado a la izquierda del encabezado de la columna. Esto abrirá un panel deslizante en la parte derecha de la pantalla.

![Una flecha roja señala el botón con el signo más situado a la derecha del encabezado de la columna «correo electrónico».](../modules/modulesfiles/csvimport_usersMapButton.png)

El panel desplegable contiene un menú para la información de los usuarios, con tres opciones:

- **Correo electrónico**: la dirección de correo electrónico del usuario
- **Nombre para mostrar**: el nombre para mostrar del usuario
- **Rol**: el [rol](../admin/users.md#roles-and-permissions) del usuario.

Los valores de rol que se deben utilizar en esta importación son los siguientes:

- `global_admin`
- `site_admin`
- `editor`
- `reviewer`
- `author`
- `researcher`.

![La misma tabla que la anterior, ahora con el panel de asignación abierto y el menú desplegable activado para mostrar las tres opciones «Correo electrónico», «Nombre para mostrar» y «Rol».](../modules/modulesfiles/csvimport_usersMap.png)

Una vez completadas las asignaciones, haz clic en el botón «Importar».

!!! Nota
  **No** se notificará a los usuarios por correo electrónico cuando se les cree una cuenta mediante la importación CSV. Normalmente, cuando se crea una cuenta manualmente, se envía a la dirección de correo electrónico una notificación que incluye un enlace para establecer la contraseña. Actualmente, la importación CSV no envía esos correos electrónicos, por lo que los usuarios no pueden establecer sus propias contraseñas. Los administradores del sitio deben establecer las contraseñas y, a continuación, compartirlas manualmente una vez que se hayan creado los usuarios mediante la importación CSV.

## Gestionar importaciones anteriores

Para revisar las importaciones anteriores, haz clic en el módulo «Importación CSV» y selecciona la pestaña «Importaciones anteriores».

![Opciones de la subpestaña «Importación CSV» en el menú de navegación de la izquierda](../modules/modulesfiles/csvimport_pastimportsnav.png)

Esto mostrará una tabla con las siguientes columnas:

- Una casilla de selección **Deshacer**
- **Fecha** de la importación
- **Acción** de la importación (crear, añadir, revisar, actualizar, sustituir o eliminar).
  - Debajo de la descripción de la acción hay enlaces a los detalles de la tarea y al registro de la tarea.
- **Comentario** introducido durante la importación o que indica un error
- **Resultado**: los elementos actualizados, añadidos o eliminados
- **Estado** de la importación
- **Responsable** de la importación.

![Tabla de importaciones anteriores de CSV](../modules/modulesfiles/csvimport_pastimports.png)

Para ver los detalles de una importación, haz clic en el enlace «Detalles del trabajo» situado debajo de la descripción de la acción. Para revisar los registros, especialmente en los casos en los que se haya producido un error, haz clic en el enlace «Registro» situado debajo de la descripción de la acción.

## Deshacer una importación

Para deshacer una importación, haz clic en el módulo «Importación CSV» y selecciona la página «Importaciones anteriores».

Marca la casilla «Deshacer» en la fila de la importación que desee deshacer y haga clic en «Enviar».

![Una flecha roja señala una casilla «Deshacer» sin marcar en la página «Importaciones anteriores».](../modules/modulesfiles/csvimport_undo.png)

Dependiendo del tamaño de la importación, la acción de deshacer puede tardar algún tiempo. Una vez completada, el estado de la importación en la tabla «Importaciones anteriores» indicará «Deshacida», seguido de la fecha en la que se revirtió la importación.

## Solución de problemas
A continuación se enumeran los errores conocidos que pueden producirse durante una importación:  

- **Codificación**: Los archivos CSV para la importación deben estar codificados en UTF-8.
- ¿Tus tareas se inician pero no se completan? Es posible que tengas que [configurar la ruta de PHP](../configuration.md#php-path) para que tu sistema pueda ejecutar el proceso en segundo plano para crear los elementos.

## Integración con otros módulos
Algunos módulos añaden funcionalidades al proceso de importación de CSV. Si tienes estos módulos instalados y activos, tendrás acceso a las siguientes opciones al utilizar la importación de CSV.

### Vocabulario personalizado
Si tienes [Vocabulario personalizado](customvocab.md) instalado y activo, añadirá tus vocabularios personalizados como tipos de datos en Omeka. Puedes seleccionar estos tipos de datos durante la importación de CSV. 

### Extraer texto

Cuando el [módulo «Extraer texto»](extracttext.md) está habilitado, se intentará extraer el texto de cualquier archivo incorporado mediante un proceso de importación de CSV. Si está disponible, esto incluirá Tesseract, un procesador de imágenes que emplea el reconocimiento óptico de caracteres (OCR). Puedes desactivar extractores individuales en el menú de configuración de «Extracción de texto» para que no se ejecuten durante la importación. 

!!! nota
  Te recomendamos que desactives Tesseract, o todo el módulo «Extract Text», cuando realices una importación que incluya imágenes como fotografías o dibujos. La aplicación del OCR a imágenes que no contengan texto consumirá muchos recursos del procesador y puede causar problemas en la importación. 

### Carga lateral de archivos
Si tienes [Carga lateral de archivos](filesideload.md) (versión mínima 1.2.0) instalado y activo, puedes utilizarlo como fuente de archivos multimedia al realizar una importación CSV.

Todo lo que aparece en la pestaña **Mapeo a datos de Omeka S** será igual. Cuando añadas un mapeo y elijas la opción «Fuente multimedia», verás que ahora hay una opción para «Sideload».

![Menú desplegable de fuentes multimedia, con «Sideload» resaltado en azul](../modules/modulesfiles/csvimport_sideload.png)

Para los datos de esta columna, debes incluir el nombre completo del archivo, incluida la extensión. Así, por ejemplo, si quieres importar un archivo JPG llamado «Jekyll_and_Hyde_Title», los datos de la columna de archivos multimedia del CSV que estés importando deberían ser `Jekyll_and_Hyde_Title.jpg`.

### Asignación
Si tienes [Mapping](mapping.md#csv-import-integration) (versión mínima 1.1.0) instalado y activo, dispondrás de opciones adicionales en el panel lateral derecho al importar elementos. Ten en cuenta que estas opciones no aparecen para ningún otro tipo de importación, incluidos los recursos mixtos.

![Añadir panel de asignación con opciones adicionales para la latitud, la longitud y los límites del mapa](../modules/modulesfiles/csvimport_mapping1.png)

Para obtener más información, consulta la [sección de la página de asignación](mapping.md#csv-import-integration).

### Tipos de datos numéricos
Si tiene instalado y activo [Tipos de datos numéricos](numericdatatypes.md), se añadirá la opción de establecer el tipo de datos de una columna como datos numéricos.

Las opciones son:

- Fecha/hora (ISO 8601)
- Intervalo (ISO 8601)
- Duración (ISO 8601)
- Número (entero o decimal).

![Panel de opciones de la columna con el menú desplegable de tipos de datos abierto, en el que se muestran las opciones para los tipos de datos numéricos, así como las opciones estándar](../modules/modulesfiles/csvimport_numericdata.png)

Al importar datos como numéricos, estos deben tener un formato preciso. Comprueba siempre que tus datos se hayan importado correctamente en el formato elegido; la importación CSV dejará los valores en blanco si no se reconoce el formato. 

Utiliza los siguientes formatos ISO 8601 para importar [fechas](https://en.wikipedia.org/wiki/ISO_8601#Dates){target=_blank}, incluyendo guiones entre los valores:

- `2022`
- `2022-08` (año y mes, sin fecha)
- `2022-08-18`.

Utiliza los siguientes formatos ISO 8601 para añadir [horas](https://en.wikipedia.org/wiki/ISO_8601#Times){target=_blank} a tus valores de fecha:

- `2022-08-18T17:26:49+00:00` ([diferencia horaria respecto a UTC](https://en.wikipedia.org/wiki/ISO_8601#Time_offsets_from_UTC){target=_blank})
- `2022-08-18T17:26:49Z` ([tiempo universal coordinado](https://en.wikipedia.org/wiki/ISO_8601#Coordinated_Universal_Time_(UTC)){target=_blank}). 

No puedes omitir el año al indicar un mes y/un día. No se pueden indicar fechas ordinales (como, por ejemplo, `2000-175` para el día 175 del año 2000). 

Utiliza el siguiente formato para importar [intervalos](https://en.wikipedia.org/wiki/ISO_8601#Intervalos_de_tiempo){target=_blank} con puntos de inicio y fin:

- `2007-03-01T13:00:00Z/2008-05-11T15:30:00Z` (Inicio y fin).

Utiliza los siguientes formatos ISO 8601 para importar [duraciones](https://en.wikipedia.org/wiki/ISO_8601#Durations){target=_blank}, expresadas como número de años, número de meses, número de días, etc.:

- `P23DT23H` (23 días y 23 horas)
- `P3Y6M4DT12H30M5S` (3 años, 6 meses, 4 días, 12 horas, 30 minutos y 5 segundos).
