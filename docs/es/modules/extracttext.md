# Extraer texto

El [módulo «Extraer texto»](https://omeka.org/s/modules/ExtractText){target=_blank} extrae texto de los archivos para que sean consultables y legibles por máquina.

Cuando está activado, «Extraer texto» añade un nuevo vocabulario de metadatos con un campo, de tipo de datos textual, tanto a nivel de elemento como a nivel de medio, con el nombre «texto extraído» y el slug `extracttext:extracted_text`. Por defecto, está configurado como público en las páginas de visualización de elementos.

Añade una pestaña «Extraer texto» a la página de edición de cada elemento, donde se puede actualizar o eliminar el texto extraído. También añade una opción de edición por lotes para extraer o borrar texto de los archivos existentes en la base de datos. Cuando está activo, extraerá automáticamente el texto de los archivos subidos en [Importación CSV](../modules/csvimport.md).

Cuando el módulo está desactivado, los elementos con texto en los campos «texto extraído» no se modificarán; el campo seguirá mostrándose.

Si tienes más de un archivo adjunto a un elemento, el texto extraído acumulado aparecerá en un único campo a nivel del elemento, en el orden en que se hayan añadido los archivos. El texto extraído de los nuevos archivos se añadirá al final del campo.

## Requisitos del sistema

Los formatos de archivo compatibles con este módulo son:

- doc
- docx
- html
- odt
- pdf
- rtf
- txt
- xml
- bmp, gif, jp2, jpg, png, tiff y webp (con Tesseract).

Debes disponer de los extractores necesarios en tu servidor para que el módulo pueda procesar estos tipos de archivo. Para ver qué tipos de archivo se pueden procesar en tu instalación, ve a la entrada «Extract Text» en la sección «Módulos» y haz clic en el botón «Configurar». Se cargará una tabla que te mostrará qué extractores están disponibles en tu servidor.

## Configuración

![La página de configuración muestra la mayoría de los extractores disponibles, Tesseract ejecutándose en segundo plano y dos extractores desactivados.](../modules/modulesfiles/extracttext_configure.png)

En esta página puedes ver qué extractores están instalados, activos y ejecutándose en segundo plano. Puedes habilitar o deshabilitar extractores específicos, y configurarlos para que se ejecuten únicamente como tareas en segundo plano, lo que puede resultar más eficiente para tu servidor. 

Tesseract se ejecuta únicamente en segundo plano, ya que puede suponer una gran carga de procesamiento. Dependiendo del tamaño de tus otros archivos, como los PDF, es posible que también quieras configurar otros extractores para que se ejecuten únicamente en segundo plano. Los extractores «solo en segundo plano» no se ejecutarán cuando se suban nuevos archivos multimedia, pero sí lo harán con las tareas de importación de CSV y al utilizar herramientas de edición por lotes.

Cuando la opción «Solo en segundo plano» no está marcada, el extractor se ejecutará al subir un archivo, al seleccionar «Actualizar texto» y al seleccionar «Actualizar texto (en segundo plano)».

Los extractores necesarios son:

- **catdoc**, utilizado para extraer texto de archivos DOC y RTF.
- **docx2txt**, que se utiliza para extraer texto de archivos DOCX.
- **lynx**, que se utiliza para extraer texto de archivos HTML.
- **odt2txt**, que se utiliza para extraer texto de archivos ODT.
- **pdftotext**, que se utiliza para extraer texto de archivos PDF.
- **filegetcontents**, que se utiliza para extraer texto de archivos TXT.
- **domdocument**, que se utiliza para extraer texto de archivos XML.
- **tesseract**, que se utiliza para reconocer caracteres de texto a partir de archivos de imagen. 

Tesseract admite los siguientes formatos de archivo de imagen si se compila con las bibliotecas necesarias:

- BMP (image/bmp)
- GIF (image/gif)
- JP2 (image/jp2)
- JPG (image/jpeg)
- PNG (image/png)
- TIFF (image/tiff)
- WEBP (image/webp).


!!! nota
  Ten en cuenta que es posible que algunas extensiones de archivo o tipos de medio no estén permitidos en la [configuración global](../admin/settings.md#security) de tu instalación. El módulo no añade ni elimina automáticamente ningún archivo en función de su activación o de tus ajustes de configuración. 

	Es posible que tengas que añadir manualmente nuevas extensiones de archivo y tipos de medios con una cuenta de administrador si estás actualizando el módulo para añadir nuevas funciones de extracción, como XML. Por ejemplo, añade «text/xml» al cuadro de tipos de medios y «xml» al cuadro de extensiones de archivo. 

Si no tienes una o varias de las herramientas de extracción deseadas instaladas en tu servidor, consulta con tu servicio de alojamiento o con el administrador de tu servidor local.

## Extraer texto de los archivos multimedia

Para extraer texto de los archivos multimedia, puedes elegir varias acciones:

- Extraer manualmente el texto de un archivo multimedia, ya sea al subirlo o más tarde desde su pantalla de edición
- Extraer manualmente texto de todos los archivos multimedia asociados a un elemento, desde su pantalla de edición
- Extraer texto por lotes de todos los archivos multimedia asociados a varios elementos, desde la página de edición por lotes
- Extraer texto por lotes de una [importación CSV](../modules/csvimport.md) que contenga archivos multimedia subidos.

La función «Extraer texto» está configurada para ejecutarse automáticamente cuando se sube un nuevo archivo multimedia en cualquier lugar, ya sea mediante una importación CSV o al subir uno o más archivos multimedia a un elemento. Es posible que la extracción de texto no se ejecute con otros tipos de importaciones o conectores añadidos por módulos. 

![Un elemento en modo de edición, en el que se muestra el campo extracttext:extracted_text con su contenido.](../modules/modulesfiles/extracttext_item_field.png)

Puedes borrar o volver a ejecutar manualmente el texto extraído editando el elemento o el archivo multimedia. Para modificar el resultado automático, ve a la pestaña «Extraer texto» de un elemento o de un archivo multimedia específico.

![Un elemento en modo de edición, en la pestaña «Extraer texto», que muestra las opciones para borrar o actualizar el texto.](../modules/modulesfiles/extracttext_item_edit.png)

Puedes borrar todo el texto reconocido que se encuentra actualmente en el campo `extracttext:extracted_text`, o bien actualizarlo. A nivel de elemento, esto extraerá texto nuevo de todos los archivos multimedia del elemento, en orden, y lo mostrará en el campo como un único valor. 

A nivel de archivo multimedia, esto borrará o actualizará únicamente el texto de ese archivo concreto. El texto actualizado aparecerá en los metadatos del elemento en el orden de los archivos multimedia. 

Cuando se selecciona «Actualizar texto», el extractor se ejecutará en primer plano, lo que podría tardar unos minutos. La página se actualizará automáticamente cuando finalice la extracción. 

Cuando se selecciona «Actualizar texto (en segundo plano)», se ejecutarán todos los extractores, incluidos aquellos configurados para ejecutarse únicamente en segundo plano (como Tesseract). Esto hará que aparezca una tarea en la pestaña «Tareas», situada a la izquierda. Accede a ella para comprobar si se ha completado o si hay errores. 

Si se reorganizan los archivos multimedia de un elemento, «Extraer texto» reorganizará automáticamente su salida para que coincida.

### Edición por lotes

Puedes borrar o actualizar el texto de más de un elemento a la vez (o de más de un archivo multimedia, seleccionado manualmente). «Extraer texto» aparece como un nuevo campo en la pantalla de edición por lotes. Esta función solo se ejecutará en primer plano, por lo que deberás esperar a que la operación finalice. Los extractores en segundo plano no se ejecutarán desde una operación de edición por lotes.

![Una pantalla de edición por lotes con tres elementos seleccionados, en la que se muestran las opciones para borrar o actualizar el texto.](../modules/modulesfiles/extracttext_batchedit.png)

### Integración de la importación CSV

La [importación CSV](../modules/csvimport.md), al añadir nuevos archivos multimedia a tu instalación de Omeka, incluirá un proceso de extracción de texto —que abarca todos los extractores en primer plano y en segundo plano— en cada uno de los archivos. 

!!! Nota
  Si no deseas que se ejecute una extracción de texto específica junto con una importación, debes desactivar los extractores en la configuración de «Extract Text» antes de iniciar una importación CSV. Te recomendamos que lo hagas al subir imágenes que no contengan texto, como fotografías, ya que Tesseract tardará mucho tiempo en intentar reconocer el texto dentro de las imágenes.

## Más opciones de configuración

Puedes modificar el funcionamiento de este módulo editando los valores del archivo `config/local.config.php` de tu instalación. Utiliza la configuración «`extract_text`/`options`». Por ejemplo, si quieres omitir siempre la primera página de los archivos PDF, añade lo siguiente:

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

Otro ejemplo: si quieres utilizar los idiomas inglés y alemán a la vez al ejecutar Tesseract como OCR en imágenes, añade lo siguiente:

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

- offset: El desplazamiento desde el que comienza la lectura (por defecto 0)
- maxlen: Longitud máxima de los datos leídos (por defecto null).

**pdftotext**:

- f: Primera página a convertir (por defecto, nulo)
- l: Última página a convertir (por defecto, nulo).

**tesseract**:

- l: Idioma/alfabeto (por defecto, «eng»)
- psm: Modo de segmentación de páginas (por defecto, 3)
- oem: Modo del motor OCR (por defecto, 3). 

También puedes consultar el [manual de Tesseract](https://github.com/tesseract-ocr/tesseract/blob/main/doc/tesseract.1.asc){target=_blank} para obtener más información.

### Extracción en segundo plano

Puedes configurar un extractor para que nunca se ejecute en primer plano utilizando el parámetro «`extract_text`/`background_only`» en tu archivo de configuración local (`config/local.config.php`). 

Por ejemplo, si quieres configurar el extractor pdftotext para que funcione solo en segundo plano, añade lo siguiente:

```php
  'extract_text' => [
 'background_only' => [
 'pdftotext',
 ],
  ],
```

Ten en cuenta que los extractores configurados como «solo en segundo plano» no extraerán automáticamente el texto al añadir un archivo multimedia. Tendrás que extraer el texto utilizando las dos opciones anteriores.

### Idiomas

Los extractores de «Extract Text», en particular el reconocimiento óptico de caracteres de Tesseract, están configurados para reconocer texto en inglés de forma predeterminada. Para configurar otros idiomas para el reconocimiento, consulta el [manual de Tesseract](https://github.com/tesseract-ocr/tesseract/blob/main/doc/tesseract.1.asc){target=_blank} para conocer los códigos de idioma necesarios.

### Desactivar por tipo de medio

Puedes desactivar la extracción de texto para un tipo de medio específico estableciendo el alias del tipo de medio en `null` en la configuración del servicio «`extract_text_extractors`» de tu archivo de configuración local (`config/local.config.php`). 

Por ejemplo, si quieres desactivar la extracción para archivos TXT (text/plain), añade lo siguiente:

```php
'extract_text_extractors' => [
    'aliases' => [
 'text/plain' => null,
    ],
],
```
