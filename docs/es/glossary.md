# Glosario

El siguiente glosario debería ayudar a aclarar algunos de los términos menos conocidos de Omeka S. Cuando ha sido oportuno, hemos incluido un término más o menos análogo de Omeka Classic, aunque algunas analogías son más evidentes que otras. 

## **Clase**: 
Un tipo de recurso, tal y como lo define un vocabulario. A menudo, los vocabularios esperan que se utilicen propiedades concretas con clases concretas. Por ejemplo, un `foaf:Person` no tendría una propiedad `dcterms:publisher`, pero cabría esperar que tuviera una propiedad `foaf:familyName`.  

*Analogía con Omeka Classic*: Tipo de elemento.

## **Archivo**: 

Datos subidos a una instalación de Omeka S y asociados directamente a un elemento (véase también: Multimedia). 

*Analogía con Omeka Classic*: Archivo (aunque la analogía es débil).

## **Administrador global**: 
Un administrador que lo controla todo y que suele ser la persona que creó la instalación.  

*Analogía con Omeka Classic*: Superusuario.

## **Instalación**: 
Una instancia de Omeka S. A veces, el departamento central de TI de una institución se encarga de configurar y mantener la instalación y sus módulos para que otros los utilicen. En otros casos, una instalación solo tiene un administrador y responsable de mantenimiento, además de un usuario que ha iniciado sesión. 

En Omeka Classic, una instalación de Classic equivaldría a un sitio, con páginas de navegación y funciones de búsqueda; cada sitio de Classic puede contener muchas exposiciones. En Omeka S, la principal diferencia es que una instalación no tiene necesariamente un sitio predeterminado, sino que puede tener muchos sitios. Cada sitio es independiente, con su propia imagen de marca, páginas de navegación, páginas de búsqueda y tantas exposiciones como se desee. Un uso habitual es que cada «sitio» sea su propia exposición. 

## **Elemento**: 
Los registros utilizados para crear un sitio de Omeka S. Los elementos se comparten y están disponibles para cualquier sitio de una instalación, a menos que se excluyan explícitamente del uso compartido.  

*Analogía con Omeka Classic*: Elemento.

## **Conjunto de elementos**: 
Una agrupación de elementos. Los elementos pueden pertenecer a cualquier número de conjuntos de elementos.  

*Analogía con Omeka Classic*: Colección; Elementos con la misma etiqueta.

## **Mapeo**:

Omeka S utiliza el término «mapeo» en dos sentidos. Uno se refiere a nuestro [módulo de mapeo](modules/mapping.md), que ofrece utilidades de geolocalización para situar elementos y otros recursos en mapas navegables. En Omeka Classic, el complemento análogo al módulo de mapeo se llama «Geolocalización». 

El otro es un significado propio del mundo de los metadatos, donde «mapeo» significa tomar un campo de metadatos y asignarlo a otro. Un término similar es «crosswalking»: por ejemplo, se podría crear una correspondencia entre Dublin Core y MODS, transfiriendo datos del campo `Title` de Dublin Core al campo `titleInfo` de MODS. Al importar información desde hojas de cálculo u otras bases de datos, será necesario asignar los campos utilizados en los recursos remotos a los campos que desees utilizar en tu instalación de Omeka. También puedes considerar esto como una migración o conversión de metadatos. 


## **Medios**: 
Al añadirse a un elemento, los medios aportan el «contenido» a la descripción de dicho elemento (sus metadatos). Normalmente, «contenido multimedia» se refiere a un archivo de cualquier tipo, pero también podría referirse a un archivo adjunto de texto sin formato o con formato HTML, fuentes de datos externas como un vídeo de YouTube, una presentación de Slideshare, un flujo de bits de DSpace, etc. Un elemento puede tener un número ilimitado de contenidos multimedia, mientras que estos solo existen adjuntos a un único elemento. (Consulta «Recursos» si necesitas archivos que no estén adjuntos a elementos, como logotipos y banners del sitio). 

*Analogía con Omeka Classic*: Archivo.

## **Módulo**: 
Un complemento para tu instalación de Omeka S que amplía la funcionalidad de Omeka S. Los módulos pueden añadir opciones a la introducción de datos y a la interacción en el back-end, así como nuevas funciones a tus sitios web.  

*Analogía con Omeka Classic*: Complemento.

## **Propiedad**: 
Un tipo de metadato definido —en mayor o menor medida— que se utiliza para describir un recurso. La más común es `dcterms:title`, que corresponde al título escrito y legible por humanos de un elemento. Los valores de las propiedades pueden ser texto escrito destinado a ser leído por personas u otros seres sensibles («literales»), recursos (entendidos aquí como internos a una instalación de Omeka S) o URI externos (por ejemplo, un URI a una página de recursos de DBpedia).  

*Analogía con Omeka Classic*: Elemento.

## **Recurso**: 
En general, término que hace referencia a elementos, medios y conjuntos de elementos. No incluye activos. Un recurso puede tener una descripción de metadatos (propiedades y valores), una clase de recurso y utilizar una plantilla. Los recursos pueden mostrarse de diferentes formas en cada sitio, utilizando los ajustes de «Configurar páginas de recursos» que contiene cada tema activo. 

## **Plantilla de recurso**: 
Un conjunto de propiedades predefinidas y, opcionalmente, una clase, que se utiliza para guiar la creación de elementos y la interpretación de las propiedades. Un uso típico es crear una plantilla para, por ejemplo, un `foaf:Person`, que haga que los elementos que utilicen esa plantilla muestren los campos correspondientes a las `foaf: propiedades` esperadas o deseadas, y establezca la clase del elemento como `foaf:Person`. 

*Analogía con Omeka Classic*: Tipo de elemento (aunque la analogía es poco precisa).

## **Administrador del sitio**: 
Un administrador de un único sitio dentro de una instalación de Omeka S.  

*Analogía con Omeka Classic*: rol de superusuario.

## **Valor**: 
Los datos reales que completan la tripleta «recurso-propiedad-valor». Si la propiedad es `dcterms:title`, un valor razonable podría ser «El corazón de las tinieblas». Los valores literales también pueden incluir información sobre el idioma en el que se expresa dicho valor. Los valores también pueden ser recursos o URI que apunten a datos externos (preferiblemente URI que devuelvan datos RDF, aunque no creo que vayamos a exigirlo).   

*Analogía con Omeka Classic*: Texto del elemento.

## **Vocabulario**: 
Conjunto de clases y propiedades de metadatos RDF publicadas para describir un recurso. Estas existen y se crean fuera de Omeka, y pueden importarse (con algunas limitaciones) a Omeka S para su uso en toda la instalación. El vocabulario más utilizado es Dublin Core Terms (`dcterms:`).  

*Analogía con Omeka Classic*: Elemento «Conjunto».