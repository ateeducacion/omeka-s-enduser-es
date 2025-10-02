# Glosario

El siguiente glosario debería ayudar a aclarar algunos de los términos menos familiares en Omeka S. Cuando ha sido apropiado, hemos proporcionado un término análogo de Omeka Classic, aunque algunas analogías son más fieles que otras.

**Clase (Class)**: Un tipo de Recurso, tal como se define en un Vocabulario. A menudo, los Vocabularios esperan que se usen Propiedades particulares con Clases particulares. Por ejemplo, una `foaf:Person` (Persona) no tendría una Propiedad `dcterms:publisher` (editor), but sí se esperaría que tuviera una Propiedad `foaf:familyName` (apellido).
*Analogía con Omeka Classic*: Tipo de Elemento (Item Type).

**Archivo (File)**: Datos subidos a una instalación de Omeka S y asociados directamente con un Elemento (ver también: Medio).
*Analogía con Omeka Classic*: Archivo (File) (aunque la analogía es débil).

**Administrador Global (Global Admin)**: Un administrador que controla todo, y típicamente es la persona que creó la Instalación.
*Analogía con Omeka Classic*: Superusuario (Superuser).

**Instalación (Installation)**: Una instancia de Omeka S. Típicamente, un departamento de TI central de una institución realiza el proceso de instalación, y probablemente también crea sitios para otros.

**Elemento (Item)**: Los registros utilizados para construir un Sitio de Omeka S. Los Elementos se comparten y están disponibles para cualquier Sitio en una Instalación, a menos que se excluyan explícitamente de ser compartidos.
*Analogía con Omeka Classic*: Elemento (Item).

**Conjunto de elementos (Item Set)**: Una agregación de Elementos. Los Elementos pueden pertenecer a cualquier número de Conjuntos de elementos.
*Analogía con Omeka Classic*: Colección (Collection); Elementos con la misma etiqueta (tag).

**Medio (Media)**: Representaciones o descripciones adicionales de un Elemento, más allá de los metadatos de los vocabularios. Típicamente, esto se refiere to un Archivo (de cualquier tipo, incluyendo, por ejemplo, fragmentos de texto o HTML), pero también podría referirse a fuentes de datos externas como un video de YouTube, una presentación de Slideshare, un bitstream de Dspace, etc.
*Analogía con Omeka Classic*: Archivo (File) (aunque la analogía es débil).

**Módulo (Module)**: Un complemento para su instalación de Omeka S que amplía su funcionalidad. Los Módulos pueden añadir opciones a la entrada de datos y a la interacción en la interfaz de administración, y añadir nuevas características a sus sitios.
*Analogía con Omeka Classic*: Plugin.

**Propiedad (Property)**: Un tipo de metadato definido —en mayor o menor grado— que se utiliza para describir un Recurso. La más común es `dcterms:title`, para el título escrito y legible por humanos de un Elemento. Los Valores para las Propiedades pueden ser lenguaje escrito destinado a que los humanos u otros seres sensibles lo lean (‘Literales’), Recursos (entendidos aquí como internos a una instalación de Omeka S), o URIs Externas (por ejemplo, una URI a una página de recursos de DBpedia).
*Analogía con Omeka Classic*: Elemento (Element).

**Plantilla de recursos (Resource Template)**: Un conjunto de Propiedades predefinidas, y opcionalmente una Clase, para guiar la creación de Elementos y la interpretación de Propiedades. El uso típico es crear una plantilla para, por ejemplo, una `foaf:Person` (Persona) que haga que los Elementos que usan esa plantilla muestren los campos para las propiedades `foaf:` esperadas o deseadas, y establezca la Clase del Elemento como `foaf:Person`.
*Analogía con Omeka Classic*: Tipo de Elemento (Item Type) (aunque la analogía es débil). Cf. Clase.

**Administrador de Sitio (Site Admin)**: Un administrador de un único Sitio dentro de una Instalación de Omeka S.
*Analogía con Omeka Classic*: Rol de Superusuario (Superuser).

**Valor (Value)**: El dato real que completa la terna Recurso-Propiedad-Valor. Si la propiedad es `dcterms:title`, un Valor razonable podría ser "El corazón de las tinieblas". Los Valores literales también pueden tener adjunta información sobre el idioma en el que se expresa ese Valor. Los Valores también pueden ser Recursos o URIs a datos externos (preferiblemente URIs que devuelvan datos RDF, aunque no creemos que vayamos a forzar eso).
*Analogía con Omeka Classic*: Texto del Elemento (Element Text).

**Vocabulario (Vocabulary)**: Una colección de Clases y Propiedades de metadatos RDF publicadas para describir un Recurso. Estos existen y se crean externamente a Omeka, y pueden ser importados (con algunas limitaciones) a Omeka S para su uso en toda la Instalación. El Vocabulario más utilizado es Dublin Core Terms (`dcterms:`).
*Analogía con Omeka Classic*: Conjunto de Elementos (Element Set).