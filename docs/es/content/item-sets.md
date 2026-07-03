# Conjuntos de elementos

Los conjuntos de elementos son agrupaciones de elementos, similares a las colecciones de Omeka Classic. En Omeka S, los elementos pueden pertenecer a cualquier número de conjuntos, y un conjunto de elementos puede contener cualquier número de elementos.

## Permisos de los conjuntos de elementos

Cuando un usuario crea un conjunto de elementos, se convierte en el «propietario» de dicho conjunto. La mayoría de los niveles de usuario tienen la capacidad de crear conjuntos de elementos y siempre pueden eliminar sus propios conjuntos. Solo los niveles superiores pueden eliminar conjuntos de elementos que sean propiedad de otros.

Los usuarios pueden añadir elementos a los conjuntos de elementos que estén abiertos a nuevas incorporaciones, así como a los conjuntos de elementos de los que sean propietarios (independientemente de si están abiertos o cerrados). Los administradores globales y los supervisores pueden añadir cualquier elemento a cualquier conjunto de elementos.

| Categoría | Permiso | Administrador global | Supervisor | Editor | Revisor | Autor | Investigador |
|-----|-----|---|---|---|---|---|---|
| Conjuntos de elementos | Añadir | Sí | Sí | Sí | Sí | Sí | No |
| | Editar | Todos | Todos | Todos | Todos | Los propios | No |
| | Eliminar | Todos | Todos | Todos | Los propios | Los propios | No |
| Anotaciones de valores | Añadir/Editar | Sí | Sí | Sí | Sí | Sí | No |
| Objetos privados | Ver | Sí | Sí | Sí | Sí | No | No |

Ten en cuenta que, cuando cambias el rol de un usuario, por ejemplo, de Autor a Investigador, seguirá siendo propietario de los conjuntos de elementos que creó cuando tenía permiso para hacerlo. Los conjuntos de elementos no se transfieren. Al eliminar a un usuario, sus conjuntos de elementos quedan huérfanos, es decir, aparecerán como si no tuvieran propietario. Solo los administradores globales pueden reasignar la propiedad de los conjuntos de elementos.

## La pestaña «Conjuntos de elementos»

Los conjuntos de elementos se gestionan a través de la pestaña **Conjuntos de elementos** (el icono de tres cajas apiladas) situada en el panel de navegación izquierdo del panel de administración.

![Vista de exploración de conjuntos de elementos con tres conjuntos de elementos.](contentfiles/itemsets_browse.png)

Al hacer clic en la pestaña, aparece una tabla en la que se enumeran todos los conjuntos de elementos con:

- el **Título**
- iconos para **editar** (lápiz), **eliminar** (papelera) o ver **detalles** (tres puntos)
- la **Clase** del conjunto de elementos
- el **Propietario** del conjunto
- la fecha en que se **creó** el conjunto.

En la esquina superior derecha de la pantalla «Conjuntos de elementos» se encuentra el botón «Añadir nuevo conjunto de elementos».

Las opciones para navegar y crear conjuntos de elementos se encuentran en el encabezado de la tabla de elementos.

- En el lado izquierdo están los controles para las páginas de los conjuntos de elementos, con flechas de avance y retroceso, y un campo para ir a una página específica de los conjuntos de elementos.
- En el centro se encuentra el botón de **Búsqueda avanzada**.
- A la derecha hay opciones para reordenar la tabla por **título**, **clase**, **propietario** o **fecha de creación**, ya sea en orden **ascendente** o **descendente**.

## Ver conjuntos de elementos

Para ver rápidamente la información sobre un conjunto de elementos, haz clic en el botón «Detalles» (el icono de los tres puntos) correspondiente al conjunto de elementos en la página de exploración de conjuntos de elementos. Esto abrirá una columna en la parte derecha de la página con el título del conjunto de elementos, su visibilidad y el número de elementos.

![Vista en forma de cajón de un conjunto de elementos, con descripción y título](contentfiles/itemsets_drawer.png)

Para ver toda la información de un conjunto de elementos, haz clic en su nombre. En la página de vista de conjuntos de elementos, hay pestañas para ver los **metadatos** y los **recursos vinculados** de un conjunto de elementos. En la parte derecha de la página de vista del conjunto de elementos se muestra información sobre la fecha de creación, el propietario y la visibilidad. En el caso de los conjuntos de elementos, la visibilidad incluye tanto si el conjunto es privado o público como si otros usuarios pueden añadir elementos al conjunto.

![Vista de lectura de un conjunto de elementos](contentfiles/itemsets_view.png)

Para ver los elementos de un conjunto de elementos, haz clic en el número de elementos del conjunto en la página de exploración de conjuntos de elementos, o bien en el botón «Ver elementos» situado en la esquina superior derecha de la página de cada conjunto de elementos.

### Recursos vinculados

Los **recursos vinculados** de un conjunto de elementos son otros recursos de Omeka (elementos, conjuntos de elementos o archivos multimedia) que están [vinculados a este conjunto de elementos a través de sus propiedades](#omeka-resource). Ten en cuenta que esta sección solo muestra los recursos que se han vinculado *a* este conjunto de elementos (que lo tienen como propiedad); los recursos vinculados *desde* este conjunto de elementos se mostrarán en la propiedad que completan.

Los recursos vinculados se agrupan según la propiedad para la que utilizan el elemento actual. En el ejemplo siguiente, el conjunto de elementos actual «Periódicos» se utiliza para la propiedad «Formato» de los recursos vinculados.

Puedes filtrar los recursos vinculados para mostrar únicamente aquellos que hacen referencia a una propiedad específica utilizando el menú desplegable «Filtrar por propiedad». Solo se mostrarán las propiedades que estén en uso.

![Un conjunto de elementos que muestra la pestaña «Recursos vinculados», donde dos elementos utilizan el conjunto de elementos como valor para la propiedad «Formato».](contentfiles/itemsets_linked.png)

Cuando se visualiza un conjunto de elementos en el sitio público, todos los recursos vinculados se muestran en una serie de tablas basadas en la propiedad de metadatos en uso. Los recursos se ordenan por tipo de recurso (elemento, conjunto de elementos o medio) y solo se muestra un tipo a la vez. Un conjunto de elementos sin recursos vinculados no mostrará estas tablas; los conjuntos de elementos que se muestren en sitios configurados para excluir los recursos que no estén incluidos en el sitio tampoco mostrarán estas entradas.

![Visualización de un conjunto de elementos en el tema predeterminado que muestra varios elementos de Omeka vinculados al conjunto de elementos, como «Formato»](contentfiles/itemsets_linked2.png)

La visualización de los recursos vinculados en las páginas de recursos se puede configurar en cada sitio. Haz clic en «Tema» y, a continuación, en el botón que dice «[Configurar páginas de recursos](../sites/site_theme.md#configure-resource-pages)», y a continuación decide si se muestran las tablas «Recursos vinculados» para cada recurso y en qué lugar.

También puede controlar si los recursos vinculados mostrarán dichos enlaces incluso cuando los recursos en cuestión no se hayan añadido al sitio en cuestión. En [Configuración del sitio, en la sección «Mostrar»](../sites/site_settings.md#show), encontrará una casilla de selección para «Excluir recursos que no estén en el sitio».

## Añadir un conjunto de elementos

Para añadir un nuevo conjunto de elementos, haz clic en la pestaña **Conjuntos de elementos** en el panel de navegación de la izquierda del panel de control. Haz clic en el botón «Añadir nuevo conjunto de elementos» situado en la parte derecha de la pantalla.

Por defecto, se cargará un nuevo conjunto de elementos con las propiedades `dcterms:title` y `dcterms:description`. Puedes añadir otros campos seleccionando una propiedad de la lista de la derecha. Explora los campos por vocabulario (Dublin Core, Ontología Bibliográfica, etc.) o busca en la barra **Filtrar propiedades** situada encima de la lista de propiedades y vocabularios.

Los conjuntos de elementos pueden utilizar las mismas plantillas de recursos disponibles para los elementos a fin de proporcionar campos preseleccionados. Entre los campos comunes de los conjuntos de elementos se incluye una breve descripción textual que utiliza `dcterms:Description`. Este texto (solo la primera entrada, si hay varias entradas de descripción) se mostrará de forma predeterminada en la página «Explorar conjuntos de elementos» (que se encuentra en `youromekaurl/site-slug/item-set`). Todos los campos de metadatos se mostrarán cuando un usuario visualice el conjunto de elementos en la parte pública (que se encuentra en `youromekaurl/site-slug/item-set/1`, donde «1» es el ID del conjunto de elementos).

Puedes añadir otros campos seleccionando una propiedad de la lista de la derecha. Explora los campos por vocabulario (Dublin Core, Ontología Bibliográfica, etc.) o realiza una búsqueda en la barra **Filtrar propiedades** situada encima de la lista de propiedades y vocabularios.

### Valores
En cada campo puedes añadir texto, un recurso de la instalación o un enlace externo.  

![Añadir conjunto de elementos, sin propiedades seleccionadas](contentfiles/itemsets_add.png)

Puede establecer los valores de cada propiedad como «Privado» o «Visible públicamente» utilizando el icono del ojo correspondiente a cada valor. Tenga en cuenta que las propiedades configuradas como privadas siguen siendo visibles para los administradores globales, los administradores del sitio y los editores. Los autores podrán ver todas las propiedades de los elementos de su propiedad, pero no verán las propiedades privadas creadas por otros usuarios.

En la imagen siguiente, la primera propiedad (Título) es pública, tal y como indica el icono del ojo abierto. La segunda propiedad (Descripción) es privada, tal y como indica el icono del ojo tachado. Al hacer clic o pulsar Intro en el icono del ojo, se alterna entre público y privado.

![Tal y como se describe](contentfiles/items_propviz.png)

#### Texto

Los campos de texto permiten introducir texto sin formato. No se permite el uso de marcas de formato en estos campos (por ejemplo, negrita, cursiva, Markdown, HTML).

Puedes indicar el idioma del contenido de un campo de entrada utilizando el símbolo del globo terráqueo situado encima del mismo. Haz clic en el globo terráqueo para activar un campo de texto y, a continuación, introduce el código [ISO 639-1](https://en.wikipedia.org/wiki/List_of_ISO_639-1_codes){target=_blank} del idioma en el que está escrito el texto.

![El campo de descripción con dos entradas, una en inglés y otra en francés, con los códigos de idioma de dos letras y las entradas de texto en cada una.](contentfiles/items_lang.png)

#### Recurso de Omeka

Estos campos crean un enlace interno entre el recurso que estás creando y el recurso que rellena ese campo.

Tienes la opción de utilizar un elemento o un conjunto de elementos.

Al seleccionar un tipo de recurso, se abrirá un panel lateral en el que podrás explorar todos los recursos de la instalación. Puedes utilizar la función de búsqueda situada en la parte superior del panel para filtrar la lista o para encontrar rápidamente un elemento o conjunto de elementos específico.

Una vez seleccionado un elemento o un conjunto de elementos, se cargará información detallada y deberás hacer clic en «Seleccionar recurso» para finalizar el enlace entre los recursos. También puedes hacer clic en el botón «X» de la esquina superior derecha para volver a la lista de elementos o conjuntos de elementos.

![Interfaz de edición de conjuntos de elementos, con el valor de la propiedad «Recurso de Omeka» añadido a la propiedad «Descripción». Los botones «Elementos» y «Conjuntos de elementos» aparecen resaltados dentro de un cuadrado rojo. El panel lateral derecho está abierto en el menú «Seleccionar elemento», con una lista de elementos entre los que elegir.](contentfiles/items_addresource.png)

Si estás utilizando un recurso de elemento para la propiedad, dispondrás de opciones adicionales para encontrar el elemento que deseas en el panel lateral. Abre estas opciones haciendo clic en el botón triangular situado junto a la frase «Filtrar búsqueda».

Esto abrirá un menú debajo del botón con las siguientes opciones para filtrar los elementos del panel lateral:

- Filtrar por clase: un menú desplegable en el que puedes seleccionar cualquier clase proporcionada por los vocabularios de la instalación
- Filtrar por conjunto de elementos: un menú desplegable en el que puedes limitar los elementos que se muestran en el panel a solo aquellos asociados a un conjunto de elementos concreto
- Filtrar por ID de elemento: un campo de búsqueda en el que puedes introducir el ID del elemento que deseas utilizar. Puedes encontrar el ID de un elemento en la URL de su página de edición; si estás editando el elemento y la URL es `admin/item/11547/edit`, entonces el ID del elemento es 11547.

![opciones tal y como se ha descrito anteriormente](contentfiles/items_addresItem.png)

Los recursos de elementos también cuentan con una opción de «Añadir rápidamente». Cuando se activa esta opción, todos los elementos del panel aparecen con una casilla de selección. Puedes utilizar estas casillas de selección para añadir varios elementos como una misma propiedad de una sola vez. Ten en cuenta que solo puedes editar una propiedad a la vez, por lo que todos los elementos deben rellenar la misma propiedad (por ejemplo, «Creador» o «Tiene parte»).

![Una flecha roja señala el botón deslizante de «Añadir rápidamente». Los dos elementos visibles tienen una casilla de selección vacía a la izquierda de su miniatura correspondiente](contentfiles/items_quickadd.png)

#### URI
Los campos URI enlazan con un sitio web externo o un recurso en línea. Cada valor URI contiene el propio enlace y una «Etiqueta» textual opcional para sustituir el URI por algo legible para los usuarios. Por ejemplo, es posible que desees introducir un «Creador» como URI que apunte a un vocabulario controlado de artistas o autores y, a continuación, incluir el nombre del creador en texto sin formato como «Etiqueta». Omeka no extraerá automáticamente la información de la URI.

### Anotación de valores
Cuando introduces un valor para una propiedad asociada a un recurso, estás realizando una afirmación sobre dicho recurso. Si lo deseas, Omeka te permite realizar afirmaciones sobre esa afirmación. A esto lo llamamos «anotación de valores». La ventaja de la anotación de valores es que puedes optar por concretar hechos ambiguos mediante la anotación de aspectos como:

- Procedencia: ¿De dónde procede este hecho?
- Tiempo: ¿Cuándo ocurrió este hecho?
- Ubicación: ¿Cuál es la ubicación asociada a este hecho?
- Certeza: ¿Cuál es el grado de confianza de este hecho?
- Tipo: ¿qué tipo de concepto o entidad es este hecho?

En el mundo de los datos enlazados, este proceso se conoce como [reificación](https://www.w3.org/wiki/RdfReification){target=_blank}. Cada valor puede tener cualquier número de anotaciones.

Para crear una anotación, haz clic en los tres puntos situados a la derecha del campo de introducción de valores y, a continuación, haz clic en el icono de anotación (el bocadillo).

![Una propiedad con el bocadillo de anotación resaltado](contentfiles/annotation_add.png)

Se abrirá la barra lateral de anotaciones a la derecha. Selecciona cualquier propiedad disponible en la instalación de Omeka S para describir la relación entre la anotación y el valor al que se refiere. Por ejemplo, el valor asociado a la propiedad `dcterms:Contributor` podría anotarse con más detalles sobre la naturaleza de la contribución. O quizá prefieras simplemente incluir una nota utilizando el campo `dcterms:Descripción`.

Selecciona un tipo de datos para la anotación: un campo de texto, un URI o un recurso de tu instalación de Omeka S. Es posible que los módulos ofrezcan tipos de datos adicionales. Haz clic en el botón «Añadir anotación» y aparecerá un nuevo campo más abajo. Introduce tu anotación. Si lo deseas, puedes repetir este proceso varias veces para el valor elegido. A continuación, haz clic en «Establecer anotaciones» para finalizar el proceso.

![La barra lateral de anotaciones de valor con una propiedad seleccionada y una anotación incluida](contentfiles/annotation_sidebar.png)

[Cada sitio dispone de una configuración](../sites/site_settings.md#show) para indicar si las anotaciones de valores son visibles para el público o no. Esto incluye las anotaciones de valores en los elementos y los archivos multimedia.

Puedes configurar vocabularios controlados para las anotaciones utilizando el [módulo Custom Vocab](../modules/customvocab.md). En este caso, no es necesario aplicar un vocabulario personalizado a una propiedad mediante una plantilla de recursos; puedes seleccionar cualquier vocabulario instalado en el menú desplegable de tipo de valor del panel lateral. De este modo, se cargarán las opciones de su vocabulario en un menú desplegable de términos.

![Una entrada de elemento con una anotación en DC:Contributor, que carga un vocabulario personalizado denominado «Tipo de anotación de colaborador», y los términos mostrados incluyen «Editor», «Traductor», «Organización editora» y más.](contentfiles/annotation_customvocab.png)

### Avanzado
Por defecto, Omeka S utilizará el archivo multimedia del primer elemento añadido a un conjunto de elementos para generar una miniatura del conjunto. Si deseas utilizar una imagen que no sea un archivo multimedia como miniatura de un conjunto de elementos, puedes configurarlo aquí.

![Pestaña «Miniatura» sin ningún recurso seleccionado. La pestaña muestra un mensaje sobre la creación de miniaturas y un botón para «seleccionar» un recurso](contentfiles/itemset_thumb1.png)

Los recursos que selecciones y subas como miniaturas en esta pestaña son los mismos que los creados para los [logotipos del sitio](../sites/site_theme.md#logo).

Para asignar un recurso como miniatura, haz clic en el botón «Seleccionar» en el área de trabajo principal de la pestaña. Esto abrirá un panel deslizante en el lado derecho.

![Panel deslizante de selección con opción de subir archivos y dos recursos, ambos imágenes.](contentfiles/itemset_thumb2.png)

El panel ofrece dos opciones: subir un archivo mediante el navegador o seleccionar uno de los recursos existentes. Para seleccionar un recurso existente, basta con hacer clic en él y se asignará automáticamente al conjunto de elementos.

![Conjunto de elementos «Añadir» abierto en la pestaña «Miniatura», donde aparece en el área de trabajo principal un recurso que es una imagen de una pluma de ave sobre un trozo de papel enrollado. Debajo hay botones para «Seleccionar» y «Borrar»](contentfiles/itemset_thumb3.png)

Para eliminar un recurso que hayas asignado como miniatura, haz clic en el botón «Borrar» situado debajo de la imagen del recurso. Para sustituirlo, haz clic en «Seleccionar» y elige o sube un nuevo recurso de miniatura.

### Configuración de acceso
Los conjuntos de elementos tienen dos ajustes que controlan su acceso. Pueden ser **públicos** o **no públicos**, y pueden estar **abiertos** o **cerrados**.

Utiliza el botón **Hacer público/privado** (icono del ojo) para que el conjunto de elementos sea visible para el público o solo para todos los usuarios de la instalación de Omeka S (no público).

Los conjuntos **abiertos** pueden ser editados y ampliados por cualquier usuario de la instalación.

Los conjuntos **cerrados** solo están disponibles y pueden ser editados por su creador, los administradores del sitio y los administradores globales.

Abierto y público: ![un conjunto que es abierto y público, con un icono de candado abierto y un icono de un ojo abierto](contentfiles/setOpenPublic.png){style="display:inline;"}

Cerrado y privado: ![un conjunto que es cerrado y privado, con un icono de candado cerrado y un icono de un ojo tachado con una barra](contentfiles/setClosedPrivate.png){style="display:inline;"}  

Ten en cuenta que los ajustes de «público/privado» y «abierto/cerrado» funcionan de forma independiente; por ejemplo, puedes tener un conjunto de elementos que sea a la vez abierto y privado.

## Editar un conjunto de elementos
Una vez creado un conjunto de elementos, puedes editarlo en cualquier momento, ya sea haciendo clic en el icono de edición (botón del lápiz) o haciendo clic en el título del conjunto de elementos y, a continuación, en el botón «Editar» situado en la esquina superior derecha de la pantalla.

Las opciones para editar un conjunto de elementos son las mismas que para crearlo.

Para cancelar la edición, haz clic en el botón «Cancelar» situado en la esquina superior derecha, entre los botones «Eliminar» y «Guardar».

### Eliminar un conjunto de elementos

Puedes eliminar conjuntos de elementos individuales o eliminar varios conjuntos de elementos a la vez, tal y como se describe a continuación.  

Al eliminar conjuntos de elementos no se eliminan los elementos asociados a ellos.

Desde la vista de exploración de conjuntos de elementos, puedes eliminar un conjunto de elementos haciendo clic en el icono de la papelera situado en la fila del conjunto que deseas eliminar. Esto abrirá un panel a la derecha con un mensaje en la parte superior en el que se te pedirá que confirmes que deseas eliminar el conjunto de elementos, y con los metadatos del conjunto debajo del botón de confirmación de eliminación. Haz clic en «Confirmar eliminación» para eliminar el conjunto de elementos, o cierra el panel para cancelar la operación.

![Vista de exploración de conjuntos de elementos con dos conjuntos y una flecha roja que apunta al icono de la papelera](contentfiles/itemsets_browseDel.png)

![Panel con un mensaje de confirmación para eliminar un conjunto de elementos, que incluye el botón «Confirmar eliminación» y los metadatos descriptivos básicos del conjunto: título, descripción y número de elementos del conjunto.](contentfiles/itemsets_browseDel2.png)

Desde la página de edición de un conjunto de elementos, haz clic en el botón «Eliminar» situado en la esquina superior derecha. Se abrirá un panel deslizante a la derecha en el que se te pedirá que confirmes que deseas eliminar el conjunto de elementos. Haz clic en «Confirmar eliminación» para eliminar el conjunto de elementos, o cierra el panel deslizante para cancelar la operación.

![El panel de advertencia, con el texto «¿Está seguro de que desea eliminar este conjunto de elementos?» y, debajo, un botón rojo con texto en blanco que dice «Confirmar eliminación».](contentfiles/itemset-delete2.png)

## Acciones en bloque

Desde la página de exploración de conjuntos de elementos (`admin/item-set`) puedes editar conjuntos de elementos de forma masiva utilizando el menú desplegable situado en la parte superior izquierda, junto a las opciones de paginación. Puedes seleccionar conjuntos de elementos manualmente para la edición masiva mediante las casillas de selección de la izquierda, seleccionar todos los conjuntos de elementos de la página o utilizar el menú desplegable para editar todos los conjuntos de elementos que se encuentran actualmente en el subconjunto. 

Los editores, supervisores y administradores globales pueden editar y eliminar de forma masiva todos los conjuntos de elementos de la instalación. Los usuarios con permisos de nivel de autor pueden editar o eliminar de forma masiva sus propios conjuntos de elementos, pero no los de otros usuarios. En este caso, al seleccionar todos los conjuntos de elementos de la página, o al seleccionar todos los conjuntos de elementos, solo se incluirán los conjuntos de elementos de los que sean propietarios. Los usuarios con nivel de «Revisor» no pueden eliminar en bloque todos los recursos, pero sí pueden eliminar en bloque los recursos seleccionados.

![Una flecha roja señala el menú desplegable con las opciones de edición y eliminación en bloque](contentfiles/itemsets_batch.png)

Las acciones en bloque son las siguientes:  

- Editar seleccionados: edita solo los conjuntos de elementos seleccionados en la página
- Editar todos: edita todos los conjuntos de elementos devueltos por una búsqueda (por defecto, todos los conjuntos de elementos)
- Eliminar seleccionados: elimina solo los conjuntos de elementos seleccionados en la página
- Eliminar todo: elimina todos los conjuntos de elementos devueltos por una búsqueda (por defecto, todos los conjuntos de elementos).

El número de resultados por página se configura en la [configuración global de la instalación](../admin/settings.md#general).

Primero puedes utilizar el enlace «🔍 Búsqueda avanzada» para reducir los conjuntos de elementos a un subconjunto que desees editar. Por ejemplo, puedes utilizar la [Búsqueda avanzada](../search.md#item-advanced-search) para limitar la búsqueda a los conjuntos de elementos que pertenezcan a un usuario específico. 

Si realizas una búsqueda, volverás a ver la página de exploración, con los parámetros seleccionados apareciendo en la parte superior de la pantalla. Desde esta pantalla de exploración puedes seleccionar manualmente los conjuntos de elementos para su edición por lotes utilizando las casillas de selección de la izquierda, seleccionar todos los conjuntos de elementos de la página o utilizar el menú desplegable para editar todos los conjuntos de elementos que se encuentran actualmente en el subconjunto. 

Si completas una acción por lotes desde la siguiente pantalla, volverás a este mismo subconjunto de conjuntos de elementos. 

### Edición por lotes

La **edición por lotes** de conjuntos de elementos te lleva a una nueva página. Los conjuntos de elementos que se están editando se muestran en una columna a la derecha. Asegúrate de que el número de conjuntos de elementos que se están editando es correcto.

El formulario de edición en bloque te ofrece las siguientes opciones:  

- **Visibilidad del conjunto**: un botón de opción. Selecciona «público» o «no público» para que el conjunto de elementos sea visible o no visible para los usuarios que no hayan iniciado sesión.
- **Establecer apertura**: un botón de opción. Selecciona «abierto» o «no abierto». Los conjuntos abiertos pueden ser editados y ampliados por cualquier usuario de la instalación; los conjuntos cerrados solo están disponibles y son editables por su creador, los administradores del sitio y los administradores globales.
- **Establecer plantilla**: un menú desplegable. Selecciona una de las plantillas de recursos de la instalación. Puedes eliminar plantillas de los conjuntos de elementos seleccionados con la opción «[Desactivar plantilla]». Aparece una barra de búsqueda en la parte superior del menú desplegable si deseas escribir algo para buscar.
- **Clase del conjunto**: un menú desplegable. Selecciona entre las clases de los vocabularios instalados. Puedes eliminar todas las clases de los conjuntos de elementos seleccionados con la opción «[Desactivar clase]». Aparece una barra de búsqueda en la parte superior del menú desplegable si deseas escribir algo para buscar.
- **Establecer miniatura**: haz clic en el botón «Seleccionar» para abrir la barra lateral de Recursos, donde puedes elegir un recurso existente o subir uno nuevo, que servirá como miniatura para todos los conjuntos de elementos incluidos. Esto sustituirá cualquier miniatura elegida automáticamente de los elementos, así como cualquier miniatura elegida manualmente al editar conjuntos de elementos individuales. 
- **Establecer propietario**: un menú desplegable. Selecciona entre los usuarios de la instalación para elegir quién debe ser el propietario de los conjuntos de elementos seleccionados. La propiedad determina [quién puede editar y eliminar esos conjuntos de elementos](#item-set-permissions), al margen de los [niveles de permiso de usuario](../admin/users.md#roles-and-permissions) superiores.
- **Borrar valores de propiedades**: un menú desplegable y un campo de texto, con todas las propiedades de todos los vocabularios. Al seleccionar una opción de este menú, se eliminarán todos los valores de esa propiedad en los conjuntos de elementos afectados. Puedes eliminar varios valores de propiedades a la vez: haz clic de nuevo en el campo de texto para ver las opciones restantes. 
- **Establecer la visibilidad del valor**: un menú desplegable y un campo de texto, con botones de opción. Establece la visibilidad de una o varias propiedades específicas como «pública» o «no pública». A diferencia de los botones de opción situados en la parte superior del formulario, esto solo afectará a uno o varios campos de metadatos, en lugar de a todo el conjunto de elementos (por ejemplo, es posible que desees ocultar el valor «Creador» en algunos conjuntos de elementos públicos). Selecciona una propiedad en el campo de texto (escribe para iniciar la búsqueda) y, a continuación, elige el botón de opción «Público» o «No público» para esta opción. Puedes añadir varias propiedades haciendo clic de nuevo en el campo de texto, pero todas pasarán a ser «Públicas» o «No públicas».

![Formulario de edición por lotes de elementos, con las opciones descritas anteriormente.](contentfiles/itemsets_batchedit.png)

Además, puede utilizar los botones situados en la parte inferior del formulario de edición por lotes para **convertir los valores existentes de cualquier propiedad de un tipo de datos a otro**, como por ejemplo un valor de texto «1900-01-01» en una fecha. 

También puedes **añadir propiedades** a cada conjunto de elementos:

- Añadir valor de texto
- Añadir valor de recurso
- Añadir valor URI.  

Al seleccionar cualquiera de estas opciones, se añadirá un bloque al formulario en el que podrás seleccionar una propiedad de los vocabularios instalados e introducir el valor de dicha propiedad.

![La imagen muestra únicamente el bloque «Añadir valor de texto» del formulario de edición por lotes, con un menú desplegable titulado «Seleccionar propiedad» situado encima de un campo de texto vacío](contentfiles/itemsets_property.png)

### Eliminación por lotes

En el caso de las **acciones de eliminación**, se abrirá un panel deslizante en la parte derecha de la pantalla que te indicará el número de conjuntos de elementos que se eliminarán. No se eliminará nada a menos que hagas clic en el botón rojo «Confirmar eliminación». Esta acción no se puede deshacer. Para cancelar la eliminación de los conjuntos de elementos, haz clic en la «X» situada en la esquina superior derecha del panel de eliminación. Para confirmar la eliminación, marca la casilla «¿Estás seguro?» (solo para «Eliminar todo», no para «Eliminar seleccionados») y, a continuación, haz clic en «Confirmar eliminación». Ten en cuenta que al eliminar el conjunto de elementos no se eliminarán los elementos asociados a dicho conjunto.

![La advertencia que verán los usuarios cuando estén a punto de eliminarse varios conjuntos de elementos. Hay una casilla de verificación que el usuario debe marcar para que el botón situado debajo de ella se active.](contentfiles/itemsets_bulkdelete.png)
