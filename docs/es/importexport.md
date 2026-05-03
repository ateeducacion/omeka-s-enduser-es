# Importación y exportación

Existen numerosos métodos para importar a un sitio de Omeka S o exportar desde él. Los módulos de terceros pueden añadir más funcionalidades; aquí solo documentamos los métodos respaldados por el equipo de Omeka. 

## Conectarse a otro sitio de Omeka

### Importar de Classic a S

Puede utilizar el [módulo Omeka Classic Importer](modules/omekaCimporter.md) para importar elementos y colecciones desde un sitio Classic. Este módulo solo importa elementos y sus metadatos (incluidas las etiquetas), archivos adjuntos y colecciones (como conjuntos de elementos). No importará contenido de Simple Page ni de Exhibit Builder.

Si hay plugins o módulos equivalentes instalados tanto en el sitio de origen como en el de destino, Omeka Classic Importer puede importar metadatos específicos de los módulos. Por ejemplo, los datos de geolocalización facilitados por el módulo Mapping en S y el plugin Geolocation en Classic se importarán automáticamente; Los elementos [Texto PDF](https://omeka.org/classic/plugins/PdfText/){target=_blank} se pueden importar y asignar a campos [Texto extraído](https://omeka.org/s/modules/ExtractText/){target=_blank}.

Actualmente no es posible exportar directamente desde un sitio de Omeka S a un sitio de Classic. Consulte a continuación las opciones para exportar e importar mediante hojas de cálculo. 

### Importar de S a S

Puede utilizar el [módulo Omeka S Item Importer](modules/ositemimporter.md) para importar elementos y conjuntos de elementos de una instalación de Omeka S a otra. No es posible importar sitios ni sus páginas. Le recomendamos que configure el sitio de destino de la forma más similar posible al sitio de origen, incluyendo la instalación y activación de todos los mismos módulos, así como la instalación de cualquier vocabulario utilizado, antes de realizar la importación.

### Importar o exportar plantillas de recursos 

[Puede compartir una plantilla de recursos entre instalaciones de Omeka S exportándola e importándola.](https://omeka.org/s/docs/user-manual/content/resource-template/#share-resource-templates)

### Importar o exportar vocabularios personalizados

[Puede compartir un vocabulario personalizado entre instalaciones de Omeka S exportándolo e importándolo.](https://omeka.org/s/docs/user-manual/modules/customvocab/#manage-custom-vocabs)

## Conectarse a plataformas ajenas a Omeka

Omeka se conecta fácilmente a otras plataformas desarrolladas por la [Corporation for Digital Scholarship](https://digitalscholar.org/){target=_blank}. 

- Omeka S cuenta con un módulo para importar elementos desde [Zotero](https://zotero.org){target=_blank}. Zotero es una herramienta de gestión de investigación que se puede utilizar para organizar artículos de revistas y materiales de lectura. Se pueden organizar elementos allí y luego exportarlos como elementos de Omeka S utilizando el [módulo de importación de Zotero](modules/zoteroimport.md), o insertar una bibliografía o citas individuales en una página del sitio de Omeka S utilizando el [módulo de citas de Zotero](modules/zoterocitation.md). 
- [Tropy](https://tropy.org){target=_blank} cuenta con un complemento para exportar elementos a Omeka S. Tropy se puede utilizar para gestionar, editar y describir imágenes digitales de materiales de archivo y patrimonio, y resulta especialmente útil para combinar múltiples imágenes de un mismo elemento (por ejemplo, libros, cartas con muchas páginas, álbumes de fotos, etc.). Instala Tropy y [añade allí el complemento «Exportar a Omeka S»](https://docs.tropy.org/other-features/omeka){target=_blank}. 

Omeka S también cuenta con módulos para importar recursos desde: 

- [Zenodo](modules/datarepositoryconnector.md)
- [Fedora](modules/fedoraconnector.md)
- [DSpace](modules/dspaceconnector.md)
- [CKAN](modules/datarepositoryconnector.md)
- [Dataverse](modules/datarepositoryconnector.md)
- [Invenio](modules/datarepositoryconnector.md). 

### Importar desde una hoja de cálculo

Omeka S puede aceptar datos en cualquier formato de hoja de cálculo (tabular), ya sea un CSV, un archivo de Excel o un ODS. Utilice el [módulo de importación CSV](modules/csvimport.md) para añadir elementos, conjuntos de elementos, medios y usuarios a su sitio de Omeka S desde una hoja de cálculo. Esto incluye datos exportados desde muchas bases de datos y plataformas diferentes. 

En primer lugar, compruebe si existe un módulo de conexión o importación para la plataforma desde la que desea exportar. Omeka S cuenta con módulos para Zotero, Zenodo, Fedora, DSpace, CKAN, Dataverse e Invenio. Si no hay un módulo específico, exporte los datos desde su plataforma de origen a una hoja de cálculo. Esto puede requerir alguna modificación o limpieza de los datos antes de importarlos a Omeka S. 

### Exportar a una hoja de cálculo

Es posible exportar recursos desde Omeka S utilizando un script de Python para consultar la API de la instalación. Puede utilizarlo para copiar sus materiales de Omeka S a otra plataforma, o como copia de seguridad de su trabajo.

[Omeka-s-csv.py](https://github.com/omeka/omeka-s-csv.py){target=_blank} es un script de Python que exporta datos de instalaciones de Omeka S en formato CSV.

Las hojas de cálculo resultantes tendrán encabezados de columna para los términos de metadatos en orden alfabético: `dcterms:description`, `dcterms:title`, etc. 

También habrá una sección de columnas `o:`, que incluye el ID interno de Omeka S (`o:id`), los ID internos de los archivos multimedia adjuntos a los elementos (`o:media`), la configuración de privacidad (`o:is_public`, con valores de «TRUE» o «FALSE»), las fechas de creación y modificación, los propietarios, los sitios y otros datos de los recursos. Al final habrá columnas `thumbnail` que contienen las URL de las miniaturas de los archivos multimedia generadas por la instalación. 

Este script no puede exportar información del sitio o de las páginas, ni exportará plantillas de recursos, vocabularios u otros datos almacenados en módulos (como la configuración de Propiedades inversas en las plantillas de recursos). 

#### Requisitos

omeka-s-csv.py funciona tanto con Python 2 como con Python 3, y no requiere dependencias adicionales ni externas.

Es probable que los usuarios de Linux ya tengan Python instalado, y los paquetes deberían estar disponibles en su distribución. Existen varias opciones para instalar Python en Windows y Mac, incluida la descarga de un instalador [desde el sitio web de Python](https://www.python.org/downloads/).

#### Exportación

En un terminal, dentro de la carpeta donde se encuentra `omeka-s-csv.py` en su sistema, ejecute el script:

```
python3 omeka-s-csv.py
```

(Dependiendo del sistema, esto también se puede hacer como `./omeka-s-csv.py`, `python omeka-s-csv.py` o `python2 omeka-s-csv.py`.)

El script le pedirá el punto final de la API de Omeka S desde el que desea exportar. Se trata de una URL que apunta a la instalación de Omeka S de destino, y debe comenzar por `http://` o `https://` y terminar en `/api`.

A continuación, se le pedirá una clave API. Las claves son necesarias para exportar datos no públicos del sitio, pero son opcionales si solo va a exportar datos públicos. Si no utiliza una clave, puede dejar el campo en blanco y simplemente pulsar «Intro».

Por último, aparecerá un mensaje pidiéndole que introduzca un «separador», un carácter que se utilizará para separar varios datos en una sola celda CSV. Es importante que el separador elegido sea un carácter que no aparezca en los datos reales. La opción predeterminada es el carácter «barra vertical» (`|`), que suele ser una opción segura. Para utilizar esa opción predeterminada, pulsa «Intro»; de lo contrario, escribe el carácter separador que desees utilizar en su lugar.

A continuación, se ejecutará el script y mostrará un resultado que indica su progreso. Los resultados exportados se colocarán en archivos en la misma carpeta que el archivo `omeka-s-csv.py`: `items.csv`, `item_sets.csv` y `media.csv`.

### Acceder a los datos mediante la API

Puede utilizar la API de su propio sitio S para rastrear datos según sea necesario, en lugar de exportar una hoja de cálculo para un uso único. Tenga en cuenta que puede [solicitar diferentes formatos a través de la API](https://omeka.org/s/docs/developer/api/rest_api/#responses){target=_blank}, incluidos `jsonld` y `rdfxml`. [Para obtener más información sobre la API, consulta la sección de documentación para desarrolladores.](https://omeka.org/s/docs/developer/api/){target=_blank}

### Acceder a los datos mediante el módulo Formatos de salida

Se puede acceder a una versión fácil de usar de los mismos datos disponibles en la API instalando el [módulo Formatos de salida](modules/outputformats.md). Esto añadirá automáticamente un menú desplegable de salida a todas las páginas de la interfaz administrativa con resultados de navegación y búsqueda, así como a las vistas de recursos individuales. El módulo también se puede habilitar para páginas públicas, lo que permite a cualquier persona exportar un conjunto de datos desde un subconjunto de navegación o búsqueda. 

Los formatos de salida disponibles para este módulo son:

- [JSON-LD](https://json-ld.org/){target=_blank}
- [Notation3](https://www.w3.org/wiki/NotationThree){target=_blank}
- [N-Triples](https://dbpedia.org/page/N-Triples){target=_blank}
- [RDF/XML](https://www.w3schools.com/XML/xml_rdf.asp){target=_blank}
- [Turtle](https://www.w3.org/TR/rdf12-turtle/){target=_blank}.

Consulte la documentación del módulo Formatos de salida para obtener más detalles. 
