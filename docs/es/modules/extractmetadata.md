# Extraer metadatos

El [módulo «Extract Metadata»](https://omeka.org/s/modules/ExtractMetadata){target=_blank} permite a los administradores del sitio extraer los metadatos incrustados de los archivos multimedia. 

El módulo añade una nueva pestaña «Extraer metadatos» a cada página de medios, lo que te permitirá extraer manualmente cualquier metadato incrustado que se encuentre en el archivo. También añade un campo «Extraer metadatos» a la página de edición por lotes. Cuando está habilitado, funciona automáticamente con los archivos recién subidos. 

Un buen flujo de trabajo consiste en instalar y configurar el módulo, extraer por lotes los metadatos de los archivos existentes en su base de datos, asignarlos a los campos de metadatos multimedia que haya elegido y, a continuación, simplemente dejar que el módulo continúe extrayendo metadatos de los archivos en el futuro.

## Configuración del módulo

Al configurar el módulo, puede:

- Ver y habilitar/deshabilitar extractores: puede elegir entre cinco extractores diferentes, incluidos ExifTool, Tika, Exif, getID3 y OHMS (véase más abajo).
- Ver y habilitar/deshabilitar mapeadores: puede seleccionar no habilitar ningún mapeador o habilitar JSON Pointer.
- Configurar la tabla de correspondencias de metadatos para el mapeador JSON Pointer (si está habilitado). Si decide utilizar el mapeador JSON Pointer, deberá definir la tabla de correspondencias de metadatos. 
 1. Haga clic en el botón «Añadir mapa +».
    1. Seleccione el recurso, el extractor y la propiedad en los menús desplegables.
    1. Proporcione un puntero con el formato de un puntero JSON tal y como se define en el [estándar IETF](https://datatracker.ietf.org/doc/html/rfc6901){target=_blank}.
    1. Si desea sustituir los valores de metadatos a través de este puntero, asegúrese de marcar la casilla situada a la derecha de estos campos.

Cuando haya terminado de configurar el módulo, haga clic en el botón «Enviar» situado en la esquina superior derecha de la pantalla.

![Vista de configuración del módulo «Extract Metadata» con la tabla de correspondencias del puntero JSON y el botón «Submit» indicado con una flecha verde azulada](../modules/modulesfiles/extractmetadata_config.png)

## Añadir archivos multimedia

Una vez que el módulo esté configurado y los extractores estén habilitados, actuarán sobre cada archivo a medida que lo añadas a un elemento o como un activo. El módulo realizará automáticamente lo siguiente:

- Extraerá los metadatos del archivo utilizando los extractores habilitados
- Guardará los metadatos como texto junto con el contenido multimedia
- Asignará los metadatos a los valores del contenido multimedia si hay un asignador habilitado.

Puede ver los metadatos extraídos en las páginas de los archivos multimedia, en la pestaña «Extraer metadatos».

## Edición de archivos multimedia y elementos

Un usuario puede editar los metadatos de los archivos multimedia adjuntos a los elementos editando directamente el elemento individual o utilizando las funciones de edición por lotes.

### Edición de elementos
Al editar un medio o elemento, el usuario puede elegir entre varias acciones, a las que se accede a través de la pestaña «Extraer metadatos» en la vista de edición del elemento. Seleccione una de las cuatro opciones del menú desplegable.

- Actualizar metadatos: (re)extraer metadatos de los archivos
- Actualizar y asignar metadatos: (re)extraer metadatos de los archivos y asignar los metadatos a los valores de los recursos
- Asignar metadatos: Asignar los metadatos extraídos a los valores de los recursos
- Eliminar metadatos: Eliminar los metadatos extraídos.

![Vista de edición de elementos con la pestaña «Extraer metadatos» activa y el menú desplegable de acciones abierto](../modules/modulesfiles/extractmetadata_actions.png)

Asegúrate de hacer clic en el botón «Guardar» situado en la esquina superior derecha de la pantalla para ejecutar la acción seleccionada.

### Edición por lotes

En la pantalla de exploración de elementos, selecciona los elementos que deseas editar por lotes. En la página de edición por lotes, puedes seleccionar cualquiera de las cuatro opciones de acción del menú desplegable «Extraer metadatos». Esto aplicará la acción a todos los elementos seleccionados para su inclusión en la edición por lotes. 

![Vista de edición por lotes con el menú desplegable «Extraer metadatos» abierto](../modules/modulesfiles/extractmetadata_batchedit.png)

## Extractores

Los extractores extraen metadatos de los archivos. Ten en cuenta que los extractores deben estar habilitados en la página de configuración del módulo. Este módulo incluye cuatro extractores, pero se pueden añadir más según tus necesidades. Es posible que tu servidor ya sea compatible con estas utilidades, pero si tienes problemas, comprueba que la dependencia esté instalada.

### ExifTool

Se utiliza para extraer muchos tipos de metadatos de muchos tipos de archivos. Requiere la aplicación de línea de comandos [ExifTool](https://exiftool.org/){target=_blank}.

### Exif

Se utiliza para extraer metadatos EXIF que suelen encontrarse en archivos JPEG y TIFF. Requiere la extensión [exif](https://www.php.net/manual/en/book.exif.php){target=_blank} de PHP.

### getID3

Se utiliza para extraer muchos tipos de metadatos de muchos tipos de archivos. Utiliza la biblioteca PHP [getID3](https://github.com/JamesHeinrich/getID3){target=_blank}, que viene incluida con este módulo.
 
### Tika

Se utiliza para extraer muchos tipos de metadatos de muchos tipos de archivos. Requiere el kit de herramientas de análisis de contenido [Apache Tika](https://tika.apache.org/){target=_blank}. Debe tener instalado Java y la ruta al archivo `tika-app-*.jar` debe configurarse en `config/module.config.php` bajo `[extract_metadata_extractor_config][tika][jar_path]`.

### OHMS

Añadido por el [módulo OHMS Embed](ohmsembed.md). Se utiliza para extraer metadatos generados por el Oral History Metadata Synchronizer Editor y contenidos en el archivo XML generado por ese sistema. El extractor OHMS puede utilizar punteros JSON para asignar los metadatos a los recursos de Omeka. Para obtener más información, consulte el [módulo OHMS Embed](ohmsembed.md). 

## Mapeadores

Los mapeadores asignan los metadatos extraídos a los valores de los recursos. Tenga en cuenta que un mapeador debe estar habilitado en la página de configuración del módulo. Este módulo incluye un mapeador. La mejor práctica para utilizar este módulo con otros mapeadores sería bifurcar el código del módulo; consulte [nuestra documentación para desarrolladores para obtener más detalles](https://omeka.org/s/docs/developer/modules/){target=_blank}.

### Punteros JSON

Puede asignar los metadatos extraídos a las propiedades de metadatos de los medios o elementos utilizando [punteros JSON](https://datatracker.ietf.org/doc/html/rfc6901){target=_blank}. Debe definir su propia tabla de correspondencias de metadatos en la página de configuración del módulo, en la pestaña «Tabla de correspondencias de punteros JSON».

Es posible que desee extraer primero los metadatos de unos pocos archivos y ver a qué información se puede apuntar, para luego probar algunas opciones sobre cuál es la mejor forma de asignarlos.

Un ejemplo habitual es asignar la fecha de creación de un archivo JPEG a la propiedad «Date Created» de Dublin Core. El puntero apunta al valor `DateTimeOriginal` en la salida de metadatos Exif, que puede ver si va a un elemento multimedia y consulta la pestaña «Extract metadata». 

Configure el mapeador de la siguiente manera:
+ Recurso: [Medio o Elemento]
+ Extractor: «Exif»
+ Puntero: `/EXIF/DateTimeOriginal`
+ Propiedad: «Dublin Core: Fecha de creación»
+ Reemplazar valores: [marcado o desmarcado].

![Vista de configuración del módulo «Extract Metadata» con la tabla de correspondencias de JSON Pointer y el botón de enviar indicado por una flecha verde azulada](../modules/modulesfiles/extractmetadata_config.png)

Una vez guardada esta asignación, ejecute la acción «Asignar metadatos» en un archivo o en un lote y, si su archivo JPEG incluye `DateTimeOriginal`, el medio debería tener ahora un valor de «Fecha de creación».

## Integración con IIIF Presentation

Este módulo puede proporcionar automáticamente metadatos precisos de ancho, alto y duración para los recursos de contenido IIIF publicados por el [módulo IIIF Presentation](iiifpresentation.md). Esto resulta útil para los visores IIIF que requieren una validación estricta según la especificación IIIF. Ten en cuenta que esto solo está disponible si los metadatos ya han sido extraídos por el extractor ExifTool.
