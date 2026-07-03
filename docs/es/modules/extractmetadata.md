# Extraer metadatos

El [módulo «Extraer metadatos»](https://omeka.org/s/modules/ExtractMetadata){target=_blank} permite a los administradores del sitio extraer los metadatos incrustados de los archivos multimedia. 

El módulo añade una nueva pestaña «Extraer metadatos» a cada página multimedia, lo que te permitirá extraer manualmente cualquier metadato incrustado que se encuentre en el archivo. También añade un campo «Extraer metadatos» a la página de edición por lotes. Cuando está activado, funciona automáticamente con los archivos recién subidos. 

Un buen flujo de trabajo consiste en instalar y configurar el módulo, extraer de forma masiva los metadatos de los archivos existentes en la base de datos, asignarlos a los campos de metadatos multimedia elegidos y, a continuación, dejar que el módulo siga extrayendo metadatos de los archivos en el futuro.

## Configuración del módulo

Al configurar el módulo, puedes:

- Ver y activar/desactivar extractores: puedes elegir entre cinco extractores diferentes, entre los que se incluyen ExifTool, Tika, Exif, getID3 y OHMS (véase más abajo).
- Ver y activar/desactivar mapeadores: puedes optar por no activar ningún mapeador o por activar JSON Pointer.
- Configurar la tabla de correspondencias de metadatos para el mapeador JSON Pointer (si está habilitado). Si decides utilizar el mapeador JSON Pointer, tendrás que definir la tabla de correspondencias de metadatos. 
 1. Haz clic en el botón «Añadir mapa +».
    1. Selecciona el recurso, el extractor y la propiedad en los menús desplegables.
    1. Introduzca un puntero con el formato definido por el [estándar IETF](https://datatracker.ietf.org/doc/html/rfc6901){target=_blank}.
    1. Si deseas sustituir los valores de metadatos mediante este puntero, asegúrate de marcar la casilla situada a la derecha de estos campos.

Cuando hayas terminado de configurar el módulo, haz clic en el botón «Enviar» situado en la esquina superior derecha de la pantalla.

![Vista de configuración del módulo «Extract Metadata» con la tabla de correspondencias del puntero JSON y el botón «Enviar» indicado con una flecha de color verde azulado](../modules/modulesfiles/extractmetadata_config.png)

## Añadir archivos multimedia

Una vez configurado el módulo y habilitados los extractores, estos actuarán sobre cada archivo a medida que lo añadas a un elemento o como recurso. El módulo realizará automáticamente lo siguiente:

- Extraerá los metadatos del archivo utilizando los extractores habilitados
- Guardará los metadatos como texto junto con el archivo multimedia
- Asignará los metadatos a los valores del archivo multimedia si hay un asignador habilitado.

Puedes ver los metadatos extraídos en las páginas de los archivos multimedia, en la pestaña «Extraer metadatos».

## Edición de archivos multimedia y elementos

Un usuario puede editar los metadatos de los archivos multimedia asociados a los elementos editando directamente el elemento concreto o utilizando las funciones de edición por lotes.

### Edición de elementos
Al editar un archivo multimedia o un elemento, el usuario puede elegir entre varias acciones, a las que se accede a través de la pestaña «Extraer metadatos» en la vista de edición del elemento. Selecciona una de las cuatro opciones del menú desplegable.

- Actualizar metadatos: (re)extraer metadatos de los archivos
- Actualizar y asignar metadatos: (re)extraer metadatos de los archivos y asignarlos a los valores de los recursos
- Asignar metadatos: Asignar los metadatos extraídos a los valores de los recursos
- Eliminar metadatos: Eliminar los metadatos extraídos.

![Vista de edición de un elemento con la pestaña «Extraer metadatos» activa y el menú desplegable de acciones abierto](../modules/modulesfiles/extractmetadata_actions.png)

Asegúrate de hacer clic en el botón «Guardar» situado en la esquina superior derecha de la pantalla para ejecutar la acción seleccionada.

### Edición por lotes

En la pantalla «Explorar elementos», selecciona los elementos que deseas editar por lotes. En la página de edición por lotes, puedes seleccionar cualquiera de las cuatro opciones de acción del menú desplegable «Extraer metadatos». Esto aplicará la acción a todos los elementos seleccionados para su inclusión en la edición por lotes. 

![Vista de edición por lotes con el menú desplegable «Extraer metadatos» abierto](../modules/modulesfiles/extractmetadata_batchedit.png)

## Extractores

Los extractores extraen metadatos de los archivos. Ten en cuenta que los extractores deben estar habilitados en la página de configuración del módulo. Este módulo incluye cuatro extractores, pero se pueden añadir más en función de tus necesidades. Es posible que tu servidor ya sea compatible con estas utilidades, pero si tienes problemas, comprueba que la dependencia esté instalada.

### ExifTool

Se utiliza para extraer muchos tipos de metadatos de muchos tipos de archivos. Requiere la aplicación de línea de comandos [ExifTool](https://exiftool.org/){target=_blank}.

### Exif

Se utiliza para extraer metadatos EXIF que suelen encontrarse en archivos JPEG y TIFF. Requiere la extensión [exif](https://www.php.net/manual/en/book.exif.php){target=_blank} de PHP.

### getID3

Se utiliza para extraer muchos tipos de metadatos de diversos tipos de archivos. Utiliza la biblioteca PHP [getID3](https://github.com/JamesHeinrich/getID3){target=_blank}, que se incluye con este módulo.
 
### Tika

Se utiliza para extraer diversos tipos de metadatos de diversos tipos de archivos. Requiere el kit de herramientas de análisis de contenido [Apache Tika](https://tika.apache.org/){target=_blank}. Es necesario tener instalado Java y configurar la ruta al archivo `tika-app-*.jar` en `config/module.config.php`, en la sección `[extract_metadata_extractor_config][tika][jar_path]`.

### OHMS

Añadido por el [módulo OHMS Embed](ohmsembed.md). Se utiliza para extraer los metadatos generados por el Oral History Metadata Synchronizer Editor y contenidos en el archivo XML generado por dicho sistema. El extractor OHMS puede utilizar punteros JSON para asignar los metadatos a los recursos de Omeka. Para obtener más información, consulta el [módulo OHMS Embed](ohmsembed.md). 

## Mapeadores

Los mapeadores asignan los metadatos extraídos a los valores de los recursos. Ten en cuenta que es necesario habilitar un mapeador en la página de configuración del módulo. Este módulo incluye un mapeador. La mejor práctica para utilizar este módulo con otros mapeadores sería crear una bifurcación del código del módulo; consulta [nuestra documentación para desarrolladores para obtener más detalles](https://omeka.org/s/docs/developer/modules/){target=_blank}.

### Punteros JSON

Puedes asignar los metadatos extraídos a las propiedades de metadatos de los archivos multimedia o de los elementos utilizando [punteros JSON](https://datatracker.ietf.org/doc/html/rfc6901){target=_blank}. Debes definir tu propia tabla de correspondencias de metadatos en la página de configuración del módulo, en la pestaña «Tabla de correspondencias de punteros JSON».

Quizá te interese extraer primero los metadatos de unos cuantos archivos y ver a qué información se puede apuntar, para luego probar algunas opciones sobre cuál es la mejor forma de asignarlos.

Un ejemplo habitual es asignar la fecha de creación de un archivo JPEG a la propiedad «Fecha de creación» de Dublin Core. El puntero apunta al valor `DateTimeOriginal` de los metadatos Exif, que puedes ver si accedes a un elemento multimedia y consultas la pestaña «Extraer metadatos». 

Configura el mapeador de la siguiente manera:
+ Recurso: [Multimedia o Elemento]
+ Extractor: «Exif»
+ Puntero: `/EXIF/DateTimeOriginal`
+ Propiedad: «Dublin Core: Fecha de creación»
+ Reemplazar valores: [marcado o desmarcado].

![Vista de configuración del módulo «Extraer metadatos» con la tabla de correspondencias de punteros JSON y el botón de envío indicado por una flecha verde azulada](../modules/modulesfiles/extractmetadata_config.png)

Una vez guardada esta asignación, ejecuta la acción «Asignar metadatos» en un solo archivo o por lotes y, si tu archivo JPEG incluye `DateTimeOriginal`, el recurso multimedia debería tener ahora un valor de «Fecha de creación».

## Integración con IIIF Presentation

Este módulo puede proporcionar automáticamente metadatos precisos de anchura, altura y duración para los recursos de contenido IIIF publicados por el [módulo IIIF Presentation](iiifpresentation.md). Esto resulta útil para los visores IIIF que requieren una validación estricta según la especificación IIIF. Ten en cuenta que esto solo está disponible si los metadatos ya han sido extraídos por el extractor ExifTool.
