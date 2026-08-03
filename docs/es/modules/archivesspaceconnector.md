# Conector de ArchivesSpace

El [módulo «ArchivesSpace Connector»](https://omeka.org/s/modules/ArchivesspaceConnector){target=_blank} te permite conectar una instancia de Omeka S a un [repositorio de ArchivesSpace](https://archivesspace.org){target=_blank} para importar elementos y conjuntos de elementos desde dicho repositorio. Este módulo funciona en combinación con el [módulo Hierarquía](hierarchy.md) para crear y mantener un árbol estructurado de colecciones y contenedores de ArchivesSpace, representando fielmente la organización de tus archivos dentro de Omeka. 

Tras importar la información, Omeka S mantendrá una conexión con el material original, lo que te permite [actualizar la información desde la fuente cuando lo desees](#update-imported-resources). 

Ten en cuenta que, por el momento, Omeka S no puede importar materiales digitales desde ArchivesSpace, sino únicamente metadatos textuales. 

Este conector se basa en la API de ArchivesSpace y en su configuración. Necesitarás una instalación de ArchivesSpace con una API pública y un conjunto preciso de configuraciones en tu cuenta para importar los materiales correctamente.

![](modulesfiles/aspace_public.png)

## Configurar tu instalación de ArchivesSpace

En primer lugar, asegúrate de que tu sitio web de ArchivesSpace tenga la API habilitada. Es posible que esto no sea posible si utilizas una instancia alojada de ArchivesSpace. 

El enlace debe comenzar por `https://` y terminar por `/api`. Comprueba que la API funciona introduciendo esta URL en tu navegador. Si funciona, es posible que veas información en formato JSON que incluya la clave «archivesSpaceVersion».

A continuación, te recomendamos que tus colecciones estén diseñadas para adaptarse al modelo de datos de Omeka S. 

### Objetos de ArchivesSpace

Por lo general, todos los contenedores (colecciones, series, subseries, archivos, etc.) deben importarse como conjuntos de elementos de Omeka, con el módulo «Jerarquía» instalado y activo para organizar dichos conjuntos de elementos en una jerarquía que se ajuste a la configuración de ArchivesSpace. 

Los objetos de ArchivesSpace de nivel más bajo deben ser «archivos» o «elementos». Estos dos tipos de objetos pueden importarse como elementos de Omeka, dependiendo de la colección y de tus intenciones. Si la colección ya está descrita hasta el nivel de elemento, utilizando el identificador «elemento» de ArchivesSpace, estos pueden importarse fácilmente como elementos de Omeka. 

Si la colección está descrita a un nivel superior, puede elegir si los «archivos» de ArchivesSpace se convierten en elementos de Omeka o en conjuntos de elementos. Esto le permitirá procesar posteriormente más materiales e incluirlos a nivel de elemento, manteniendo la coherencia con la primera importación. Si reconfigura los materiales de ArchivesSpace (por ejemplo, cambiando los objetos «archivo» por objetos «elemento»), le recomendamos que deshaga la importación original y empiece de cero. 

### Herencia de metadatos

ArchivesSpace cuenta con un parámetro de configuración, activado por defecto, que permite que los metadatos de nivel superior se muestren en los objetos de nivel inferior: «Herencia». Cuando está activa, la salida de la API de ArchivesSpace envía información sin contexto: es decir, el alcance a nivel de colección se duplicará en los metadatos de todos sus objetos de nivel inferior que no tengan su propio alcance, pero no se representa como «De la colección» en la API. 

Por lo tanto, recomendamos desactivar esta opción al importar a Omeka, para garantizar que los metadatos no se repliquen fuera de contexto. Puedes consultar cómo desactivar esta opción en tu instalación en la [documentación técnica de ArchivesSpace](https://archivesspace.github.io/tech-docs/architecture/public/){target=_blank}; busca la sección «Herencia». El [archivo que hay que editar se llama `config-defaults.rb`](https://github.com/archivesspace/archivesspace/blob/master/common/config/config-defaults.rb){target=_blank}. 

## Configurar tu instalación de Omeka

El módulo ArchivesSpace no tiene opciones de configuración y no añade ninguna configuración específica del sitio. 

Recomendamos instalar y activar el módulo Hierarchy para optimizar el uso de este conector. Se crearán automáticamente jerarquías que representarán tu sistema de organización de ArchivesSpace y te ayudarán a gestionar los conjuntos de elementos que se crean con cada importación. 

## Importar colecciones

En Omeka S, ve a la sección denominada «Conector de ArchivesSpace» dentro de «Módulos». Al principio verás la pantalla «Importar».

![Las opciones de importación del conector de ArchivesSpace. Los campos se enumeran en el texto a continuación.](modulesfiles/aspace_import.png)

En el formulario de importación, introduce la siguiente información:

* **URL de la API de ArchivesSpace**: La URL completa, incluyendo `https://`. Debe terminar en `/api`.
* **Ruta de destino de ArchivesSpace**: La parte de la URL correspondiente a una colección específica. Tendrá el formato `/repositories/1/resource/1`. 
* **Mantener la jerarquía de la colección**: Una casilla de selección para habilitar la conexión de la importación con el módulo «Jerarquía» de Omeka S. Si no se marca, no se crearán conjuntos de elementos con esta importación, y no se creará ninguna jerarquía a través del [módulo Hierarchy](hierarchy.md). 
* **Nivel de elemento de Omeka**: Elige cuáles de las opciones de objetos de ArchivesSpace se importarán como elementos de Omeka S. Puede elegir «Elementos», «Archivos» o ambos. Si elige «Elementos», los objetos contenedores de nivel superior (incluidos los «Archivos») se importarán como conjuntos de elementos de Omeka. 
* **Eliminar elementos que faltan al actualizar**: Una casilla de selección para cambiar el comportamiento al volver a ejecutar una importación. Si se marca, un elemento creado en una importación anterior pero eliminado en ArchivesSpace se eliminará en Omeka. Si no se marca, las actualizaciones no eliminarán los objetos que ya no existan. 
* **Comentario**: Un campo de texto para dejar un recordatorio para ti mismo o para otros sobre los detalles de esta importación.
* **Plantilla de recursos**: Puede optar por aplicar una plantilla de recursos a todos los elementos y conjuntos de elementos creados por el proceso de importación. Si desea utilizar más de una (por ejemplo, una para los elementos creados y otra para los conjuntos de elementos creados), puede editar los recursos de forma masiva una vez finalizada la importación, utilizando los enlaces de la tabla «Importaciones anteriores» (véase más abajo). 
* **Sitios**: Añade inmediatamente los recursos importados (elementos, conjuntos de elementos y jerarquías) a los siguientes sitios. Este campo carga todos los sitios de forma predeterminada. Para eliminarlos, haz clic en la X; para añadir sitios, haz clic en el campo: aparecerá un menú desplegable. 

Haga clic en el botón «Importar». Si la información anterior se ha introducido correctamente, verá una nueva página con un banner verde en la parte superior que indica el número de tarea de la importación. 

Puede realizar un seguimiento del estado de las importaciones accediendo a la pestaña «Importaciones anteriores» del ArchivesSpace Connector, o en la página [Tareas](../admin/jobs.md) del panel de administración.

!!! Nota
  ¿Tus trabajos se inician pero no se completan? Es posible que tengas que [configurar la ruta de PHP](../configuration.md#php-path) para que tu sistema pueda ejecutar el proceso en segundo plano para crear los elementos.

### Confirmar la importación

Para confirmar que la importación se ha realizado correctamente, puedes hacer clic en cualquiera de los recursos importados (elementos o conjuntos de elementos) para ver su página de vista en el panel de administración. Los elementos se clasificarán automáticamente en los conjuntos de elementos correspondientes, por lo que ambos recursos mostrarán la jerarquía tal y como está. 

![Página de vista de un elemento, en la que se muestra que se encuentra dentro de un conjunto de elementos y que la jerarquía se muestra en la barra lateral derecha.](modulesfiles/aspace_item.png)

Una vez que hayas confirmado que la jerarquía se ha creado correctamente, comprueba que se haya añadido a cada uno de los sitios que especificaste en la configuración de importación. 

A continuación, asegúrate de que la configuración específica de cada sitio para las jerarquías se ajusta a cómo deseas que se muestren tus jerarquías de ArchivesSpace. Probablemente querrás desactivar las páginas de visualización de agrupaciones para que las jerarquías enlacen directamente con los conjuntos de elementos y muestren todos los metadatos importados. Es posible que no quieras mostrar el recuento de elementos si tus importaciones no contienen objetos importados como elementos.  

## Importaciones anteriores

La página «Importaciones anteriores» muestra una tabla con las conexiones existentes de ArchivesSpace, con el **ID de tarea** de la importación, una opción radial para **Deshacer** o **Volver a ejecutar** la importación, la **Colección de ArchivesSpace** del repositorio con un enlace a la salida de la API para compararla (que se muestra como nombre de la colección si se encuentra), cualquier **Comentario** establecido para la importación, el número de **Recursos** importados con un enlace a los resultados de la búsqueda avanzada, la **Fecha** de la importación, el **Estado** de la importación y el **Propietario** que inició la importación.

![Tabla de importaciones anteriores.](modulesfiles/aspace_past.png)

Puedes ver directamente la salida de la API haciendo clic en los enlaces que aparecen debajo de la columna «Colección de ArchivesSpace». Esto puede ayudarte a identificar cualquier error que surja durante el proceso, como la aparición de metadatos de nivel superior en objetos de nivel inferior.

## Actualizar recursos importados

Para actualizar los recursos creados mediante el conector de ArchivesSpace, basta con marcar «Reejecutar» y, a continuación, hacer clic en «Enviar» en la página «Importaciones anteriores». Los recursos se actualizarán, no se volverán a importar. Esto te permite utilizar el conector para sincronizar datos entre las instalaciones de ArchivesSpace y Omeka S. Puedes volver a ejecutar más de una importación a la vez. 

No puedes modificar la configuración de importación al volver a ejecutar una importación. 

## Deshacer una importación

Puede ver las conexiones existentes en la página «Importaciones anteriores». Para deshacer una importación completada y eliminar todos los recursos asociados, cambie el botón de opción de cada importación que desee deshacer y haga clic en el botón «Enviar». Esto también eliminará la jerarquía que se creó para la importación. 