# OHMS Embed

El [módulo OHMS Embed](https://omeka.org/s/modules/OhmsEmbed/){target=_blank} permite a los administradores del sitio añadir objetos del [Oral History Metadata Synchonizer](https://www.oralhistoryonline.org/){target=_blank} como contenido multimedia a los elementos de Omeka S.

Este módulo añadirá un visor OHMS a los lugares donde se puede incrustar contenido multimedia, lo que permitirá a los usuarios ver índices, transcripciones y/o traducciones de vídeos y audios mientras se reproducen. 

![Visualización pública de un visor OHMS en una página de Omeka, con un pequeño vídeo en la parte superior, una transcripción a la izquierda y un índice a la derecha.](modulesfiles/ohmsembed_public.png)

Los archivos XML de OHMS se pueden subir a los elementos de Omeka como archivos multimedia. Sin este módulo, aparecerán como archivos adjuntos disponibles para su descarga. Con este módulo instalado y activado, se mostrarán como reproducciones de vídeo/audio con transcripciones, índices, etc. 

El reproductor multimedia OHMS puede aparecer en las páginas de elementos y de archivos multimedia, y puede colocarse en las páginas del sitio de Omeka mediante el bloque de página «Incrustar multimedia».

Preparar tu instalación de Omeka para recibir archivos OHMS puede requerir algo de trabajo e incluye algunos pasos opcionales para mejorar el proceso. Lee detenidamente los siguientes pasos antes de realizar ninguna acción, para que puedas configurar tu instalación correctamente en función de tus necesidades específicas. 

## Crear archivos OHMS

Para crear paquetes OHMS con tus entrevistas, debes utilizar la aplicación OHMS disponible en el [sitio web de OHMS](https://www.oralhistoryonline.org/){target=_blank}, lo que requiere solicitar una cuenta gratuita y trabajar con la aplicación web. 

La aplicación OHMS generará archivos XML que contienen toda la información creada en dicha herramienta. 

Los archivos OHMS incluyen un enlace al archivo de vídeo o audio que se presentará junto con el índice y los textos. **No** incluyen el archivo multimedia en sí. Este debe estar alojado en otro lugar. Entre las opciones de alojamiento se incluyen YouTube, Vimeo, SoundCloud y otros proveedores de alojamiento de audio y vídeo. 

### Aloja tus archivos multimedia en Omeka (opcional)

Puedes alojar tus archivos dentro de tu instalación de Omeka, como archivos multimedia añadidos a los elementos, y luego proporcionar las URL de esos archivos a los paquetes OHMS que generes. 

Esto significa que debes: 

- crear elementos de Omeka incorporando tus archivos multimedia, ya sea mediante una subida manual o un proceso de incorporación masiva
- recopilar las URL de tus archivos multimedia del servidor de Omeka
- proporcionar esas URL a la aplicación OHMS
- exportar los archivos XML que se van a generar a Omeka
- y, a continuación, adjuntar esos archivos XML a los elementos respectivos que ya hayas creado.

Las ventajas de este enfoque incluyen la simplicidad del autoalojamiento y el control sobre tu propiedad intelectual, además de las características de los datos enlazados (Linked Data), los tipos de datos y los vocabularios controlados que puedes utilizar para añadir metadatos específicos de los archivos multimedia directamente en Omeka.

Una vez que hayas subido tu archivo de audio o vídeo a un elemento, tendrás que localizar la URL directa del archivo. Ve a tu elemento y, a continuación, haz clic en el archivo multimedia que desees utilizar. En la descripción situada en la parte derecha de la pantalla, busca la sección «Derivados del archivo». El enlace «Original» será el que debas proporcionar a la aplicación OHMS. Puedes hacer clic con el botón derecho del ratón para copiar esta URL.

![Panel derecho de la descripción del archivo multimedia, con la sección «Derivados del archivo» resaltada, donde se muestra el enlace al archivo «Original».](modulesfiles/ohmsembed_original.png)

En la aplicación OHMS, utiliza «Host» como opción de «Media File Host». Introduce la URL del archivo original de la instalación de Omeka S como «Media URL». 

![Imagen de la pantalla del Editor de metadatos de OHMS, centrada en la sección «Media and Technical», que muestra la opción «Host» seleccionada entre las disponibles y la URL de un archivo original en la propiedad «Media URL»](modulesfiles/ohmsembed_ohms_mediahost.png)

Cuando el paquete de historia oral esté completo, exporta tu archivo XML de OHMS como de costumbre.

![Vista de registro de OHMS con la opción «Exportar XML» disponible.](../modules/modulesfiles/ohmsembed_ohms_xmlexport.png)

Cuando vuelvas al elemento correspondiente de Omeka S y subas el archivo XML como contenido multimedia, asegúrate de establecer dicho archivo como contenido multimedia principal del elemento.

## Añadir archivos OHMS a Omeka

El editor de OHMS genera un archivo XML que contiene los metadatos, el índice y la transcripción que acompañan a la historia oral. El archivo debe añadirse a un elemento de Omeka S como archivo multimedia para que aparezca el visor de OHMS. 

Por lo general, el formato XML no se encuentra entre los tipos de archivos multimedia y las extensiones de archivo permitidos en una instalación de Omeka S. Primero tendrás que habilitarlo. 

### Habilitar la subida de archivos XML

Ve a la página de Configuración de tu instalación y navega hasta la sección Seguridad. 

- Añade `text/xml` a la lista de **Tipos de medios permitidos**.
- Añade `xml` a la lista de **Extensiones de archivo permitidas**. 

![Vista de la configuración de seguridad para **Tipos de medios permitidos** y **Extensiones de archivo permitidas** con XML añadido a las listas.](../modules/modulesfiles/ohmsembed_xmlsettings.png)

Cuando hayas terminado, haz clic en el botón «Guardar» situado en la esquina superior derecha de la pantalla.

### Configurar la extracción de metadatos (opcional)

Mediante el módulo [Extract Metadata](extractmetadata.md), puedes rellenar los campos de metadatos de tus elementos de Omeka con información de los archivos XML: título, fecha, duración, fuente, etc. 

En primer lugar, actualiza el módulo «Extract Metadata» a la versión 1.2.0 o posterior. Esto añadirá un extractor específico de OHMS a las herramientas disponibles (la herramienta de extracción de OHMS forma parte, de hecho, de este módulo, y no aparecerá si OHMS Embed no está instalado y activado). 

Ve a la página «Módulos», comprueba que esté actualizado y activado y, a continuación, haz clic en el botón «Configurar». Verás una lista de herramientas de extracción disponibles, entre las que debería figurar «OHMS». Marca la casilla para asegurarte de que está habilitado y, a continuación, guarda la página. 

![Página de configuración del módulo «Extract Metadata» con «OHMS» disponible y habilitado.](modulesfiles/ohmsembed_extractmetadata.png)

A continuación, para asignar la información de los metadatos XML a tus elementos de Omeka, activa «JSON Pointer» en la pestaña «Mappers». Después, ve a la pestaña «JSON Pointer crosswalk» para configurar los campos de metadatos, ya sea para el archivo multimedia o para el elemento. Los metadatos extraídos se generarán como texto sin formato. Te recomendamos que consultes un paquete OHMS de ejemplo y compruebes qué campos se están utilizando. 

También te sugerimos que utilices una plantilla de recursos para tus archivos OHMS, lo que te ayudará a planificar los campos de metadatos seleccionados.

![Página de configuración del módulo «Extract Metadata» en la que se muestra la pestaña «JSON Pointer crosswalk». Se enumeran varios punteros OHMS: por ejemplo, el «/id» de OHMS mapeado al «Identificador» de Dublin Core del recurso multimedia.](modulesfiles/ohmsembed_EMcrosswalk.png)

A continuación se muestra una lista de posibles punteros generados por la aplicación OHMS (asegúrate de incluir la barra en la interfaz de Omeka):

| Metadatos | Puntero |
|-----------------------------|-----------------------------|
| Fecha de la entrevista | `/date` |
| Fecha (formato no preferido) | `/date_nonpreferred_format` |
| Título | `/title` |
| Resumen | `/description` |
| Tema | `/subject` |
| Palabras clave | `/keyword` |
| Entrevistado | `/interviewee` |
| Entrevistador | `/interviewer` |
| Idioma | `/language` |
| Idioma de la traducción    | `/transcript_alt_lang` |
| Tipo | `/type` |
| Formato | `/format` |
| Declaración de derechos | `/rights` |
| Declaración de uso | `/usage` |
| Número de acceso | `/accession` |
| Duración | `/duration` |
| ID de la colección | `/collection_id` |
| Nombre de la colección | `/collection_name` |
| Enlace a la colección | `/collection_link` |
| ID de la serie | `/series_id` |
| Serie (nombre) | `/series_name` |
| Enlace a la serie | `/series_link` |
| Organización | `/repository` |
| URL de la organización | `/repository_url` |
| Agradecimientos | `/funding` |
| Notas del usuario | `/user_notes` |
| Archivo multimedia | `/file_name` |
| ID del archivo multimedia | `/media_id` |
| URL del archivo multimedia | `/media_url` |
| Formato del archivo multimedia | `/fmt` |
| Ubicación del XML de OHMS | `/xmllocation` |
| Nombre del archivo XML de OHMS | `/xmlfilename` |
| Versión de OHMS | `/version` |
| ID del registro en el CMS | `/cms_record_id` |
| ID del registro | `/id` |
| Fecha del registro | `/dt` |
| Rel | `/rel` |

### Subir archivos XML

!!! Nota
  Si utilizas el módulo [Extract Text](extracttext.md), es posible que desees desactivarlo antes de subir un archivo XML. El contenido de estos archivos no es legible para los usuarios. Si deseas que el contenido de tus textos de OHMS (transcripciones, traducciones, índices, etc.) sea buscable por texto en tu sitio de Omeka, puedes extraer el texto con este módulo; sin embargo, todo el código XML quedará visible como metadatos en tus elementos y archivos multimedia. Puedes ocultar este campo utilizando el [módulo «Ocultar propiedades»](https://omeka.org/s/modules/HideProperties/){target=_blank}, lo que afectará a este campo en todos los recursos. 

Puedes subir tus archivos XML de OHMS de forma individual a los elementos desde tu ordenador, o bien importar por lotes archivos OHMS a elementos nuevos o existentes mediante la [importación CSV](csvimport.md). 

!!! Nota
  Omeka S no podrá generar una miniatura del elemento a partir de archivos OHMS. Quizá te interese añadir una [miniatura personalizada](https://omeka.org/s/docs/user-manual/content/items/#thumbnail) desde la pestaña «Avanzado» de la interfaz de edición del elemento.

#### Importación masiva de archivos OHMS

Si te interesa añadir muchos objetos OHMS a tu instalación de Omeka S de una sola vez, puedes utilizar la [importación CSV](csvimport.md). También puedes utilizar la [carga lateral de archivos](filesideload.md) para alojar los archivos XML que vas a importar, si es necesario.

Sube los archivos XML a tu servicio de alojamiento o al directorio de carga lateral de archivos. A continuación, crea una hoja de cálculo que enumere las URL de los archivos y los metadatos que deseas importar. Si tienes previsto extraer todos los metadatos de los archivos XML, puedes incluir únicamente una columna con las URL de los archivos.

Si ya has creado elementos de Omeka S para [alojar archivos multimedia de audio y vídeo](#host-your-media-in-omeka-optional), busca un identificador único de elemento de Omeka para adjuntar los archivos correspondientes (como el ID interno de Omeka) y añade esos ID a las filas de tu hoja de cálculo. A continuación, utiliza el módulo de importación CSV para [importar archivos multimedia](https://omeka.org/s/docs/user-manual/modules/csvimport/#import-media).

Si aún no dispone de elementos de Omeka de destino, puede utilizar la importación CSV para crear nuevos elementos a partir de sus archivos XML. 

#### Extracción masiva desde archivos OHMS

Tenga en cuenta que no es necesario ejecutar «Extraer metadatos» ni «Extraer texto» en el momento de la importación. Quizá prefieras desactivar los módulos, importar primero tus archivos XML y, a continuación, extraer de forma masiva el texto y los metadatos. 

Selecciona varios elementos en la página de exploración de elementos de la interfaz de administración, elige «Editar seleccionados» en el menú desplegable «Acciones por lotes» y, a continuación, busca el campo «Extraer metadatos» en la lista de opciones. Selecciona «Actualizar y asignar metadatos». Repite el proceso, busca «Extraer texto» en la lista y selecciona «Actualizar texto».

![Actualiza y asigna metadatos de forma masiva para las historias orales una vez que se hayan subido.](modulesfiles/ohmsembed_EMbatch.png)

## Incrustar el visor OHMS

Una vez añadidos los archivos XML de OHMS a tus elementos de Omeka S, ya estás listo para mostrarlos en tus sitios web. 

### Visor OHMS en las páginas de elementos y de medios

El visor OHMS se cargará en [las páginas de recursos (elementos y archivos multimedia)](../sites/site_theme.md#configure-resource-pages) si tu tema está configurado para mostrar el bloque «Incrustaciones multimedia» en las páginas de elementos y el bloque «Representación multimedia» en las páginas de archivos multimedia. 

![Configuración de la página de recursos con el bloque «Incrustaciones multimedia» en la parte superior de la página de elementos.](modulesfiles/ohmsembed_itemRes.png)

!!! Nota
  Actualmente, el bloque de galería Lightbox no muestra el visor OHMS cuando se detecta un archivo XML de OHMS. Para que se muestre OHMS, **debe** utilizarse el bloque «Incrustaciones multimedia» o «Representación multimedia». Es posible que tu sitio web necesite alguna reconfiguración para incorporar esto sin problemas, en lugar de incluir tanto el bloque Lightbox como el de «Media», lo que provocaría que otros archivos multimedia se representaran dos veces. 

### Visor OHMS en las páginas del sitio

Puedes utilizar el [«bloque de página “Incrustación de medios”»](https://omeka.org/s/docs/user-manual/sites/site_pages/#media-embed) para colocar el visor OHMS directamente en las páginas del sitio. 

![Edición de página que muestra el bloque «Incrustación de medios» con su configuración.](modulesfiles/ohmsembed_mediaEmbed.png)

Debes seleccionar el archivo XML como medio adjunto; no elijas el vídeo o el audio que hayas importado al mismo elemento. Asegúrate también de que la opción «Incrustar multimedia» esté seleccionada en el menú desplegable «Visualización multimedia».

![Vista de la página con el bloque «Incrustar multimedia», con el visor OHMS en la primera columna y un ejemplo de código HTML en la segunda columna](modulesfiles/ohmsembed_public_mediaembed.png)

El visor OHMS se mostrará como una columna alta y estrecha si la disposición está configurada en «Vertical», y se mostrará a ancho completo si la disposición está configurada en «Horizontal». 

![Vista de elemento de Omeka S con el visor OHMS](modulesfiles/ohmsembed_public_itemshow.png)

#### Uso del visor OHMS

El visor OHMS de Omeka S cuenta con varios controles públicos: un botón para alternar entre el índice y la transcripción y/o la traducción, si dichos elementos están disponibles; un icono de información que muestra los metadatos del contenido multimedia; y una opción para pasar a la vista de pantalla completa.

![Controles de la interfaz pública del visor OHMS de Omeka S que muestran un selector entre índice, transcripción y traducciones, así como el icono «i» y el botón de pantalla completa](../modules/modulesfiles/ohmsembed_public_controllers.png)
