# DataScribe

El [módulo DataScribe](https://omeka.org/s/modules/DataScribe){target=_blank} añade herramientas de transcripción detalladas a los elementos de Omeka S, de modo que tus usuarios puedan transcribir texto en conjuntos de datos estructurados. 

![Interfaz de transcripción de DataScribe](modulesfiles/datascribe_admin.png)

Los investigadores suelen recopilar fuentes, como formularios gubernamentales o registros institucionales, con la intención de transcribirlas en conjuntos de datos que puedan analizarse o visualizarse. Este módulo permite a los investigadores identificar la estructura de los datos dentro de sus fuentes, acelerar la transcripción de las mismas y estructurar de forma fiable sus transcripciones en un formato apto para el análisis computacional. Los investigadores pueden convertir las fuentes en tablas de datos almacenadas como números, fechas, categorías y mucho más. Dado que el módulo DataScribe se basa en Omeka S, permite a los investigadores mostrar las transcripciones junto con las imágenes y los metadatos de las fuentes, realizar transcripciones de forma colaborativa y publicar sus resultados en la web.

!!! nota
  Las instrucciones detalladas para el usuario, los tutoriales y los casos prácticos están disponibles en [la wiki de este módulo](https://github.com/omeka-s-modules/Datascribe/wiki/){target=_blank}, que se encuentra en [el repositorio de Github del módulo](https://github.com/omeka-s-modules/Datascribe){target=_blank}. Esta página del manual incluirá un enlace a dicho repositorio para obtener más información cuando esté disponible. 

## Permisos

DataScribe añade funcionalidades exclusivamente a la parte administrativa de Omeka S. Los usuarios deben haber iniciado sesión para añadir transcripciones a los formularios de datos estructurados. A cualquier usuario de Omeka S, independientemente de su nivel, se le puede asignar un rol específico para el panel de control de DataScribe: transcriptor o revisor. Solo los administradores globales y los supervisores pueden asignar usuarios a estos roles, crear nuevos proyectos de DataScribe y gestionarlos.

Los proyectos de DataScribe configurados con visibilidad «pública» pueden ser vistos por cualquier usuario que haya iniciado sesión; los proyectos «privados» siguen siendo visibles para los usuarios con nivel de supervisor o administrador global. 

## Requisitos

Para poder exportar conjuntos de datos, el directorio `/files/assets` de su instalación de Omeka S debe ser escribible por el sistema.

### Tipos de archivo

La interfaz de transcripción de DataScribe admite actualmente los siguientes tipos de archivo:

- image/bmp
- image/gif
- image/jpeg
- image/png
- image/svg+xml.

Si tienes archivos TIFF o PDF, deberás convertirlos a uno de los formatos anteriores.

## Terminología

DataScribe es un módulo que utiliza elementos y conjuntos de elementos de Omeka S para facilitar la transcripción de datos estructurados (es decir, información escrita en columnas y filas o registrada en otros tipos de tablas).

**Proyecto**: un conjunto de datos o un grupo de conjuntos de datos. Algunos usos de DataScribe pueden tener varios proyectos, otros pueden tener solo uno. Cada proyecto tiene al menos un conjunto de datos. Se accede a todos los proyectos de DataScribe a través del panel de control.

**Conjunto de datos**: un grupo de documentos con el mismo marco de datos (estructura de tabla, conjunto de filas y columnas, etc.). Un conjunto de datos puede capturar toda la información registrada en un documento histórico, o solo una parte del documento. Los conjuntos de datos se crean utilizando conjuntos de elementos en Omeka S. Los conjuntos de datos están compuestos por elementos.

**Los elementos de DataScribe** se corresponden con los elementos de Omeka S: se trata de una correlación uno a uno. Cada elemento de DataScribe también existe como elemento en la instalación de Omeka S. El elemento de Omeka S es donde se pueden encontrar los metadatos (información) sobre la fuente, los derechos, etc., de cada elemento. Los archivos multimedia que se ven al transcribir están adjuntos a los elementos de Omeka S. Tenga en cuenta que un elemento de DataScribe puede estar en más de un conjunto de datos. Al transcribir, un elemento tiene al menos un registro.

**Los registros** son datos individuales de un elemento. Un único registro de DataScribe aparecerá como una fila cuando se exporten los datos transcritos. En términos de flujo de trabajo general, la transcripción se realiza a nivel de registro y la revisión a nivel de elemento. Sin embargo, los transcriptores pueden dejar notas y marcar registros individuales para que se les preste atención, incluso cuando el elemento completo no esté listo para ser revisado.

**Transcriptor**: un usuario de Omeka S (de cualquier nivel) puede ser designado transcriptor de DataScribe. Este usuario podrá transcribir los elementos que se le hayan asignado a través de proyectos. 

**Revisor**: un usuario de Omeka S (de cualquier nivel) puede ser designado revisor de DataScribe. Este usuario puede revisar y aprobar registros y elementos creados por otros. 

## El panel de control de DataScribe

Consulte esta guía en la wiki: [El panel de control de DataScribe](https://github.com/omeka-s-modules/Datascribe/wiki/Dashboard){target=_blank}.

## Crear un proyecto

!!! nota
	La wiki del módulo contiene información sobre [la planificación de proyectos y la conceptualización de cómo se puede configurar DataScribe para sus materiales](https://raw.githubusercontent.com/wiki/omeka-s-modules/Datascribe/Site-docs/support/projectplanning.md){target=_blank}. Es posible que desee leerla y planificar sus proyectos, formularios y conjuntos de datos antes de instalar o trabajar con DataScribe. 

El primer paso para trabajar en DataScribe es crear un nuevo proyecto. Cuando inicie sesión en una instalación y acceda al panel de control de DataScribe, es posible que vea todos los proyectos que otros usuarios han creado en DataScribe (si su nivel de permisos es lo suficientemente alto). Sin embargo, la sección «Mis proyectos» del panel de control estará vacía. Hay un botón en la esquina superior derecha que le permitirá «Añadir un nuevo proyecto».

![captura de pantalla del panel de control de DataScribe que muestra que el usuario no posee ni pertenece actualmente a ningún proyecto, con el botón «Añadir nuevo proyecto» visible en la esquina superior derecha](modulesfiles/datascribe_buildproject2.png)

Todos los proyectos deben tener un nombre, que se configura en la pestaña «Configuración» (y que puede editar más tarde). Opcionalmente, también puede añadir una descripción a su proyecto. 

Debe decidir si su proyecto va a ser público (visible para otras personas en la instalación) o privado. Hay un icono de un ojo tachado junto a los botones «Añadir» y «Cancelar»: al hacer clic en él, podrá activar y desactivar el modo privado. El modo predeterminado es privado.

![Captura de pantalla de la página de configuración de un nuevo proyecto de DataScribe con la pestaña «Configuración» activa y los campos del formulario para el nombre y la descripción del proyecto. En la esquina superior derecha, el cursor se encuentra sobre un símbolo de ojo tachado y muestra una información sobre herramientas con el texto «Hacer público»](modulesfiles/datascribe_buildproject3.png)

A continuación, debe añadir usuarios al proyecto. Si usted es tanto el creador como el responsable del proyecto, este paso incluirá añadirse a sí mismo como usuario, incluso si no hay nadie más trabajando en el proyecto con usted. A pesar de ser el propietario del proyecto, no se le convierte automáticamente en usuario del mismo. Esto significa que los proyectos pueden ser configurados por personas que gestionan la instalación de Omeka S, pero que no forman necesariamente parte de los equipos de proyecto individuales.

En la parte derecha de la pantalla aparecerá un menú que muestra todos los usuarios de la instalación de Omeka S. Puedes utilizar los elementos del menú alfabético (que se despliega al hacer clic en el triángulo) para navegar y buscar usuarios, o bien utilizar el campo «Filtrar usuarios» para buscar usuarios por nombre. Una vez que encuentres al usuario que deseas añadir, haz clic en su nombre para añadirlo al proyecto.

![Captura de pantalla de la página de configuración de un nuevo proyecto de DataScribe con la pestaña «Usuarios» activa y un menú en el lado derecho que muestra 72 usuarios potenciales para añadir al proyecto](modulesfiles/datascribe_buildproject1.png)

Una vez que haya añadido un usuario al proyecto, deberá establecer su función en el proyecto. Todos los usuarios comienzan automáticamente como «Transcriptor» y hay un menú desplegable que se puede utilizar para cambiar su función en el proyecto a «Revisor» si es necesario.

Añádase a sí mismo si tiene previsto utilizar su cuenta de usuario actual para trabajar como transcriptor o revisor. Si eres supervisor o administrador global y solo tienes previsto administrar el proyecto, no es necesario que te añadas a ti mismo: siempre tendrás acceso a todos los proyectos de la instalación. 

Completa el proceso de añadir un proyecto haciendo clic en el botón «Añadir» situado en la esquina superior derecha. Esto añade el proyecto a DataScribe y te redirigirá al panel de control del nuevo proyecto.

![Captura de pantalla de la página «Nuevo proyecto» de DataScribe.](modulesfiles/datascribe_buildproject4.png)

Verás un banner verde en la parte superior de la pantalla que te indicará que el proyecto se ha creado correctamente.  Desde aquí puedes utilizar el botón «Editar proyecto» situado en la esquina superior derecha para volver atrás y modificar cualquiera de los detalles del proyecto que hayas configurado inicialmente o para añadir usuarios adicionales. Como alternativa, puede pasar a la siguiente fase de la creación del proyecto y añadir un nuevo conjunto de datos.

## Crear un formulario

Los formularios proporcionan el marco para la transcripción estructurada en DataScribe. Al crear formularios para sus conjuntos de datos, dedique un tiempo a examinar sus fuentes y a pensar en cómo desea organizar sus formularios. Con algunas fuentes, puede que valga la pena crear varios formularios para capturar subconjuntos distintos de datos en la misma página.

DataScribe utiliza conjuntos de elementos de Omeka S como base para los conjuntos de datos. Los conjuntos de datos son un grupo de documentos con el mismo marco de datos (estructura de tabla, conjunto de filas y columnas, etc.). Un conjunto de datos puede capturar toda la información registrada en un documento histórico, o solo una parte del documento. Cada conjunto de datos tiene un formulario de transcripción.

Tendrás que crear un conjunto de elementos único para cada tipo de formulario que pretendas crear. Por ejemplo, si tienes datos con variaciones a lo largo del tiempo —como los registros de mortalidad o el censo de EE. UU.—, tendrás que crear diferentes conjuntos de elementos para cada variación del formulario que quieras capturar.

Este tutorial le guiará a través del proceso de planificación y creación de un formulario a partir de una fuente histórica con datos estructurados. El tutorial utiliza el [Directorio de Liverpool de Gore de 1860](https://archive.org/details/goresliverpooldi1860lond){target=_blank} como ejemplo, pero puede sustituirlo por sus propias fuentes si lo desea.

### Evalúa la fuente

Antes de empezar a crear tu formulario en DataScribe, revisa la fuente y hazte estas preguntas:

-   ¿Qué información necesito capturar para los análisis que quiero realizar?
-   ¿Qué resultados serán más útiles para ese análisis?

Revisa la fuente original. Anota todos los posibles puntos de datos de la página. A continuación, decide cuáles son relevantes para tus preguntas y, por lo tanto, deben incluirse en tu(s) formulario(s).

![Ejemplo de página de directorio digitalizada](modulesfiles/datascribe_goresliverpooldirectory1860_p40.png)

En esta página del _Gore's Liverpool Directory_, hay al menos 11 puntos de datos potenciales: número de página, apellido, nombre, tipo de entrada (persona, empresa, etc.), descripción, número de calle, nombre de la calle, otra información de la dirección, número de calle de la segunda dirección, nombre de la calle de la segunda dirección, otra información de la segunda dirección. La forma de organizarlos depende de ti y puede guiarse por tus preguntas de investigación.

### Hacer coincidir los puntos de datos y los campos del formulario

Crearás tu formulario en DataScribe, que cuenta con un conjunto definido de opciones para los campos.

|Campo |Tipo de entrada |Opciones|
--- | --- | --- |
|Casilla de verificación |Casilla de verificación | Marcar la casilla de forma predeterminada|
|Fecha|Menús desplegables|Establecer el año mínimo y máximo. Establecer el año, mes y/o día predeterminados|
|Fecha y hora|Menús desplegables|Establecer el año mínimo y máximo. Establecer el año, mes, día, hora, minuto y/o segundo predeterminados|
|Número|Solo números. Decimales con punto, no con coma.|Establecer el valor mínimo y máximo.|
|Botón de opción|Haga clic en un botón de opción|Introduzca las opciones para el botón de opción escribiendo cada una en una nueva línea|
|Seleccionar|Menú desplegable|Introduzca las opciones para el botón de selección escribiendo cada una en una nueva línea|
|Texto|Campo de texto de una sola línea|Establezca una longitud mínima o máxima|
|Área de texto|Área de texto grande|Establezca el número de filas para la altura del campo
Hora|Menús desplegables|Establezca la hora, los minutos y/o los segundos por defecto|

Además, puede marcar cualquier campo como obligatorio. Si un transcriptor deja en blanco un campo obligatorio, DataScribe marca ese registro como no válido.

Se debe designar un campo como campo principal, que actuará como identificador del registro.

Utilice la hoja de cálculo o su propio documento para decidir qué campos desea utilizar al crear su formulario o formularios. Es posible que tenga que crear varios formularios para capturar mejor los datos de una fuente.

Un formulario para la página de ejemplo podría ser el siguiente:

| Datos en la fuente | Tipo de campo | Ajustes opcionales | Notas |
| :----------------|:----------------|:------------------|:----- |
| Nombre (R, P)  | Texto | | ¿Separar en nombre y apellidos? ¿O un solo campo para ambos? |
| Tipo de entrada  | Seleccionar o radio |  | Particular, empresa, organización, etc. |
| Descriptor     | Área de texto | | Escribir tal y como aparece en el directorio, por ejemplo, «agentes de seguros» o «estanco júnior»  |
| Número de calle  | Número | | Si se indica |
| Nombre de la calle    | Texto | | Se puede concatenar con el número en la exportación |
| Zona | Texto o selección  | | ¿Está lo suficientemente estandarizado como para crear un campo de selección? |

Nota: Los campos obligatorios están marcados con R. Los campos principales están marcados con P.

### Crea un formulario siguiendo tu plan

Puedes crear un formulario para tu conjunto de datos al añadirlo o editarlo. En la pestaña del generador de formularios, utiliza el plan que has elaborado como guía para añadir bloques de campos al formulario.

Esta imagen muestra el formulario descrito anteriormente en proceso de creación. El usuario ha guardado el formulario al menos una vez, por lo que los campos «Nombre» y «Tipo de anuncio» tienen la etiqueta correcta en lugar de simplemente «Nuevo campo». El bloque del descriptor está abierto para mostrar la guía que se ha añadido a la descripción del campo, tal y como se sugiere en las notas anteriores.

![Imagen tal y como se describe. La guía dice: «Escriba tal y como aparece en el directorio, es decir, “agentes de seguros” ](modulesfiles/datascribe_buildform.png)

### Importar y exportar formularios

En un proyecto de DataScribe, es posible que necesites utilizar el mismo formulario o uno similar para varios conjuntos de datos. En lugar de crear el mismo formulario una y otra vez, puedes exportarlo desde un conjunto de datos existente y reutilizarlo. Esto resulta especialmente útil cuando se trata de formularios más largos.

Ten en cuenta que solo puedes importar un formulario cuando añades un nuevo conjunto de datos. No puedes importar un formulario a un conjunto de datos ya existente. 

<div style="padding:68.15% 0 0 0;position:relative;"><iframe src="https://player.vimeo.com/video/1192402311?badge=0&amp;autopause=0&amp;player_id=0&amp;app_id=58479" frameborder="0" allow="autoplay; fullscreen; picture-in-picture; clipboard-write; encrypted-media; web-share" referrerpolicy="strict-origin-when-cross-origin" style="position:absolute;top:0;left:0;width:100%;height:100%;" title="Exportar e importar formularios en DataScribe"></iframe></div><script src="https://player.vimeo.com/api/player.js"></script>

#### Exportar un formulario de conjunto de datos

Vaya al conjunto de datos en el que ya ha creado el formulario que desea utilizar o modificar. Desplácese hasta la parte inferior de la página del conjunto de datos. En el panel de la derecha hay un encabezado que dice «Exportar formulario». Debajo del encabezado hay un enlace con el texto «Haga clic para exportar el formulario (JSON)».

Haga clic en el enlace para descargar el formulario. El título predeterminado de cualquier formulario exportado es «form_export»: si tiene pensado utilizar el formulario más de una vez, o va a exportar varios formularios, cambie el nombre del archivo al descargarlo.

#### Importar un formulario de conjunto de datos

**Solo** puede importar un formulario existente al crear un nuevo conjunto de datos.

Recuerde que un conjunto de datos se basa en un conjunto de elementos, así que organice los elementos pertinentes en un conjunto de elementos, luego cree un nuevo conjunto de datos basado en ese conjunto de elementos e importe el formulario durante ese proceso de creación. 

Crea un nuevo conjunto de datos que utilice el mismo formulario que has exportado anteriormente. Añade información para el título (obligatorio) y selecciona un conjunto de elementos que desees utilizar. Si no añades directrices al crear el conjunto de datos, asegúrate de añadirlas más adelante.

Hacia la parte inferior del formulario «Añadir conjunto de datos», hay una opción para importar un formulario. Haga clic en el botón. A continuación, utilizando el gestor de archivos de su navegador, busque el archivo del formulario que ya ha descargado. Asegúrese de guardarlo. Haga clic en «Añadir nuevo conjunto de datos».

Cuando entre a editar su nuevo conjunto de datos, ahora debería ver el formulario que ha importado. Desde aquí, también puede añadir, eliminar o modificar campos según sea necesario para este conjunto de datos específico.

## Sincronizar un conjunto de datos

<div style="padding:60.52% 0 0 0;position:relative;"><iframe src="https://player.vimeo.com/video/1192402310?badge=0&amp;autopause=0&amp;player_id=0&amp;app_id=58479" frameborder="0" allow="autoplay; fullscreen; picture-in-picture; clipboard-write; encrypted-media; web-share" referrerpolicy="strict-origin-when-cross-origin" style="position:absolute;top:0;left:0;width:100%;height:100%;" title="DataScribe - Sincronizar conjunto de datos"></iframe></div><script src="https://player.vimeo.com/api/player.js"></script>

La sincronización actualiza el conjunto de datos con los elementos que se encuentran actualmente en el conjunto de elementos de Omeka S. Asegúrate de sincronizar tus conjuntos de datos y conjuntos de elementos con frecuencia, especialmente cada vez que se añadan o eliminen elementos del conjunto de elementos en la instalación de Omeka S.

Por ejemplo, es posible que hayas iniciado un proyecto y hayas creado un formulario para que coincida con un conjunto de elementos lleno de elementos que parecen similares, como páginas del censo. Entonces descubres que, en algún momento, se ha producido un cambio en el formato de cada página. Puedes crear un segundo conjunto de elementos, mover los elementos posteriores del primer conjunto al segundo, copiar (exportar y volver a importar) tu primer formulario y modificarlo para adaptarlo al segundo formato que has descubierto, sincronizar el proyecto para mostrar los elementos actuales de cada conjunto de elementos y continuar transcribiendo los elementos posteriores. 

Una vez que hayas creado el conjunto de datos, se te redirigirá a la página de exploración del conjunto de datos. Debería aparecer un mensaje en el área de trabajo principal que dice «No se han encontrado elementos. Sincronizar este conjunto de datos».

Para sincronizar tu conjunto de datos tienes dos opciones.

En primer lugar, puedes hacer clic en la frase «Sincronizar este conjunto de datos» situada en el centro del panel de control del conjunto de datos, y, a continuación, hacer clic de nuevo en el panel de la derecha para confirmar la sincronización. La primera sincronización rellenará el conjunto de datos con elementos del conjunto de elementos de origen.

![Página de nuevo conjunto de datos creado sin elementos. Una flecha grande apunta al enlace «sincronizar este conjunto de datos».](modulesfiles/datascribe_syncDataset1.png)

En segundo lugar, puede utilizar el menú desplegable «Más acciones» situado en la esquina superior derecha de la ventana y seleccionar la opción «Sincronizar conjunto de datos». Esta acción está siempre disponible, incluso después de haber comenzado a transcribir los elementos del conjunto de datos.

![Página de nuevo conjunto de datos creado sin elementos y con el menú desplegable «Más acciones» abierto. Una flecha grande señala la opción «sincronizar conjunto de datos» en el menú desplegable.](modulesfiles/datascribe_syncDataset2.png)

Actualice la página del conjunto de datos para comprobar los elementos. El proceso de sincronización actualiza el conjunto de datos para que coincida con los elementos del conjunto de elementos de Omeka S de origen. 

Tenga en cuenta que cualquier elemento que se haya eliminado del conjunto de elementos de Omeka S se eliminará del conjunto de datos de DataScribe, junto con cualquier registro que se haya creado para esos elementos.

Por último, recuerde que la sincronización no envía ninguna información de DataScribe a Omeka S. Los datos de DataScribe (guardados en formularios) permanecen en las entradas de la propia base de datos del módulo y no se transfieren a metadatos visibles en los elementos de Omeka S. 

## Transcribir un elemento

[Hay información más detallada sobre la transcripción en la wiki](https://github.com/omeka-s-modules/Datascribe/wiki/Transcribing-data){target=_blank}.

Para comenzar a transcribir, vaya a la página Elementos de su conjunto de datos. Verá todos los elementos de ese conjunto de datos. Una vez que filtre los elementos «bloqueados para mí», podrá hacer clic en cualquiera de ellos.

Se le redirigirá a la página de registros. Los registros de las transcripciones aparecerán en el centro de la pantalla. En la parte derecha de la pantalla se encuentran las acciones del elemento con el estado de bloqueo, lo que significa que solo el revisor y la persona a la que está bloqueado pueden editarlo. En la esquina superior derecha, haga clic en «Añadir nuevo registro».

### La pantalla de transcripción

En la parte central derecha se encuentra el formulario que debe rellenar según la imagen de la parte central izquierda de la pantalla. Un asterisco significa que ese campo es obligatorio.

En «Directrices» hay instrucciones específicas que el gestor del proyecto puede dejar para que las sigan los transcriptores mientras trabajan.

En la parte derecha de la pantalla hay un panel llamado «Acciones del registro», para notas adicionales destinadas a los transcriptores o revisores.

En la parte superior izquierda hay tres botones para ajustar la pantalla y mejorar el flujo de trabajo. «Habilitar modo de enfoque» te permite ocultar los paneles laterales mientras transcribes. «Modo de entrada rápida» elimina las casillas de verificación adicionales del formulario. El tercer botón modifica el diseño: puedes elegir la vista horizontal (imagen junto al formulario) o vertical (imagen encima del formulario).

En la esquina superior derecha, haz clic en «Guardar y...» para permanecer en el registro si guardas periódicamente o para volver a la página de registros.

De vuelta en la página de registros, hay un menú desplegable en el panel lateral derecho, debajo de «Acciones del elemento», para el «Estado del envío». Haz clic en él para seleccionar «Enviar para revisión» y ya está.

<div style="padding:56.25% 0 0 0;position:relative;"><iframe src="https://player.vimeo.com/video/1192402313?badge=0&amp;autopause=0&amp;player_id=0&amp;app_id=58479" frameborder="0" allow="autoplay; pantalla completa; imagen en imagen; escritura en el portapapeles; medios cifrados; web-share" referrerpolicy="strict-origin-when-cross-origin" style="position:absolute;top:0;left:0;width:100%;height:100%;" title="Cómo transcribir con DataScribe"></iframe></div><script src="https://player.vimeo.com/api/player.js"></script>

### Transcribir fuentes no digitalizadas 

[Consulte el tutorial en la wiki](https://raw.githubusercontent.com/wiki/omeka-s-modules/Datascribe/Site-docs/resources/tutorials/nondigitizedsources.md){target=_blank}.

## Revisar transcripciones

[Hay información más detallada sobre la revisión de transcripciones en la wiki](https://github.com/omeka-s-modules/Datascribe/wiki/Reviewing-transcriptions){target=_blank}.

Los revisores comprueban las transcripciones después de que los transcriptores hayan completado la transcripción de un elemento de DataScribe y la hayan enviado para su revisión. Usted deberá aprobar la transcripción o devolverla al transcriptor para que la corrija.

Hay varias formas de encontrar los registros para su revisión. La forma más fácil es buscar en Mis proyectos y seleccionar Todos los elementos que necesitan revisión en el conjunto de datos que desees revisar. Una vez que llegues a la página de un conjunto de datos, puedes filtrar los elementos que necesitan revisión.

Como revisor, verás todas las opciones de filtro disponibles para los transcriptores, así como «Elementos que necesitan revisión» y «Elementos que he revisado». Seleccione la opción «Elementos que necesitan revisión» y haga clic en el botón «Filtrar» para ver solo los elementos que necesitan revisión.

![Tabla de elementos de un conjunto de datos con las opciones de filtro abiertas. Una flecha señala la opción «Todos los elementos que necesitan revisión».](modulesfiles/datascribe_reviewitems-filter.png)

Puede ordenar estos elementos por título, fecha de envío para revisión, historial de revisión del elemento y si el elemento tiene prioridad o no.

Una vez que encuentre el elemento que debe revisar, seleccione el título del elemento para ver la página de registros. Las directrices de su proyecto deben determinar la relación entre los registros y los elementos.

Un icono de exclamación roja junto a cualquier número de registro indica un problema con los campos obligatorios de los registros. Otros problemas de transcripción, como errores ortográficos, campos omitidos accidentalmente o secciones ilegibles, requieren que revises todo el formulario.

Es posible desplazarse por la tabla de registros para ver las entradas sin la imagen del elemento, pero esto depende del nivel de revisión que exijan las directrices del proyecto.

En este punto, revisar una transcripción es muy similar a transcribirla. Haz clic en el icono del lápiz para ir al formulario de DataScribe.

Puedes marcar «Necesita revisión» y dejar notas en el registro. Si estás transcribiendo varios registros por elemento, las acciones del registro en el lado derecho permitirán a los revisores marcar el registro específico.

Puedes dejar notas a nivel de elemento en «Acciones del elemento». Desde aquí, haz clic en «Guardar… y volver a los registros».

Establecer un estado de revisión para el elemento es el último paso. El elemento debe establecerse como «aprobado» o «no aprobado». En «Estado de revisión», seleccione «Marcar como aprobado» o «Marcar como no aprobado».

Si el elemento no se aprueba, debe dejar una nota en el elemento o registro para indicar al transcriptor qué problemas debe corregir y marcar solo las áreas que necesitan revisión cuando se vuelva a enviar el elemento.

Haga clic en «guardar» para asegurarse de que se guardan los cambios.

<div style="padding:56.25% 0 0 0;position:relative;"><iframe src="https://player.vimeo.com/video/1192402312?badge=0&amp;autopause=0&amp;player_id=0&amp;app_id=58479" frameborder="0" allow="autoplay; fullscreen; picture-in-picture; clipboard-write; encrypted-media; web-share" referrerpolicy="strict-origin-when-cross-origin" style="position:absolute;top:0;left:0;width:100%;height:100%;" title="DataScribe: cómo revisar"></iframe></div><script src="https://player.vimeo.com/api/player.js"></script>

## Exportar un conjunto de datos 

Puede comenzar a exportar su conjunto de datos tan pronto como tenga al menos un elemento aprobado. Primero debe validar el conjunto de datos. Para ello, vaya al menú desplegable «Más acciones» situado en la esquina superior derecha de la ventana del navegador. Seleccione «Validar conjunto de datos».

Al hacer clic en esta opción, se abre un panel que explica en qué consiste la validación. Para validar el conjunto de datos, haz clic en el botón del panel. Puedes actualizar la página y comprobar la marca de tiempo de la validación más reciente en el panel «Metadatos del conjunto de datos» para asegurarte de que se ha ejecutado correctamente.

<div style="padding:73.62% 0 0 0;position:relative;"><iframe src="https://player.vimeo.com/video/1192400871?badge=0&amp;autopause=0&amp;player_id=0&amp;app_id=58479" frameborder="0" allow="autoplay; fullscreen; picture-in-picture; clipboard-write; encrypted-media; web-share" referrerpolicy="strict-origin-when-cross-origin" style="position:absolute;top:0;left:0;width:100%;height:100%;" title="DataScribe - Exportar datos"></iframe></div><script src="https://player.vimeo.com/api/player.js"></script>

Una vez validados los datos, puede exportar su conjunto de datos. En el menú desplegable «Más acciones», seleccione «Exportar conjunto de datos». Haga clic en el botón de exportar conjunto de datos y espere a que finalice la tarea. Puede ver la marca de tiempo de la última exportación en el panel de metadatos del conjunto de datos.

![Panel de metadatos del conjunto de datos con flechas azules que señalan las opciones de último conjunto de datos validado, último conjunto de datos exportado y descarga del conjunto de datos](modulesfiles/datascribe_exportData.png)

Para acceder a la exportación, utilice el enlace «Haga clic para descargar el conjunto de datos (CSV)» situado en la parte inferior de la barra lateral de metadatos del conjunto de datos. Si hace clic en el enlace, se abrirán los datos CSV en la ventana de su navegador. Para guardar el archivo, haga clic con el botón derecho o pulse Control y haga clic, y utilice el menú de su navegador para guardar el archivo vinculado en su ordenador.

Cada exportación de DataScribe tiene columnas para el número de elemento de Omeka, el número de elemento de DataScribe, el número de registro de DataScribe y la posición del registro de DataScribe.

![Fragmento de un CSV exportado visualizado en Excel que muestra las columnas con la metainformación de Omeka y DataScribe](modulesfiles/datascribe_exportDataExcsv.png)

## Importar un conjunto de datos existente 

[Consulte el tutorial en la wiki](https://raw.githubusercontent.com/wiki/omeka-s-modules/Datascribe/Site-docs/resources/tutorials/reimportdata.md){target=_blank}.
