# Consejos de planificación

## Conceptos básicos

Una instalación nueva de Omeka S incluye varios tipos de página prediseñados listos para compartir:

- Al añadir un nuevo sitio, puedes elegir directamente un tema instalado o dejar que utilice el tema «Predeterminado». 
- La navegación de tu primer sitio S incluirá de forma predeterminada una página «Explorar» para examinar los elementos. Puedes añadir rápidamente la página «Bienvenida» preinstalada, que muestra algunos estilos de formato de texto. 
- Una vez que añadas tu primer elemento, podrás ver la «[página de vista del elemento](content/items.md#public-views-for-items)». Personalízala desde el botón «Configurar páginas de recursos» en la pestaña «Tema». Hay un diseño de página independiente para ver los archivos multimedia adjuntos a los elementos.
- Cuando empieces a clasificar elementos en conjuntos de elementos, puedes añadir una página similar de «Explorar conjuntos de elementos» a tu navegación y personalizar una página similar de «vista de conjunto de elementos». 
- Dependiendo del tema que elijas, estas páginas de recursos pueden tener sus propios bloques preconfigurados. La mayoría de los temas mostrarán por defecto: 
  - para los elementos: una incrustación a tamaño completo del archivo multimedia, los metadatos del elemento ordenados por esquema, una lista de conjuntos de elementos y páginas del sitio donde aparece el elemento, y luego una lista de todos los archivos multimedia adjuntos al elemento con pequeñas miniaturas;
	- para los medios: una representación a tamaño completo del medio, seguida de los metadatos del medio; 
  - para los conjuntos de elementos: los metadatos del conjunto de elementos, seguidos de una cuadrícula de navegación o una lista del contenido del conjunto.
- Las páginas para navegar por elementos y conjuntos de elementos enlazan cada una con [un formulario de búsqueda avanzada](search.md#public-views), al igual que la barra de búsqueda situada en la parte superior de su sitio.

En Omeka S, construyes tus [sitios](sites/index.md) página a página, utilizando los recursos que has añadido a tu instalación. Deberías empezar a planificar tu sitio antes de comenzar a añadir recursos a gran escala, pero te sugerimos que experimentes con algunos elementos y conjuntos de elementos de muestra para familiarizarte con la forma en que Omeka los gestiona.

A continuación se incluyen algunas preguntas e ideas que te servirán de guía a la hora de planificar tus sitios en Omeka S.

## Público y objetivos del sitio

**¿Quién es el público principal de este sitio?** Ser específico te ayudará a dar forma al sitio; «personas interesadas en la arquitectura histórica» es mucho más útil que «el público en general». ¿Tienes públicos secundarios? ¿Qué quieres que estos públicos específicos consigan cuando visiten el sitio?

**¿Cuáles son los objetivos de su sitio?** ¿Qué quiere que logren sus públicos específicos cuando visiten el sitio? ¿Qué quiere que la gente se lleve del sitio? ¿Qué contenido quiere destacar?

## Recursos

**¿Qué hará con los elementos de este sitio web?**
Los [elementos](content/items.md) son los componentes básicos de Omeka S. ¿Qué tipo de [plantillas de recursos](content/resource-template.md) querrás crear y utilizar para describir completamente tus elementos? Cualquier elemento que incluyas en un Omeka S tendrá una página pública de visualización, así que intenta asegurarte de que la información de los metadatos de un elemento sea autosuficiente. 

**¿Qué vas a hacer con los conjuntos de elementos?**
Puedes utilizar [conjuntos de elementos](content/item-sets.md) para agrupar los elementos que se incluirán en un [sitio](sites/index.md), y pueden ser una forma de guiar la navegación de los visitantes por tus sitios. Para algunos sitios, los conjuntos de elementos son recursos sólidos en sí mismos.

¿Cómo quieres agrupar los elementos en conjuntos? ¿Qué campos de metadatos utilizarán tus conjuntos de elementos? ¿Tienen tus conjuntos de elementos relaciones entre sí o con los elementos?

**¿Qué quieres que hagan tus datos?**
¿Qué propiedades vas a querer describir de forma coherente en tu sitio? ¿Quieres que algunas de ellas se muestren con una etiqueta diferente, por ejemplo, «autor» en lugar de «creador» para los libros? Utilice una [plantilla de recurso](content/resource-template.md) y cambie la etiqueta de la propiedad.

En Omeka S, los elementos y los conjuntos de elementos pueden utilizar otros recursos —elementos, conjuntos de elementos y medios— como propiedades; por ejemplo, puede crear un elemento para William Shakespeare y hacer que ese elemento complete la propiedad «creador» de un elemento «Hamlet». ¿Cómo pueden sus recursos utilizar esta funcionalidad?

¿Desea utilizar un conjunto de términos (vocabulario controlado) para determinados elementos? Quizás le interese utilizar [Custom Vocab](modules/customvocab.md). ¿O prefiere utilizar una lista de términos creada por la Biblioteca del Congreso o el Getty? En ese caso, podría utilizar [Value Suggest](modules/valuesuggest.md).

## Creación de un sitio
Con Omeka S, puedes crear tus sitios desde cero o configurar rápidamente nuestras páginas integradas. También es fácil utilizar varios sitios para alcanzar tus objetivos. 

**¿Qué páginas quieres incluir?** ¿Qué tipo de contenido quieres en estas páginas? ¿Cómo quieres organizarlas? Intenta esbozar un menú de muestra o esquemas funcionales para el sitio. Echa un vistazo a sitios de ejemplo de otras organizaciones o personas. Úsalos como guía mientras creas tus páginas.

Las páginas se componen de [bloques](sites/site_pages.md#page-blocks) que se pueden reorganizar y que pueden incluir texto, imágenes y mucho más. ¿Qué tipo de contenido quieres que haya en las páginas que crees? ¿Cómo quieres que la gente acceda e interprete tus colecciones?

**¿Cómo quieres interactuar con los visitantes de tu sitio?** ¿Quieres [recopilar](modules/collecting.md) recursos de tus visitantes? ¿Permitirles [compartir](modules/sharing.md) tu contenido en las redes sociales? 

¿Permitirás que [los usuarios creen cuentas](admin/users.md) en tu sitio y les dejarás añadir sus propios elementos, metadatos o exposiciones?

## Módulos recomendados
El equipo de Omeka y nuestra comunidad de desarrolladores de código abierto han creado cientos de módulos para ampliar la funcionalidad básica de Omeka S. Para ayudar a los administradores a instalar y configurar Omeka S de modo que se adapte a tipos de trabajo concretos, a continuación se incluyen algunas colecciones de módulos recomendadas:

### Publicación de colecciones digitales

- Descripción de recursos 
 - [Extract Metadata](https://omeka.org/s/modules/ExtractMetadata/){target=_blank}: Extrae metadatos incrustados de archivos, como datos EXIF de fotografías.
    - [Extract Text](https://omeka.org/s/modules/ExtractText/){target=_blank}: Extrae texto de archivos (PDF, documentos de Word, imágenes) para que se puedan buscar. 
 - [Vocabulario personalizado](https://omeka.org/s/modules/CustomVocab/){target=_blank}: Describe tus recursos utilizando vocabularios que tú mismo crees.
    - [Sugerencias de valores](https://omeka.org/s/modules/ValueSuggest/){target=_blank}: Describa sus recursos utilizando valores sugeridos automáticamente por servicios de vocabulario controlado. 
 - [Tipos de datos numéricos](https://omeka.org/s/modules/NumericDataTypes/){target=_blank}: Añada tipos de datos para números y fechas. 
- Importación de recursos
    - [Importación CSV](https://omeka.org/s/modules/CSVImport/){target=_blank}: Importe y actualice contenido (elementos, conjuntos de elementos, medios, usuarios) desde un archivo CSV, TSV u ODS. 
    - [Carga lateral de archivos](https://omeka.org/s/modules/FileSideload/){target=_blank}: Añade a los elementos archivos que ya se encuentran en tu servidor. 
 - Otros importadores incluyen DSpace, Fedora, Dataverse, Invenio, Zenodo, Zotero o colecciones existentes de Omeka Classic o S.
- Aumentar la visibilidad
    - [Mapeo](https://omeka.org/s/modules/Mapping/){target=_blank}: Geolocaliza tus elementos en una o más ubicaciones mapeadas.
    - [Compartir](https://omeka.org/s/modules/Sharing/){target=_blank}: Ofrece metadatos OpenGraph para que tus enlaces de Omeka S se muestren perfectamente en las redes sociales.
    - [Metadatos de recursos](https://omeka.org/s/modules/ResourceMeta/){target=_blank}: Haz que los metadatos de tus recursos sean legibles por máquina.
    - [Identificadores persistentes](https://omeka.org/s/modules/PersistentIdentifiers/){target=_blank}: Crea, importa o asigna DOI o ARK a los elementos.
    - [Presentación IIIF](https://omeka.org/s/modules/IiifPresentation/){target=_blank}: Ofrece tus recursos utilizando la API de presentación IIIF.
- Visualización de recursos
    - [Navegación por facetas](https://omeka.org/s/modules/FacetedBrowse/){target=_blank}: Añade herramientas de navegación más detalladas a tus colecciones.
    - [Navegación por metadatos](https://omeka.org/s/modules/MetadataBrowse/){target=_blank}: Explora recursos que comparten los mismos metadatos.
    - [Desreferenciador de URI](https://omeka.org/s/modules/UriDereferencer/){target=_blank}: Muestra metadatos de control de autoridad a partir de URI externos. 

Además de estos grupos básicos de módulos, es posible que le interesen los siguientes tipos específicos de funcionalidades.

### Modelado de datos complejos

- Descripción de recursos
    - [Limpieza de datos](https://omeka.org/s/modules/DataCleaning/){target=_blank}: Auditoría y limpieza de bajo nivel de los metadatos de los recursos.
    - [Propiedades inversas](https://omeka.org/s/modules/InverseProperties/){target=_blank}: Define relaciones recíprocas entre propiedades.
- Datos privados
    - [Ocultar propiedades](https://omeka.org/s/modules/HideProperties/){target=_blank}: Ocultar propiedades en el lado administrativo o público.
    - [Ocultar valores](https://omeka.org/s/modules/RedactValues/){target=_blank}: Ocultar valores para que no sean visibles para el público.
    - [Ver recursos privados](https://omeka.org/s/modules/ViewPrivateResources/){target=_blank}: Permitir que los usuarios con roles inferiores vean los recursos privados.
- Visualización de datos
    - [Visualización de datos](https://omeka.org/s/modules/Datavis/){target=_blank}: Visualizar información sobre sus colecciones y elementos.
    - [Mapeo](https://omeka.org/s/modules/Mapping/){target=_blank}: Geolocaliza tus elementos en una o más ubicaciones mapeadas; incluye una línea de tiempo para mostrar los elementos cronológicamente.

### Contribuciones de la comunidad

- Contribuciones públicas
    - [Recopilación](https://omeka.org/s/modules/Collecting/){target=_blank}: Añade formularios de recopilación a tus sitios. Se integra con Cartografía, Tipos de datos Numerica, Vocabulario personalizado y Sugerencias de valores.
- Transcripción
    - [Scripto](https://omeka.org/s/modules/Scripto/){target=_blank}: Transcribe y traduce elementos.
    - [DataScribe](https://omeka.org/s/modules/Datascribe/){target=_blank}: Permite a los visitantes de la comunidad transcribir datos estructurados.

### Geoespacial y temporal

- Descripción de recursos
    - [Mapeo](https://omeka.org/s/modules/Mapping/){target=_blank}: Añade información de ubicación a tus elementos y sitios.
    - [Tipos de datos numéricos](https://omeka.org/s/modules/NumericDataTypes/){target=_blank}: Añade tipos de datos para números y fechas. Permite la creación de líneas de tiempo en combinación con Cartografía.
   
### Trabajar con otros sistemas digitales

- Repositorios institucionales
    - [Conector de repositorios de datos](https://omeka.org/s/modules/DataRepositoryConnector/){target=_blank} incluye Zenodo, Dataverse, Invenio y CKAN
    - [Conector DSpace](https://omeka.org/s/modules/DspaceConnector/){target=_blank}
    - [Conector Fedora](https://omeka.org/s/modules/FedoraConnector/){target=_blank}
- Otras instalaciones de Omeka
    - [Importador Omeka Classic](https://omeka.org/s/modules/Omeka2Importer/){target=_blank}
    - [Importador de elementos de Omeka S](https://omeka.org/s/modules/Osii/){target=_blank}
- Zotero
    - [Citas de Zotero](https://omeka.org/s/modules/ZoteroCitations/){target=_blank}: Utiliza Zotero para generar citas y bibliografías.
    - [Importador de Zotero](https://omeka.org/s/modules/ZoteroImport){target=_blank}: Importa elementos y archivos desde las bibliotecas de usuarios y grupos de Zotero.
