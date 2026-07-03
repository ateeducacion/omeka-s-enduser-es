# Propiedades inversas

El [módulo «Propiedades inversas»](https://omeka.org/s/modules/InverseProperties/){target=_blank} permite a los administradores definir propiedades inversas entre recursos (elementos, conjuntos de elementos y archivos multimedia) para que los valores de las propiedades puedan vincularse de forma concreta en ambas direcciones. 

En Omeka S, los recursos de una instalación pueden vincularse a otros: [elementos](../content/items.md#linked-resources) a otros elementos, conjuntos de elementos o a sus propios recursos multimedia; [recursos multimedia](../content/media.md#omeka-resource) a elementos o conjuntos de elementos; [conjuntos de elementos](../content/item-sets.md#linked-resources) a otros conjuntos de elementos o a elementos. Estos enlaces se añaden a través de valores de metadatos; por ejemplo, utilizando un elemento de persona «William Shakespeare» como valor de «Creador» en un elemento de obra de teatro «Mucho ruido y pocas nueces». Al visualizar el elemento de persona, verás los enlaces entrantes en la tabla «Recursos vinculados». 

Por defecto, estos enlaces de metadatos son unidireccionales: si editas el elemento de obra de teatro, el elemento de persona no se ve afectado. El módulo «Propiedades inversas» convierte ese enlace unidireccional en uno bidireccional, añadiendo un valor de metadatos recíproco al elemento de persona para representar la relación de esa persona con el elemento de obra de teatro. (Por ejemplo, la propiedad «Publicaciones» de «Amigo de un amigo» podría utilizarse para indicar las múltiples publicaciones de las que es autor la persona).

Algunas propiedades inversas son obvias (por ejemplo, «Tiene parte» de Dublin Core es la inversa prevista de «Es parte de»), pero otras son flexibles según el tipo de elementos de la instalación. Por lo tanto, las relaciones de propiedades inversas de tu instalación deben especificarse manualmente.

Los enlaces inversos creados de esta manera pueden ahorrar tiempo en la introducción de datos y resultar útiles en [visualizaciones de datos](datavisualization.md), en la navegación avanzada o por facetas, y en la [importación por lotes](csvimport.md) de relaciones entre recursos.

### Propiedades inversas sugeridas

- Dublin Core (`dcterms:`):
  - Reemplaza y Es reemplazado por (`dcterms:replaces`; `dcterms:isreplacedby`)
	- Requiere y es requerido por
  - Referencias y es referenciado por
  - Tiene formato y es formato de
  - Tiene parte y es parte de
  - Tiene versión y es versión de
  - Relación (puede ser su propia propiedad inversa).
- Ontología bibliográfica (`bibo:`):
	- citedBy y cites
  - presents y presentedAt
- Amigo de un amigo (`foaf:`):
  - depicts y depiction
- [Relación](http://purl.org/vocab/relationship) (`relationship:`)
	- Hijo de y Padre de 
  - Cónyuge de (puede ser su propia propiedad inversa).

Se pueden formar pares inversos con propiedades de dos vocabularios diferentes (por ejemplo, «Creator» de Dublin Core y «publications» de Friend of a Friend). 

También se puede definir un emparejamiento inverso entre diferentes tipos de recursos: por ejemplo, entre un conjunto de elementos y un elemento, o entre un elemento y un medio. Estos emparejamientos de recursos mixtos no necesitan utilizar la misma plantilla de recurso. Por ejemplo, un elemento «persona» puede tener un conjunto de elementos «comunidad» como valor en la propiedad «Forma parte de». Al configurar la propiedad inversa en una plantilla de recurso «persona», al conjunto de elementos relacionado se le asignará la propiedad inversa «Tiene parte», independientemente de su propia plantilla de recurso o de los metadatos existentes. 

## Asignar propiedades inversas en plantillas de recursos

Una vez instalado el módulo, debería aparecer en el menú de navegación de la izquierda. Al seleccionar «Propiedades inversas», se te redirigirá a una tabla con las plantillas de recursos disponibles. Además de la etiqueta y el propietario, hay una columna que indica el número de propiedades inversas de cada plantilla. Para utilizar «Propiedades inversas», empieza por editar una plantilla de recurso con el icono del lápiz. 

Es posible que tengas una plantilla «Persona» que incluya propiedades como «Cónyuge», «Hijo» y «Padre» que pretendes utilizar para mostrar relaciones recíprocas con otros recursos. 

![Edita una plantilla de recurso existente para añadir propiedades inversas.](modulesfiles/inverseProperties_edit.png)

Para asignar una propiedad inversa, selecciona una inversa para esa propiedad en el menú desplegable. Puedes desplazarte por la lista de opciones o utilizar la barra de búsqueda para ir directamente a una propiedad específica. Ten cuidado, en instalaciones con varios vocabularios, de seleccionar el vocabulario correcto y la propiedad deseada dentro de él. 

Ten en cuenta que establecer un único emparejamiento solo significará que, al editar el primer valor, se creará el segundo. Editar el segundo valor no creará el primero, a menos que lo configures como un emparejamiento independiente. Por ejemplo, si se configura «Hijo de» para que tenga como inversa «Padre de», guardar un valor de «Hijo de» creará un valor de «Padre de», pero guardar un valor de «Padre de» **no** creará un valor de «Hijo de». Debes configurar «Padre de» para que tenga como inverso «Hijo de» también.

La excepción a esto sería configurar un emparejamiento propio, como «Cónyuge de» o «Relación». 

![Selecciona la propiedad inversa en el menú desplegable.](modulesfiles/inverseProperties_dropdown.png)

Una vez que hayas seleccionado todas las propiedades inversas para esa plantilla de recurso, haz clic en «Enviar» en la esquina superior derecha para guardar los cambios.

## Propiedades inversas en acción

Al añadir o editar un elemento, selecciona una plantilla de recurso que tenga propiedades inversas. A continuación, en una propiedad que tenga una inversa, haz clic en «Recurso de Omeka». Después, haz clic en el tipo de recurso (como «Elemento») y selecciona el recurso que desees añadir desde el panel lateral. Después de hacer clic en el título del recurso, asegúrate de hacer clic en el botón «Seleccionar recurso» situado en la parte inferior del panel lateral para añadir el elemento al campo de metadatos. Puedes añadir varios recursos a la vez con el botón «Añadir rápidamente». 

![Pantalla de edición de un elemento centrada en la propiedad «Relación». Una flecha azul señala el botón «Recurso de Omeka» dentro del cuadro de la propiedad. El panel de la derecha está abierto y muestra una lista de elementos.](modulesfiles/inverseProperties_add.png)

Una vez que hayas terminado de editar el elemento, haz clic en «Guardar». El elemento que has añadido como recurso vinculado debería aparecer ahora en la página de visualización del elemento.

![Página de visualización del elemento guardado, en la que se muestra un elemento vinculado en la propiedad «Relación». Hay una flecha azul que apunta hacia él. La miniatura del elemento se muestra a la izquierda del título del elemento, con un icono de cubo a la derecha que indica que se trata de un tipo de datos de recurso vinculado.](modulesfiles/inverseProperties_itemShow.png)

Si haces clic en el recurso que acabas de vincular, deberías ver que el valor de la propiedad inversa se ha creado automáticamente.

![Página de visualización del elemento para el recurso que se ha vinculado. Su propiedad «Relación» también se ha rellenado, con un enlace que remite al primer elemento. Se muestran su miniatura y su título, también con un icono de cubo.](modulesfiles/inverseProperties_linkedProperty.png)

Si eliminas un valor, su inverso no se eliminará automáticamente. Debes eliminar cada valor manualmente desde su propio recurso.

### Actualización por lotes de propiedades inversas

Si ya tienes recursos vinculados configurados y, a continuación, activas las «Propiedades inversas» y asignas emparejamientos en las plantillas de recursos, puedes crear por lotes tus valores recíprocos utilizando la función de edición por lotes. Ve a «Elementos», «Multimedia» o «Conjuntos de elementos» en el menú de navegación de la izquierda y, a continuación, selecciona varios recursos (utiliza la «Búsqueda avanzada» para encontrar todos los recursos que utilicen la plantilla). A continuación, utiliza el menú desplegable «Acciones en bloque» para editar los recursos seleccionados o todos los recursos de los resultados de la búsqueda. 

![El formulario de edición por lotes muestra una entrada para «Propiedades inversas», con una casilla de selección para generar los emparejamientos IR.](modulesfiles/inverseProperties_batchedit.png)

En el formulario de edición en bloque verás una entrada para «Propiedades inversas». Utiliza la casilla de selección para indicar que todas las propiedades inversas establecidas para todos los recursos que has seleccionado deben generar sus emparejamientos. A continuación, haz clic en «Enviar» para enviar el formulario. 

!!! Nota
  Las «Propiedades inversas» **no** funcionarán con la [importación CSV](csvimport.md). Importa los recursos vinculados como de costumbre y, a continuación, utiliza el formulario de edición por lotes para actualizar los emparejamientos inversos.
