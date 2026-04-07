# Glosario

El siguiente glosario debería ayudar a aclarar algunos de los términos menos conocidos de Omeka S. Cuando ha sido oportuno, hemos incluido un término más o menos equivalente de Omeka Classic, aunque algunas analogías son más evidentes que otras. 

**Clase**: Un tipo de recurso, tal y como lo define un vocabulario. A menudo, los vocabularios esperan que se utilicen propiedades concretas con clases concretas. Por ejemplo, un `foaf:Person` no tendría una propiedad `dcterms:publisher`, pero cabría esperar que tuviera una propiedad `foaf:familyName`.  
*Analogía con Omeka Classic*: Tipo de elemento.

**Archivo**: Datos cargados en una instalación de Omeka S y asociados directamente a un elemento (véase también: Medios).    
*Analogía con Omeka Classic*: Archivo (pero la analogía es débil).

**Administrador global**: Un administrador que lo controla todo y que suele ser la persona que creó la instalación.  
*Analogía con Omeka Classic*: Superusuario.

**Instalación**: Una instancia de Omeka S. A veces, el departamento central de TI de una institución se encarga de configurar y mantener la instalación y sus módulos para que otros los utilicen. En otros casos, una instalación solo tiene un administrador y mantenedor, además de un usuario que ha iniciado sesión. 

**Elemento**: Los registros utilizados para construir un sitio de Omeka S. Los elementos se comparten y están disponibles para cualquier sitio de una instalación, a menos que se excluyan explícitamente del uso compartido.  
*Analogía con Omeka Classic*: Elemento.

**Conjunto de elementos**: Una agrupación de elementos. Los elementos pueden pertenecer a cualquier número de conjuntos de elementos.  
*Analogía con Omeka Classic*: Colección; elementos con la misma etiqueta.

**Medios**: Añadidos a un elemento, los medios aportan el «contenido» a la descripción de un elemento (sus metadatos). Normalmente, «medios» se refiere a un archivo de cualquier tipo, pero también podría referirse a un archivo adjunto de texto sin formato o con formato HTML, fuentes de datos externas como un vídeo de YouTube, una presentación de Slideshare, un flujo de bits de DSpace, etc. Un elemento puede tener un número infinito de medios, mientras que los medios solo existen adjuntos a un elemento. (Consulte «Recursos» si necesita archivos no adjuntos a elementos, como logotipos y banners del sitio). 
*Analogía con Omeka Classic*: Archivo.

**Módulo**: Un complemento para su instalación de Omeka S que amplía la funcionalidad de Omeka S. Los módulos pueden añadir opciones a la introducción de datos y la interacción en el back-end, así como nuevas funciones a sus sitios.  
*Analogía con Omeka Classic*: Complemento.

**Propiedad**: Un tipo de metadatos definido —en mayor o menor medida— que se utiliza para describir un recurso. La más común es dcterms:title, para el título escrito y legible por humanos de un elemento. Los valores de las propiedades pueden ser lenguaje escrito destinado a ser leído por humanos u otros seres sensibles («literales»), recursos (entendidos aquí como internos a una instalación de Omeka S) o URI externos (por ejemplo, un URI a una página de recursos de DBpedia).  
*Analogía con Omeka Classic*: Elemento.

**Recurso**: En general, un término que se refiere a elementos, medios y conjuntos de elementos. No incluye activos. Un recurso puede tener una descripción de metadatos (propiedades y valores), una clase de recurso y utilizar una plantilla. Los recursos se pueden mostrar de diferentes maneras en cada sitio, utilizando los ajustes de «Configurar páginas de recursos» que se incluyen en cada tema activo. 

**Plantilla de recurso**: Un conjunto de propiedades predefinidas y, opcionalmente, una clase, que se utiliza para guiar la creación de elementos y la interpretación de las propiedades. Un uso típico es crear una plantilla para, por ejemplo, un `foaf:Person`, que hace que los elementos que utilizan esa plantilla muestren las entradas para las propiedades `foaf:` esperadas o deseadas, y establece la clase del elemento como `foaf:Person`. 
*Analogía con Omeka Classic*: Tipo de elemento (aunque la analogía es débil).

**Administrador del sitio**: Un administrador de un único sitio dentro de una instalación de Omeka S.  
*Analogía con Omeka Classic*: Rol de superusuario.

**Valor**: Los datos reales que completan la tripleta recurso-propiedad-valor. Si la propiedad es `dcterms:title`, un valor razonable podría ser «El corazón de las tinieblas». Los valores literales también pueden incluir información sobre el idioma en el que se expresa dicho valor. Los valores también pueden ser recursos o URI a datos externos (preferiblemente URI que devuelvan datos RDF, pero no creo que vayamos a imponerlo).   
*Analogía con Omeka Classic*: Texto del elemento.

**Vocabulario**: Una colección de clases y propiedades de metadatos RDF publicadas para describir un recurso. Estas existen y se crean externamente a Omeka, y pueden importarse (con algunas limitaciones) a Omeka S para su uso en toda la instalación. El vocabulario más utilizado es Dublin Core Terms (`dcterms:`).  
*Analogía con Omeka Classic*: Conjunto de elementos.
