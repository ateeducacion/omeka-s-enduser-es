# Presentación IIIF

El [módulo de presentación IIIF](https://omeka.org/s/modules/IiifPresentation/){target=_blank} permite a las instalaciones ofrecer [puntos finales y visores de la API de presentación IIIF](https://iiif.io/api/presentation/3.0/){target=_blank} para sus elementos y conjuntos de elementos de Omeka S. Estos puntos de conexión de la API están disponibles automáticamente para todos los elementos y conjuntos de elementos cuando el módulo está instalado y activo. 

Omeka S ofrece el [visor Mirador IIIF](https://projectmirador.org/){target=_blank} en su código base, lo que permite a Omeka [importar y mostrar contenidos multimedia IIIF](../content/media.md#add-media-to-an-item) procedentes de toda la web. Esto puede resultar útil para instituciones que alojan sus colecciones digitales en otros lugares pero desean utilizar esos materiales en exposiciones virtuales de Omeka, o para educadores que deseen utilizar materiales compartidos públicamente con fines didácticos. 

Este módulo añade la capacidad de enviar los elementos o conjuntos de elementos de una instalación de Omeka S a otros visores IIIF para su visualización, así como de cargar visores IIIF en la instalación para su previsualización y configuración. Esto puede ser utilizado por otras personas que deseen mostrar tus recursos de Omeka en sus propios sitios web. 

Un visor IIIF puede configurarse para mostrar cualquier elemento, un conjunto de varios elementos, cualquier conjunto de elementos o un conjunto de varios conjuntos de elementos, simplemente creando la URL deseada. El módulo no tiene ajustes ni opciones adicionales en la interfaz de administración. 

## Uso del módulo

Tras la instalación, las URL del manifiesto y del visor se crean utilizando la URL base de tu instalación de Omeka S, no la de ningún sitio concreto de la instalación. Por lo tanto, los usuarios pueden encontrar la URL del visor IIIF para cada elemento en 

`
https://example.com/omeka-s/iiif-presentation/3/item/123/
`

y la URL del manifiesto en 

`
https://example.com/omeka-s/iiif-presentation/3/item/123/manifest
`

donde 

- `https://example.com/omeka-s/` es la URL base de tu instalación (no incluyas la URL de ningún sitio concreto, ni el `/s/` que precede al nombre del sitio)
- `iiif-presentation/3/` indica que estás ofreciendo un manifiesto IIIF de tipo 3.0
- `item` indica que el objeto es un elemento de Omeka S
- `123` es el ID concreto del elemento.

Del mismo modo, la URL de cada conjunto de elementos es

`
https://example.com/omeka-s/iiif-presentation/3/item-set/45
`

donde `45` es el identificador del conjunto de elementos.

Puedes proporcionar más de un ID de elemento, o más de un ID de conjunto de elementos, incluyendo los valores separados por comas en el mismo lugar, por ejemplo:

`
https://example.com/omeka-s/iiif-presentation/3/item/6,7,8,9
`

Los valores pueden aparecer en cualquier orden y se mostrarán en el visor en el orden indicado.


Puedes comprobar que el módulo funciona correctamente accediendo directamente a la URL de un visor o de un manifiesto en tu navegador. 

En el visor, deberías ver cómo se carga el contenido multimedia de tu elemento, con los metadatos en la barra lateral. La URL se redirigirá a algo con el siguiente formato: 

`
https://example.com/omeka-s/iiif-viewer?url=https://example.com/omeka-s/iiif-presentation/3/item/1082/manifest
`

![Vista de un visor IIIF Mirador que muestra un libro con varias páginas.](modulesfiles/iiifpresentation_viewer.png)

En cuanto al manifiesto, deberías ver una página de JSON cargándose en la que «Manifest» aparece al principio como tipo. 

![Vista de la salida JSON de un manifiesto IIIF.](modulesfiles/iiifpresentation_json.png)

También puedes utilizar herramientas de validación como [https://presentation-validator.iiif.io/](https://presentation-validator.iiif.io/){target=_blank}.

## Puntos finales

### IIIF Presentation v3

Estos puntos finales están disponibles para la versión 3 de la API de IIIF Presentation.

- `/iiif-presentation/3/item/:item-id/manifest`
    Obtiene el recurso de manifiesto IIIF para un elemento de Omeka. Genera JSON-LD.
    - `:item-id`: El ID del elemento de Omeka
- `/iiif-presentation/3/item/:item-id`
    Visualiza el recurso de manifiesto IIIF de un elemento de Omeka. Redirige al visor IIIF de Omeka S (Mirador).
    - `:item-id`: El ID del elemento de Omeka
- `/iiif-presentation/3/item/:item-ids/collection`
    Obtiene el recurso de colección IIIF para dos o más elementos de Omeka. Devuelve JSON-LD.
    - `:item-ids`: Los identificadores de los elementos de Omeka, delimitados por comas
- `/iiif-presentation/3/item/:item-ids`
    Ver el recurso de colección IIIF correspondiente a dos o más elementos de Omeka. Redirige al visor IIIF de Omeka (Mirador).
    - `:item-ids`: Los ID de los elementos de Omeka, delimitados por comas
- `/iiif-presentation/3/item-set/:item-set-id/collection`
    Obtiene el recurso de colección IIIF para un conjunto de elementos de Omeka. Genera JSON-LD.
    - `:item-set-id`: El identificador del conjunto de elementos de Omeka
- `/iiif-presentation/3/item-set/:item-set-id`
    Visualiza el recurso de colección IIIF correspondiente a un conjunto de elementos de Omeka. Redirige al visor IIIF de Omeka S (Mirador).
    - `:item-set-id`: El ID del conjunto de elementos de Omeka
- `/iiif-presentation/3/item-set/:item-set-ids/collection`
    Obtiene el recurso de colección IIIF para dos o más conjuntos de elementos de Omeka. Genera JSON-LD.
    - `:item-set-ids`: Los identificadores de los conjuntos de elementos de Omeka, separados por comas
- `/iiif-presentation/3/item-set/:item-set-ids`
    Visualiza el recurso de colección IIIF para dos o más conjuntos de elementos de Omeka. Redirige al visor IIIF de Omeka (Mirador).
    - `:item-set-ids`: Los ID de los conjuntos de elementos de Omeka, delimitados por comas.

### Presentación IIIF v2

Estos puntos finales están disponibles para la versión 2 de la API de presentación IIIF.

- `/iiif-presentation/2/item/:item-id/manifest`
    Obtiene el recurso de manifiesto IIIF de un elemento de Omeka. Devuelve JSON-LD.
    - `:item-id`: El identificador del elemento de Omeka
- `/iiif-presentation/2/item/:item-id`
    Visualiza el recurso de manifiesto IIIF de un elemento de Omeka. Redirige al visor IIIF de Omeka S (Mirador).
    - `:item-id`: El ID del elemento de Omeka
- `/iiif-presentation/2/item/:item-ids/collection`
    Obtiene el recurso de colección IIIF para dos o más elementos de Omeka. Genera JSON-LD.
    - `:item-ids`: Los ID de los elementos de Omeka, delimitados por comas
- `/iiif-presentation/2/item/:item-ids`
    Ver el recurso de colección IIIF para dos o más elementos de Omeka. Redirige al visor IIIF de Omeka (Mirador).
    - `:item-ids`: Los ID de los elementos de Omeka, delimitados por comas
- `/iiif-presentation/2/item-set/:item-set-id/collection`
    Obtiene el recurso de colección IIIF para un conjunto de elementos de Omeka. Genera JSON-LD.
    - `:item-set-id`: El identificador del conjunto de elementos de Omeka
- `/iiif-presentation/2/item-set/:item-set-id`
    Visualiza el recurso de colección IIIF correspondiente a un conjunto de elementos de Omeka. Redirige al visor IIIF de Omeka S (Mirador).
    - `:item-set-id`: El identificador del conjunto de elementos de Omeka
- `/iiif-presentation/2/item-set/:item-set-ids/collection`
    Obtiene el recurso de colección IIIF para dos o más conjuntos de elementos de Omeka. Genera JSON-LD.
    - `:item-set-ids`: Los identificadores de los conjuntos de elementos de Omeka, separados por comas
- `/iiif-presentation/2/item-set/:item-set-ids`
    Visualiza el recurso de colección IIIF para dos o más conjuntos de elementos de Omeka. Redirige al visor IIIF de Omeka (Mirador).
    - `:item-set-ids`: Los ID de los conjuntos de elementos de Omeka, delimitados por comas.

## Eventos

Este módulo activa estos eventos durante la composición de determinados recursos de presentación IIIF (manifiesto, lienzo, colección, etc.). Utiliza el método `getTarget()` del evento para obtener el controlador actual.

### Presentación IIIF v3

Estos eventos están disponibles para la versión 3 de la API de presentación IIIF.

- `iiif_presentation.3.media.canvas`
    Se activa tras componer una matriz de lienzos multimedia. Para modificar el lienzo, los controladores pueden modificar el parámetro `canvas` y volver a asignarlo al evento.
    - `canvas`: La matriz de lienzos
    - `canvas_type`: El objeto de servicio del tipo de lienzo
    - `media_id`: El ID del medio
- `iiif_presentation.3.item.manifest`
    Se activa tras componer una matriz de manifiesto de elementos. Para modificar el manifiesto, los controladores pueden modificar el parámetro `manifest` y volver a asignarlo al evento.
    - `manifest`: El array del manifiesto
    - `item_id`: El ID del elemento
- `iiif_presentation.3.item.collection`
    Se activa tras componer un array de la colección de elementos. Para modificar la colección, los gestores pueden modificar el parámetro `collection` y volver a asignarlo al evento.
    - `collection`: El array de la colección
    - `item_ids`: Los ID de los elementos de la colección
- `iiif_presentation.3.item_set.collection`
    Se activa tras componer un array de colecciones de conjuntos de elementos. Para modificar la colección, los controladores pueden modificar el parámetro `collection` y volver a asignarlo al evento.
    - `collection`: El array de la colección
    - `item_set_id`: El identificador del conjunto de elementos
- `iiif_presentation.3.item_set.collections`
    Se activa tras componer un array de colecciones de conjuntos de elementos. Para modificar la colección, los controladores pueden modificar el parámetro `collection` y volver a asignarlo al evento.
    - `collection`: El array de la colección
    - `item_set_ids`: Los ID de los conjuntos de elementos de la colección.

### IIIF Presentation v2

Estos eventos están disponibles para la versión 2 de la API de IIIF Presentation.

- `iiif_presentation.2.media.canvas`
    Se activa tras componer una matriz de lienzos multimedia. Para modificar el lienzo, los controladores pueden modificar el parámetro `canvas` y volver a asignarlo al evento.
    - `canvas`: La matriz de lienzos
    - `canvas_type`: El objeto de servicio del tipo de lienzo
    - `media_id`: El ID de los medios
- `iiif_presentation.2.item.manifest`
    Se activa tras componer una matriz de manifiesto de elementos. Para modificar el manifiesto, los controladores pueden modificar el parámetro `manifest` y volver a asignarlo al evento.
    - `manifest`: El array del manifiesto
    - `item_id`: El ID del elemento
- `iiif_presentation.2.item.collection`
    Se activa tras componer un array de la colección de elementos. Para modificar la colección, los controladores pueden modificar el parámetro `collection` y volver a asignarlo al evento.
    - `collection`: El array de la colección
    - `item_ids`: Los ID de los elementos de la colección
- `iiif_presentation.2.item_set.collection`
    Se activa tras crear un array de la colección de conjuntos de elementos. Para modificar la colección, los controladores pueden modificar el parámetro `collection` y volver a asignarlo al evento.
    - `collection`: El array de la colección
    - `item_set_id`: El ID del conjunto de elementos
- `iiif_presentation.2.item_set.collections`
    Se activa tras componer una matriz de colecciones de conjuntos de elementos. Para modificar la colección, los controladores pueden modificar el parámetro `collection` y volver a asignarlo al evento.
    - `collection`: La matriz de la colección
    - `item_set_ids`: Los ID de los conjuntos de elementos de la colección.
