# Conjuntos de elementos

Los conjuntos de elementos son agrupaciones de elementos, similares a las colecciones de Omeka Classic. En Omeka S, los elementos pueden pertenecer a cualquier número de conjuntos, y un conjunto de elementos puede contener cualquier número de elementos.

## Permisos de conjuntos de elementos

Cuando un usuario crea un conjunto de elementos, se convierte en el «propietario» de dicho conjunto. La mayoría de los niveles de usuario tienen la capacidad de crear conjuntos de elementos y siempre pueden eliminar sus propios conjuntos. Solo los niveles superiores pueden eliminar conjuntos de elementos que sean propiedad de otros.

Los usuarios pueden añadir elementos a los conjuntos de elementos que estén abiertos a nuevas incorporaciones, así como a los conjuntos de elementos de los que sean propietarios (independientemente de si están abiertos o cerrados). Los administradores globales y los supervisores pueden añadir cualquier elemento a cualquier conjunto de elementos.

| Categoría | Permiso | Administrador global | Supervisor | Editor | Revisor | Autor | Investigador |
|-----|-----|---|---|---|---|---|---|
| Conjuntos de elementos | Añadir | Sí | Sí | Sí | Sí | Sí | No |
| | Editar | Todos | Todos | Todos | Todos | Los propios | No |
| | Eliminar | Todos | Todos | Todos | Los propios | Los propios | No |
| Anotaciones de valores | Añadir/Editar | Sí | Sí | Sí | Sí | Sí | No |
| Objetos privados | Ver | Sí | Sí | Sí | Sí | No | No |

Ten en cuenta que cuando cambias el rol de un usuario, por ejemplo, de Autor a Investigador, seguirá siendo propietario de los conjuntos de elementos que creó cuando tenía permiso para hacerlo. Los conjuntos de elementos no se transfieren. Al eliminar un usuario, sus conjuntos de elementos quedan huérfanos: aparecerán como si no tuvieran propietario. Solo los administradores globales pueden reasignar la propiedad de los conjuntos de elementos.

## La pestaña Conjuntos de elementos

Los conjuntos de elementos se gestionan a través de la pestaña **Conjuntos de elementos** (el icono de tres cajas apiladas) situada en el panel de navegación izquierdo del panel de administración.

![Vista de exploración de conjuntos de elementos con tres conjuntos de elementos.](contentfiles/itemsets_browse.png)

Al hacer clic en la pestaña, aparece una tabla que muestra todos los conjuntos de elementos con:

- el **Título**
- iconos para **editar** (lápiz), **eliminar** (papelera) o **detalles** (tres puntos)
- la **Clase** del conjunto de elementos
- el **Propietario** del conjunto
- la fecha en que se **creó** el conjunto.

En la esquina superior derecha de la pantalla de conjuntos de elementos se encuentra el botón «Añadir nuevo conjunto de elementos».

Las opciones para navegar y crear conjuntos de elementos se encuentran en el encabezado de la tabla de elementos.

- En el lado izquierdo están los controles para las páginas de conjuntos de elementos, con flechas de avance y retroceso, y un campo para ir a una página específica de conjuntos de elementos.
- En el centro está el botón de **Búsqueda avanzada**.
- A la derecha hay opciones para reordenar la tabla por **título**, **clase**, **propietario** o **fecha de creación**, en orden **ascendente** o **descendente**.

## Ver conjuntos de elementos

Para ver rápidamente la información de un conjunto de elementos, haz clic en el botón «Detalles» (el icono de los tres puntos) del conjunto de elementos en la página de exploración de conjuntos de elementos. Esto abrirá una columna en el lado derecho de la página con el título del conjunto de elementos, su visibilidad y el número de elementos.

![Vista en forma de cajón de un conjunto de elementos, con descripción y título](contentfiles/itemsets_drawer.png)

Para ver toda la información de un conjunto de elementos, haz clic en su nombre. En la página de vista de conjuntos de elementos, hay pestañas para ver los **metadatos** y los **recursos vinculados** de un conjunto de elementos. En la parte derecha de la página de vista del conjunto de elementos se encuentra la información sobre la fecha de creación, el propietario y la visibilidad. En el caso de los conjuntos de elementos, la visibilidad incluye tanto si el conjunto es privado o público como si otros usuarios pueden añadir elementos al conjunto.

![Vista de lectura de un conjunto de elementos individual](contentfiles/itemsets_view.png)

Para ver los elementos de un conjunto de elementos, haz clic en el número de elementos del conjunto en la página de exploración de conjuntos de elementos, o haz clic en el botón «Ver elementos» situado en la esquina superior derecha de la página del conjunto de elementos individual.

### Recursos vinculados

Los **recursos vinculados** de un conjunto de elementos son otros recursos de Omeka (elementos, conjuntos de elementos o medios) que están [vinculados a este conjunto de elementos a través de sus propiedades](#omeka-resource). Tenga en cuenta que esta sección solo muestra los recursos que se han vinculado *a* este conjunto de elementos (que lo tienen como propiedad); los recursos que están vinculados *desde* este elemento se mostrarán en la propiedad que ocupan.

Los recursos vinculados se agrupan por la propiedad para la que utilizan el conjunto de elementos actual. En el ejemplo siguiente, el conjunto de elementos actual «Periódicos» se utiliza para la propiedad «Formato» de los recursos vinculados.

Puede filtrar los recursos vinculados para mostrar solo aquellos que hacen referencia a una propiedad específica utilizando el menú desplegable «Filtrar por propiedad». Solo se mostrarán las propiedades que estén en uso.

![Un conjunto de elementos que muestra la pestaña Recursos vinculados, donde dos elementos utilizan el conjunto de elementos como valor para la propiedad «Formato».](contentfiles/itemsets_linked.png)

Cuando se visualiza un conjunto de elementos en el sitio público, todos los recursos vinculados se muestran en una serie de tablas basadas en la propiedad de metadatos en uso. Los recursos se ordenan por tipo de recurso (elemento, conjunto de elementos o medio) y solo se muestra un tipo a la vez. Un conjunto de elementos sin recursos vinculados no mostrará estas tablas; los conjuntos de elementos que se muestran en sitios configurados para excluir recursos que no están incluidos en el sitio tampoco mostrarán estas entradas.

![Visualización de un conjunto de elementos en el tema predeterminado que muestra varios elementos de Omeka vinculados al conjunto de elementos, como «Formato»](contentfiles/itemsets_linked2.png)

La visualización de los recursos vinculados en las páginas de recursos se puede configurar en cada sitio. Haz clic en «Tema» y, a continuación, en el botón que dice «[Configurar páginas de recursos](../sites/site_theme.md#configure-resource-pages)», y luego decide si se muestran las tablas de «Recursos vinculados» para cada recurso y dónde.

También puede controlar si los recursos vinculados mostrarán esos enlaces incluso cuando los recursos en cuestión no se hayan añadido al sitio en cuestión. En [Configuración del sitio, en la sección «Mostrar»](../sites/site_settings.md#show), encontrará una casilla de verificación para «Excluir recursos que no están en el sitio».

## Añadir un conjunto de elementos

Para añadir un nuevo conjunto de elementos, haz clic en la pestaña **Conjuntos de elementos** en el panel de navegación de la izquierda del panel de control. Haz clic en el botón «Añadir nuevo conjunto de elementos» en la parte derecha de la pantalla.

Por defecto, se cargará un nuevo conjunto de elementos con las propiedades `dcterms:title` y `dcterms:description`. Puede añadir otros campos seleccionando una propiedad de la lista de la derecha. Explore los campos por vocabulario (Dublin Core, Ontología Bibliográfica, etc.) o busque en la barra **Filtrar propiedades** situada encima de la lista de propiedades y vocabularios.

Los conjuntos de elementos pueden utilizar las mismas plantillas de recursos disponibles para los elementos a fin de proporcionar campos preseleccionados. Los campos comunes para los conjuntos de elementos incluyen una breve descripción textual que utiliza `dcterms:Description`. Este texto (solo la primera entrada, si hay varias entradas de descripción) se mostrará en la página «Explorar conjuntos de elementos» de forma predeterminada (que se encuentra en `youromekaurl/site-slug/item-set`). Todos los campos de metadatos se mostrarán cuando un usuario vea el conjunto de elementos en la parte pública (que se encuentra en `youromekaurl/site-slug/item-set/1`, donde «1» es el ID del conjunto de elementos).

Puede añadir otros campos seleccionando una propiedad de la lista de la derecha. Explora los campos por vocabulario (Dublin Core, Ontología Bibliográfica, etc.) o busca en la barra **Filtrar propiedades** situada encima de la lista de propiedades y vocabularios.

### Valores
Puedes añadir texto, un recurso de la instalación o un enlace externo en cada campo.  

![Añadir conjunto de elementos, sin propiedades seleccionadas](contentfiles/itemsets_add.png)

Puede establecer los valores de las propiedades individuales como Privados o Visibles públicamente utilizando el icono del ojo para cada valor. Tenga en cuenta que las propiedades establecidas como privadas siguen siendo visibles para los administradores globales, los administradores del sitio y los editores. Los autores podrán ver todas las propiedades de los elementos que posean, pero no verán las propiedades privadas creadas por otros usuarios.

En la imagen siguiente, la primera propiedad (Título) es pública, tal y como indica el icono del ojo abierto. La segunda propiedad (Descripción) es privada, tal y como indica el icono del ojo tachado. Al hacer clic o pulsar Intro en el icono del ojo, se alterna entre público y privado.

![Como se describe](contentfiles/items_propviz.png)

#### Texto

Los campos de texto permiten introducir texto sin formato. No se permite el uso de marcas de formato en estos campos (por ejemplo, negrita, cursiva, Markdown, HTML).

Puede indicar el idioma del contenido de un campo de entrada utilizando el símbolo del globo terráqueo situado encima del campo. Haga clic en el globo para activar un campo de texto y, a continuación, introduzca el código [ISO 639-1](https://en.wikipedia.org/wiki/List_of_ISO_639-1_codes){target=_blank} del idioma en el que está escrito el texto.

![El campo de descripción con dos entradas, una en inglés y otra en francés, con los códigos de idioma de dos letras y las entradas de texto en cada una.](contentfiles/items_lang.png)

#### Recurso de Omeka

Estos campos crean un enlace interno entre el recurso que está creando y el recurso que rellena ese campo.

Tiene la opción de utilizar un elemento u otro conjunto de elementos.

Al elegir un tipo de recurso, se abrirá un panel lateral donde podrás explorar todos los recursos de la instalación. Puedes utilizar la función de búsqueda situada en la parte superior del panel para filtrar la lista o para encontrar rápidamente un elemento o conjunto de elementos específico.

Una vez que seleccione un elemento o un conjunto de elementos, se cargará información detallada y deberá hacer clic en «Seleccionar recurso» para finalizar el enlace de los recursos. También puede hacer clic en el botón «X» de la esquina superior derecha para volver a la lista de elementos o conjuntos de elementos.

![Interfaz de edición de conjuntos de elementos, con el valor de la propiedad «Recurso de Omeka» añadido a la propiedad Descripción. Los botones «Elementos» y «Conjuntos de elementos» están resaltados dentro de un cuadrado rojo. El panel de la derecha está abierto en el menú «Seleccionar elemento», con una lista de elementos entre los que elegir.](contentfiles/items_addresource.png)

Si está utilizando un recurso de elemento para la propiedad, dispondrá de opciones adicionales para encontrar el elemento que desea en el panel. Abra estas opciones haciendo clic en el botón triangular situado junto a la frase «Filtrar búsqueda».

Esto abrirá un menú debajo del botón con las siguientes opciones para filtrar los elementos del panel:

- Filtrar por clase: un menú desplegable en el que puede seleccionar cualquier clase proporcionada por los vocabularios de la instalación
- Filtrar por conjunto de elementos: un menú desplegable en el que puede limitar los elementos mostrados en el panel a solo aquellos asociados con un conjunto de elementos concreto
- Filtrar por ID de elemento: un campo de búsqueda en el que puede introducir el ID del elemento que desea utilizar. Puedes encontrar el ID de un elemento en la URL de su página de edición; si estás editando el elemento y la URL es `admin/item/11547/edit`, entonces el ID del elemento es 11547.

![opciones descritas anteriormente](contentfiles/items_addresItem.png)

Los recursos de elementos también tienen una opción de «Añadir rápidamente». Cuando se activa esta opción, todos los elementos del panel tienen una casilla de verificación. Puede utilizar estas casillas para añadir varios elementos como una propiedad a la vez. Tenga en cuenta que solo puede editar una propiedad a la vez, por lo que todos los elementos deben rellenar la misma propiedad (por ejemplo, Creador o Tiene parte).

![Una flecha roja señala el botón deslizante de «Añadir rápidamente». Los dos elementos visibles tienen una casilla de verificación vacía a la izquierda de su miniatura representativa](contentfiles/items_quickadd.png)

#### URI
Los campos URI enlazan con un sitio web externo o un recurso en línea. Cada valor URI contiene el enlace en sí mismo y una etiqueta textual opcional para sustituir el URI por algo legible para los humanos. Por ejemplo, es posible que desee introducir un Creador como URI a un vocabulario controlado de artistas o autores, y luego incluir el nombre del creador en texto sin formato como Etiqueta. Omeka no extraerá automáticamente la información del URI.

### Anotación de valores
Cuando introduce un valor para una propiedad asociada a un recurso, está realizando una afirmación sobre ese recurso. Si lo deseas, Omeka te permite realizar afirmaciones sobre esa afirmación. A esto lo llamamos anotación de valor. La ventaja de la anotación de valor es que puedes optar por concretar hechos ambiguos mediante la anotación de aspectos como:

- Procedencia: ¿De dónde procede este hecho?
- Tiempo: ¿Cuándo ocurrió este hecho?
- Ubicación: ¿Cuál es la ubicación asociada a este hecho?
- Certeza: ¿Cuál es el grado de confianza de este hecho?
- Tipo: ¿Qué tipo de concepto o entidad es este hecho?

En el mundo de los datos enlazados, este proceso se conoce como [reificación](https://www.w3.org/wiki/RdfReification){target=_blank}. Cada valor puede tener cualquier número de anotaciones.

Para crear una anotación, haz clic en los tres puntos situados a la derecha de la interfaz de introducción de valores y, a continuación, haz clic en el icono de anotación (el bocadillo).

![Una propiedad con el bocadillo de anotación resaltado](contentfiles/annotation_add.png)

La barra lateral de anotaciones se abrirá a la derecha. Seleccione cualquier propiedad disponible en la instalación de Omeka S para describir la relación entre la anotación y el valor que describe. Por ejemplo, el valor asociado a la propiedad `dcterms:Contributor` podría anotarse con más detalles sobre la naturaleza de la contribución. O tal vez desee simplemente incluir una nota utilizando el campo `dcterms:Description`.

Seleccione un tipo de datos para la anotación: un campo de texto, un URI o un recurso de su instalación de Omeka S. Es posible que los módulos ofrezcan tipos de datos adicionales. Haga clic en el botón «Añadir anotación» y aparecerá un nuevo campo debajo. Introduzca su anotación. Si lo desea, puede hacerlo varias veces para el valor elegido. A continuación, haga clic en «Establecer anotaciones» para finalizar el proceso.

![La barra lateral de anotaciones de valor con una propiedad seleccionada y una anotación incluida](contentfiles/annotation_sidebar.png)

[Cada sitio tiene una configuración](../sites/site_settings.md#show) para indicar si las anotaciones de valor son visibles para el público. Esto incluirá las anotaciones de valor en los elementos y los medios.

Puede establecer vocabularios controlados para las anotaciones utilizando el [módulo Custom Vocab](../modules/customvocab.md). En este caso, no es necesario aplicar un vocabulario personalizado a una propiedad mediante una plantilla de recursos; puede seleccionar cualquier vocabulario instalado en el menú desplegable de tipo de valor del panel. Esto cargará las opciones de su vocabulario en un menú desplegable de términos.

![Una entrada de elemento con una anotación en DC:Contributor, cargando un vocabulario personalizado llamado «Contributor Annotation Type», y los términos mostrados incluyen «Editor», «Traductor», «Organización editora» y más.](contentfiles/annotation_customvocab.png)

### Avanzado
De forma predeterminada, Omeka S utilizará el medio del primer elemento añadido a un conjunto de elementos para generar una miniatura para el conjunto. Si desea utilizar una imagen que no sea un medio para la miniatura de un conjunto de elementos, puede configurarlo aquí.

![Pestaña «Miniatura» sin ningún recurso seleccionado. La pestaña muestra un mensaje sobre la creación de miniaturas y un botón para «seleccionar» un recurso](contentfiles/itemset_thumb1.png)

Los recursos que seleccione y suba como miniaturas en esta pestaña son los mismos que los creados para los [logotipos del sitio](../sites/site_theme.md#logo).

Para asignar un recurso como miniatura, haz clic en el botón «Seleccionar» en el área de trabajo principal de la pestaña. Esto abrirá un panel deslizante en el lado derecho.

![Panel deslizante de selección con opción de subir y dos recursos, ambos imágenes.](contentfiles/itemset_thumb2.png)

El panel ofrece dos opciones: subir un archivo mediante el navegador o seleccionar uno de los recursos existentes. Para seleccionar un recurso existente, basta con hacer clic en él y se asignará automáticamente al conjunto de elementos.

![Añadir conjunto de elementos abierto en la pestaña Miniaturas, donde se encuentra en el área de trabajo principal un recurso que es una imagen de una pluma sobre un trozo de papel enrollado. Debajo hay botones para Seleccionar y Borrar](contentfiles/itemset_thumb3.png)

Para eliminar un recurso que hayas asignado como miniatura, haz clic en el botón «Borrar» situado debajo de la imagen del recurso. Para sustituirlo, haz clic en «Seleccionar» y elige o sube un nuevo recurso de miniatura.

### Configuración de acceso
Los conjuntos de elementos tienen dos ajustes que controlan su acceso. Pueden ser **públicos** o **no públicos** y pueden estar **abiertos** o **cerrados**.

Utilice el botón **hacer público/privado** (icono del ojo) para que el conjunto de elementos sea visible para el público o solo para todos los usuarios de la instalación de Omeka S (no público).

Los conjuntos **abiertos** pueden ser editados y ampliados por cualquier usuario de la instalación.

Los conjuntos **cerrados** solo están disponibles y son editables por su creador, los administradores del sitio y los administradores globales.

Abierto y público: ![un conjunto que es abierto y público, con un icono de candado abierto y un icono de un ojo abierto](contentfiles/setOpenPublic.png){style="display:inline;"}

Cerrado y privado: ![un conjunto que es cerrado y privado, con un icono de candado cerrado y  un icono de un ojo tachado](contentfiles/setClosedPrivate.png){style="display:inline;"}  

Ten en cuenta que los ajustes público/privado y abierto/cerrado funcionan de forma independiente; por ejemplo, puedes tener un conjunto de elementos abierto y privado.

## Editar un conjunto de elementos
Una vez que haya creado un conjunto de elementos, puede editarlo en cualquier momento, ya sea haciendo clic en el icono de edición (botón del lápiz) o haciendo clic en el título del conjunto de elementos y, a continuación, en el botón «Editar» situado en la esquina superior derecha de la pantalla.

Las opciones para editar un conjunto de elementos son las mismas que para crearlo.

Para cancelar la edición, haz clic en el botón «Cancelar» situado en la esquina superior derecha, entre los botones «Eliminar» y «Guardar».

### Eliminar un conjunto de elementos

Puede eliminar conjuntos de elementos individuales o eliminar varios conjuntos de elementos a la vez, tal y como se describe a continuación.  

Al eliminar conjuntos de elementos no se eliminan los elementos asociados a ellos.

Desde la vista de exploración de conjuntos de elementos, puede eliminar un conjunto de elementos haciendo clic en el icono de la papelera situado en la fila del conjunto de elementos que desea eliminar. Esto abrirá un panel a la derecha con un mensaje en la parte superior pidiéndole que confirme que desea eliminar el conjunto de elementos, con los metadatos del conjunto de elementos debajo del botón «Confirmar eliminación». Haga clic en «Confirmar eliminación» para eliminar el conjunto de elementos, o cierre el panel para cancelar.

![Vista de exploración de conjuntos de elementos con dos conjuntos de elementos y una flecha roja apuntando al icono de la papelera](contentfiles/itemsets_browseDel.png)

![Panel con un mensaje de confirmación para eliminar un conjunto de elementos, que incluye el botón «Confirmar eliminación» y los metadatos descriptivos básicos del conjunto de elementos: título, descripción y número de elementos del conjunto.](contentfiles/itemsets_browseDel2.png)

En la página de edición de un conjunto de elementos, haz clic en el botón «Eliminar» situado en la esquina superior derecha. Esto abrirá un panel deslizante en el lado derecho en el que se le pedirá que confirme que desea eliminar el conjunto de elementos. Haga clic en «Confirmar eliminación» para eliminar el conjunto de elementos, o cierre el panel para cancelar la acción.

![El panel de advertencia, con el texto «¿Está seguro de que desea eliminar este conjunto de elementos?» y, debajo, un botón rojo con texto en blanco que dice «Confirmar eliminación».](contentfiles/itemset-delete2.png)

## Acciones por lotes

Desde la página de exploración de conjuntos de elementos (`admin/item-set`) puede editar conjuntos de elementos por lotes, utilizando el menú desplegable situado en la parte superior izquierda, cerca de las opciones de paginación. Puede seleccionar conjuntos de elementos manualmente para la edición por lotes utilizando las casillas de verificación de la izquierda, o seleccionar todos los conjuntos de elementos de la página, o utilizar el menú desplegable para editar todos los conjuntos de elementos que se encuentran actualmente en el subconjunto. 

Los editores, supervisores y administradores globales pueden editar y eliminar por lotes todos los conjuntos de elementos de la instalación. Los usuarios con permisos de nivel de autor pueden editar o eliminar por lotes sus propios conjuntos de elementos, pero no los de otros usuarios. En este caso, al seleccionar todos los conjuntos de elementos de la página, o al seleccionar todos los conjuntos de elementos, solo se incluirán los conjuntos de elementos de su propiedad. Los usuarios con nivel de revisor no pueden eliminar por lotes todos los recursos, pero sí pueden eliminar por lotes los recursos seleccionados.

![Una flecha roja señala el menú desplegable de opciones de edición y eliminación por lotes](contentfiles/itemsets_batch.png)

Las acciones por lotes son las siguientes:  

- Editar seleccionados: edita solo los conjuntos de elementos seleccionados en la página
- Editar todos: edita todos los conjuntos de elementos devueltos por una búsqueda (por defecto, todos los conjuntos de elementos)
- Eliminar seleccionados: elimina solo los conjuntos de elementos seleccionados en la página
- Eliminar todo: elimina todos los conjuntos de elementos devueltos por una búsqueda (por defecto, todos los conjuntos de elementos).

El número de resultados por página se configura en la [configuración global de la instalación](../admin/settings.md#general).

Primero puede utilizar el enlace «🔍 Búsqueda avanzada» para reducir los conjuntos de elementos a un subconjunto para su edición. Por ejemplo, puede utilizar la [Búsqueda avanzada](../search.md#item-advanced-search) para limitar los conjuntos de elementos a aquellos que pertenecen a un usuario específico. 

Si realiza una búsqueda, volverá a ver la página de exploración, con los parámetros seleccionados apareciendo en la parte superior de la pantalla. Desde esta pantalla de exploración, puede seleccionar conjuntos de elementos manualmente para la edición por lotes utilizando las casillas de verificación de la izquierda, seleccionar todos los conjuntos de elementos de la página o utilizar el menú desplegable para editar todos los conjuntos de elementos que se encuentran actualmente en el subconjunto. 

Si completa una acción por lotes desde la siguiente pantalla, volverá a este mismo subconjunto de conjuntos de elementos. 

### Edición por lotes

La **edición por lotes** de conjuntos de elementos le lleva a una nueva página. Los conjuntos de elementos que se están editando se mostrarán en el lado derecho en un panel desplegable. Asegúrese de que el número de conjuntos de elementos que se están editando es correcto.

El formulario de edición por lotes le ofrece las siguientes opciones:  

- **Visibilidad del conjunto**: un botón de opción. Seleccione entre «público» o «no público» para que el conjunto de elementos sea visible o no visible para los usuarios que no hayan iniciado sesión.
- **Establecer apertura**: un botón de opción. Seleccione entre abierto o no abierto. Los conjuntos abiertos pueden ser editados y ampliados por cualquier usuario de la instalación; los conjuntos cerrados solo están disponibles y son editables por su creador, los administradores del sitio y los administradores globales.
- **Establecer plantilla**: un menú desplegable. Seleccione entre las plantillas de recursos de la instalación. Puede eliminar plantillas de los conjuntos de elementos seleccionados con la opción «[Desactivar plantilla]». Aparece una barra de búsqueda en la parte superior del menú desplegable si desea escribir para buscar.
- **Clase del conjunto**: un menú desplegable. Seleccione entre las clases de los vocabularios instalados. Puede eliminar todas las clases de los conjuntos de elementos seleccionados con la opción «[Desactivar clase]». Aparecerá una barra de búsqueda en la parte superior del menú desplegable si desea escribir para buscar.
- **Establecer propietario**: un menú desplegable. Seleccione entre los usuarios de la instalación para elegir quién debe establecerse como propietario de los conjuntos de elementos seleccionados. La propiedad determina [quién puede editar y eliminar esos conjuntos de elementos](#item-set-permissions), al margen de los [niveles de permiso de usuario](../admin/users.md#roles-and-permissions) superiores.
- **Borrar valores de propiedad**: un menú desplegable y un campo de texto, con todas las propiedades de todos los vocabularios. Al seleccionar una de estas opciones, se eliminarán todos los valores de esa propiedad en los conjuntos de elementos afectados. Puedes eliminar varios valores de propiedad a la vez: haz clic de nuevo en el campo de texto para ver las opciones restantes. 
- **Establecer visibilidad del valor**: un menú desplegable y un campo de texto, con botones de opción. Establezca la visibilidad de una o varias propiedades específicas como pública o no pública. A diferencia de los botones de opción de la parte superior del formulario, esto solo afectará a uno o varios campos de metadatos, en lugar de a todo el conjunto de elementos (por ejemplo, es posible que desee ocultar el valor «Creador» en algunos conjuntos de elementos públicos). Seleccione una propiedad en el campo de texto (escriba para iniciar la búsqueda) y, a continuación, elija el botón de opción «Público» o «No público» para esta opción. Puede añadir varias propiedades haciendo clic de nuevo en el campo de texto, pero todas pasarán a ser «Públicas» o «No públicas».

![Formulario de edición por lotes de elementos, con las opciones descritas anteriormente.](contentfiles/itemsets_batchedit.png)

Además, puede utilizar los botones de la parte inferior del formulario de edición por lotes para **convertir los valores existentes de cualquier propiedad de un tipo de datos a otro**, como por ejemplo un valor de texto «1900-01-01» en una fecha. 

También puede **añadir propiedades** a cada conjunto de elementos:

- Añadir valor de texto
- Añadir valor de recurso
- Añadir valor URI.  

Al seleccionar cualquiera de estas opciones, se añadirá un bloque al formulario en el que podrá seleccionar una propiedad de los vocabularios instalados e introducir el valor de dicha propiedad.

![La imagen muestra únicamente el bloque «Añadir valor de texto» del formulario de edición por lotes, con un menú desplegable etiquetado como «seleccionar propiedad» sobre un campo de texto vacío](contentfiles/itemsets_property.png)

### Eliminación por lotes

Para las **acciones de eliminación**, se abrirá un panel en el lado derecho de la pantalla que le indicará el número de conjuntos de elementos que se eliminarán. No se eliminará nada a menos que haga clic en el botón rojo «Confirmar eliminación». Esta acción no se puede deshacer. Para cancelar la eliminación de los conjuntos de elementos, haga clic en la «X» situada en la esquina superior derecha del panel de eliminación. Para confirmar la eliminación, marque la casilla «¿Está seguro?» (solo para «Eliminar todo», no para «Eliminar seleccionados») y, a continuación, haga clic en «Confirmar eliminación». Ten en cuenta que al eliminar el conjunto de elementos no se eliminarán los elementos asociados a dicho conjunto.

![La advertencia que verán los usuarios cuando estén a punto de eliminarse varios conjuntos de elementos. Hay una casilla de verificación que el usuario debe marcar para que el botón situado debajo de ella se active.](contentfiles/itemsets_bulkdelete.png)
