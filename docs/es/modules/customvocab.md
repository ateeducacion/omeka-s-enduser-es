# Vocabulario personalizado

El [módulo «Vocabulario personalizado»](https://omeka.org/s/modules/CustomVocab){target=_blank} te permite crear un vocabulario controlado con tus propias entradas. Al tratarse de un nuevo [tipo de datos](../content/resource-template.md#data-types), podrás añadir el vocabulario a las propiedades de las plantillas de recursos. Al utilizar la plantilla para un elemento, la propiedad se cargará con un menú desplegable limitado a las opciones del vocabulario controlado, en lugar de un cuadro de entrada de texto.

Por ejemplo, quizá quieras crear una lista específica de la institución con las ubicaciones que corresponden a las diferentes colecciones de tu campus, o una lista controlada de personas o lugares relacionados con tus fondos. Esto puede ayudar a reducir los errores tipográficos y las variaciones en los nombres, y te permite ofrecer [navegación por metadatos](../modules/metadatabrowse.md) para más campos.

«Custom Vocab» está disponible para los usuarios con el [rol de editor o superior](../admin/users.md).

## Crear un vocabulario personalizado

Una vez que hayas instalado y activado el módulo, ve a la sección «Custom Vocab» en el menú de navegación de la izquierda, dentro de «Módulos».

Haz clic en el botón «Añadir nuevo vocabulario» situado en la esquina superior derecha de la ventana.

La página «Añadir vocabulario personalizado» tiene cuatro campos: Etiqueta, Idioma, Tipo de vocabulario («Términos», «Elementos» o «URI») y un campo para introducir tus opciones.

![La página «Añadir vocabulario personalizado», con datos introducidos en los campos «Etiqueta», «Idioma» y «URI»](../modules/modulesfiles/customVocab-add-URI.png)

- **Etiqueta**: Un nombre para el vocabulario. Quizá te interese incluir una indicación del tipo de datos que elijas para este vocabulario. 
- **Idioma** (opcional): El idioma del vocabulario, utilizando el [código de idioma ISO 639-1](http://www.iso.org/iso/language_codes){target=_blank}.
- **Tipo de vocabulario**: Puedes configurar los términos del vocabulario controlado como una lista de términos introducidos, una lista de elementos existentes o una lista de URI externos con o sin etiquetas. Dependiendo de esta selección, el siguiente campo será:
	- **Términos**: Una lista de cadenas de texto sin formato, con una palabra o frase por línea.
  - **Elementos**: Un menú desplegable con los conjuntos de elementos de tu instalación de Omeka S. Al seleccionar uno de ellos, se creará un vocabulario personalizado que se completará con los elementos de ese conjunto. Cuando se utiliza, la propiedad se rellena con un enlace al recurso de la instalación. Es posible que tengas que crear ahora un conjunto de elementos que contenga los elementos que deseas; todos los elementos de dicho conjunto aparecerán en el vocabulario. 
  - **URI**: Una lista de URI, una URI por línea. Para incluir una etiqueta, añade un espacio y la etiqueta después de la URI (por ejemplo, «http://viaf.org/viaf/136600716 Canada»). Cuando se utilice, la propiedad se rellenará con un enlace al recurso externo. Si estás utilizando un vocabulario publicado, consulta primero el [módulo Value Suggest](valuesuggest.md) para comprobar si el vocabulario que deseas ya está incluido allí. Si es así, te recomendamos utilizar ese módulo. Como alternativa, puedes utilizar Custom Vocab para proporcionar URI estandarizadas a términos externos, pero introduciendo las etiquetas que desees. 

!!! nota
  Ten en cuenta que los términos o URI introducidos manualmente no tienen por qué ser únicos en el momento de su introducción; el módulo solo conservará una lista de entradas únicas al guardar. Si introduces URI idénticos con etiquetas diferentes, solo se conservará la última entrada y se ignorarán las etiquetas anteriores.

## Gestionar vocabularios personalizados

Una vez que hayas creado al menos un vocabulario, la pantalla «Custom Vocab» mostrará una tabla con tus vocabularios existentes. La tabla muestra la etiqueta, los botones para editar, eliminar y mostrar información (un icono de tres puntos), y la cuenta de usuario propietaria del vocabulario. 

También hay un botón para «Importar» un vocabulario desde un archivo, situado en la esquina superior derecha. La importación añadirá una nueva entrada a la tabla. Si intentas actualizar un vocabulario existente en tu instalación, no utilices el botón «Importar desde archivo»; «Actualiza» el vocabulario desde su entrada en la tabla.

![Pestaña «Vocabulario personalizado» con dos vocabularios existentes en la tabla](../modules/modulesfiles/customVocab_manage.png)

Al hacer clic en los tres puntos, se mostrará el idioma de un vocabulario, así como una lista completa de sus términos. Hay dos botones que permiten «Exportar» un vocabulario, que luego se puede compartir con otras instalaciones de Omeka, o «Actualizar» el vocabulario existente a partir de un archivo. 

Los vocabularios de tipo «elementos» no se pueden exportar ni importar, ya que son listas de recursos internos de Omeka y no se pueden replicar en otro sitio. Si deseas publicar tus propios recursos de Omeka como URI, crea un vocabulario de URI utilizando enlaces a los elementos de un sitio específico de Omeka S en tu instalación. 

![Pestaña «Vocabulario personalizado» con la barra lateral abierta, mostrando las opciones para actualizar o exportar el vocabulario](../modules/modulesfiles/customVocab_updateExport.png)

Al editar un vocabulario personalizado, puede cambiar la etiqueta, el idioma o los términos.

## Uso de un vocabulario personalizado

Los vocabularios personalizados se aplican de dos maneras: 

1. A través de [plantillas de recursos](../content/resource-template.md).
2. A través de [tipos de datos](../content/resource-template.md#data-types) aplicados a los valores de propiedades existentes. 

La primera opción garantizará que todos los elementos que se creen en el futuro utilizando la plantilla de recurso requieran valores de propiedad de tu vocabulario personalizado. También afectará a los elementos existentes que utilicen la plantilla de recurso, de modo que la próxima vez que se editen dichos elementos, aparecerá el vocabulario personalizado. Esto **no** afectará a los valores existentes en esas propiedades. 

La segunda opción puede tomar valores de texto o URI introducidos previamente en elementos existentes y registrarlos como las opciones proporcionadas por tu vocabulario personalizado. Esto requerirá una coincidencia exacta de la cadena de texto o del URI. Por el momento, los valores de las propiedades de los recursos de Omeka no se pueden convertir a un vocabulario personalizado. 

### Vocabularios personalizados en plantillas

Ve a la pantalla de plantillas de recursos y añade una nueva plantilla o edita una ya existente. Una vez en la pantalla de edición de plantillas:

1. Añade la propiedad a la que deseas aplicar el vocabulario personalizado.
1. Edita la propiedad.
1. En el panel que se abre a la derecha, ve a la sección «Otras opciones» y busca el menú desplegable «Tipo de datos».
1. Desplázate por el menú desplegable y selecciona el vocabulario que desees utilizar.
1. Haz clic en «Aplicar cambios» en la parte inferior del panel.

A continuación, guarda los cambios en la plantilla.

![Datos de una plantilla de recursos en proceso de edición con el menú desplegable abierto para mostrar los vocabularios disponibles](../modules/modulesfiles/customVocab_select.png)

Al hacer clic en el título de una plantilla de recurso para ver sus detalles, el vocabulario personalizado aparecerá en la columna «Tipo de datos» de la tabla, en la fila de la propiedad correspondiente.

![Plantilla de recurso «Parque Nacional» con el vocabulario personalizado «Estado» aplicado a la «Cobertura espacial»](../modules/modulesfiles/customVocab_resource.png)

Cuando se utiliza esta plantilla de recurso para un elemento, un medio o un conjunto de elementos, la propiedad designada siempre se cargará como un menú desplegable con los valores del vocabulario personalizado. Recuerda que el vocabulario personalizado **requiere** que los usuarios lo utilicen. Si deseas ofrecer el vocabulario personalizado únicamente como una opción, añade un segundo tipo de datos o varios tipos de datos que ofrezcan alternativas, como un campo de texto sin formato. 

En la siguiente imagen, la plantilla de recurso modificada anteriormente se carga para un nuevo elemento. El campo «Cobertura espacial» muestra el mensaje «Seleccionar a continuación» y unas flechas que indican que el campo de la propiedad es un menú desplegable.

![como se describe](../modules/modulesfiles/customVocab_item1.png)

La siguiente imagen muestra el menú desplegable abierto, en el que se muestran los valores del vocabulario «Estados y territorios de EE. UU.».

![como se describe](../modules/modulesfiles/customVocab_item2.png)

### Convertir tipos de datos

También puedes aplicar vocabularios personalizados como tipos de datos a valores existentes en recursos ya creados, independientemente de si utilizan o no alguna plantilla de recurso. 

Esto puede resultar útil en el caso de una importación CSV u otra ingesta en la que no se aplicara el tipo de datos correcto en su momento. O en el caso de que los valores introducidos manualmente puedan ahora relacionarse con un vocabulario controlado en línea (quizás uno que haya publicado la propia institución). 

Selecciona varios recursos en la página de exploración de la interfaz de administración y, a continuación, elige la opción por lotes «Editar seleccionados» (o «Editar todo»). En la siguiente pantalla, busca la opción «Convertir tipo de datos» en la sección «Valores», cerca de la parte inferior del formulario. Esto te permitirá elegir una propiedad de entre todos los elementos seleccionados y aplicar un vocabulario personalizado como tipo de datos. 

![La opción «Convertir tipo de datos» en la pantalla de edición por lotes, que muestra «Creador» como primera selección y el menú desplegable expandido para mostrar los vocabularios de Custom Vocab en la segunda selección.](../modules/modulesfiles/customVocab_batchEdit.png)

Esta configuración del tipo de datos se aplicará a los valores existentes en la propiedad si es posible. Los valores de texto, si coinciden exactamente con las entradas de una lista de vocabulario personalizado de texto, funcionarán. Las URI, si coinciden exactamente con las entradas de una lista de vocabulario personalizado de URI, también funcionarán. No se pueden asignar URI mediante etiquetas coincidentes. 

Por el momento, no es posible convertir recursos vinculados a un vocabulario personalizado. 

!!! nota
  Ten en cuenta que, si has introducido un valor URI y una etiqueta y, a continuación, lo conviertes al tipo de datos de vocabulario personalizado, tu etiqueta original será sustituida por la etiqueta del vocabulario personalizado.

Puede comprobar que la conversión se ha realizado correctamente editando uno de los elementos y comprobando que el valor original ha sido sustituido por un menú desplegable que muestra las demás opciones del vocabulario personalizado. 

Si, por ejemplo, tienes valores URI con formato de texto sin formato en elementos existentes y deseas convertirlos para que coincidan con un vocabulario personalizado de URI, puedes hacerlo mediante un proceso en dos fases. En primer lugar, convierte los valores de las propiedades de los elementos de texto a URI utilizando el mismo proceso de edición por lotes; a continuación, convierte esas URI al vocabulario personalizado que hayas elegido. 