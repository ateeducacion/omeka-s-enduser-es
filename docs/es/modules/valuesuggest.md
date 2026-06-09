# Value Suggest

El [módulo Sugerencia de valores](https://omeka.org/s/modules/ValueSuggest){target=_blank} añade una función de autocompletado a las propiedades de las plantillas de recursos y se basa en vocabularios controlados publicados (consulte el final de esta página para ver la lista completa) para ayudar a los usuarios a rellenarlas. Los usuarios pueden, por ejemplo, rellenar el campo «Tema» en Dublin Core con términos de los encabezados de materia de la Biblioteca del Congreso. 

Cuando un usuario edita los metadatos de un recurso (un elemento, un medio o un conjunto de elementos) que utiliza la plantilla de recursos habilitada para Sugerencia de valores, puede elegir entre las opciones de un vocabulario. Funciona como un [tipo de datos](../content/resource-template.md#tipos-de-datos), pero funciona como una modificación de un campo de texto: un usuario puede empezar a escribir y seleccionar una sugerencia del menú desplegable, o ignorar el menú y escribir una entrada textual.

Value Suggest incluye de serie muchos vocabularios populares; consulte la lista a continuación. Algunos ejemplos: VIAF, PBCore para información editorial, RDA para multimedia, RightsStatements y licencias Creative Commons. El módulo proporciona términos en varios idiomas. 

Este módulo también permite que cualquier campo [sugiera valores ya almacenados en esa propiedad en toda la instalación de Omeka](#internal-suggestions). Puede optar por limitar los valores sugeridos a aquellos de recursos con la misma clase, o a los de recursos que utilicen la misma plantilla de recursos, para reducir el número de sugerencias y hacerlas más relevantes. 

Esta función ayuda a fomentar la introducción coherente de metadatos y la compatibilidad de los datos con otras bases de datos. Tenga en cuenta que Value Suggest ofrece, pero no puede exigir, términos de la función de autosugestión. Los usuarios siempre tendrán la opción de crear su propio valor de texto en su lugar.

## Sugerir valores a través de plantillas de recursos

Los vocabularios de Value Suggest se aplican a través de plantillas de recursos. Para obtener información adicional sobre las plantillas de recursos, consulte la [documentación de plantillas de recursos](../content/resource-template.md).

1. En la página Plantillas de recursos del panel de administración, añada una nueva [plantilla](../content/resource-template.md) o edite una ya existente.
1. Añada la propiedad a la que desea ofrecer un vocabulario de Value Suggest. 
1. Una vez añadida la propiedad a la plantilla, haz clic en el icono del lápiz/editar de dicha propiedad.
1. En la parte inferior del panel que se abre a la derecha, abre el menú desplegable «Tipo de datos». Debajo de las opciones estándar, verás las opciones de Value Suggest. Selecciona el vocabulario que desees utilizar en el menú desplegable. Ten en cuenta que puedes añadir etiquetas alternativas y comentarios para la propiedad en este panel.
1. Haz clic en el botón «Aplicar cambios» en la parte inferior del panel para asignar los valores a la propiedad. 
1. Guarde los cambios en la plantilla de recurso. 

![Edición de la propiedad «Tema», con el menú desplegable abierto para mostrar los vocabularios de sugerencias de valores de la Biblioteca del Congreso](../modules/modulesfiles/ValSug-ResTemplate1.png)

Al hacer clic en el título de una plantilla de recurso para ver sus detalles, el vocabulario de Value Suggest aparecerá bajo el encabezado de la tabla «Tipo de datos».

![Un rectángulo rojo resalta el hecho de que el tipo de datos para «Tema» es «LC: Subject Headings»](../modules/modulesfiles/ValSug-ResTemplate2.png)

## Sugerir valores para recursos

Cuando se utiliza una plantilla de recursos de sugerencia de valores para un elemento, un medio o un conjunto de elementos, las propiedades designadas sugerirán automáticamente valores del vocabulario especificado en la plantilla. 

Los usuarios deben empezar a escribir en el cuadro de texto abierto de esa propiedad específica para activar la función de sugerencia automática. Puede haber un ligero retraso, pero aparecerá un menú desplegable con opciones extraídas directamente de la lista de autoridades o del vocabulario que haya asociado a esa propiedad. En algunos casos, el texto buscará valores en segundo plano: por ejemplo, ROR mostrará nombres de organizaciones con acrónimos coincidentes; ORCID mostrará nombres de investigadores que coincidan con un identificador ORCID que haya introducido. 

![Propiedad del elemento «Tema» con «moda» escrito en el campo. Un menú desplegable sugiere automáticamente términos, entre ellos «diseño de moda», que es el seleccionado.](../modules/modulesfiles/ValSug-ItemProperty1.png)

Pase el cursor sobre las opciones del menú desplegable para ver una descripción de ese vocabulario.

![Propiedad del elemento Material con «litografía» escrito en el campo. Un menú desplegable sugiere automáticamente términos, entre ellos «litografías en color», que es el seleccionado. El texto de ayuda en una pequeña ventana superpuesta dice: «Litografías impresas en varios colores.»](../modules/modulesfiles/ValSug-ItemProperty2.png)

Tras seleccionar un valor, debería aparecer un cuadro con una URL debajo del valor. Este enlace dirigirá a los visitantes a una página web con información adicional sobre el valor seleccionado. Este cuadro se puede eliminar haciendo clic en la «X».

![Propiedad del elemento «Tipo de obra» con «Ilustraciones de moda (características de maquetación)» seleccionada. Debajo, en rojo, hay un hipervínculo a Getty Collections, con una pequeña «X» roja.](../modules/modulesfiles/ValSug-ItemProperty3.png)

### Aplicar vocabularios por lotes

También puede aplicar los vocabularios de Value Suggest como tipos de datos a los **valores de propiedad existentes** de los recursos, independientemente de si utilizan alguna plantilla de recursos. Esto **no** establecerá un tipo de datos de Value Suggest en la propiedad de los recursos para su uso futuro, tal y como lo hace una plantilla de recursos. 

Esto permite convertir un valor de texto o URI existente en un valor reconocido de Value Suggest procedente de uno de sus vocabularios. Por ejemplo, es posible que haya introducido manualmente URI de RightsStatements en el campo de derechos de autor de muchos elementos y ahora desee convertir esos valores en una de las entradas estructuradas del «tipo de datos» RightsStatements de Value Suggest para que coincidan con futuras entradas. 

Esta conversión puede funcionar con valores de texto. Value Suggest busca la cadena de texto que coincida con un formato de URL (por ejemplo, «https://creativecommons.org/licenses/by/4.0/»). Si sus valores están en formato URI, Value Suggest buscará la coincidencia entre el valor URI o la cadena de texto de la etiqueta.

Para ello, seleccione los recursos deseados y edítelos por lotes. Busque el botón «Convertir tipo de datos» cerca de la parte inferior del formulario, en la sección «Valores». Seleccione la propiedad (por ejemplo, «Derechos» en Dublin Core) y, a continuación, elija el vocabulario de Value Suggest en el menú desplegable «Tipo de datos» (por ejemplo, Creative Commons o RightsStatements). 

![La pantalla de edición por lotes mostrando la opción «Convertir tipo de datos» expandida con la propiedad «Derechos» en la primera selección y «Creative Commons» en la segunda selección.](../modules/modulesfiles/ValSug-BatchConvert.png)

Al convertir un valor existente a un tipo de datos de Value Suggest, **la etiqueta estructurada no se importará** del vocabulario de origen a tus campos de metadatos. Si utilizas URI, se conservarán tus etiquetas existentes, o si los campos de etiqueta están vacíos, permanecerán así. Si utilizas valores de texto, se conservará el URI y se convertirá en un URI, pero el campo de etiqueta quedará vacío.

Puede comprobar si la conversión de tipo de datos se ha realizado correctamente al consultar el elemento en la interfaz de administración. El valor original, ya sea texto (sin enlace) o URI (enlace con un icono de sitio web externo a la derecha), debería aparecer ahora como un enlace sin icono. 

Recomendamos comprobar que la conversión se ha realizado correctamente entrando en el modo de edición de los recursos una vez finalizado el proceso y verificando que el valor muestra ahora el menú desplegable «Sugerencias de valor» correcto al hacer clic en él. En ese momento, puede seleccionar la etiqueta adecuada proporcionada por el vocabulario. 

## Sugerencias internas

Este módulo ofrece la posibilidad de sugerir valores almacenados actualmente en su instalación de Omeka, es decir, cuando un recurso ya tiene el valor en una propiedad:

- Omeka: Propiedad (valores de la misma propiedad, por ejemplo, `dcterms:creator`)
- Omeka: Propiedad / Plantilla de recurso (valores de la misma propiedad que están siendo utilizados por elementos que comparten la misma plantilla de recurso, por ejemplo, «Recurso base»)
- Omeka: Propiedad / Clase de recurso (valores de la misma propiedad que están siendo utilizados por elementos que comparten la misma clase, por ejemplo `dctype:StillImage`).

![Captura de pantalla del campo «Editor» utilizándose para sugerir varias opciones de otros elementos que comienzan por «Glasg».](modulesfiles/ValSug-OmekaProperty.png)

## Vocabularios disponibles

Este módulo incluye los siguientes vocabularios:

- Creative Commons
- Dublin Core
- Gemeinsame Normdaten (GND)
- GeoNames
- Los vocabularios Getty
- Homosaurus
- IdRef
- Servicio de datos enlazados de la Biblioteca del Congreso
- Nomenclatura
- Nuovo Soggettario
- Servicios de metadatos de OCLC
- ORCID (Identificador abierto de investigadores y colaboradores)
- Vocabularios controlados de PBCore
- PACTOLS de Frantiq
- PeriodO
- Vocabularios de valores RDA
- RightsStatements.org
- Registro de Organizaciones de Investigación (ROR)
- Tesauros del patrimonio cultural de España
- UNESCO
- Vocabularios del Ministerio de Cultura
- Tesauro de la Universitat de Barcelona (THUB).

Ten en cuenta que los [vocabularios de NDE Termennetwerk ya están disponibles como un módulo independiente](ndetermennetwerk.md). Ese módulo requiere que Value Suggest esté instalado y activo.

!!! nota
  Algunos vocabularios aparecen en varios idiomas en la lista siguiente: por ejemplo, Homosaurus (en inglés) aparece por separado de la traducción al neerlandés de Homosaurus que se encuentra en el [módulo NDE Termennetwerk](ndetermennetwerk.md). Busque en la lista y consulte los servicios para ver qué idiomas admiten. Hemos indicado aquí los idiomas de los servicios que prestan servicio principalmente en un idioma (distinto del inglés).

### [Creative Commons (CC)](https://creativecommons.org/share-your-work/cclicenses/)

- Proporciona una forma estandarizada de conceder al público permiso para utilizar sus obras creativas en virtud de la ley de derechos de autor.

### [Dublin Core (Términos de metadatos DCMI)](https://www.dublincore.org/specifications/dublin-core/dcmi-terms/){target=_blank}

- Clases
- Elementos
- Términos
- Tipos.

### [Gemeinsame Normdatei (GND)](http://lobid.org/gnd){target=_blank} (`de`)

- El GND contiene entradas estandarizadas para personas, corporaciones, congresos, áreas geográficas, palabras clave y títulos de obras.

### [GeoNames](http://www.geonames.org/){target=_blank}

- La base de datos geográfica de GeoNames
- Características de GeoNames.

### [Los vocabularios del Getty](https://www.getty.edu/research/tools/vocabularies/index.html){target=_blank}

- El Tesauro de Arte y Arquitectura (AAT)
- El Tesauro de Nombres Geográficos del Getty (TGN)
- La Lista Unificada de Nombres de Artistas (ULAN)
- Autoridad de Nombres de Objetos Culturales (CONA)
- Autoridad Iconográfica del Getty (IA).

### [Homosaurus](http://homosaurus.org/){target=_blank}

- Vocabulario de datos enlazados de Homosaurus.org.

### [IdRef](https://www.idref.fr/){target=_blank} (`fr`)

- Base de datos nacional francesa de identificadores para la investigación (todos los repositorios)
- Nombres de personas
- Colectividades (Corporaciones)
- Conferencias
- Encabezamientos de materia (todos)
- Encabezamientos de materia [RAMEAU](https://rameau.bnf.fr){target=_blank} (Répertoire d’autorité-matière encyclopédique et alphabétique unifié, o Lista unificada enciclopédica y alfabética de autoridades de materia)
- Encabezamientos de materia [F-MeSH](http://mesh.inserm.fr/FrenchMesh){target=_blank} (versión francesa de los encabezamientos de materia médicos)
- Nombres geográficos
- Apellidos
- Títulos
- Autores-Títulos
- Marcas registradas
- PPN (identificador único utilizado para cualquier elemento de toda la base de datos)
- Bibliotecas (RCR: Répertoire des centres de ressources).

### [Servicio de datos enlazados de la Biblioteca del Congreso](http://id.loc.gov/){target=_blank}

- Todo
- Encabezamientos de materia
- Fichero de autoridad de nombres (LCNAF)
- Clasificación
- Encabezamientos de materia infantiles
- Términos de género/forma (LCGFT)
- Tesauro de medios de interpretación musical
- Términos de grupos demográficos
- Tesauro de materiales gráficos
- Tesauro etnográfico de la AFS
- Organizaciones de patrimonio cultural
- Idiomas ISO 639-1
- Idiomas ISO 639-2
- Idiomas ISO 639-5
- Países MARC
- Áreas geográficas MARC
- Idiomas MARC
- Reladores MARC
- Catalogación de materiales raros de la LC.

### [Nomenclatura para la catalogación de museos](https://page.nomenclature.info/apropos-about.app?lang=en){target=_blank}

- Todo
- Categoría 01: Objetos del entorno construido
- Categoría 02: Mobiliario
- Categoría 03: Objetos personales
- Categoría 04: Herramientas y equipos para materiales
- Categoría 05: Herramientas y equipos para ciencia y tecnología
- Categoría 06: Herramientas y equipos para la comunicación
- Categoría 07: Objetos de distribución y transporte
- Categoría 08: Objetos de comunicación
- Categoría 09: Objetos recreativos
- Categoría 10: Objetos inclasificables.

### [Nuevo Sujetario](https://thes.bncf.firenze.sbn.it/){target=_blank} (`it`)

- Agentes: Organismos
- Agentes: Organizaciones
- Agentes: Personas y grupos
- Acciones: Actividades
- Acciones: Disciplinas
- Acciones: Procesos
- Cosas: Formas
- Cosas: Materia
- Cosas: Objetos
- Cosas: Espacio
- Cosas: Instrumentos
- Cosas: Estructuras
- Tiempo.

### [Servicios de metadatos de OCLC](https://www.oclc.org/en/services/a-z.html/:F2664:/){target=_blank}

- El Archivo Virtual Internacional de Autoridades (VIAF)
- Aplicación facetada de terminologías temáticas (FAST).

### [ORCID (Identificador abierto de investigadores y colaboradores)](https://info.orcid.org/){target=_blank}

- ORCID. Busca por nombre o introduciendo un número ORCID y seleccionando el nombre en el menú desplegable.

### [Vocabularios controlados de PBCore](https://pbcore.org/pbcore-controlled-vocabularies)

- pbcoreAssetType
- @dateType
- @titleType
- @descriptionType
- pbcoreRelationType
- instantiationRelationType
- creatorRole y contributorRole
- publisherRole
- instantiationPhysical: Audio
- instantiationPhysical: Película
- instantiationPhysical: Vídeo
- instantiationMediaType
- instantiationGenerations.

### [PACTOLS de Frantiq](https://pactols.frantiq.fr/){target=_blank} (`fr`)
 
- El tesauro PACTOLS completo
- Solo el grupo de temas.

### [PeriodO](http://perio.do/en/){target=_blank}

- Un nomenclátor de definiciones de períodos para vincular y visualizar datos.

### [Vocabularios de valores RDA](http://www.rdaregistry.info/termList/){target=_blank}

#### Vocabularios de valores de referencia RDA

- Designación de la relación de aspecto
- Formato bibliográfico
- Norma de radiodifusión
- Unidad de extensión de la portadora
- Tipo de portadora
- Tipo de datos cartográficos
- Contenido de color
- Configuración de los canales de reproducción
- Tipo de contenido
- Título colectivo convencional
- Tipo de archivo
- Tamaño de fuente
- Forma de notación musical
- Forma de movimiento notado
- Forma de notación táctil
- Formato de la música notada
- Frecuencia
- Generación
- Altura del surco de un cilindro analógico
- Ancho del surco de un disco analógico
- Contenido ilustrativo
- Maquetación
- Material
- Tipo de soporte
- Modo de publicación
- Polaridad
- Formato de presentación
- Método de producción
- Soporte de grabación
- Designación de la relación de reducción
- Codificación regional
- Designación de escala
- Contenido sonoro
- Características especiales de reproducción
- Estado de identificación
- Términos
- Configuración de la pista
- Tipo de grabación
- Formato de vídeo.

#### Vocabularios de valores locales de RDA

- Género.

#### Vocabularios de valores del marco RDA/ONIX

- Carácter
- Modo de extensión
- Requisito de extensión
- Terminación de la extensión
- Formato de alojamiento
- Dimensionalidad de la imagen
- Movimiento de la imagen
- Interacción
- Herramienta de intermediación
- Modo de revisión
- Requisito de revisión
- Terminación de la revisión
- Modo sensorial
- Formato del soporte de almacenamiento.

### [RightsStatements.org](https://rightsstatements.org/){target=_blank}

- Declaraciones de derechos estandarizadas para instituciones del patrimonio cultural que pueden utilizarse para comunicar al público el estado de los derechos de autor y la reutilización de los objetos digitales.

### [Registro de Organizaciones de Investigación (ROR)](https://ror.org/){target=_blank}

- El Registro de Organizaciones de Investigación (ROR) es un registro global, gestionado por la comunidad, de identificadores abiertos y persistentes para organizaciones de investigación.

### [Tesauros del patrimonio cultural de España](http://tesauros.mecd.es/tesauros){target=_blank} (`es`)

- Diccionario de Bienes Culturales
- Diccionario de Materias
- Diccionario de Técnicas
- Diccionario de Contextos Culturales
- Diccionario Geográfico
- Diccionario de Toponimia Histórica
- Diccionario de Cerámica
- Diccionario de Numismática
- Diccionario de Mobiliario.

### [UNESCO](http://skos.um.es/){target=_blank} (`es`)

- Tesauro
- Nomenclatura de Ciencia y Tecnología
- Biblioteca Digital Floridablanca.

### [Vocabularios del Ministerio de Cultura](http://data.culture.fr/thesaurus/){target=_blank} (`fr`)

- Categorías técnicas y ámbitos - Inventario/MH
- Ámbitos archivísticos para la indexación de circulares
- Estado de conservación del patrimonio mueble - Inventario/MH
- Inscripciones, marcas, emblemas y punzones - Inventario/MH
- Lista de autoridad Acciones para la indexación de los archivos locales
- Lista de autoridad Contexto histórico para la indexación de los archivos locales
- Lista de autoridad Tipología documental para la indexación de los archivos locales
- Lista de autoridades Autores - Joconde
- Lista de autoridades Ámbitos - Joconde
- Lista de autoridades Descubrimiento - Joconde
- Lista de autoridades Denominación - Joconde
- Lista de autoridades Génesis - Joconde
- Lista de autoridades Inscripciones - Joconde
- Lista de autoridades: Lugares - Joconde
- Lista de autoridades: Localización - Joconde
- Lista de autoridades: Periodos - Joconde
- Lista de autoridades: Representación - Joconde
- Lista de autoridades: Fuentes de la representación - Joconde
- Lista de autoridades Técnicas – Joconde
- Lista de autoridades Uso - Joconde
- Lista de autoridades Escuelas - Joconde
- Lista de autoridades Épocas - Joconde
- Material de la cubierta - Inventario/MH
- Material de la obra gruesa y ejecución - Inventario/MH
- Materiales y técnicas del patrimonio mueble - Inventario/MH
- Nomenclaturas HADOC
- Referencial de comunicabilidad de los archivos públicos
- Etapa de creación de los objetos muebles - Inventario/MH
- Régimen de propiedad de los bienes culturales - Inventario/MH
- Técnicas fotográficas
- Tesauro de la designación de los objetos muebles
- Tesauro de la designación de obras arquitectónicas y espacios acondicionados
- Tesauro temático para la indexación de los archivos locales
- Tipo de cubierta - Inventario/MH
- Tipo de protección MH - Inventario/MH
- Vocabulario de las actividades de las entidades productoras de archivos
- Vocabulario de las alteraciones
- Vocabulario de los ámbitos de actuación u objetos de las entidades productoras de archivos
- Vocabulario para las técnicas fotográficas.

### [Tesauro de la Universitat de Barcelona (THUB)](https://vocabularis.crai.ub.edu/ca/thub){target=_blank} (`es`)
 
- Tesauro de la Universitat de Barcelona (THUB).

## Solicitar más vocabularios

Puedes solicitar que se añadan nuevos vocabularios a este módulo. Ponte en contacto con el equipo de Omeka en [el repositorio GitHub dedicado al módulo](https://github.com/omeka-s-modules/ValueSuggest){target=_blank}, creando una incidencia y compartiendo los vocabularios que te gustaría que se añadieran. 

Quizá te interese utilizar o bifurcar [el módulo NDE Termennetwerk](https://github.com/omeka-s-modules/NdeTermennetwerk/){target=_blank}, que es una bifurcación de este módulo diseñada específicamente para proporcionar [términos de la Red de Patrimonio Digital Neerlandés](https://termennetwerk.netwerkdigitaalerfgoed.nl/en){target=_blank}. 
