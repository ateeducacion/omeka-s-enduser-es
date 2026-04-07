# Extraer texto

El [módulo «Extract Text»](https://omeka.org/s/modules/ExtractText){target=_blank} extrae texto de los archivos para que sean consultables y legibles por máquinas.

Cuando está activado, «Extraer texto» añade un nuevo vocabulario de metadatos con un campo, de tipo de datos textual, tanto a nivel de elemento como a nivel de medio, con el nombre «texto extraído» y el slug `extracttext:extracted_text`. Por defecto, está configurado como público en las páginas de vista de elementos.

Añade una pestaña «Extraer texto» a cada página de edición de elementos, donde puedes actualizar o eliminar el texto extraído. También añade una opción de edición por lotes para extraer o borrar texto de los archivos existentes en tu base de datos. Cuando está activo, extraerá automáticamente el texto de los archivos subidos en [Importación CSV](../modules/csvimport.md).

Cuando el módulo está desactivado, los elementos con texto en los campos de «texto extraído» no se modificarán; el campo seguirá mostrándose.

Si tienes más de un archivo adjunto a un elemento, el texto extraído acumulado aparecerá en un único campo a nivel del elemento, en el orden en que se añaden los archivos. El texto extraído de los archivos nuevos se añadirá al final del campo.

## Requisitos del sistema

Los formatos de archivo potencialmente compatibles con este módulo son:

- doc
- docx
- html
- odt
- pdf
- rtf
- txt
- xml
- bmp, gif, jp2, jpg, png, tiff y webp (con Tesseract).

Debe tener los extractores necesarios disponibles en su servidor para que el módulo funcione con estos tipos de archivo. Para ver qué tipos de archivo se pueden procesar en su instalación, vaya a la entrada «Extract Text» en Módulos y haga clic en el botón «Configurar». Esto cargará una tabla que le mostrará qué extractores están disponibles en su servidor.

## Configuración

![La página de configuración que muestra la mayoría de los extractores disponibles, Tesseract ejecutándose en segundo plano y dos extractores desactivados.](../modules/modulesfiles/extracttext_configure.png)

En esta página puede ver qué extractores están instalados, activos y ejecutándose en segundo plano. Puede activar o desactivar extractores específicos y configurarlos para que se ejecuten solo como tareas en segundo plano, lo que puede resultar más eficiente en su servidor. 

Tesseract se ejecuta solo en segundo plano, ya que puede requerir un gran volumen de procesamiento. Dependiendo del tamaño de tus otros archivos, como los PDF, es posible que también desees configurar otros extractores para que se ejecuten solo en segundo plano. Los extractores de «solo segundo plano» no se ejecutarán cuando se suban nuevos archivos multimedia, pero sí se ejecutarán con las tareas de importación de CSV y al utilizar herramientas de edición por lotes.

Cuando la opción «Solo en segundo plano» no está marcada, el extractor se ejecutará al subir un archivo, al hacer clic en «Actualizar texto» y al hacer clic en «Actualizar texto (en segundo plano)».

Los extractores necesarios son:

- **catdoc**, utilizado para extraer texto de archivos DOC y RTF.
- **docx2txt**, utilizado para extraer texto de archivos DOCX.
- **lynx**, utilizado para extraer texto de archivos HTML.
- **odt2txt**, utilizado para extraer texto de archivos ODT.
- **pdftotext**, utilizado para extraer texto de archivos PDF.
- **filegetcontents**, utilizado para extraer texto de archivos TXT.
- **domdocument**, utilizado para extraer texto de archivos XML.
- **tesseract**, utilizado para reconocer caracteres de texto a partir de archivos de imagen. 

Tesseract admite los siguientes archivos de imagen si se compila con las bibliotecas necesarias:

- BMP (image/bmp)
- GIF (image/gif)
- JP2 (image/jp2)
- JPG (image/jpeg)
- PNG (image/png)
- TIFF (image/tiff)
- WEBP (image/webp).


!!! nota
  Ten en cuenta que algunas extensiones de archivo o tipos de medios pueden estar deshabilitados en la [configuración global](../admin/settings.md#security) de tu instalación. El módulo no añade ni elimina automáticamente ningún archivo en función de la activación o de tu configuración. 

	Es posible que tenga que añadir manualmente nuevas extensiones de archivo y tipos de medios con una cuenta de administrador si está actualizando el módulo para añadir nuevas funciones de extracción, como XML. Por ejemplo, añada «text/xml» al cuadro de tipos de medios y añada «xml» al cuadro de extensiones de archivo. 

Si no tiene una o varias de las herramientas de extracción deseadas instaladas en su servidor, consulte con su servicio de alojamiento o con el administrador de su servidor local.

## Extraer texto de los archivos multimedia

Para extraer texto de los archivos multimedia, puede elegir varias acciones:

- Extraer manualmente el texto de un archivo multimedia, cuando se suba el archivo o más tarde desde su pantalla de edición
- Extraer manualmente el texto de todos los archivos multimedia asociados a un elemento, desde su pantalla de edición
- Extraer por lotes el texto de todos los archivos multimedia asociados a varios elementos, desde la página de edición por lotes
- Extraer texto por lotes de una [importación CSV](../modules/csvimport.md) que contenga archivos multimedia subidos.

La función «Extraer texto» está configurada para ejecutarse automáticamente cuando se sube un nuevo archivo multimedia en cualquier lugar, ya sea mediante una importación CSV o subiendo uno o más archivos multimedia a un elemento. Es posible que la extracción de texto no se ejecute con otros tipos de importaciones o conectores añadidos por módulos. 

![Un elemento en modo de edición, mostrando el campo extracttext:extracted_text con su contenido.](../modules/modulesfiles/extracttext_item_field.png)

Puedes borrar o volver a ejecutar manualmente el texto extraído editando el elemento o el archivo multimedia. Para cambiar la salida automática, ve a la pestaña «Extract Text» en un elemento o en un archivo multimedia específico.

![Un elemento en modo de edición, en la pestaña Extract Text, mostrando las opciones para borrar o actualizar el texto.](../modules/modulesfiles/extracttext_item_edit.png)

Puede borrar todo el texto reconocido que se encuentra actualmente en el campo `extracttext:extracted_text`, o puede actualizarlo. A nivel de elemento, esto extraerá texto nuevo de todos los archivos multimedia del elemento, en orden, y lo generará todo en el campo como un único valor. 

A nivel de archivo multimedia, esto borrará o actualizará solo el texto de ese archivo multimedia. El texto actualizado aparecerá en los metadatos del elemento en el orden de los archivos multimedia. 

Cuando se selecciona «Actualizar texto», el extractor se ejecutará en primer plano, lo que podría tardar unos minutos. La página se actualizará automáticamente cuando finalice la extracción. 

Cuando se selecciona «Actualizar texto (en segundo plano)», se ejecutarán todos los extractores, incluidos aquellos configurados para ejecutarse solo en segundo plano (incluido Tesseract). Esto hará que aparezca una tarea en la pestaña «Tareas» situada en el lado izquierdo. Acceda a ella para comprobar si se ha completado o si hay errores. 

Si se reorganizan los archivos multimedia de un elemento, «Extraer texto» reorganizará automáticamente su salida para que coincida.

### Edición por lotes

Puede borrar o actualizar el texto de más de un elemento a la vez (o de más de un archivo multimedia, seleccionados manualmente). «Extract Text» aparece como un nuevo campo en la pantalla de edición por lotes. Esto funcionará únicamente como una tarea en primer plano, y deberá esperar a que la operación se complete. Los extractores en segundo plano no se ejecutarán desde una operación de edición por lotes.

![Una pantalla de edición por lotes con tres elementos seleccionados, que muestra las opciones para borrar o actualizar el texto.](../modules/modulesfiles/extracttext_batchedit.png)

### Integración de la importación CSV

[La importación CSV](../modules/csvimport.md), al añadir nuevos medios a su instalación de Omeka, incluirá un proceso de extracción de texto, que abarca todos los extractores en primer plano y en segundo plano, en cada uno de los archivos. 

!!! nota
  Si no deseas ejecutar una extracción de texto específica junto con una importación, debes desactivar los extractores en la configuración de Extract Text antes de iniciar una importación CSV. Te recomendamos que lo hagas al subir imágenes que no contengan texto, como fotografías, ya que Tesseract tardará mucho tiempo en intentar reconocer el texto dentro de las imágenes.

## Más opciones de configuración

Puede modificar el funcionamiento de este módulo editando los valores del archivo `config/local.config.php` de su instalación. Utilice la configuración «`extract_text`/`options`». Por ejemplo, si desea omitir siempre la primera página de los archivos PDF, añada lo siguiente:

```
php
'extract_text' => [
    'options' => [
 'pdftotext' => [
 'f' => 2,
 ],
    ],
],
```

Otro ejemplo: si desea utilizar los idiomas inglés y alemán conjuntamente al ejecutar Tesseract como OCR en imágenes, añada lo siguiente:

```php
'extract_text' => [
    'options' => [
 'tesseract' => [
 'l' => 'eng+deu',
 ],
    ],
],
```

Los siguientes extractores tienen opciones de configuración:

**filegetcontents**:

- offset: El desplazamiento donde comienza la lectura (por defecto 0)
- maxlen: Longitud máxima de los datos leídos (por defecto, nulo).

**pdftotext**:

- f: Primera página a convertir (por defecto, nulo)
- l: Última página a convertir (por defecto, nulo).

**tesseract**:

- l: Idioma/alfabeto (por defecto, «eng»)
- psm: Modo de segmentación de páginas (por defecto 3)
- oem: Modo del motor OCR (por defecto 3). 

También puedes consultar el [manual de Tesseract](https://github.com/tesseract-ocr/tesseract/blob/main/doc/tesseract.1.asc){target=_blank} para obtener más información.

### Extraer en segundo plano

Puede configurar un extractor para que nunca se ejecute en primer plano utilizando el ajuste «`extract_text`/`background_only`» en su archivo de configuración local (`config/local.config.php`). 

Por ejemplo, si desea configurar el extractor pdftotext para que se ejecute solo en segundo plano, añada lo siguiente:

```php
  'extract_text' => [
 'background_only' => [
 'pdftotext',
 ],
  ],
```

Tenga en cuenta que los extractores configurados para funcionar solo en segundo plano no extraerán automáticamente el texto al añadir un archivo multimedia. Deberá extraer el texto utilizando las dos opciones anteriores.

### Idiomas

Los extractores de Extract Text, en particular el reconocimiento óptico de caracteres de Tesseract, están configurados para reconocer texto en inglés de forma predeterminada. Para configurar otros idiomas para el reconocimiento, consulta el [manual de Tesseract](https://github.com/tesseract-ocr/tesseract/blob/main/doc/tesseract.1.asc){target=_blank} para conocer los códigos de idioma necesarios.

### Desactivar por tipo de medio

Puede desactivar la extracción de texto para un tipo de medio específico estableciendo el alias del tipo de medio en `null` en la configuración del servicio «`extract_text_extractors`» de su archivo de configuración local (`config/local.config.php`). 

Por ejemplo, si desea desactivar la extracción para archivos TXT (text/plain), añada lo siguiente:

```php
'extract_text_extractors' => [
    'aliases' => [
 'text/plain' => null,
    ],
],
```
