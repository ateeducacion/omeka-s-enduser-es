# Recursos

La pestaña «Recursos» del menú contextual del sitio te permite configurar qué elementos y conjuntos de elementos están disponibles en las páginas de navegación de tu sitio. La pestaña «Elementos» también permite configurar qué elementos están disponibles en la barra lateral al crear páginas.

Recursos tiene dos pestañas en la parte superior de la ventana: **Elementos** y **Conjuntos de elementos**. 

En la pestaña **Elementos**, puede configurar los elementos disponibles para su selección y exploración en su sitio.

La pestaña **Conjuntos de elementos** es donde se seleccionan los conjuntos que aparecerán en la página «Explorar conjuntos de elementos», en caso de que decida incluirla.

!!! nota
  Las dos pestañas funcionan *de forma independiente* entre sí. Las selecciones realizadas en una no afectarán a la otra. La pestaña «Elementos» limita qué elementos están disponibles, mientras que la pestaña «Conjuntos de elementos» limita qué conjuntos son visibles para la navegación pública.

También tienes la posibilidad de mostrar u ocultar [recursos vinculados](../content/items.md#linked-resources) que no se encuentran en el sitio en cuestión. Vaya a la página de configuración del sitio y [en la sección «Mostrar» encontrará una casilla de verificación](site_settings.md#show) para excluir los recursos que no se hayan añadido al sitio. Tenga en cuenta que, si sigue mostrando recursos externos enlazados, los usuarios podrán hacer clic en el enlace del recurso externo tal y como aparece en los metadatos y ver el recurso como si perteneciera al sitio. Esos recursos externos no aparecerán en las exploraciones ni en las búsquedas.

## Elementos

La pestaña Elementos determina qué aparece automáticamente en las opciones de selección de recursos de las [páginas](../sites/site_pages.md) de tu [sitio](../sites/index.md) de Omeka S. También limita los recursos que aparecen en una página de exploración de tu sitio.

Cuando acceda por primera vez a la pestaña «Elementos», se mostrará información sobre el número de elementos del sitio y se le ofrecerán opciones para realizar cambios. Verá:

- Una indicación del número de elementos asignados actualmente al sitio. Haga clic en el número para abrir una nueva pestaña del navegador que muestre todos esos elementos.
- Una indicación de si el sitio incluye automáticamente nuevos elementos, y un enlace al administrador del sitio para cambiar esa configuración. 
- Una tabla con las siguientes opciones para gestionar tus elementos actuales:
  - No hacer nada: no realizar cambios
  - Añadir: conservar los elementos existentes y asignar elementos de una nueva búsqueda
  - Reemplazar: desasignar todos los elementos y asignar elementos de una nueva búsqueda
  - Eliminar: desasignar elementos de una nueva búsqueda
  - Eliminar todo: desasignar todos los elementos.

![Página de recursos de elementos de un sitio con 28 elementos](../sites/sitesfiles/sites_resources1.png)

Si desea realizar cambios en las fuentes de elementos de su sitio, seleccione el botón de opción correspondiente a la acción que desee realizar. Para todas las opciones excepto «No hacer nada» y «Eliminar todo», aparecerá un elemento **Editar consulta**.

![Recursos de elementos con «Añadir» seleccionado y el formulario de búsqueda cargado](../sites/sitesfiles/sites_resources_query_element.png)

Al hacer clic en «Editar» se mostrará un formulario de búsqueda avanzada en el panel. 

![Panel de búsqueda avanzada con plantillas de recursos de Personas, Ubicación y Evento añadidas](../sites/sitesfiles/sites_resources_query_drawer.png)

Ten en cuenta que las opciones de búsqueda del formulario funcionan conjuntamente para crear una búsqueda global. Si tuvieras la búsqueda de la imagen anterior, buscando elementos en los que «Creador» contenga la palabra «Doyle» y añadieras un criterio donde `Clase=Texto`, solo se añadirían a tu conjunto los elementos que cumplieran *ambas* condiciones.

Las opciones de los formularios de búsqueda son:

**Búsqueda de texto completo**: busca todos los valores de todos los elementos. 

**Búsqueda por valor**: busca un término o frase que introduzcas. 

- El primer selector te permite especificar una propiedad para buscar. 
- El segundo selector te permite establecer la relación que tiene la propiedad con el valor. Las opciones son:
  - es exactamente, 
  - no es exactamente, 
  - contiene,
  - no contiene,
  - es un recurso con ID,
	- no es un recurso con ID,
  - tiene cualquier valor (hay algo en la propiedad), y
  - no tiene valores.
- Por último, hay un campo de texto para que introduzcas el valor que quieres que tenga la propiedad.

Para encontrar un ID de recurso, ve al recurso y mira la URL en la barra de direcciones de tu navegador. Los números al final de la URL son el ID del recurso. 

**Buscar por clase**: seleccione una o más clases del menú desplegable; la búsqueda solo mostrará elementos con esta clase. 

**Buscar por plantilla**: seleccione entre las plantillas de recursos existentes y la búsqueda solo mostrará elementos que utilicen esta plantilla o plantillas de recursos. 

**Buscar por conjunto de elementos**: seleccione de un menú desplegable de conjuntos de elementos.

**Buscar por propietario**: seleccione de un menú desplegable de usuarios del sitio. 

Tenga en cuenta que los campos para búsquedas por valor, clase, plantilla y conjunto de elementos tienen un gran signo más rojo a la izquierda de las opciones de selección. Utilícelos para añadir más de una búsqueda de este tipo a su formulario. Puede utilizar el icono de la papelera roja situado a la derecha del campo para eliminarlo.

En la parte inferior de los campos de búsqueda dentro del panel hay un conjunto de botones para controlar lo que ocurre con su búsqueda. Al hacer clic en el botón «Vista previa» después de crear una búsqueda, se abrirá un nuevo panel con los elementos que cumplen los criterios de la búsqueda. Si desea borrar su búsqueda, seleccione «Restablecer». Una vez que esté satisfecho con sus elementos, seleccione «Aplicar» para establecer el universo. 

Incluso después de haber aplicado su consulta, aún puede «Editar», «Restaurar» su consulta anterior o «Borrar» su consulta. Además, si se trata de una consulta que probablemente vaya a repetir, puede marcar la casilla «Conservar esta consulta».

![Elemento de consulta de recursos de elementos con opciones de actualización ](../sites/sitesfiles/sites_resources_query_update.png)

Conjuntos de elementos
---------------------------
En esta pestaña puede seleccionar qué conjuntos de elementos se mostrarán en la página «Explorar conjuntos de elementos» cuando se añadan a la [navegación](../sites/site_navigation.md). 

La tabla de la pestaña «Conjuntos de elementos» muestra los conjuntos de elementos ya añadidos, con su título y la dirección de correo electrónico del propietario. 

![Pestaña Conjuntos de elementos de los recursos del sitio](../sites/sitesfiles/siteres_itemsets.png)

Para añadir un conjunto de elementos, selecciónelo en la barra lateral derecha. Puede encontrar el conjunto de elementos deseado de dos maneras:

- escribiendo el nombre del conjunto de elementos en la barra de búsqueda y haciendo clic en el conjunto correcto, o
- haciendo clic en el nombre del propietario del conjunto de elementos y, a continuación, en el nombre del conjunto.

![Selección de un conjunto de elementos desde la sección del propietario de la barra lateral](../sites/sitesfiles/siteres_itemsetsel.png)

Elimine un conjunto de elementos haciendo clic en el botón rojo de eliminar (icono de la papelera). Seguirá estando disponible para volver a añadirlo desde el cajón de la derecha.

Puede cambiar el orden de los conjuntos de elementos arrastrando y soltando mediante el icono de tres barras situado en el extremo izquierdo de la fila.

La siguiente imagen muestra una vista pública de los conjuntos de elementos utilizando el tema «Predeterminado»: 

![Página pública de un sitio que muestra los conjuntos de elementos disponibles para su exploración.](../sites/sitesfiles/siteres_ispublic.png)

