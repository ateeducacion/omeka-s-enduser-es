# Conector de ArchivesSpace

El [módulo Conector de ArchivesSpace](https://omeka.org/s/modules/ArchivesspaceConnector){target=_blank} te permite conectar una instancia de Omeka S a un [repositorio de ArchivesSpace](https://archivesspace.org){target=_blank} para importar elementos y conjuntos de elementos desde dicho repositorio. Este módulo funciona en combinación con el [módulo Hierarchy](hierarchy.md) para crear y mantener un árbol estructurado de colecciones y contenedores de ArchivesSpace, representando fielmente su organización archivística dentro de Omeka. 

Tras importar la información, Omeka S mantendrá una conexión con el material original, lo que le permite [actualizar la información desde la fuente cuando lo desee](#update-imported-resources). 

Tenga en cuenta que, por el momento, Omeka S no puede importar materiales digitales desde ArchivesSpace, solo metadatos textuales. 

Este conector depende de la API de ArchivesSpace y de su configuración. Necesitará una instalación de ArchivesSpace con una API pública y un conjunto preciso de configuraciones en su cuenta para importar los materiales correctamente.

![](modulesfiles/aspace_public.png)

## Configure su instalación de ArchivesSpace

En primer lugar, asegúrese de que su sitio web de ArchivesSpace tiene la API habilitada. Es posible que esto no sea posible si utiliza una instancia alojada de ArchivesSpace. 

El enlace debe comenzar por `https://` y terminar por `/api`. Compruebe que la API funciona introduciendo esta URL en su navegador. Si funciona, es posible que vea información en formato JSON que incluya la clave «archivesSpaceVersion».

A continuación, recomendamos que sus colecciones se diseñen para adaptarse al modelo de datos de Omeka S. 

### Objetos de ArchivesSpace

Por lo general, todos los contenedores (colecciones, series, subseries, archivos, etc.) deben importarse como conjuntos de elementos de Omeka, con el módulo Hierarchy instalado y activo para organizar dichos conjuntos de elementos en una jerarquía que coincida con la configuración de ArchivesSpace. 

Sus objetos de ArchivesSpace de nivel más bajo deben ser «archivos» o «elementos». Estos dos tipos de objetos se pueden importar como elementos de Omeka, dependiendo de la colección y de sus intenciones. Si la colección ya está descrita hasta el nivel de elemento, utilizando el identificador «elemento» de ArchivesSpace, estos se pueden importar fácilmente como elementos de Omeka. 

Si la colección está descrita a un nivel superior, puede elegir si los «archivos» de ArchivesSpace se convierten en elementos de Omeka o en conjuntos de elementos. Esto le permitirá procesar posteriormente más materiales e incluirlos a nivel de elemento, haciendo coincidir con la primera importación. Si reconfigura sus materiales de ArchivesSpace (por ejemplo, cambiando objetos de «archivo» a objetos de «elemento»), le recomendamos deshacer la importación original y empezar de cero. 

### Herencia de metadatos

ArchivesSpace tiene un ajuste de configuración, habilitado por defecto, que permite que los metadatos de nivel superior se muestren en objetos de nivel inferior: «Herencia». Cuando está activo, la salida de la API de ArchivesSpace envía información sin contexto: es decir, una extensión a nivel de colección se duplicará en los metadatos de todos sus objetos de nivel inferior que no tengan su propia extensión, pero no se representa como «De la colección» en la API. 

Por lo tanto, recomendamos desactivar esta opción al importar a Omeka, para garantizar que los metadatos no se repliquen fuera de contexto. Puede consultar cómo desactivar esta opción en su instalación en la [documentación técnica de ArchivesSpace](https://archivesspace.github.io/tech-docs/architecture/public/){target=_blank} —busque la sección «Herencia». El [archivo que hay que editar se llama `config-defaults.rb`](https://github.com/archivesspace/archivesspace/blob/master/common/config/config-defaults.rb){target=_blank}. 

## Configure su instalación de Omeka

El módulo ArchivesSpace no tiene opciones de configuración y no añade ninguna configuración específica del sitio. 

Recomendamos instalar y activar el módulo Hierarchy para optimizar el uso de este conector. Se crearán jerarquías automáticamente para representar su sistema organizativo de ArchivesSpace y le ayudarán a gestionar los conjuntos de elementos que se crean con cada importación. 

## Importar colecciones

En Omeka S, vaya a la sección denominada «ArchivesSpace Connector» en Módulos. Al principio verá la pantalla «Importar».

![Las opciones de importación del conector de ArchivesSpace. Los campos se enumeran en el texto a continuación.](modulesfiles/aspace_import.png)

En el formulario de importación, introduzca la siguiente información:

* **URL de la API de ArchivesSpace**: La URL completa, incluyendo `https://`. Debe terminar en `/api`.
* **Ruta de destino de ArchivesSpace**: La parte de la URL correspondiente a una colección específica. Tendrá el formato `/repositories/1/resource/1`. 
* **Mantener jerarquía de la colección**: Una casilla de verificación para habilitar la conexión de la importación con el módulo Jerarquía de Omeka S. Si no se marca, no se crearán conjuntos de elementos con esta importación, y no se creará ninguna jerarquía a través del [módulo Jerarquía](hierarchy.md). 
* **Nivel de elemento de Omeka**: Elige cuáles de las opciones de objetos de ArchivesSpace se importarán como elementos de Omeka S. Puedes elegir «Elementos», «Archivos» o ambos. Si eliges «Elementos», los objetos contenedores de nivel superior (incluidos los archivos) se importarán como conjuntos de elementos de Omeka. 
* **Eliminar elementos que faltan al actualizar**: Una casilla de verificación para cambiar el comportamiento al volver a ejecutar una importación. Si está marcada, un elemento creado en una importación anterior pero eliminado en ArchivesSpace se eliminará en Omeka. Si no está marcada, las actualizaciones no eliminarán los objetos que faltan. 
* **Comentario**: Un campo de texto para proporcionar un recordatorio a usted mismo o a otros sobre los detalles de esta importación.
* **Plantilla de recursos**: Puede optar por aplicar una plantilla de recursos a todos los elementos y conjuntos de elementos creados por el proceso de importación. Si desea utilizar más de una (por ejemplo, una para los elementos creados y otra para los conjuntos de elementos creados), puede editar los recursos por lotes una vez finalizada la importación, utilizando los enlaces de la tabla Importaciones anteriores (véase más abajo). 
* **Sitios**: Añade los recursos importados (elementos, conjuntos de elementos y jerarquías) a los siguientes sitios de forma inmediata. Este campo carga todos los sitios de forma predeterminada. Elimínalos haciendo clic en la X; añade sitios haciendo clic en el campo: aparecerá un menú desplegable. 

Haga clic en el botón «Importar». Si la información anterior se ha introducido correctamente, verá una nueva página con un banner verde en la parte superior que indica el número de trabajo de la importación. 

Puede realizar un seguimiento del estado de las importaciones navegando a la pestaña «Importaciones anteriores» del conector de ArchivesSpace, o en la página [Trabajos](../admin/jobs.md) del panel de administración.

!!! nota
  ¿Sus trabajos se inician pero no se completan? Es posible que tenga que [configurar la ruta de PHP](../configuration.md#php-path) para que su sistema pueda ejecutar el proceso en segundo plano para crear los elementos.

### Confirmar la importación

Para confirmar que la importación se ha realizado correctamente, puede hacer clic en cualquiera de los recursos importados (elementos o conjuntos de elementos) para ver su página de vista en el panel de administración. Los elementos se clasificarán automáticamente en los conjuntos de elementos pertinentes, por lo que ambos recursos mostrarán la jerarquía tal y como está. 

![Una página de vista de un elemento, que muestra que se encuentra dentro de un conjunto de elementos y que la jerarquía se muestra en la barra lateral derecha.](modulesfiles/aspace_item.png)

Una vez que haya confirmado que la jerarquía se ha creado correctamente, compruebe que se ha añadido a cada sitio que especificó en la configuración de importación. 

A continuación, asegúrese de que la configuración específica del sitio para las jerarquías se ajusta a cómo desea que se muestren sus jerarquías de ArchivesSpace. Probablemente desee desactivar las páginas de visualización de agrupaciones para que las jerarquías enlacen directamente con los conjuntos de elementos y muestren todos los metadatos importados. Es posible que no desee mostrar el recuento de elementos si sus importaciones no contienen objetos importados como elementos.  

## Importaciones anteriores

La página «Importaciones anteriores» muestra una tabla de conexiones existentes de ArchivesSpace, con el **ID de tarea** de la importación, una opción radial para **Deshacer** o **Volver a ejecutar** la importación, la **Colección de ArchivesSpace** del repositorio con un enlace a la salida de la API para compararla (que se muestra como nombre de la colección si se encuentra), cualquier **Comentario** establecido para la importación, el número de **Recursos** importados con un enlace a los resultados de la búsqueda avanzada, la **Fecha** de la importación, el **Estado** de la importación y el **Propietario** que inició la importación.

![Tabla de importaciones anteriores.](modulesfiles/aspace_past.png)

Puede ver la salida de la API directamente haciendo clic en los enlaces de la columna «Colección de ArchivesSpace». Esto puede ayudarle a identificar cualquier error que aparezca durante el proceso, como metadatos de nivel superior que aparecen en objetos de nivel inferior.

## Actualizar recursos importados

Para actualizar los recursos creados con el conector de ArchivesSpace, simplemente marque «Re-run» (Volver a ejecutar) y, a continuación, haga clic en «Submit» (Enviar) en la página «Past Imports» (Importaciones anteriores). Los recursos se actualizarán, no se volverán a importar. Esto le permite utilizar el conector para sincronizar datos entre las instalaciones de ArchivesSpace y Omeka S. Puede volver a ejecutar más de una importación a la vez. 

No se pueden cambiar los ajustes de importación al volver a ejecutar una importación. 

## Deshacer una importación

Puede ver las conexiones existentes en la página «Importaciones anteriores». Para deshacer una importación completada y eliminar todos los recursos asociados, cambie el botón de opción de cada importación que desee deshacer y haga clic en el botón «Enviar». Esto también eliminará la jerarquía que se creó para la importación. 