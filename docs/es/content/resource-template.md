# Plantillas de recursos

Una **plantilla de recursos** es un conjunto de propiedades predefinidas, que puede incluir opcionalmente una clase, y que sirve para guiar la creación de elementos y la interpretación de las propiedades. 

Las plantillas de recursos se gestionan desde el panel de administración, al que se accede a través del menú de navegación de la izquierda, en la sección denominada **Recursos**. 

![Vista básica de la pestaña de plantillas de recursos, en la que se muestran los títulos de las columnas y una plantilla](contentfiles/templates_browse.png)

En la parte superior izquierda de la tabla aparece el número de páginas de elementos, junto con flechas de avance y retroceso. El número de página actual es un campo editable: introduce cualquier número de página válido y pulsa la tecla «Intro» en tu teclado para ir a esa página.

En la parte derecha, encima de la tabla, hay dos menús desplegables que te permiten ordenar las plantillas de recursos. Puedes ordenarlas por: **etiqueta**, **clase**, **propietario** o número de **elementos** asignados a una plantilla, y mostrarlas en orden ascendente o descendente. 

Puedes utilizar los iconos de la fila de cada plantilla para: **editar** (lápiz), **eliminar** (papelera) o **ver detalles** (tres puntos). Si haces clic en el número de elementos que aparecen en una plantilla, accederás a una lista con todos esos elementos. 

[Este vídeo tutorial](https://vimeo.com/290924872){target=_blank} ofrece una visión general sobre cómo crear y aplicar plantillas de recursos:

<div style="padding:62.5% 0 0 0;position:relative;"><iframe src="https://player.vimeo.com/video/290924872?h=c6359076cd" style="position:absolute;top:0;left:0;width:100%;height:100%;" frameborder="0" allow="autoplay; fullscreen; picture-in-picture" allowfullscreen></iframe></div><script src="https://player.vimeo.com/api/player.js"></script>
<p><a href="https://vimeo.com/290924872">Plantillas de recursos de Omeka S</a> de <a href="https://vimeo.com/omeka">Omeka</a> en <a href="https://vimeo.com">Vimeo</a>.</p>

## Permisos de las plantillas de recursos

Cuando un usuario crea una plantilla de recurso, se convierte en el «propietario» de dicha plantilla. La mayoría de los niveles de usuario tienen la capacidad de crear plantillas y siempre pueden eliminar sus propias plantillas. Solo los niveles superiores pueden eliminar plantillas que sean propiedad de otros. 

| Categoría | Permiso | Administrador global | Supervisor | Editor | Revisor | Autor | Investigador |
|-----|-----|---|---|---|---|---|---|
| Plantillas de recursos | Añadir | Sí | Sí | Sí | No | Sí | No |
| | Editar/Eliminar  | Todas | Todas | Todas | No | Las propias | No |

Ten en cuenta que, cuando cambias el rol de un usuario —por ejemplo, de Autor a Investigador—, seguirá siendo propietario de las plantillas que creó cuando tenía permiso para hacerlo. Al eliminar a un usuario, sus plantillas quedan huérfanas: aparecerán como «[sin propietario]» y no podrán reasignarse a otro usuario.

## Ver plantillas de recursos
Al hacer clic en el título de una plantilla de recurso, se accede a una vista en tabla de todas las propiedades y opciones de propiedad de dicha plantilla.

![Vista de la plantilla «Texto», con las propiedades en una tabla, incluyendo la configuración del tipo de datos y la etiqueta alternativa.](contentfiles/templates_view.png)

Cada propiedad se muestra como una fila en la tabla, con columnas para:

- Etiqueta original, con un botón de puntos suspensivos para ver el vocabulario de la propiedad, el término, el comentario original y el número de elementos que utilizan actualmente la propiedad
- Tipo(s) de datos
- Etiqueta alternativa
- Comentario alternativo
- Si la propiedad es obligatoria
- Si los valores de la propiedad son privados
- Si la propiedad tiene un idioma predeterminado (que se puede anular al introducir valores).

Utiliza los botones de la esquina superior derecha de esta página para exportar o editar la plantilla. 

## Recurso base
Todas las instalaciones de Omeka S incluyen una plantilla de «Recurso base» que se corresponde con los campos de metadatos exigidos por la [Biblioteca Pública Digital de Estados Unidos (DPLA)](https://dp.la/){target=_blank}. Aparecerá en la tabla de plantillas de recursos como «Recurso base» sin propietario. 

![Plantilla de recurso base mostrada en la tabla de plantillas](contentfiles/templates_base1.png)

La plantilla de recurso base contiene los siguientes campos de Dublin Core: Título; Derechos; Tipo; Creador; Fecha; Descripción; Formato; Idioma; Cobertura espacial (Lugar); Editor; Título alternativo; Colaborador; Extensión; Identificador; Relación; Es sustituido por; Sustituye a; Titular de los derechos; Tema; Cobertura temporal.

## Añadir una plantilla de recurso
En la pestaña **Plantillas de recursos** del panel de administración, haz clic en el botón «Añadir nueva plantilla de recurso».

Se cargará la página «Nueva plantilla de recurso» con opciones para la etiqueta, la clase sugerida y las propiedades **Título** (`dcterms:title`) y **Descripción** (`dcterms:description`).

![La página «Añadir plantilla de recurso», con los campos de título, clase y las propiedades Título y Descripción ya rellenados](contentfiles/templates_add.png)

1. En la propiedad «Etiqueta», escribe la etiqueta de tu nueva plantilla. Este será el texto que aparecerá en el menú desplegable de plantillas de recursos al crear un elemento, así que asegúrate de que la etiqueta sea clara.
1. Si lo deseas, selecciona una clase para asociarla a la plantilla.
1. Añade propiedades de la lista de vocabularios del menú situado a la derecha de la pantalla. Puedes filtrar las propiedades en el cuadro de texto o seleccionar una de un vocabulario específico utilizando las flechas situadas a la derecha de los nombres de los vocabularios. 
1. Si lo deseas, modifica la propiedad (consulta «Opciones de la propiedad», más abajo).

Asegúrate de «Guardar» tu plantilla de recurso antes de salir de esta página.

Los usuarios que seleccionen esta plantilla de recurso al crear un elemento podrán seguir añadiendo otras propiedades al elemento, y solo tendrán que rellenar aquellos campos que marques como obligatorios.

### Opciones de propiedad
Puede modificar la etiqueta de visualización, añadir un comentario a la etiqueta, establecer una propiedad como obligatoria y definir el tipo de datos predeterminado para cada propiedad de su plantilla.

Para ello, haga clic en el icono de edición (lápiz) situado en la fila de la propiedad que desee modificar. Esto abrirá un panel en la parte derecha de la pantalla que te permitirá editar las propiedades.

![El panel de opciones de la propiedad «Título» sin cambios, con las opciones que se describen a continuación](contentfiles/template_configdrawer.png)

Debes hacer clic en el botón «Aplicar cambios», situado en la parte inferior del panel, para cada propiedad que edites antes de salir del panel o pasar a otra propiedad. Si no haces clic en «Aplicar cambios», tus modificaciones no se guardarán.

![Primer plano del panel de edición de opciones de propiedades con una gran flecha roja apuntando hacia abajo en ángulo hacia el botón «Aplicar cambios», que se encuentra en la parte inferior de la imagen.](contentfiles/templates_setchanges.png)

#### Etiqueta 
Cambia la etiqueta que se muestra para la propiedad cuando se aplica la plantilla a un elemento introduciendo el texto que desees que aparezca en el campo de etiqueta «Alternativa» de cada propiedad. Esto modificará tanto la página de edición del elemento en el panel de administración como la página de visualización del elemento en la parte pública. 

#### Comentario
Añade comentarios alternativos para la propiedad en el campo «Alternativo» de esta sección. Esto modificará el texto que aparece debajo del nombre de la propiedad cuando los usuarios creen elementos utilizando tu plantilla de recursos. Los comentarios son solo para uso interno y se muestran en la página de edición del elemento, pero no se puede acceder a ellos desde las páginas públicas. Puedes utilizar este campo para proporcionar orientación e instrucciones a los usuarios con permisos de edición.
 
#### Otras opciones 

La casilla de verificación «Usar como título del recurso» te permite seleccionar una propiedad que sirva como título del recurso, en lugar de la predeterminada (`dcterms:title`). Esta propiedad se mostrará en el campo «título» de las páginas de navegación.

La casilla de selección «Usar como descripción del recurso» le permite seleccionar una propiedad que sirva como descripción del recurso, en lugar de la predeterminada (`dcterms:description`). Esta propiedad se mostrará en el campo «descripción» de las páginas de navegación. 

La casilla de selección «Obligatorio» establece si una propiedad es obligatoria cuando se utiliza la plantilla. Si se marca, los usuarios no podrán guardar un elemento o un conjunto de elementos utilizando esta plantilla sin añadir datos para esta propiedad.

La casilla de selección «Privado» establece la visibilidad predeterminada de los datos de esta propiedad. Si está marcada, cualquier dato añadido por un usuario para esta propiedad solo será visible para el propietario del elemento o conjunto de elementos, los administradores globales, los administradores del sitio y los editores. No será visible para el público. **Nota**: Los usuarios que trabajen con la plantilla podrán activar o desactivar la visibilidad de esta propiedad según cada caso concreto. Se trata únicamente de una configuración predeterminada, no de una restricción obligatoria.

##### Tipos de datos

En Omeka S hay tres tipos de datos predeterminados. Estos tipos de datos permiten introducir texto simple, o bien dos tipos que ofrecen enlaces dinámicos a otros recursos: ya sean recursos dentro de tu instalación de Omeka o, mediante un URI, a sitios externos. Por ejemplo, es posible que desees tener un elemento «Persona» y utilizar esa persona en el campo «Creador» de otros elementos; o bien, quizá quieras enlazar a una entrada externa del vocabulario controlado correspondiente al «Creador», como en Wikidata. 

Todos los campos de todas las plantillas de recursos ofrecen estos tres tipos de datos de forma predeterminada, a menos que se indique lo contrario. Mediante el menú desplegable «Tipo de datos», puedes designar uno o más tipos de datos para cada propiedad. Cualquiera que elijas se cargará automáticamente cuando alguien edite un recurso utilizando esa plantilla, y solo podrá utilizar esos tipos de datos para el elemento al usar esta plantilla de recurso. 

- Texto: entrada textual. 
- URI: un enlace con etiqueta.
- Recurso: los usuarios de la plantilla pueden seleccionar entre elementos, archivos multimedia o conjuntos de elementos existentes en la instalación, o bien seleccionar cualquier recurso.
- Los módulos pueden añadir opciones adicionales: 
  - [Tipos de datos numéricos](../modules/numericdatatypes.md) pueden restringir los valores a uno de los cuatro tipos de datos numéricos, lo que permite una introducción de datos estructurada. 
	- [Sugerencia de valores](../modules/valuesuggest.md) modificará el campo de entrada de texto para ofrecer valores sugeridos a partir de vocabularios controlados, pero el usuario puede ignorar estas sugerencias e introducir cualquier texto. 
	- [Vocabulario personalizado](../modules/customvocab.md) **obligará** a los usuarios a elegir una de las entradas del vocabulario proporcionado como valor de la propiedad. Si se desea, se pueden asignar otros tipos de datos (como «Texto») como alternativa al vocabulario personalizado. 

![Página de edición de un elemento, en la que se muestra una propiedad dcterms:date que restringe la entrada a los tipos de datos «Timestamp» e «Interval».](contentfiles/templates_datatype-date.png)

Se pueden seleccionar varios tipos de datos; por ejemplo, ofreciendo a los usuarios la opción de introducir «Texto» o «Recurso», pero no «URI». Todas las opciones aparecerán en el campo de tipos de datos con una «X» a la derecha de su etiqueta; haz clic en la «X» para eliminar ese tipo de datos. 

Ten en cuenta que, aunque los tipos de datos del vocabulario sugeridos son esencialmente entradas de texto, al seleccionar uno o varios de ellos se impedirá que el usuario introduzca valores URI, a menos que esto también se incluya explícitamente como opción. Es posible que tengas que añadir URI si hay vocabularios externos no incluidos en Value Suggest que desees utilizar como alternativa. Los tipos de datos aparecen en el mismo orden en que aparecen en el menú desplegable, por lo que no puedes priorizar los tipos de datos ordenándolos.

![Página de edición de un elemento, en la que se muestra una propiedad dcterms:subject con campos de texto ya existentes y la opción de añadir más utilizando las incorporaciones del módulo Value Suggest: «LC: Subject Headings», «LC: Children’s Subject Headings» y «Omeka: Property».](contentfiles/templates_datatype-valuesuggest.png)

En la imagen anterior, se pueden añadir entradas de tema textuales utilizando vocabularios controlados, así como valores ya existentes en la instalación de Omeka (incluyendo «Omeka: Propiedad» como tipo de datos), todos ellos proporcionados por el módulo Value Suggest.

Los valores preexistentes no se modificarán al editar una plantilla de recurso, por lo que los datos existentes que no se ajusten a la nueva restricción del tipo de datos no se verán afectados por estos cambios.

## Editar una plantilla de recurso
Puedes editar la plantilla de recurso base o cualquier plantilla que crees haciendo clic en el icono de edición de la tabla de plantillas de recursos, o bien haciendo clic en «Editar» en la esquina superior derecha al visualizar una plantilla de recurso.

Si decides que no quieres editar la plantilla o no deseas guardar los cambios, simplemente haz clic en el botón «Cancelar», situado entre los botones «Eliminar» y «Guardar» en la esquina superior derecha de la ventana.

![Vista de edición de la plantilla «Persona». Hay ocho propiedades en uso.](contentfiles/templates_edit.png)

## Compartir plantillas de recursos
Puedes compartir una plantilla de recursos entre instalaciones de Omeka S exportándola e importándola.

### Exportar una plantilla de recursos
Para exportar una plantilla de recurso desde tu instalación de Omeka S:

1. Ve al menú «Plantillas de recursos» en la navegación principal.
1. Haz clic en el nombre de la plantilla que deseas exportar.
1. En la página de vista de la plantilla de recurso, haz clic en el botón «Exportar» situado en la esquina superior derecha de la pantalla.

![Una flecha roja señala el botón de exportación en una pantalla que muestra una plantilla de recurso etiquetada como «Recurso textual»](contentfiles/templates_export.png)

Al exportar una plantilla de recurso, esta se descargará en la ubicación predeterminada de tu ordenador como un archivo JSON con el mismo nombre que la etiqueta de la plantilla de recurso.

### Importar una plantilla de recurso

!!! nota
  Si deseas importar una plantilla de recurso que utilice un [Vocabulario personalizado](../modules/customvocab.md), tendrás que reproducir manualmente el Vocabulario personalizado en la segunda instalación de Omeka S *antes* de importar la plantilla de recurso. También debes instalar y habilitar [Value Suggest](../modules/valuesuggest.md) antes de importar una plantilla que lo utilice para los tipos de datos.

Para importar una plantilla de recursos (un archivo JSON exportado desde otra instalación de S) a tu instalación de Omeka S:  

- Ve a la pestaña **Plantillas de recursos** en la navegación principal
- Haz clic en el botón «Importar» situado en la esquina superior derecha de la pantalla.

![La flecha roja señala el botón «Importar» en la página de exploración de plantillas de recursos del sitio de administración de una instalación de Omeka S](contentfiles/templates_import1.png)

- En la página «Plantillas de recursos: Importar», haz clic en el botón «Elegir archivo».
	- Se abrirá la ventana de selección de archivos de tu navegador. Elige el archivo JSON de la plantilla de recurso que deseas importar.
- Haz clic en el botón «Revisar importación».
  - En la página «Revisar», podrás comprobar que las propiedades y las opciones de las propiedades sean correctas.
	- Las plantillas importadas que utilizaban [Value Suggest](../modules/valuesuggest.md) o [Custom Vocab](../modules/customvocab.md) indicarán en la columna «Tipo de datos» cuál era la fuente original, y aparecerá un menú desplegable que te permitirá seleccionar un nuevo «Tipo de datos». Si no dispones de los módulos necesarios, el menú desplegable solo mostrará las opciones predeterminadas.

![En la página de revisión de plantillas importadas, todos los elementos de la importación revisada aparecen resaltados en verde.](contentfiles/templates_import2.png)