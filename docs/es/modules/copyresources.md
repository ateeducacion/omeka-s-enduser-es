# Copiar recursos

El [módulo «Copiar recursos»](https://omeka.org/s/modules/CopyResources){target=_blank} te permite duplicar sitios de Omeka S, páginas de sitios, elementos y conjuntos de elementos.

Una vez activado en la sección [Módulos](https://omeka.org/s/docs/user-manual/modules/){target=_blank} del panel de administración, «Copiar recursos» inserta un botón «copiar» en la interfaz de varias páginas del panel de administración, incluyendo la vista del recurso, la tabla de sitios, la tabla de páginas de cada sitio y las tablas de elementos y conjuntos de elementos. 

![La tabla de páginas del panel de administración, en la que se muestran los botones «Copiar» junto a cada página de la tabla. El panel lateral derecho está abierto en la página «Bienvenida» y muestra un menú desplegable «Visibilidad» situado encima del botón «Confirmar copia».](modulesfiles/copyResources_pages.png)

Los elementos y los conjuntos de elementos recibirán un nuevo identificador único, pero se duplicarán todos sus campos de metadatos, incluidos los datos capturados por los módulos, como los datos de geolocalización en Mapping. Los elementos duplicados se añadirán a los mismos conjuntos de elementos que los originales; los recursos duplicados se añadirán a los mismos sitios que los originales. Sin embargo, los elementos duplicados no tendrán ningún archivo multimedia copiado junto con ellos.

Los sitios y las páginas de los sitios tendrán el mismo nombre, pero sus slugs de URL serán únicos. Las páginas tendrán duplicados todos sus bloques de página, incluidos los bloques añadidos por los módulos y la configuración de dichos bloques.

Algunos contenidos no se copiarán exactamente; asegúrate de revisar minuciosamente los recursos duplicados y de comprobar si falta algo antes de hacer público el nuevo recurso. 

### Permisos

Los administradores globales, supervisores y editores pueden utilizar este módulo para copiar elementos, conjuntos de elementos, sitios y páginas de sitio.

Los usuarios con los niveles de «Autor» y «Revisor» pueden copiar elementos y conjuntos de elementos. 

Los permisos específicos del sitio no afectan a la capacidad de un usuario para copiar sitios. La copia de sitios está reservada a los administradores globales, supervisores y editores. 

Los usuarios con permisos específicos del sitio de «Creador» y «Gestor» pueden copiar páginas. 

Los usuarios pueden copiar recursos de los que no sean propietarios. Cuando se copia un recurso, el usuario que ha creado la copia se convierte en su propietario; el recurso no conservará al propietario del original. 

### Requisitos

«Copiar recursos» requiere Omeka S 4.1.0 o posterior. 

Si utilizas los siguientes módulos, te recomendamos que actualices a las versiones que se han actualizado desde el lanzamiento de «Copiar recursos», concretamente:

- [Recopilación](collecting.md) versión 1.12 o posterior
- [Visualización de datos](datavisualization.md) versión 1.3
- [Item Carousel Block](itemcarouselblock.md), versión 1.3
- [Faceted Browse](facetedbrowse.md), versión 1.5.1
- [Mapping](mapping.md), versión 2.0
- [Scripto](scripto/index.md) versión 1.5
- [Compartir](sharing.md) versión 1.5.

Otros módulos cuyos datos pueden ser copiados por Copy Resources, como la búsqueda por metadatos, no tienen dependencias. 

## Copia de recursos

![La tabla de elementos en el panel de administración, que muestra botones de «copiar» junto a cada elemento de la tabla y una ventana de confirmación en el panel lateral derecho.](modulesfiles/copyResources_items.png)

Al copiar un elemento o un conjunto de elementos, el botón «copiar» aparece a la izquierda del botón «editar» (icono del lápiz) en cada fila de la tabla de recursos. Los elementos y los conjuntos de elementos se pueden copiar manualmente, de uno en uno (no de forma masiva). 

Al hacer clic en el botón «Copiar», aparecerá una ventana de confirmación en el panel lateral derecho. Esta ventana de confirmación te permitirá configurar la visibilidad del recurso duplicado; las opciones son «Igual que el original», «Privado» o «Público». 

!!! Nota
  Los elementos se copiarán sin sus archivos multimedia, con el fin de limitar la carga de procesamiento del servidor y el uso de espacio. Si necesitas copiar los archivos multimedia de un elemento, utiliza el módulo [Omeka S Item Importer](ositemimporter.md), que permite copiar elementos junto con sus archivos multimedia. Introduce la API de tu propia instalación para acceder a los elementos existentes. Recuerda que los archivos multimedia solo existen asociados a un único elemento; no puedes «añadir» archivos multimedia existentes a un segundo elemento.

Cuando el recurso se haya copiado correctamente, se te redirigirá a la página de visualización del nuevo recurso. 

![La página de visualización del elemento, con un mensaje de confirmación de que el elemento se ha copiado correctamente.](modulesfiles/copyResources_itemsCopied.png)

También puedes copiar recursos al visualizarlos individualmente: aparecerá un botón «Copiar» en la esquina superior derecha de la pantalla.

!!! nota
  Ten en cuenta que los recursos duplicados tendrán los mismos [enlaces a otros recursos de Omeka S](../content/items.md#linked-resources), pero cualquier enlace que apunte al recurso original no se redirigirá automáticamente a su duplicado. Si lo deseas, tendrás que establecer estos enlaces manualmente o utilizar módulos como [Inverse Properties](inverseproperties.md). 

## Copiar sitios y páginas

### Páginas

Las páginas se pueden copiar desde la tabla de páginas de cada sitio o desde la interfaz de edición de cada página. 

![La tabla de páginas, con un botón «Copiar» en cada fila, y la ventana de confirmación abierta en el panel de la derecha.](modulesfiles/copyResources_pages.png)

Al hacer clic en el botón «Copiar», aparecerá una ventana de confirmación en el panel de la derecha. Esta ventana de confirmación te permitirá establecer la visibilidad del recurso duplicado; las opciones son «Igual que el original», «Privado» o «Público». 

Al copiar páginas, la página duplicada tendrá el slug original con «-1» añadido al final. A continuación, puedes cambiar el nombre y el slug de la página. 

![La tabla de páginas, después de que una página se haya copiado correctamente.](modulesfiles/copyResources_pagesCopied.png)

Todos los bloques de la página deberían copiarse, incluidos los bloques introducidos por módulos, [siempre que el módulo correspondiente se haya actualizado donde sea aplicable (véase la sección «Requisitos» más arriba)](#requirements).

Este módulo no añade las páginas recién copiadas a la navegación del sitio; las páginas duplicadas deberán añadirse manualmente. 

No puedes utilizar este módulo para copiar una página de un sitio a otro.

### Sitios

Al copiar un sitio, encontrarás el botón «Copiar» en la tabla de sitios o en la página de vista de un sitio concreto.

Al hacer clic en el botón «Copiar», aparecerá una ventana de confirmación en el panel lateral derecho. Esta ventana de confirmación te permitirá configurar la visibilidad del sitio duplicado; las opciones son «Igual que el original», «Privado» o «Público». 

El módulo duplicará todas las páginas, todas las entradas de navegación, todos los ajustes del sitio y del tema, y todos los permisos de usuario. Todos los recursos añadidos al sitio original se transferirán al sitio duplicado. El nuevo sitio apuntará a los mismos recursos (logotipo, banner, etc.) que el sitio original.

![La página de vista del sitio, con un botón «Copiar» en la esquina superior derecha de la pantalla y la ventana de confirmación abierta en el panel lateral derecho.](modulesfiles/copyResources_sites.png)

Al copiar un sitio, las páginas conservarán sus slugs únicos; el sitio en sí tendrá el slug del sitio original con «-1» añadido al final. A continuación, puedes cambiar el nombre y el slug del sitio en su configuración. 

![La página de vista del sitio, tras haber copiado correctamente un sitio.](modulesfiles/copyResources_sitesCopied.png)

En los casos en que otros módulos introduzcan datos específicos del sitio (como «Metadata Browse», «Sharing», «Data Visualization», «Collecting», «Faceted Browse», «Item Carousel Block», etc.), esta información se copiará, [siempre que el módulo correspondiente se haya actualizado donde sea aplicable (véase la sección «Requisitos» más arriba)](#requirements). 

#### Después de duplicar un sitio

Asegúrate de revisar minuciosamente el sitio duplicado para comprobar que todo se ha copiado correctamente. Es posible que algunas páginas, bloques de página o datos de módulos no se hayan copiado como se esperaba y que sea necesario volver a configurarlos manualmente, como los elementos seleccionados en el bloque de página «Incrustación de medios» o las páginas configuradas en la navegación. 

Copiar un sitio web completo es un proceso complicado; los sitios contienen una gran variedad de datos, incluidos los procedentes de módulos y temas. La copia de un sitio puede dar lugar a errores que deben corregirse antes de que el sitio pueda hacerse público, y puede que sea necesario recrear manualmente algunos datos a partir del sitio original para obtener una copia perfecta. 

Algunos problemas con los que te puedes encontrar:

- Un sitio cuya navegación tenga entradas de página que faltan puede provocar errores hasta que se eliminen o se corrijan las páginas que faltan. Esto puede incluir problemas al cambiar el tema, el nombre o el slug del sitio. Si ves los errores «Navegación no válida: enlace a la página sin ID de página» o «Navegación no válida: datos de enlace no válidos», comprueba tu navegación en busca de entradas que muestren «[Página ausente]».
- Algunos sitios que utilicen el módulo [Navegación por facetas](facetedbrowse.md) pueden mostrar errores si el usuario que duplica el sitio no tiene permisos para utilizar la navegación por facetas (los administradores globales y los supervisores sí pueden, pero los editores no). 
