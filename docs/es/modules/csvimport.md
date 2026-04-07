# Importación CSV

El [módulo de importación CSV](https://omeka.org/s/modules/CSVImport){target=_blank} te permite importar elementos, conjuntos de elementos, archivos multimedia y usuarios a tu instalación de Omeka S desde un archivo CSV (valores separados por comas), TSV (valores separados por tabulaciones) u ODS (OpenDocument Spreadsheet). Este módulo solo está disponible para [usuarios con roles de administrador global y supervisor](../admin/users.md).

La importación CSV requiere que tu instalación de Omeka S [tenga PHP en funcionamiento para ejecutar tareas de importación en segundo plano](../install.md#test-and-set-the-php-path). Antes de utilizar la importación CSV, debes confirmar que PHP se reconoce desde la [página de información del sistema](../admin-dashboard.md#system-information). 

## Prepara tu archivo CSV

La mayoría de los editores de hojas de cálculo (incluidos Microsoft Excel, Google Sheets y Apple Numbers) pueden exportar a formato CSV, TSV u ODS. 

!!! nota
	Los archivos CSV para importar **deben estar codificados en UTF-8**, por lo que, al exportar o guardar un nuevo documento, asegúrate de comprobar que la codificación sea UTF-8.

La mayoría de las opciones de importación de CSV se basan en que solo importes un tipo de datos: una lista de elementos, una lista de conjuntos de elementos, una lista de medios, etc. Existe la opción de una [importación de recursos mixtos](#mixed-resource-import), que requiere una columna que identifique el tipo de cada fila.

Si la hoja de cálculo ya está creada, piensa qué columnas quieres que se correspondan con qué [propiedades del vocabulario](../content/vocabularies.md). Tu archivo CSV **debe tener una fila de encabezado** para que el módulo lo procese correctamente, por lo que es posible que tengas que añadir una fila en la parte superior con los nombres de las columnas.

Si tienes varias entradas para una misma propiedad, puedes separarlas con un **separador de valores múltiples**. Por ejemplo, una obra con varios autores (E.B. White y William Strunk Jr.) en la que la columna «Creador» contenga «E.B. White;William Strunk Jr» tiene un punto y coma (;) como separador de valores múltiples. Al importarla a Omeka S, cada uno de ellos aparecería como una entrada independiente en la propiedad (Creador: «E.B. White» y Creador: «William Strunk Jr."). Tenga en cuenta que la importación será la misma tanto si deja un espacio después del separador (como en «E.B. White; William Strunk Jr») como si no. 

### Nombres de columnas

Puede asignar manualmente cada columna a su propiedad correspondiente, y es necesario que asigne manualmente las columnas que no sean de metadatos, como la URL del archivo para la carga. El módulo asignará automáticamente las columnas de metadatos según los nombres proporcionados en la fila de encabezado, si se ajustan a los términos de propiedad de los [vocabularios](../content/vocabularies.md) de su instalación en el formato `prefijo:propiedad`. Por ejemplo, un archivo CSV con un encabezado de columna «dcterms:title» se asignaría automáticamente a la propiedad «Título» de Dublin Core cuando se cargue el CSV para la asignación. Puedes modificar estas columnas asignadas automáticamente antes de la importación.

Para encontrar los términos que debe utilizar para los encabezados de sus columnas, vaya a la pestaña Vocabularios desde el panel de administración. Haga clic en el número de propiedades del vocabulario que desea utilizar (por ejemplo, Dublin Core en la imagen siguiente).

En la tabla de propiedades del vocabulario, hay una columna para **Término**. Utilice el Término como encabezado de columna para la propiedad que desee asignar automáticamente en la importación CSV. Por ejemplo, «dcterms:abstract» se asignaría automáticamente a la propiedad «Abstract» de Dublin Core y «foaf:firstName» se asignaría automáticamente a la propiedad «firstName» de Friend of a Friend.

![flecha que apunta a la columna Término de las propiedades de Dublin Core.](../modules/modulesfiles/csvimport_automap2.png)

En la configuración inicial de importación hay una opción para realizar la asignación automática con etiquetas simples; esto funcionará con columnas cuyos nombres coincidan con una etiqueta del vocabulario, por ejemplo «title» o «abstract», sin necesidad de proporcionar el término. Tenga en cuenta que esta opción utiliza por defecto Dublin Core (`dcterms:title` y `dcterms:abstract`) antes de pasar a otros vocabularios instalados.

Si los nombres de sus columnas no coinciden exactamente y la función de asignación automática no los reconoce, debería etiquetarlos de forma que le resulte útil para poder asignarlos manualmente durante la importación.

Si tiene previsto importar por lotes metadatos o propiedades que vienen con un módulo (como la latitud y la longitud del módulo Mapping) o utilizar vocabularios estructurados que provienen de módulos (como los tipos de datos del módulo Value Suggest), instale y configure primero esos módulos para asegurarse de que los campos existen en el modelo de datos de su sitio, antes de intentar introducir información en ellos. Se pueden perder datos si desinstala esos módulos más adelante.

## Configuración inicial de la importación

Inicie una importación haciendo clic en la pestaña Importación CSV en el panel de navegación de la izquierda. Esto abrirá la página inicial «Configuración de importación». Para la mayoría de las hojas de cálculo exportadas directamente desde un programa de software en el formato correcto, estos ajustes pueden dejarse en sus valores predeterminados.

- Utilice el botón «Elegir archivo» para seleccionar una hoja de cálculo de su ordenador.
- En el menú desplegable **Delimitador de columnas CSV**, elija entre las siguientes opciones (debe coincidir con el formato de su archivo) el carácter que separa los diferentes valores en una fila:
  - coma (predeterminado)
  - punto y coma
  - dos puntos
  - tabulación
  - retorno de carro
  - espacio
  - barra vertical (`|`).

- En el menú desplegable **Delimitador de columna CSV**, elija la opción que delimita el texto largo en su archivo, si procede:
  - comillas dobles (predeterminado)
  - comillas
  - almohadilla (`#`).

- En el menú desplegable **Tipo de importación**, seleccione lo que va a importar:
  - Artículos
  - Conjuntos de artículos
  - Medios (se requiere una columna que relacione los medios con los artículos ya existentes)
	- Recursos mixtos (la hoja de cálculo puede incluir conjuntos de elementos, elementos y medios; se requiere una columna que identifique el tipo de cada fila)
  - Usuarios.

- Marque la casilla **Asignar automáticamente con etiquetas simples**. La importación CSV asignará automáticamente los encabezados de columna con formato especial (en `prefijo:propiedad`); si marca esta casilla, también asignará automáticamente cualquier encabezado de columna que coincida con las etiquetas de propiedades del vocabulario existentes (como «Título»). 

- Los **comentarios** aparecerán en la página «Importaciones anteriores»; esto puede resultarle útil para tomar nota de lo que se está importando y de cualquier configuración que haya elegido en esta página, por ejemplo, si está trabajando por lotes o si desea deshacer una importación más adelante.

![Configuración de importación tal y como se describe, sin entradas](../modules/modulesfiles/csvimport_settings.png)

Haga clic en el botón «Siguiente» para continuar con el proceso de importación.

## Importar elementos
Para importar elementos, seleccione «Elementos» en «Tipo de importación» en la primera página.

Al hacer clic en «Siguiente», se cargará la página con las siguientes pestañas:

### Asignar a datos de Omeka S 

Esta pestaña muestra una tabla con las columnas de su hoja de cálculo como filas. Cada fila muestra:

- Una casilla de verificación
- El encabezado de columna de la hoja de cálculo
- Un botón con el símbolo «+» para añadir o modificar una asignación
- Un botón con el símbolo de una llave inglesa para las opciones de las columnas de la hoja de cálculo
- Una columna que muestra las propiedades asignadas, ya sea de forma automática o manual
- Una papelera para eliminar asignaciones existentes
- Una columna que muestra las opciones específicas seleccionadas (como si se deben buscar separadores de valores múltiples o la visibilidad de esa columna).

![Asignaciones para una hoja de cálculo con diez columnas. Algunas de las columnas, como las denominadas «Descripción» y «Título», se han asignado automáticamente a propiedades de Dublin Core.](../modules/modulesfiles/csvimport_itemsMap1.png)

#### Opciones de asignación

Para asignar el encabezado de una columna a una propiedad del vocabulario, haz clic en el botón con el símbolo más. Esto abrirá un panel deslizante en la parte derecha de la pantalla.

El panel deslizante ofrece varias opciones de asignación:

**Propiedades** le permite seleccionar una propiedad a la que asignar los datos de la columna, de cualquiera de los vocabularios instalados. Utilice el campo «Filtro» para buscar una propiedad específica.

![Opción Propiedades abierta, mostrando todos los vocabularios instalados para la instalación de Omeka S: Dublin Core, Bibliographic Ontology, Friend of a Friend, Scripto y OWL-Time Ontology.](../modules/modulesfiles/csvimport_itemsMapProp.png)

**Datos específicos del elemento** cuenta con un menú desplegable para establecer un conjunto de elementos según la propiedad seleccionada. Si tienes una columna que identifica un conjunto de elementos al que deseas añadir cada elemento (en lugar de colocar todos los elementos importados en los mismos conjuntos de elementos en la pestaña «Configuración básica»), puede definir cómo se asigna mediante este menú desplegable. Puede utilizar el ID interno del conjunto de elementos o cualquiera de sus propiedades (como el título).

![menú desplegable tal y como se describe](../modules/modulesfiles/csvimport_itemsMapISD.png)

**Datos genéricos** también cuenta con un menú desplegable en el que puede seleccionar una de estas cuatro opciones:

- **Plantilla de recurso (por etiqueta)**: Establezca la plantilla de un elemento por su nombre. El nombre de la plantilla tal y como se ha introducido en la hoja de cálculo y el nombre de la plantilla en Omeka S deben coincidir exactamente.
- **Clase de recurso (por término)**: Establezca la clase de recurso de un elemento. El término de la clase en la hoja de cálculo y en la instalación de Omeka S debe coincidir exactamente; consulte la pestaña Vocabularios de su instalación. Por ejemplo, introduzca «dctype:Dataset», «dcterms:Location», «bibo:Interview» o «foaf:Person» con dos puntos separando el prefijo del vocabulario y el término, sin espacios.
- **Propietario (por dirección de correo electrónico)**: Establece el propietario de un elemento mediante su dirección de correo electrónico. Debe ser la dirección de correo electrónico asociada a la cuenta del usuario en la instalación de Omeka S.
- **Visibilidad pública/privada**: Establece la visibilidad del elemento. Utiliza «privada» o «público» en la hoja de cálculo.

![Menú desplegable tal y como se describe](../modules/modulesfiles/csvimport_itemsMapgeneric.png)

**Fuente multimedia** te permite importar [multimedia](../content/media.md#add-media-to-an-item) junto con tus elementos, seleccionando el método de origen en el menú desplegable:

- HTML
- Imagen IIIF (enlace)
- Presentación IIIF (enlace)
- oEmbed (enlace)
- URL
- YouTube (enlace).

Aquí pueden aparecer otras opciones en función de tus módulos activos, como File Sideload. 

Asegúrate de hacer clic en «Aplicar cambios» en la parte inferior del panel; de lo contrario, no se guardará nada de lo que hayas configurado aquí.

Para eliminar una asignación, haz clic en el icono de la papelera en la fila correspondiente a esa asignación de datos. Esto eliminará *solo* la asignación, no los datos de la columna. 

Si tienes datos en una columna de tu CSV que no deseas importar a tu instalación de Omeka S, simplemente no asignes esa columna a una propiedad o tipo de datos.

#### Opciones de columna

Las opciones de columna son adicionales a las asignaciones. Si añades opciones sin asignar también los datos de la columna a un recurso, un medio u otros datos, no se importará nada. Si tienes varias asignaciones configuradas en una sola columna de tus datos, estas opciones se aplicarán a todas ellas.

Para acceder a las opciones de una columna de tu CSV (representada por una fila en la tabla de importación), haz clic en el icono de la llave inglesa correspondiente al encabezado de esa columna.

![cajón con opciones como se describe a continuación](../modules/modulesfiles/csvimport_ItemColOpt.png)

Esto abrirá un panel en el lado derecho de la ventana del navegador con las siguientes opciones:

- **Usar separador de valores múltiples**: Marque esta casilla para utilizar el separador de valores múltiples para los datos de esta columna. El separador de valores múltiples se configura en la página de importación inicial, pero puede cambiarlo en la pestaña Configuración básica.  
- **Idioma**: Establezca el idioma de esta columna utilizando la [etiqueta de idioma IETF](https://en.wikipedia.org/wiki/IETF_language_tag){target=_blank} correspondiente al idioma en el que está escrito el texto. Esto anulará lo que haya introducido en la configuración básica.
- **Importar valores como privados**: Marque esta casilla para establecer como privados todos los valores de propiedad *de esta columna*.
- **Tipo de datos**: Un menú desplegable con al menos tres opciones, que se corresponden con los [valores](../content/items.md#values) que se pueden utilizar al añadir propiedades a un elemento:
  - Importar como texto (predeterminado).
	- Importar como referencia URI. Puede establecer la etiqueta de una URI incluyendo el texto deseado después de un espacio, por ejemplo: `http://example.com El texto de la etiqueta va aquí`.
  - Importar como recurso Omeka S. Esto creará [recursos vinculados](../content/items.md#linked-resources). Si selecciona esta opción, debes elegir qué valores de propiedad deben coincidir para encontrar el recurso de Omeka deseado en tu instalación, en el siguiente menú desplegable **Propiedad identificadora del recurso**. Debe ser una propiedad única, por lo que «Título» puede no ser una buena opción. 
 - Puedes utilizar el ID interno de Omeka. El ID de un recurso es la secuencia numérica al final de la URL cuando estás en la página de visualización o edición, por lo que para `/admin/item/11576` el ID es 11576. También puede ver el ID del recurso en el panel de la derecha de la página de visualización del recurso. Los elementos, los conjuntos de elementos y los medios tienen todos ID.
    - Puede incluir recursos que se estén creando en el mismo CSV, siempre que los recursos a los que se vinculan ya se hayan creado en filas anteriores y se puedan encontrar con el valor de propiedad único indicado aquí. Si desea hacer esto, le recomendamos establecer un número de lote bajo (incluso 1) en la pestaña «Configuración avanzada», para garantizar que los recursos se hayan creado por completo antes de que otro recurso nuevo intente vincularse a ellos. 
	- Si tiene instalados determinados módulos, como [Tipos de datos numéricos](../modules/numericdatatypes.md), es posible que dichos módulos ofrezcan opciones adicionales de tipos de datos.

Asegúrese de hacer clic en el botón «Aplicar cambios» situado en la parte inferior del panel para guardar los cambios. Para eliminar una configuración de opción de columna, haga clic de nuevo en el icono de la llave inglesa y deshaga los cambios manualmente.

#### Edición por lotes
Cuando seleccione una o más filas de la tabla (columnas de su archivo CSV), puede utilizar el botón «Opciones de edición por lotes» para aplicar las opciones de columna descritas anteriormente —separador de valores múltiples, idioma, tipo de datos y privacidad de la propiedad— a varias columnas CSV a la vez.

![una captura de pantalla de la pestaña Asignación, con dos casillas de columna marcadas. En la parte derecha de la pantalla, un panel ofrece opciones para cambiar la configuración.](modulesfiles/csvimport_batchOptions.png)

Asegúrate de hacer clic en el botón «Aplicar cambios» situado en la parte inferior del panel para guardar los cambios.

### Pestaña «Configuración básica»

Esta configuración se aplica a todo el archivo CSV que está importando. Tenga en cuenta que esta configuración puede ser sobrescrita por las opciones de columna de la pestaña «Asignar a datos de Omeka S». Si una columna está asignada a una plantilla, clase o propietario, esos valores anularán esta configuración; al igual que la configuración de las columnas de idioma y privacidad.

![La página «Configuración de importación de elementos», que muestra la pestaña «Configuración básica», con las opciones que se enumeran a continuación. La visibilidad está establecida en «Pública» y el separador de valores múltiples es «;»; las demás opciones están vacías.](../modules/modulesfiles/csvimport_itemsbasic.png)

- **Plantilla de recurso**: Selecciona una [plantilla de recurso](../content/resource-template.md) en el menú desplegable para aplicarla a los elementos importados. Puedes utilizar el campo de búsqueda situado en la parte superior del menú desplegable para filtrar los resultados o encontrar una plantilla concreta. Ten en cuenta que las plantillas de recurso pueden tener campos obligatorios, y los elementos no se importarán si no se rellenan todos los campos obligatorios de la plantilla seleccionada. Por ejemplo, si su hoja de cálculo tiene entradas sin un valor `dcterms:title`, y la plantilla de recursos requiere títulos, esas filas no se importarán y aparecerán errores en el registro.
- **Clase**: Seleccione una clase del menú desplegable para aplicarla a los elementos importados. Puede utilizar el campo de búsqueda situado en la parte superior del menú desplegable para filtrar los resultados o encontrar una clase concreta.
- **Propietario**: Establezca el propietario de los elementos seleccionando un usuario del menú desplegable. Puede utilizar el campo de búsqueda situado en la parte superior del menúpara filtrar los resultados o buscar un usuario concreto.
- **Visibilidad**: Establezca la visibilidad de los elementos importados como pública  o privada.
- **Conjuntos de elementos**: Añada los elementos importados a uno o varios conjuntos de elementos específicos mediante el menú desplegable.
- **Sitios**: Añada los elementos importados al sitio o sitios especificados. Aquí aparecerán preseleccionados los sitios predeterminados globales y específicos del usuario.
- **Separador de valores múltiples**: Introduzca aquí el carácter separador de valores múltiples, si ha utilizado alguno.
 - Las columnas de datos de su CSV deben estar separadas por comas; sin embargo, dentro de esas columnas puede añadir un carácter especial para crear entradas múltiples, por ejemplo, un punto y coma. Aquí es donde puede especificar varios creadores, varios temas u otros usos comunes.
- **Idioma**: Establezca el idioma de los valores de la hoja de cálculo utilizando la [etiqueta de idioma IETF](https://en.wikipedia.org/wiki/IETF_language_tag){target=_blank} adecuada.

!!! nota
  Si va a cargar datos en diferentes formatos (por ejemplo, algunos nombres de creadores basados en texto y algunos enlaces de creadores basados en URI) en el mismo campo (`dcterms:creator`, en este caso), utilice dos columnas (con nombres útiles como «dcterms:creator-text» y «dcterms:creator-uri») y, al importarlas, asigne esas dos columnas a diferentes tipos de datos. Utilice el icono de la llave inglesa para abrir las asignaciones de columnas y seleccione el tipo de datos correcto para cada columna.

### Pestaña «Configuración avanzada»

Hay dos opciones en la pestaña «Configuración avanzada».

![Página de configuración avanzada que muestra solo el menú desplegable «Acción» y el campo para el número de filas a procesar. ](../modules/modulesfiles/csvimport_ItemsAdvanced.png)

La Configuración de «Acción» le permite cambiar la acción del proceso de una importación directa a una de las siguientes opciones:

- **Crear un nuevo recurso**: Opción predeterminada. Cada fila del CSV se convertirá en un nuevo recurso.
- **Añadir datos al recurso**: Añade nuevos datos al recurso, basándose en un identificador de un recurso existente. (No se puede deshacer.) Esta opción le permite proporcionar varios valores para el mismo elemento; cada fila se añadirá (es decir, puede añadir un título a un elemento en una fila y añadir otro título al mismo elemento en otra fila). Tenga en cuenta que no puede proporcionar plantillas de recursos ni asignaciones de clases en las filas de su CSV con un proceso de «Añadir»; obtendrá un error. 
- **Revisar datos del recurso**: Reemplaza los datos existentes del recurso por los datos del CSV, *excepto si* la celda correspondiente en el CSV está vacía. (No se puede deshacer.)
- **Actualizar datos del recurso**: Reemplaza los datos existentes del recurso por los datos del CSV, *incluso cuando* la celda correspondiente en el CSV esté vacía. (No se puede deshacer.)
- **Reemplazar todos los datos del recurso**: Elimina todas las propiedades del recurso y rellena con la nueva información de la hoja. (No se puede deshacer.)
- **Eliminar el recurso**: Elimina todos los recursos coincidentes. (No se puede deshacer.)

Si seleccionas una de estas opciones en el menú desplegable, aparecerán tres ajustes adicionales en la pestaña. Estos ajustes ayudan al proceso a determinar sobre qué recursos actuar.

- **Columna de identificador de recurso**: Seleccione de un menú desplegable las columnas de su CSV. Estos son los datos de su hoja de cálculo que identifican los elementos existentes en su instalación de Omeka S. Elija un identificador único (por ejemplo, podría utilizar la columna «Título» de su CSV).  No es necesario asignar esta columna en la otra pestaña.
- **Propiedad de identificador de recurso**: Seleccione de un menú desplegable todas las propiedades de su instalación de Omeka S. Esta debe ser la propiedad equivalente en su instalación de Omeka S a la columna que seleccionó anteriormente (por ejemplo, `dcterms:title`). Esto solo funcionará con coincidencias exactas. Si tiene más de un recurso con datos coincidentes, solo se aplicará la acción al recurso más antiguo.
- **Acción sobre recursos no identificados**: Esta opción determina qué hacer cuando no existe ningún recurso coincidente en la instalación de Omeka S, siempre que la acción seleccionada se aplique a un recurso existente («Añadir», «Revisar», «Actualizar» o «Reemplazar»). Esta opción no se utiliza cuando la acción principal es «Crear» o «Eliminar». Las opciones disponibles son:
  - Saltar la fila e ignorar su contenido
	- Crear un nuevo recurso con la información proporcionada.

Además de lo anterior, la pestaña «Configuración avanzada» tiene una opción para establecer el número de filas que se procesarán por lote. Por defecto, está establecido en 20. Sin embargo, si se producen errores durante una importación, es posible que desee establecerlo en 5 o incluso en 1 para solucionar el problema y determinar el origen del error.

!!! nota
  Ten en cuenta que la opción «Añadir datos» te permitirá introducir varias filas con el mismo identificador; los valores de cada fila se añadirán junto a los anteriores.

  Las opciones «Revisar», «Actualizar» y «Reemplazar» **borrarán** los datos introducidos en filas anteriores de tu CSV, si las filas posteriores utilizan el mismo identificador. Si desea importar varios valores (por ejemplo, dos valores de «Creador») en estos procesos, puede: colocarlos en dos columnas de la misma fila, asignados a la misma propiedad; o bien, colocarlos en una sola celda y utilizar separadores de valores múltiples. No olvide especificar su separador de valores múltiples en la pestaña «Configuración básica» y marcar la casilla «Usar separador de valores múltiples» en las opciones (icono de llave inglesa) de cada columna.

### Finalizar la importación
Una vez que haya completado las asignaciones, las opciones de columna y la configuración, haga clic en el botón «Importar» situado en la esquina superior derecha de la ventana del navegador. Esto debería iniciar la importación y redirigirle a la pestaña «Importaciones anteriores». Debería ver un mensaje de confirmación en verde en la parte superior de la pantalla que dice «Importando en ID de trabajo [número]».


## Importar conjuntos de elementos
Para importar conjuntos de elementos, seleccione «Conjunto de elementos» en «Tipo de importación» en la primera página.

Al hacer clic en «Siguiente», se cargará la página con las siguientes pestañas:

### Asignar a datos de Omeka S
Esta pestaña muestra una tabla con las columnas de su hoja de cálculo como filas. Cada fila muestra:

- una casilla de verificación
- el encabezado de la columna de la hoja de cálculo
- Un botón con el símbolo «+» para añadir o modificar una asignación
- Un botón con el símbolo de una llave inglesa para las opciones de las columnas de la hoja de cálculo
- Una columna que muestra las propiedades asignadas, ya sea de forma automática o manual
- Una papelera para eliminar las asignaciones existentes
- Una columna para mostrar las opciones concretas seleccionadas.

![Asignaciones para una hoja de cálculo con cuatro columnas, todas ellas asignadas automáticamente](../modules/modulesfiles/csvimport_ItemSet1.png)

#### Opciones de asignación

Para asignar un encabezado de columna a una propiedad del vocabulario, haz clic en el botón con el símbolo de más situado a la izquierda del encabezado de la columna. Esto abrirá un panel deslizante en la parte derecha de la pantalla.

El panel ofrece varias opciones de asignación:

**Propiedades**: Seleccione una propiedad a la que asignar los datos de la columna, de cualquiera de los vocabularios instalados. Utilice el campo Filtro para buscar una propiedad específica entre las disponibles.

![Opción Propiedades abierta mostrando todos los vocabularios instalados para la instalación de Omeka S: Dublin Core, Bibliographic Ontology, Friend of a Friend, Scripto y OWL-Time Ontology.](../modules/modulesfiles/csvimport_itemsMapProp.png)

**Datos específicos del conjunto de elementos** es una casilla de verificación para «Abierto a adiciones». Márquela para permitir que otros usuarios editen o añadan elementos al conjunto. Déjela sin marcar para que el conjunto de elementos solo sea editable por su creador, los administradores del sitio y los administradores globales.

![Panel de asignación «Añadir» que muestra la sección «Datos específicos del conjunto de elementos». Debajo del encabezado de la sección hay una única casilla de verificación sin seleccionar con la etiqueta «Abierto a adiciones».](../modules/modulesfiles/csvimport_itemSetSD.png)

****Datos genéricos** también cuenta con un menú desplegable en el que puede establecer una de estas cuatro opciones:

- **Plantilla de recurso (por etiqueta)**: Establezca la plantilla para un conjunto de elementos  por su nombre. El nombre de la plantilla tal y como se ha introducido en la hoja de cálculo y el nombre de la plantilla en Omeka S deben coincidir exactamente.
- **Clase de recurso (por término)**: Establece la clase de recurso para un conjunto de elementos. El término de la clase en la hoja de cálculo y en la instalación de Omeka S debe coincidir exactamente; consulta la pestaña Vocabularios de tu instalación. Por ejemplo, introduce «dctype:Dataset», «dcterms:Location», «bibo:Interview» o «foaf:Person» con dos puntos separando el prefijo del vocabulario y el término, sin espacios.
- **Propietario (por dirección de correo electrónico)**: Establezca el propietario de un conjunto de elementos mediante una dirección de correo electrónico. Debe ser la dirección de correo electrónico asociada a la cuenta del usuario en la instalación de Omeka S.
- **Visibilidad pública/privada**: Establezca la visibilidad del conjunto de elementos. Utilice «privada» o «pública» en la hoja de cálculo.

![Menú desplegable tal y como se describe](../modules/modulesfiles/csvimport_itemsMapgeneric.png)

Asegúrate de hacer clic en «Aplicar cambios» en la parte inferior del panel; de lo contrario, no se guardará nada de lo que hayas configurado aquí.

Para eliminar una asignación, haz clic en el icono de la papelera en la fila correspondiente a esa asignación de datos. Esto eliminará *solo* la asignación, no los datos de la columna.

Si tienes datos en una columna de tu CSV que no deseas importar a tu instalación de Omeka S, simplemente no asignes esa columna a una propiedad o tipo de datos.

#### Opciones de columna

Las opciones de columna son adicionales a las asignaciones. Si añades opciones sin asignar también los datos de la columna a un recurso, un medio u otros datos, no se importará nada.

Para acceder a las opciones de los datos de una columna de tu CSV (representada por una fila en la tabla de importación), haz clic en el icono de la llave inglesa correspondiente al encabezado de esa columna.

Esto abrirá un panel en el lado derecho de la ventana del navegador con las siguientes opciones:

- **Usar separador de valores múltiples**: marca esta casilla para utilizar el separador de valores múltiples para los datos de esta columna. El separador de valores múltiples se configura en la página de importación inicial, pero puedes cambiarlo en la pestaña «Configuración básica».  
- **Idioma**: Establece el idioma de esta columna utilizando la [etiqueta de idioma IETF](https://en.wikipedia.org/wiki/IETF_language_tag){target=_blank} correspondiente al idioma en el que está escrito el texto. Esto anulará lo que hayas introducido en la configuración básica.
- **Importar valores como privados**: Marque esta casilla para establecer todos los valores de propiedad *de esta columna* como privados.
- **Tipo de datos**: Un menú desplegable con al menos tres opciones, que se corresponden con los [valores](../content/items.md#values) que se pueden utilizar al añadir propiedades a un elemento:
  - Importar como texto (predeterminado).
  - Importar como referencia URL. Puede establecer la etiqueta para el URI incluyendo el texto deseado después de un espacio, por ejemplo:  `http://example.com This Is The Label`
	- Importar como recurso Omeka S. Esto creará [recursos vinculados](../content/item-sets.md#linked-resources). Si selecciona esta opción, debe elegir qué valores de propiedad deben coincidir para encontrar el recurso Omeka deseado en su instalación, en el siguiente menú desplegable **Propiedad identificadora del recurso**. Debe ser una propiedad única, por lo que «Título» puede no ser una buena opción. 
		- Puede utilizar el ID interno de Omeka. El ID de un recurso es la secuencia numérica que aparece al final de la URL en la página de visualización o edición; por lo tanto, para `/admin/item/11576`, el ID es 11576. También puede ver el ID del recurso en el panel de la derecha de la página de visualización del recurso. Los elementos, los conjuntos de elementos y los medios tienen todos ID.
    - Puede incluir recursos que se estén creando en el mismo CSV, siempre que los recursos a los que se vinculan ya se hayan creado en filas anteriores y se puedan encontrar con el valor de propiedad único indicado aquí. Si desea hacerlo, le recomendamos establecer un número de lote bajo (incluso 1) en la pestaña «Configuración avanzada», para garantizar que los recursos se hayan creado por completo antes de que otro recurso nuevo intente vincularse a ellos. 
  - Si tiene instalados determinados módulos, como «Tipos de datos numéricos», es posible que dichos módulos ofrezcan opciones adicionales de tipos de datos.

Asegúrese de hacer clic en el botón «Aplicar cambios» situado en la parte inferior del panel para guardar los cambios. Para eliminar una configuración de opción de columna, haga clic de nuevo en el icono de la llave inglesa y deshaga los cambios manualmente.

#### Edición por lotes
Cuando seleccione una o más filas de la tabla (columnas de su archivo CSV), puede utilizar el botón «Opciones de edición por lotes» para aplicar las opciones de columna descritas anteriormente a varias columnas CSV a la vez.

![Un panel ofrece opciones para cambiar la configuración por lotes.](../modules/modulesfiles/csvimport_batchOptions2.png)

Asegúrate de hacer clic en el botón «Aplicar cambios» situado en la parte inferior del panel para guardar los cambios.

### Pestaña «Configuración básica» de la importación de conjuntos de elementos

Esta configuración se aplica a todo el CSV que está importando. Tenga en cuenta que esta configuración puede ser sobrescrita por las opciones de columna de la pestaña «Asignar a datos de Omeka S». Si una columna está asignada a una plantilla, clase o propietario, esos valores anularán esta configuración; lo mismo ocurrirá con la configuración de columna para el idioma y la privacidad.

![La página «Configuración de importación para conjuntos de elementos», que muestra la pestaña «Configuración básica», con las opciones que se enumeran a continuación. La visibilidad está establecida en «Pública» y el separador de valores múltiples es «;»; las demás opciones están vacías.](../modules/modulesfiles/csvimport_ItemSetBasic.png)

- **Plantilla de recurso**: Seleccione una plantilla de recurso del menú desplegablepara aplicarla a los conjuntos de elementos importados. Puede utilizar el campo de búsqueda situado en la parte superior del menú desplegable para filtrar los resultados o encontrar una plantilla concreta.
- **Clase**: Seleccione una clase del menú desplegable para aplicarla a los conjuntos de elementos importados. Puede utilizar el campo de búsqueda situado en la parte superior del menú desplegable para filtrar los resultados o encontrar una clase concreta.
- **Propietario**: Establezca el propietario de los conjuntos de elementos seleccionando un usuario del menú desplegable. Puede utilizar el campo de búsqueda situado en la parte superior del menú desplegable para filtrar los resultados o encontrar un usuario concreto.
- **Visibilidad**: Establezca la visibilidad de los conjuntos de elementos importados como pública o privada.
- **Abierto/cerrado a nuevas entradas**: Establezca si los usuarios distintos del propietario (y los administradores del sitio y globales) podrán añadir o editar los conjuntos de elementos.
- **Separador de valores múltiples**: Introduzca aquí el carácter separador de valores múltiples, si ha utilizado alguno.
      - Las columnas de datos de tu CSV deben estar separadas por comas; sin embargo, dentro de esas columnas puedes añadir un carácter especial para crear entradas múltiples, por ejemplo, un punto y coma.
- **Idioma**: Establece el idioma de los valores de la hoja de cálculo utilizando la [etiqueta de idioma IETF](https://en.wikipedia.org/wiki/IETF_language_tag){target=_blank} adecuada.

### Pestaña «Configuración avanzada» de la importación de conjuntos de elementos

La pestaña «Configuración avanzada» tiene una opción para establecer el número de filas que se procesarán por lote. De forma predeterminada, está establecido en 20. Sin embargo, si se producen errores durante una importación, es posible que desee establecerlo en 5 o incluso en 1 para solucionar el problema y determinar el origen del error.

![Página de configuración avanzada en la que solo se muestran el menú desplegable Acción y el campo para el número de filas a procesar. ](../modules/modulesfiles/csvimport_ItemSetAdv.png)

#### Acción

Esta configuración le permite cambiar la acción del proceso de una importación directa a una de las siguientes opciones:

- **Crear un nuevo recurso**: Opción predeterminada. Cada fila del CSV se convertirá en un nuevo recurso.
- **Añadir datos al recurso**: añade nuevos datos al recurso, basándose en un identificador de un recurso existente. (No se puede deshacer.) Esta opción le permite proporcionar varios valores para el mismo conjunto de elementos; cada fila se añadirá (es decir, puede añadir un título a un conjunto de elementos en una fila y añadir otro título al mismo conjunto de elementos en otra fila).
- **Revisar los datos del recurso**: Reemplaza los datos existentes del recurso por los datos del CSV, *excepto si* la celda correspondiente en el CSV está vacía. (No se puede deshacer.)
- **Actualizar datos del recurso**: Reemplaza los datos existentes del recurso por los datos del CSV, *incluso cuando* la celda correspondiente en el CSV esté vacía. (No se puede deshacer.)
- **Reemplazar todos los datos del recurso**: Elimina todas las propiedades del recurso y rellena con la nueva información de la hoja. (No se puede deshacer.)
- **Eliminar el recurso**: Elimina todos los recursos coincidentes. (No se puede deshacer.)

Si seleccionas una de estas opciones del menú desplegable, aparecerán tres ajustes adicionales en la pestaña. Estos ajustes ayudan al proceso a determinar sobre qué recursos se debe actuar.

![Pestaña de opciones avanzadas con las opciones descritas a continuación](../modules/modulesfiles/csvimport_itemSetAdvAct.png)

- **Columna de identificador de recurso**: Seleccione de un menú desplegable las columnas de su CSV. Estos son los datos de su hoja de cálculo que se asignan a los datos existentes en su instalación de Omeka S. No es necesario asignar esta columna en la otra pestaña.
- **Propiedad de identificador de recurso**: Seleccione de un menú desplegable todas las propiedades de su instalación de Omeka S. Debe ser la propiedad en la que ya tiene datos, la que utilizó para crear los datos de la columna anterior.
  - Ejemplo: si los datos de la columna **Identificador de recurso** son «Título», y la primera fila de datos tiene el título «Un estudio en escarlata», y usted establece la propiedad **Identificador de recurso** en «Dublin Core: Título», entonces las acciones se aplicarán a un recurso que ya se encuentre en su instalación de Omeka S cuya propiedad dc:title sea «Estudio en escarlata».
  - Esto solo funcionará con coincidencias exactas.
  - Si tiene más de un recurso con datos coincidentes, solo se aplicará la acción al recurso más antiguo.
- **Acción sobre recursos no identificados**: Esta opción determina qué hacer cuando no existe ningún recurso coincidente en la instalación de Omeka S, pero la acción seleccionada solo se aplica a un recurso existente («Añadir», «Revisar», «Actualizar» o «Reemplazar»). Esta opción no se utiliza cuando la acción principal es «Crear» o «Eliminar». Las opciones son dos botones de radio:
	- Saltar la fila
  - Crear un nuevo recurso.

!!! nota
  Ten en cuenta que al añadir datos podrás proporcionar varias filas con el mismo identificador; los valores de cada fila se añadirán junto a los anteriores.

  La revisión, actualización y sustitución de datos **borrarán** los datos proporcionados en filas anteriores de tu CSV, si las filas posteriores utilizan el mismo identificador. Si deseas importar varios valores (por ejemplo, dos valores de «Creador») en estos procesos, puedes: colocarlos en dos columnas de la misma fila, asignados a la misma propiedad; o bien, colocarlos en una sola celda y utilizar separadores de valores múltiples. No olvide especificar su separador de valores múltiples en la pestaña «Configuración básica» y marcar la casilla «Usar separador de valores múltiples» en las opciones (icono de llave inglesa) de cada columna.

### Completar la importación
Una vez que haya completado las asignaciones, las opciones de las columnas y cualquier configuración, haga clic en el botón «Importar» situado en la esquina superior derecha de la ventana del navegador. Esto debería iniciar la importación y redirigirle a la pestaña Importaciones anteriores. Debería ver un mensaje de confirmación que dice «Importando en ID de tarea [número]».

## Importar archivos multimedia
Para importar archivos multimedia, seleccione «Archivos multimedia» en «Tipo de importación» en la primera página.

Para importar archivos multimedia, debe haber una columna en el CSV que se asigne a los datos de los elementos. Los archivos multimedia no pueden existir a menos que estén asociados a un elemento mediante un identificador único (ID de elemento de Omeka, título, etc.). Tenga en cuenta que si está ejecutando una tarea avanzada, como una actualización o sustitución, no es necesario que haya una columna con datos de elementos asociados, solo una forma de hacer coincidir las filas con los archivos multimedia que ya existen.

Al hacer clic en «Siguiente», se cargará la página con las siguientes pestañas:

### Asignar a datos de Omeka S
Esta pestaña muestra una tabla con las columnas de su hoja de cálculo como filas. Cada fila muestra:

- una casilla de verificación
- el encabezado de columna de la hoja de cálculo
- un botón con el símbolo «+» para añadir o modificar una asignación
- un botón con el símbolo de una llave inglesa para las opciones de las columnas de la hoja de cálculo
- una columna que muestra las propiedades asignadas, ya sea de forma automática o manual
- Una papelera para eliminar asignaciones existentes
- Una columna para mostrar las opciones concretas seleccionadas.

![Asignaciones para una hoja de cálculo con diez columnas. Algunas de las columnas, como las denominadas Descripción y Título, se han asignado automáticamente a propiedades de Dublin Core.](../modules/modulesfiles/csvimport_mediaMap1.png)

#### Opciones de asignación

Para asignar un encabezado de columna a una propiedad del vocabulario, haz clic en el botón con el símbolo de más situado a la izquierda del encabezado de la columna. Esto abrirá un panel deslizante en la parte derecha de la pantalla.

El panel ofrece varias opciones de asignación:

**Propiedades**: Seleccione una propiedad a la que asignar los datos de la columna, de cualquiera de los vocabularios instalados. Utilice el campo Filtro para buscar una propiedad específica entre las disponibles.

![Opción de propiedades abierta mostrando todos los vocabularios instalados para la instalación de Omeka S: Dublin Core, Bibliographic Ontology, Friend of a Friend, Scripto y OWL-Time Ontology.](../modules/modulesfiles/csvimport_itemsMapProp.png)

**Los datos específicos de los medios** tienen un menú desplegable para establecer el elemento al que se deben añadir los medios. Puede utilizar el ID interno del elemento o hacer coincidir cualquiera de sus propiedades únicas (título, descripción). El ID de un elemento es la secuencia numérica al final de la URL cuando se encuentra en la página de visualización o edición, por lo que para `/admin/item/11576` el ID es 11576. También puede ver el ID del elemento en el panel de la derecha de la página de visualización del elemento.

![Datos específicos de los medios con menú desplegable](../modules/modulesfiles/csvimport_mediaMapData.png)

**Los **datos genéricos** también tienen un menú desplegable en el que puedes seleccionar una de estas cuatro opciones:

- **Plantilla de recurso (por etiqueta)**: Establece la plantilla para el medio por su nombre. El nombre de la plantilla tal y como se ha introducido en la hoja de cálculo y el nombre de la plantilla en Omeka S deben coincidir exactamente.
- **Clase de recurso (por término)**: Establece la clase de recurso para el material multimedia. El término de la clase en la hoja de cálculo y en la instalación de Omeka S debe coincidir exactamente; consulta la pestaña Vocabularios de tu instalación. Por ejemplo, introduce «dctype:Dataset», «dcterms:Location», «bibo:Interview» o «foaf:Person» con dos puntos separando el prefijo del vocabulario y el término, sin espacios.
- ****Propietario (por dirección de correo electrónico)**: Establezca el propietario del medio mediante su dirección de correo electrónico. Debe ser la dirección de correo electrónico asociada a la cuenta del usuario en la instalación de Omeka S.
- **Visibilidad pública/privada**: Establezca la visibilidad del medio. Utilice «private» o «público» en la hoja de cálculo.

![Menú desplegable tal y como se describe](../modules/modulesfiles/csvimport_itemsMapgeneric.png)

**Fuente del medio**: Para la columna de la hoja de cálculo que apunta al medio que está creando, seleccione de qué tipo de medio se trata en el menú desplegable:

- HTML
- Imagen IIIF (enlace)
- Presentación IIIF (enlace)
- oEmbed (enlace)
- URL
- YouTube (enlace).

Aquí pueden aparecer otras opciones en función de tus módulos activos, como File Sideload. 

Asegúrate de hacer clic en «Aplicar cambios» en la parte inferior del panel; de lo contrario, no se guardará nada de lo que hayas configurado aquí.

Para eliminar una asignación, haz clic en el icono de la papelera en la fila correspondiente a esa asignación de datos. Esto eliminará *solo* la asignación, no los datos de la columna.

Si tiene datos en una columna de su CSV que no desea importar a su instalación de Omeka S, simplemente no asigne esa columna a una propiedad o tipo de datos.

#### Opciones de columna

Las opciones de columna son adicionales a las asignaciones. Si añades opciones sin asignar también los datos de la columna a un recurso, un medio u otros datos, no se importará nada.

Para acceder a las opciones de los datos de una columna de tu CSV (representada por una fila en la tabla de importación), haz clic en el icono de la llave inglesa correspondiente al encabezado de esa columna.

![panel con opciones como se describe a continuación](../modules/modulesfiles/csvimport_mediaColOpt.png)

Esto abrirá un panel en el lado derecho de la ventana del navegador con las siguientes opciones:

- **Usar separador de valores múltiples**: Marque esta casilla para utilizar el separador de valores múltiples para los datos de esta columna. El separador de valores múltiples se configura en la página de importación inicial, pero puede cambiarlo en la pestaña Configuración básica.  
- **Idioma**: Establezca el idioma de esta columna utilizando la [etiqueta de idioma IETF](https://en.wikipedia.org/wiki/IETF_language_tag){target=_blank} para el idioma en el que está escrito el texto. Esto anulará lo que haya introducido en la configuración básica.
- **Importar valores como privados**: Marque esta casilla para establecer todos los valores de propiedad *de esta columna* como privados.
- **Tipo de datos**: Un menú desplegable con al menos tres opciones, que se corresponden con los [valores](../content/items.md#values) que se pueden utilizar al añadir propiedades a un elemento:
  - Importar como texto (predeterminado).
  - Importar como referencia URL. Puede establecer la etiqueta para el URI incluyendo el texto deseado después de un espacio, por ejemplo:  `http://example.com This Is The Label`.
	- Importar como recurso Omeka S. Esto creará [recursos vinculados](../content/media.md#omeka-resource). Si selecciona esta opción, debe elegir qué valores de propiedad deben coincidir para encontrar el recurso Omeka deseado en su instalación, en el siguiente menú desplegable **Propiedad identificadora del recurso**. Debe ser una propiedad única, por lo que «Título» puede no ser una buena opción. 
		- Puedes utilizar el ID interno de Omeka. El ID de un recurso es la secuencia numérica que aparece al final de la URL en la página de visualización o edición; así, para `/admin/item/11576`, el ID es 11576. También puedes ver elen el panel de la derecha de la página de vista del recurso. Los elementos, los conjuntos de elementos y los medios tienen todos un ID.
    - Puede incluir recursos (elementos o conjuntos de elementos) que se estén creando en el mismo CSV, siempre que los recursos a los que se vinculan ya se hayan creado en filas anteriores y se puedan encontrar con el valor de propiedad único indicado aquí. Si desea hacerlo, le recomendamos establecer un número de lote bajo (incluso 1) en la pestaña «Configuración avanzada», para garantizar que los recursos se hayan creado por completo antes de que otro recurso nuevo intente vincularse a ellos. 
  - Si tiene instalados determinados módulos, como «Tipos de datos numéricos», es posible que dichos módulos ofrezcan opciones adicionales de tipos de datos.

Recuerde hacer clic en el botón «Aplicar cambios». Para eliminar una configuración de opción de columna, haga clic de nuevo en el icono de la llave inglesa y deshaga los cambios manualmente.

#### Edición por lotes
Cuando seleccione una o más filas de la tabla (columnas de su archivo CSV), puede utilizar el botón «Opciones de edición por lotes» para aplicar las opciones de columna descritas anteriormente a varias columnas CSV a la vez.

![Un panel ofrece opciones para cambiar la configuración por lotes.](../modules/modulesfiles/csvimport_batchOptions2.png)

Asegúrate de hacer clic en el botón «Aplicar cambios» situado en la parte inferior del panel para guardar los cambios.

### Ajustes básicos de importación de medios
Estos ajustes se aplican a todo el CSV que está importando. Tenga en cuenta que estos ajustes pueden ser sobrescritos por las opciones de columna en la pestaña «Asignar a datos de Omeka S». Si una columna está asignada a una plantilla, clase o propietario, esos valores anularán estos ajustes; lo mismo ocurrirá con los ajustes de columna para el idioma y la privacidad.

- **Plantilla de recurso**: Seleccione una plantilla de recurso en el menú desplegable para aplicarla a los archivos multimedia importados. Puede utilizar el campo de búsqueda situado en la parte superior del menú desplegable para filtrar los resultados o encontrar una plantilla concreta. 
- **Clase**: Seleccione una clase en el menú desplegable para aplicarla a los archivos multimedia importados. Puede utilizar el campo de búsqueda situado en la parte superior del menú desplegable para filtrar los resultados o encontrar una clase concreta. 
- ****Propietario**: Establezca el propietario de los archivos multimedia seleccionando un usuario del menú desplegable. Puede utilizar el campo de búsqueda situado en la parte superior del menú desplegable para filtrar los resultados o encontrar un usuario concreto. 
- **Visibilidad**: Establezca la visibilidad de los archivos multimedia importados como pública o privada.
- **Separador de valores múltiples**: Introduzca aquí el carácter separador de valores múltiples, si ha utilizado alguno.
      - Las columnas de datos de su CSV deben estar separadas por comas; sin embargo, dentro de esas columnas puede añadir un carácter especial para crear entradas múltiples, por ejemplo, un punto y coma.
- **Idioma**: Establezca el idioma de los valores de la hoja de cálculo utilizando la [etiqueta de idioma IETF](https://en.wikipedia.org/wiki/IETF_language_tag){target=_blank} adecuada.

### Ajustes avanzados de importación de medios
En esta pestaña hay dos opciones que son solo para uso avanzado.

El ajuste Acción te permite cambiar la acción del proceso de una importación directa a una de las siguientes opciones:

- **Crear un nuevo recurso**: Opción predeterminada. Cada fila del CSV se convertirá en un nuevo recurso.
- **Añadir datos al recurso**: Añade nuevos datos al recurso. 
- **Revisar los datos del recurso**: Reemplaza los datos existentes en el recurso por los datos del CSV, excepto si están vacíos.
- **Actualizar los datos del recurso**: Reemplaza los datos existentes en el recurso por los datos del CSV, incluso cuando la celda esté vacía.
- **Reemplazar todos los datos del recurso**: Elimina todas las propiedades del recurso y rellena con nueva información de la hoja.
- **Eliminar el recurso**: Eliminar todos los recursos coincidentes.

Si seleccionas una de estas opciones del menú desplegable, aparecerán tres ajustes adicionales en la pestaña. Estos ajustes ayudan al proceso a determinar sobre qué recursos se debe actuar.

![Opciones descritas a continuación](../modules/modulesfiles/csvimport_mediaAdvAct.png)

- **Columna de identificador de recurso**: Seleccione de un menú desplegable las columnas de su CSV. Estos son los datos de su hoja de cálculo que se asignan a los datos existentes en su instalación de Omeka S. No es necesario asignar esta columna en la otra pestaña.
- **Propiedad del identificador de recurso**: Seleccione de un menú desplegable todas las propiedades de su instalación de Omeka S. Debe ser la propiedad en la que ya tiene datos, la que utilizó para crear los datos de la columna anterior.
	- Ejemplo: si los datos de la columna **Identificador de recurso** son «Título» y la primera fila de datos tiene el título «Un estudio en escarlata», y configura la propiedad **Identificador de recurso** como «Dublin Core: Título», entonces las acciones se aplicarán a un recurso que ya se encuentre en su instalación de Omeka S cuya propiedad `dcterms:title` sea «Un estudio en escarlata».
  - Esto solo funcionará con coincidencias exactas.
	- Si tiene más de un recurso con datos coincidentes, solo se aplicará la acción al recurso más antiguo.
- **Acción sobre recursos no identificados**: Esta opción determina qué hacer cuando no existe ningún recurso coincidente en la instalación de Omeka S, pero la acción seleccionada solo se aplica a un recurso existente («Añadir», «Revisar», «Actualizar» o «Reemplazar»). Esta opción no se utiliza cuando la acción principal es «Crear» o «Eliminar». Las opciones son dos botones de opción:
  - Omitir la fila
  - Crear un nuevo recurso.

Además de lo anterior, la pestaña «Configuración avanzada» tiene una opción para establecer el número de filas que se procesarán por lote. Por defecto, está establecido en 20. Sin embargo, si se producen errores durante la importación, es posible que desee establecerlo en 5 o incluso en 1 para solucionar el problema y determinar el origen del error.

!!! nota
  Tenga en cuenta que al añadir datos podrá proporcionar varias filas con el mismo identificador; los valores de cada fila se añadirán junto a los anteriores.

	La revisión, actualización y sustitución de datos **borrarán** los datos proporcionados en filas anteriores de tu CSV, si las filas posteriores utilizan el mismo identificador. Si deseas importar varios valores (por ejemplo, dos valores de Creador) en estos procesos, puede: colocarlos en dos columnas de la misma fila, asignados a la misma propiedad; o bien, colocarlos en una sola celda y utilizar separadores de valores múltiples. No olvide especificar su separador de valores múltiples en la pestaña «Configuración básica» y marcar la casilla «Usar separador de valores múltiples» en las opciones (icono de llave inglesa) de cada columna.

### Importación completa
Una vez que haya completado las asignaciones, las opciones de columna y cualquier configuración, haga clic en el botón Importar situado en la esquina superior derecha de la ventana del navegador. Esto debería iniciar la importación y redirigirle a la pestaña Importaciones anteriores. Debería ver un mensaje de confirmación que dice «Importando en ID de tarea [número]».

## Importación de recursos mixtos
Esta opción de recursos te permite importar una hoja con una combinación de tipos de recursos: elementos, conjuntos de elementos y medios.

### Asignar a datos de Omeka S
Esta pestaña muestra un menú desplegable inicial sobre una tabla con las columnas de tu hoja de cálculo como filas. Cada fila muestra:

- una casilla de verificación
- el encabezado de la columna de la hoja de cálculo
- un botón con el símbolo «+» para añadir o modificar una asignación
- un botón con el símbolo de una llave inglesa para las opciones de las columnas de la hoja de cálculo
- una columna que muestra las propiedades asignadas, ya sea de forma automática o manual
- una papelera para eliminar las asignaciones existentes
- una columna para mostrar las opciones concretas seleccionadas.

![Asignaciones para una hoja de cálculo con nueve columnas.](../modules/modulesfiles/csvimport_mixedR1.png)

El menú desplegable situado encima de la tabla es donde se establece qué columna del archivo CSV indica si los datos de esa fila son un elemento, un conjunto de elementos o un medio. No es necesario asignar estos datos en la tabla de esta pestaña. Los valores de esta columna pueden ser `elemento` o `elementos`, `conjunto de elementos` o `conjuntos de elementos`, o `medios`. Otros valores, o los campos vacíos, harán que la fila no se importe.

Las filas con «media» en la columna de tipo de recurso deben indicar a qué elemento se van a adjuntar, tal y como se indica en la [sección de medios anterior](#import-media), y requieren que se incluya una fuente de medios.

#### Opciones de asignación

Para asignar un encabezado de columna a una propiedad del vocabulario, haz clic en el botón con el símbolo más situado a la izquierda del encabezado de la columna. Esto abrirá un panel deslizante en el lado derechode la pantalla.

El panel ofrece varias opciones de asignación:

**Propiedades**: selecciona una propiedad a la que asignar los datos de la columna, de cualquiera de los vocabularios instalados. Utiliza el campo Filtro para buscar una propiedad específica entre las disponibles.
![Opción Propiedades abierta mostrando todos los vocabularios instalados para la instalación de Omeka S: Dublin Core, Bibliographic Ontology, Friend of a Friend, Scripto y OWL-Time Ontology.](../modules/modulesfiles/csvimport_itemsMapProp.png)

**Datos específicos del elemento** cuenta con un menú desplegable para establecer el conjunto de elementos según la propiedad seleccionada. Si tiene una columna con datos de un conjunto de elementos al que desea añadir el elemento, puede configurar cómo se asigna mediante este menú desplegable. Puede utilizar el ID interno del conjunto de elementos o cualquiera de sus propiedades (título, descripción).

![menú desplegable tal y como se describe](../modules/modulesfiles/csvimport_itemsMapISD.png)

**Datos específicos del conjunto de elementos** es una casilla de verificación para «Abierto a adiciones». Márquela para permitir que otros usuarios editen o añadan elementos al conjunto. Déjela sin marcar para que el conjunto de elementos solo sea editable por su creador, los administradores del sitio y los administradores globales.

![Añadir el panel de asignación que muestra la sección «Datos específicos del conjunto de elementos». Debajo del encabezado de la sección hay una única casilla de verificación sin marcar con la etiqueta «Abierto a adiciones».](../modules/modulesfiles/csvimport_itemSetSD.png)

**Datos específicos del medio** tiene un menú desplegable para establecer el elemento al que se debe añadir el medio. Puede utilizar el ID interno del elemento o cualquiera de sus propiedades (título, descripción). El ID de un elemento es la secuencia numérica que aparece al final de la URL en la página de visualización o edición; por lo tanto, para `/admin/item/11576`, el ID es 11576. También puede ver el ID del elemento en el panel de la derecha de la página de visualización del elemento.

![Datos específicos del medio con menú desplegable](../modules/modulesfiles/csvimport_mediaMapData.png)

**Datos genéricos** tiene un menú desplegable en el que puedes seleccionar una de cuatro opciones:

- **Plantilla de recurso (por etiqueta)**: Establece la plantilla para el medio por su nombre. El nombre de la plantilla tal y como se ha introducido en la hoja de cálculo y el nombre de la plantilla en Omeka S deben coincidir exactamente.
- **Clase de recurso (por término)**: Establece la clase de recurso para el medio. El término de la clase en la hoja de cálculo y en la instalación de Omeka S deben coincidir exactamente.
- **Propietario (por dirección de correo electrónico)**: Establezca el propietario del medio por dirección de correo electrónico. Debe ser la dirección de correo electrónico asociada a la cuenta del usuario en la instalación de Omeka S.
- **Visibilidad pública/privada**: Establezca la visibilidad del medio. Utilice «privada» o «pública» en la hoja de cálculo.

![Menú desplegable tal y como se describe](../modules/modulesfiles/csvimport_itemsMapgeneric.png)

**Fuente del archivo multimedia** Para las columnas de la hoja de cálculo que hacen referencia al archivo multimedia, selecciona para cada columna en el menú desplegable:

- HTML
- Imagen IIIF (enlace)
- Presentación IIIF (enlace)
- oEmbed (enlace)
- URL
- YouTube (enlace).

Aquí pueden aparecer otras opciones en función de tus módulos activos, como File Sideload. 

Asegúrate de hacer clic en «Aplicar cambios» en la parte inferior del panel; de lo contrario, no se guardará nada de lo que hayas configurado aquí.

Para eliminar una asignación, haz clic en el icono de la papelera en la fila correspondiente a esa asignación de datos. Esto eliminará *solo* la asignación, no los datos de la columna.

Si tiene datos en una columna de su CSV que no desea importar a su instalación de Omeka S, simplemente no asigne esa columna a una propiedad o tipo de datos.

#### Opciones de columna

Las opciones de columna son adicionales a las asignaciones. Si añade opciones sin asignar también los datos de la columna a un recurso, medio u otros datos, no se importará nada.

Para acceder a las opciones de los datos de una columna de tu CSV (representada por una fila en la tabla de importación), haz clic en el icono de la llave inglesa correspondiente al encabezado de esa columna.

Esto abrirá un panel deslizante en el lado derecho de la ventana del navegador con las siguientes opciones:

- **Usar separador de valores múltiples**: Marca esta casilla para utilizar el separador de valores múltiples para los datos de esta columna. El carácter del separador de valores múltiples se configura en la página de importación inicial, pero puedes cambiarlo en la pestaña «Configuración básica».
- **Idioma**: Establece el idioma de esta columna utilizando la [etiqueta de idioma IETF](https://en.wikipedia.org/wiki/IETF_language_tag){target=_blank} correspondiente al idioma en el que está escrito el texto. Esto anulará lo que hayas introducido en la configuración básica.
- **Importar valores como privados**: Marque esta casilla para establecer como privados todos los valores de propiedad *de esta columna*.
- **Tipo de datos**: Un menú desplegable con al menos tres opciones, que se corresponden con los [valores](../content/items.md#values) que se pueden utilizar al añadir propiedades a un elemento:
  - Importar como texto (predeterminado).
  - Importar como referencia URL. Puede establecer la etiqueta para el URI incluyendo el texto deseado después de un espacio, por ejemplo: `http://example.com This Is The Label`.
  - Importar como recurso Omeka S. Esto creará [recursos vinculados](../content/items.md#linked-resources). Si selecciona esta opción, debe elegir qué valores de propiedad deben coincidir para encontrar el recurso de Omeka deseado en su instalación, en el siguiente menú desplegable **Propiedad identificadora del recurso**. Debe ser una propiedad única, por lo que «Título» puede no ser una buena opción. 
		- Puede utilizar el ID interno de Omeka. El ID de un recurso es la secuencia numérica que aparece al final de la URL en la página de visualización o edición; por lo tanto, para `/admin/item/11576`, el ID es 11576. También puede ver el ID del recurso en el panel de la derecha de la página de visualización del recurso. Los elementos, los conjuntos de elementos y los medios tienen todos un ID.
		- Puedes incluir recursos que se estén creando en el mismo CSV, siempre y cuando los recursos a los que se vinculan ya se hayan creado en filas anteriores y se puedan encontrar con el valor de propiedad único indicado aquí. Si desea hacer esto, le recomendamos establecer un número de lote bajo (incluso 1) en la pestaña «Configuración avanzada», para garantizar que los recursos se hayan creado por completo antes de que otro recurso nuevo intente vincularse a ellos. 
  - Si tiene instalados ciertos módulos, como «Tipos de datos numéricos», es posible que haya opciones de tipo de datos adicionales proporcionadas por esos módulos.

Asegúrese de hacer clic en el botón «Aplicar cambios» situado en la parte inferior del panel. Para eliminar una configuración de opción de columna, haga clic de nuevo en el icono de la llave inglesa y deshaga los cambios manualmente.

#### Edición por lotes
Cuando seleccione una o más filas de la tabla (columnas de su archivo CSV), puede utilizar el botón «Opciones de edición por lotes» para aplicar las opciones de columna descritas anteriormente a varias columnas CSV a la vez.

![Un panel ofrece opciones para cambiar la configuración por lotes.](../modules/modulesfiles/csvimport_batchOptions2.png)

Asegúrate de hacer clic en el botón «Aplicar cambios» situado en la parte inferior del panel para guardar los cambios.

### Ajustes básicos para la importación de recursos mixtos

Estos ajustes se aplican a todo el CSV que está importando. Tenga en cuenta que estos ajustes pueden ser sobrescritos por las opciones de columna en la pestaña «Asignar a datos de Omeka S». Si una columna está asignada a una plantilla, clase o propietario, esos valores anularán estos ajustes; lo mismo ocurrirá con los ajustes de columna para el idioma y la privacidad.

![opciones descritas a continuación](../modules/modulesfiles/csvimport_mixedRBasic.png)

- **Plantilla de recurso**: Seleccione una plantilla de recurso del menú desplegable para aplicarla a los conjuntos de elementos importados. Puede utilizar el campo de búsqueda situado en la parte superior del menú desplegable para filtrar los resultados o encontrar una plantilla concreta.
- **Clase**: Seleccione una clase del menú desplegable para aplicarla a los conjuntos de elementos importados. Puede utilizar el campo de búsqueda situado en la parte superior del menú desplegable para filtrar los resultados o encontrar una clase concreta.
- **Propietario**: Establezca el propietario de los conjuntos de elementos seleccionando un usuario del menú desplegable. Puede utilizar el campo de búsqueda situado en la parte superior del menú desplegable para filtrar los resultados o encontrar un usuario concreto.
- **Visibilidad**: Establezca la visibilidad de los conjuntos de elementos importados como pública  o privada.
- **Conjuntos de elementos abiertos/cerrados a nuevas adiciones**: Establezca si los usuarios que no sean el propietario (ni los administradores del sitio ni los administradores globales) podrán añadir o editar los conjuntos de elementos.
- **Conjunto de elementos para elementos**: Seleccione de un menú desplegable los conjuntos de elementos existentes.
- **Sitios para elementos**: Seleccione uno o varios de sus sitios existentes para añadir nuevos elementos como recursos.
- **Separador de valores múltiples**: Introduzca aquí el carácter separador de valores múltiples, si ha utilizado alguno.
 - Las columnas de datos de su CSV deben estar separadas por comas; sin embargo, dentro de esas columnas puede añadir un carácter especial para crear entradas múltiples, por ejemplo, un punto y coma.
- **Idioma**: Establezca el idioma de los valores de la hoja de cálculo utilizando la [etiqueta de idioma IETF](https://en.wikipedia.org/wiki/IETF_language_tag){target=_blank} adecuada.

### Configuración avanzada de la importación de recursos mixtos

La configuración de Acción le permite cambiar la acción del proceso de una importación directa a una de las siguientes opciones:

- **Crear un nuevo recurso**: Opción predeterminada. Cada fila del CSV se convertirá en un nuevo recurso.
- **Añadir datos al recurso**: Añade nuevos datos al recurso.
- **Revisar datos del recurso**: Reemplaza los datos existentes en el recurso por los datos del CSV, excepto si están vacíos.
- **Actualizar datos del recurso**: Reemplaza los datos existentes en el recurso por los datos del CSV, incluso cuando la celda esté vacía.
- **Reemplazar todos los datos del recurso**: Elimina todas las propiedades del recurso y rellena con nueva información de la hoja.
- **Eliminar el recurso**: Elimina todos los recursos coincidentes.

Si seleccionas una de estas opciones en el menú desplegable, aparecerán tres ajustes adicionales en la pestaña. Estos ajustes ayudan al proceso a determinar sobre qué recursos se debe actuar.

![Opciones descritas a continuación](../modules/modulesfiles/csvimport_mixedRAdvAct.png)

- **Columna de identificador de recurso**: Seleccione de un menú desplegable las columnas de su CSV. Estos son los datos de su hoja de cálculo que se asignan a los datos existentes en su instalación de Omeka S.
- **Propiedad de identificador de recurso**: Seleccione de un menú desplegable todas las propiedades de su instalación de Omeka S. Esta debe ser la propiedad en la que ya tiene datos, la que utilizó para crear los datos de la columna anterior.
	- Ejemplo: si los datos de la columna **Identificador de recurso** son «Título» y la primera fila de datos tiene el título «Un estudio en escarlata», y configura la propiedad **Identificador de recurso** como «Dublin Core: Título», entonces las acciones se aplicarán a un recurso ya existente en su instalación de Omeka S cuya propiedad dc:title sea «Un estudio en escarlata».
	- Esto solo funcionará con coincidencias exactas.
  - Si tiene más de un recurso con datos coincidentes, solo se aplicará la acción al recurso más antiguo.
- **Acción sobre recursos no identificados**: Esta opción determina qué hacer cuando no existe ningún recurso coincidente en la instalación de Omeka S, pero la acción seleccionada solo se aplica a un recurso existente («Añadir», «Revisar», «Actualizar» o «Reemplazar»). Esta opción no se utiliza cuando la acción principal es «Crear» o «Eliminar». Las opciones disponibles son dos botones de opción:
  - Saltar la fila
  - Crear un nuevo recurso.

Además de lo anterior, la pestaña «Configuración avanzada» tiene una opción para establecer el número de filas que se procesarán por lote. Por defecto, está establecido en 20. Sin embargo, si se producen errores durante una importación, es posible que desee establecerlo en 5 o incluso en 1 para solucionar el problema y determinar el origen del error.

!!! nota
  Tenga en cuenta que al añadir datos podrá proporcionar varias filas con el mismo identificador; los valores de cada fila se añadirán junto a los anteriores.

	La revisión, actualización y sustitución de datos **borrarán** los datos proporcionados en filas anteriores de su CSV, si las filas posteriores utilizan el mismo identificador. Si desea importar varios valores (por ejemplo, dos valores de «Creador») en estos procesos, puede: colocarlos en dos columnas de la misma fila, asignados a la misma propiedad; o bien, colocarlos en una sola celda y utilizar separadores de valores múltiples. No olvide especificar su separador de valores múltiples en la pestaña «Configuración básica» y marcar la casilla «Usar separador de valores múltiples» en las opciones (icono de llave inglesa) de cada columna.

### Importación completa
Una vez que haya completado las asignaciones, las opciones de columna y cualquier configuración, haga clic en el botón Importar situado en la esquina superior derecha de la ventana del navegador. Esto debería iniciar la importación y redirigirle a la pestaña Importaciones anteriores. Debería ver un mensaje de confirmación que dice «Importando en ID de tarea [número]».

## Importar usuarios
Al importar usuarios, solo puede importar datos relacionados con la tabla de usuarios de Omeka S: el correo electrónico del usuario, el nombre para mostrar y el rol. No se importarán los datos adicionales que haya en su CSV. Ninguna de estas propiedades puede ser multivalor.

Esta pestaña muestra un menú desplegable inicial sobre una tabla con las columnas de su hoja de cálculo como filas. Cada fila muestra:

- Una casilla de verificación
- Un encabezado de columna de la hoja de cálculo
- Un botón con el símbolo más para añadir o modificar una asignación
- Una papelera para eliminar asignaciones
- Una columna para mostrar las opciones seleccionadas.

![Tabla como se ha descrito anteriormente, con filas para las columnas del CSV tituladas «correo electrónico», «nombre de visualización» y «rol».](../modules/modulesfiles/csvimport_users.png)

Para asignar un encabezado de columna a la información de usuario, haz clic en el botón con el símbolo más situado a la izquierda del encabezado de columna. Esto abrirá un panel deslizante en la parte derecha de la pantalla.

![Una flecha roja señala el botón con el signo más situado a la derecha del encabezado de columna «correo electrónico».](../modules/modulesfiles/csvimport_usersMapButton.png)

El panel desplegable contiene un menú desplegable para la información de los usuarios, con tres opciones:

- **Correo electrónico**: La dirección de correo electrónico del usuario
- **Nombre para mostrar**: El nombre para mostrar del usuario
- **Rol**: El [rol](../admin/users.md#roles-and-permissions) del usuario.

Los valores de rol que se deben utilizar en esta importación son los siguientes:

- `global_admin`
- `site_admin`
- `editor`
- `reviewer`
- `author`
- `researcher`.

![La misma tabla que la anterior, ahora con el panel de asignación abierto y el menú desplegable activado para mostrar las tres opciones «Correo electrónico», «Nombre para mostrar» y «Rol».](../modules/modulesfiles/csvimport_usersMap.png)

Una vez completadas las asignaciones, haz clic en el botón «Importar».

!!! nota
	Los usuarios **no** recibirán una notificación por correo electrónico cuando se cree una cuenta para ellos mediante la importación CSV. Normalmente, cuando se crea una cuenta manualmente, se envía a la dirección de correo electrónico una notificación que incluye un enlace para establecer la contraseña. Actualmente, la importación CSV no envía esos correos electrónicos, por lo que los usuarios no pueden establecer sus propias contraseñas. Los administradores del sitio deben establecer las contraseñas y luego compartirlas manualmente una vez que se hayan creado los usuarios mediante la importación CSV.

## Gestionar importaciones anteriores

Para revisar importaciones anteriores, haz clic en el módulo de importación CSV y selecciona la pestaña «Importaciones anteriores».

![Opciones de la subpestaña Importación CSV en el menú de navegación de la izquierda](../modules/modulesfiles/csvimport_pastimportsnav.png)

Esto mostrará una tabla con las siguientes columnas:

- Una casilla de verificación **Deshacer**
- **Fecha** de la importación
- **Acción** de la importación (crear, añadir, revisar, actualizar, sustituir o eliminar).
	- Debajo de la descripción de la acción hay enlaces a los detalles del trabajo y al registro del trabajo.
- **Comentario** introducido durante la importación o que indica un error
- **Resultado**: los elementos actualizados, añadidos o eliminados
- **Estado** de la importación
- **Propietario** de la importación.

![Tabla de importaciones anteriores de CSV](../modules/modulesfiles/csvimport_pastimports.png)

Para ver los detalles de una importación, haz clic en el enlace «Detalles del trabajo» situado debajo de la descripción de la acción. Para revisar los registros, especialmente en los casos en los que se haya producido un error, haz clic en el enlace «Registro» situado debajo de la descripción de la acción.

## Deshacer una importación

Para deshacer una importación, haz clic en el módulo Importación CSV y selecciona la página «Importaciones anteriores».

Marca la casilla «Deshacer» en la fila de la importación que deseas deshacer y haz clic en «Enviar».

![Una flecha roja señala una casilla «Deshacer» sin marcar en la página «Importaciones anteriores».](../modules/modulesfiles/csvimport_undo.png)

Dependiendo del tamaño de la importación, la acción de deshacer puede tardar algún tiempo. Una vez completada, el estado de la importación en la tabla «Importaciones anteriores» indicará «Deshacida», seguido de la fecha en la que se revirtió la importación.

## Solución de problemas
A continuación se enumeran los errores conocidos que pueden producirse durante una importación:  

- **Codificación**: Los archivos CSV para la importación deben estar codificados en UTF-8.
- ¿Sus tareas se inician pero no se completan? Es posible que tenga que [configurar la ruta de PHP](../configuration.md#php-path) para que su sistema pueda ejecutar el proceso en segundo plano para crear los elementos.

## Integración con otros módulos
Algunos otros módulos añaden funcionalidades al proceso de importación de CSV. Si tiene estos módulos instalados y activos, tendrá acceso a las siguientes opciones al utilizar la importación de CSV.

### Vocabulario personalizado
Si tienes [Vocabulario personalizado](customvocab.md) instalado y activo, añadirá tus vocabularios personalizados como tipos de datos en Omeka. Puede seleccionar estos tipos de datos durante la importación CSV. 

### Extract Text

Cuando el [módulo Extract Text](extracttext.md) está habilitado, se intentará extraer texto de cualquier archivo importado a través de un proceso de importación CSV. Si está disponible, esto incluirá Tesseract, un procesador de imágenes que emplea el reconocimiento óptico de caracteres (OCR). Puede desactivar extractores individuales en el menú de configuración de Extract Text para que no se ejecuten durante la importación. 

!!! nota
  Le recomendamos que desactive Tesseract, o todo el módulo Extract Text, cuando realice una importación que incluya imágenes como fotografías o dibujos. El OCR aplicado a imágenes que no contienen texto consumirá muchos recursos del procesador y puede causar problemas con la importación. 

### Carga lateral de archivos
Si tiene [Carga lateral de archivos](filesideload.md) (versión mínima 1.2.0) instalado y activo, puede utilizarlo como fuente de medios al ejecutar una importación CSV.

Todo lo que aparece en la pestaña **Asignar a datos de Omeka S** será igual. Cuando añadas una asignación y elijas la opción «Fuente multimedia», verás que ahora hay una opción para «Carga lateral».

![Menú desplegable de origen multimedia, con Sideload resaltado en azul](../modules/modulesfiles/csvimport_sideload.png)

Para los datos de esta columna, debes incluir el nombre completo del archivo, incluida la extensión. Así, por ejemplo, si quieres importar un archivo JPG llamado «Jekyll_and_Hyde_Title», los datos de la columna de medios del CSV que estás importando deberían ser `Jekyll_and_Hyde_Title.jpg`.

### Mapeo
Si tienes [Mapeo](mapping.md#csv-import-integration) (versión mínima 1.1.0) instalado y activo, dispondrás de opciones adicionales en el panel de la derecha al importar elementos. Ten en cuenta que estas opciones no aparecen para ningún otro tipo de importación, incluidos los recursos mixtos.

![Añadir panel de asignación con opciones adicionales para la latitud, la longitud y los límites del mapa](../modules/modulesfiles/csvimport_mapping1.png)

Para obtener más información, consulta la [sección de la página de asignación](mapping.md#csv-import-integration).

### Tipos de datos numéricos
Si tiene [Tipos de datos numéricos](numericdatatypes.md) instalado y activo, se añadirá la opción de establecer el tipo de datos de una columna como datos numéricos.

Las opciones son:

- Fecha/hora (ISO 8601)
- Intervalo (ISO 8601)
- Duración (ISO 8601)
- Número (entero o decimal).

![Panel de opciones de columna con el menú desplegable de tipos de datos abierto, mostrando opciones para tipos de datos numéricos, así como las opciones estándar](../modules/modulesfiles/csvimport_numericdata.png)

Al importar datos numéricos, estos deben tener un formato preciso. Comprueba siempre que tus datos se hayan importado correctamente en el formato elegido; CSV Import dejará los valores vacíos si no reconoce el formato. 

Utilice los siguientes formatos ISO 8601 para importar [fechas](https://en.wikipedia.org/wiki/ISO_8601#Dates){target=_blank}, incluyendo guiones entre los valores:

- `2022`
- `2022-08` (año y mes, sin fecha)
- `2022-08-18`.

Utilice los siguientes formatos ISO 8601 para añadir [horas](https://en.wikipedia.org/wiki/ISO_8601#Times){target=_blank} a sus valores de fecha:

- `2022-08-18T17:26:49+00:00` ([diferencia horaria con respecto al UTC](https://en.wikipedia.org/wiki/ISO_8601#Time_offsets_from_UTC){target=_blank})
- `2022-08-18T17:26:49Z` ([tiempo universal coordinado](https://en.wikipedia.org/wiki/ISO_8601#Coordinated_Universal_Time_(UTC)){target=_blank}). 

No se puede omitir el año al indicar un mes y/o un día. No se pueden proporcionar fechas ordinales (como, por ejemplo, `2000-175` para el día 175 del año 2000). 

Utilice el siguiente formato para importar [intervalos](https://en.wikipedia.org/wiki/ISO_8601#Time_intervals){target=_blank} con puntos de inicio y fin:

- `2007-03-01T13:00:00Z/2008-05-11T15:30:00Z` (Inicio y fin).

Utilice los siguientes formatos ISO 8601 para importar [duraciones](https://en.wikipedia.org/wiki/ISO_8601#Durations){target=_blank}, expresadas como número de años, número de meses, número de días, etc.:

- `P23DT23H` (23 días y 23 horas)
- `P3Y6M4DT12H30M5S` (3 años, 6 meses, 4 días, 12 horas, 30 minutos y 5 segundos).
