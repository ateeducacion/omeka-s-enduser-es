# Vocabulario personalizado

El [módulo Vocabulario personalizado](https://omeka.org/s/modules/CustomVocab){target=_blank} te permite crear un vocabulario controlado con tus propias entradas. Como nuevo [tipo de datos](../content/resource-template.md#data-types), puede añadir el vocabulario a las propiedades de las plantillas de recursos. Al utilizar la plantilla para un elemento, la propiedad se cargará con un menú desplegable limitado a las opciones del vocabulario controlado, en lugar de un cuadro de entrada de texto.

Por ejemplo, es posible que desees crear una lista específica de la institución con ubicaciones que correspondan a diferentes colecciones de tu campus, o una lista controlada de personas o lugares relacionados con tus fondos. Esto puede ayudar a reducir los errores tipográficos y las variaciones de nombres, y te permite ofrecer [navegación por metadatos](../modules/metadatabrowse.md) para más campos.

Custom Vocab está disponible para los usuarios con el [rol de Editor o superior](../admin/users.md).

## Crear un vocabulario personalizado

Una vez que hayas instalado y activado el módulo, ve a la sección Custom Vocab en el menú de navegación de la izquierda, bajo Módulos.

Haz clic en el botón «Añadir vocabulario nuevo» situado en la esquina superior derecha de la ventana.

La página «Añadir vocabulario personalizado» tiene cuatro campos: Etiqueta, Idioma, Tipo de vocabulario («Términos», «Elementos» o «URI») y un campo para introducir tus opciones.

![La página «Añadir vocabulario personalizado», con datos introducidos en los campos «Etiqueta», «Idioma» y «URI»](../modules/modulesfiles/customVocab-add-URI.png)

- **Etiqueta**: Un nombre para el vocabulario. Es posible que desee incluir una indicación del tipo de datos que elija para este vocabulario. 
- **Idioma** (opcional): El idioma del vocabulario, utilizando el [código de idioma ISO 639-1](http://www.iso.org/iso/language_codes){target=_blank}.
- **Tipo de vocabulario**: Puedes configurar los términos del vocabulario controlado como una lista de términos introducidos, una lista de elementos existentes o una lista de URI externos con o sin etiquetas. Dependiendo de esta selección, el siguiente campo será:
	- **Términos**: Una lista de cadenas de texto sin formato, una palabra o frase por línea.
  - **Elementos**: Un menú desplegable con conjuntos de elementos de su instalación de Omeka S. Al elegir uno de estos, se creará un vocabulario personalizado poblado con elementos de ese conjunto. Cuando se utiliza, la propiedad se rellena con un enlace al recurso de la instalación. Es posible que tengas que crear ahora un conjunto de elementos que contenga los elementos que deseas; todos los elementos del conjunto aparecerán en el vocabulario. 
  - **URI**: Una lista de URI, una URI por línea. Para incluir una etiqueta, añada un espacio y la etiqueta después del URI (por ejemplo, «http://viaf.org/viaf/136600716 Canada»). Cuando se utilice, la propiedad se rellenará como un enlace al recurso externo. Si está utilizando un vocabulario publicado, compruebe primero el [módulo Value Suggest](valuesuggest.md) para ver si el vocabulario que desea ya está incluido allí. Si es así, le recomendamos utilizar ese módulo. Como alternativa, puede utilizar Custom Vocab para proporcionar URI estandarizadas a términos externos, pero introduciendo las etiquetas que desee. 

!!! nota
  Ten en cuenta que los términos o URI introducidos manualmente no tienen que ser únicos al introducirlos; el módulo solo conservará una lista de entradas únicas al guardarlas. Si introduces URI idénticos con etiquetas diferentes, solo se conservará la última entrada y se ignorarán las etiquetas anteriores.

## Gestionar vocabularios personalizados

Una vez que haya creado al menos un vocabulario, la pantalla «Custom Vocab» mostrará una tabla con sus vocabularios existentes. La tabla muestra la etiqueta, los botones para editar, eliminar y mostrar información (un icono de tres puntos), y la cuenta de usuario propietaria del vocabulario. 

También hay un botón para «Importar» un vocabulario utilizando un archivo, en la parte superior derecha. La importación añadirá una nueva entrada a la tabla. Si intentas actualizar un vocabulario existente en tu instalación, no utilices el botón «Importar desde archivo»; «Actualiza» el vocabulario desde su entrada en la tabla.

![Pestaña Vocabulario personalizado con dos vocabularios existentes listados en la tabla](../modules/modulesfiles/customVocab_manage.png)

Al hacer clic en los tres puntos, se mostrará el idioma de un vocabulario, así como una lista completa de sus términos. Hay dos botones que permiten «Exportar» un vocabulario, que luego se puede compartir con otras instalaciones de Omeka, o «Actualizar» el vocabulario existente a partir de un archivo. 

Los vocabularios de tipo «Items» no se pueden exportar ni importar, ya que son listas de recursos internos de Omeka y no se pueden replicar en otro sitio. Si deseas publicar tus propios recursos de Omeka como URI, crea un vocabulario de URI utilizando enlaces a los elementos de un sitio específico de Omeka S en tu instalación. 

![Pestaña «Vocabulario personalizado» con la barra lateral abierta, mostrando las opciones para actualizar o exportar el vocabulario](../modules/modulesfiles/customVocab_updateExport.png)

Al editar un vocabulario personalizado, puede cambiar la etiqueta, el idioma o los términos.

## Uso de un vocabulario personalizado

Los vocabularios personalizados se aplican de dos maneras: 

1. A través de [plantillas de recursos](../content/resource-template.md).
2. A través de [tipos de datos](../content/resource-template.md#data-types) aplicados a valores de propiedad existentes. 

La primera opción garantizará que todos los elementos futuros creados utilizando la plantilla de recursos requieran valores de propiedad de su vocabulario personalizado. También afectará a los elementos existentes que utilicen la plantilla de recursos, de modo que la próxima vez que se editen dichos elementos, aparecerá el vocabulario personalizado. Esto **no** afectará a los valores existentes en esas propiedades. 

La segunda opción puede tomar valores de texto o URI introducidos previamente en elementos existentes y registrarlos como las opciones proporcionadas por su vocabulario personalizado. Esto requerirá una coincidencia exacta de la cadena de texto o la URI. En este momento, los valores de las propiedades de los recursos de Omeka no se pueden convertir a un vocabulario personalizado. 

### Vocabularios personalizados en plantillas

Ve a la pantalla de plantillas de recursos y añade una nueva plantilla o edita una existente. Una vez en la pantalla de edición de plantillas:

1. Añade la propiedad a la que deseas aplicar el vocabulario personalizado.
1. Edita la propiedad.
1. En el panel que se abre a la derecha, ve a la sección «Otras opciones» y busca el menú desplegable «Tipo de datos».
1. Desplázate por el menú desplegable y selecciona el vocabulario que desees utilizar.
1. Haz clic en «Aplicar cambios» en la parte inferior del panel.

A continuación, guarda los cambios en la plantilla.

![Datos de la plantilla de recursos en proceso de edición con el menú desplegable abierto para mostrar los vocabularios disponibles](../modules/modulesfiles/customVocab_select.png)

Al hacer clic en el título de una plantilla de recurso para ver sus detalles, el vocabulario personalizado aparecerá en la columna «Tipo de datos» de la tabla, en la fila de la propiedad correspondiente.

![Plantilla de recurso «Parque Nacional» con el vocabulario personalizado «Estado» aplicado a la cobertura espacial](../modules/modulesfiles/customVocab_resource.png)

Cuando se utiliza esta plantilla de recurso para un elemento, un medio o un conjunto de elementos, la propiedad designada siempre se cargará como un menú desplegable con los valores del vocabulario personalizado. Recuerde que el vocabulario personalizado **requiere** que los usuarios lo utilicen. Si desea ofrecer el vocabulario personalizado solo como una opción, añada un segundo tipo de datos o varios tipos de datos que ofrezcan alternativas, como un campo de texto sin formato. 

En la siguiente imagen, la plantilla de recurso modificada anteriormente se carga para un nuevo elemento. El campo «Cobertura espacial» tiene un mensaje «seleccionar a continuación» y flechas que indican que la entrada de la propiedad es un menú desplegable.

![como se describe](../modules/modulesfiles/customVocab_item1.png)

La siguiente imagen muestra el menú desplegable abierto, mostrando los valores del vocabulario «Estados y territorios de EE. UU.».

![como se describe](../modules/modulesfiles/customVocab_item2.png)

### Convertir tipos de datos

También puede aplicar vocabularios personalizados como tipos de datos a valores existentes en recursos existentes, independientemente de si utilizan alguna plantilla de recurso. 

Esto puede resultar útil en el caso de una importación CSV u otra ingesta en la que no se aplicó el tipo de datos correcto en su momento. O en el caso de que los valores introducidos manualmente puedan ahora hacerse coincidir con un vocabulario controlado en línea (quizás uno que haya publicado la propia institución). 

Seleccione varios recursos en la página de exploración de la interfaz de administración y, a continuación, elija la opción por lotes «Editar seleccionados» (o «Editar todo»). En la siguiente pantalla, busque la opción «Convertir tipo de datos» en la sección «Valores», cerca de la parte inferior del formulario. Esto le permitirá elegir una propiedad de entre todos los elementos seleccionados y aplicar un vocabulario personalizado como tipo de datos. 

![La opción «Convertir tipo de datos» en la pantalla de edición por lotes, que muestra «Creador» como primera selección y el menú desplegable expandido para mostrar los vocabularios de Custom Vocab en la segunda selección.](../modules/modulesfiles/customVocab_batchEdit.png)

Esta configuración de tipo de datos se aplicará a los valores existentes en la propiedad si es posible. Los valores de texto, si coinciden exactamente con las entradas de una lista de vocabulario personalizado de texto, funcionarán. Los URI, si coinciden exactamente con las entradas de una lista de vocabulario personalizado de URI, también funcionarán. No se pueden asignar URI mediante etiquetas coincidentes. 

Por el momento, no se pueden convertir recursos vinculados a un vocabulario personalizado. 

!!! nota
  Ten en cuenta que si has introducido un valor URI y una etiqueta, y luego lo conviertes al tipo de datos de vocabulario personalizado, tu etiqueta original será sustituida por la etiqueta del vocabulario personalizado.

Puede confirmar que la conversión se ha realizado correctamente editando uno de los elementos y comprobando que el valor original ha sido sustituido por un menú desplegable que muestra las demás opciones del vocabulario personalizado. 

Si, por ejemplo, tienes valores URI con formato de texto sin formato en elementos existentes y deseas convertirlos para que coincidan con un vocabulario personalizado de URI, puedes hacerlo mediante un proceso en dos etapas. En primer lugar, convierta los valores de las propiedades de los elementos de texto a URI utilizando el mismo proceso de edición por lotes; a continuación, convierta esos URI al vocabulario personalizado que haya elegido. 