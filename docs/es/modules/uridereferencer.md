# Desreferenciador de URI

El [módulo Desreferenciador de URI](https://omeka.org/s/modules/UriDereferencer/){target=_blank} permite que las páginas muestren dinámicamente datos procedentes de numerosas URI en las páginas de elementos, medios y conjuntos de elementos de Omeka. 

Este módulo no tiene ajustes de configuración y no añade funciones al panel de administración. Aparece en la interfaz de usuario, en los URI reconocibles de los [servicios de datos enlazados](#linked-data-services) integrados, en cualquier vista de recurso donde se haya introducido un URI como valor de metadatos.

![Dos URI en el campo Creador con enlaces de alternancia [+] junto a ellos.](modulesfiles/uri-display.png)

Este módulo busca URI en la página y ofrece a los usuarios una instantánea de los datos enlazados sin necesidad de salir de la página. Desreferenciará automáticamente todos los valores de tipo de datos «URI» que coincidan con un servicio registrado. Las URI reconocidas se mostrarán con un enlace «[+]» junto a ellas, en el que se puede hacer clic para ampliar la información encontrada en la fuente. Una vez expandidos, los enlaces cambiarán a «[-]». La instantánea de los metadatos externos se carga debajo del URI.

![Entradas URI en la página de edición del elemento.](modulesfiles/uri-entry.png)

Estos botones de alternancia se cargarán con la clase `uri-dereferencer-toggle` y se pueden personalizar mediante el [módulo Editor CSS](../modules/csseditor.md) o con hojas de estilo alojadas externamente. Cuando se expanden, los metadatos externos se cargarán dentro de un `div` con la clase `uri-dereferencer-markup` y, desde allí, en una lista de descripción `dl`. Las propiedades aparecerán como `dt` y los valores como `dd`. 

![Las mismas entradas URI mostradas en la página de vista del elemento, expandidas para mostrar la información de una de las URI.](modulesfiles/uri-expanded.png)

El número de valores de metadatos desreferenciados, y cuáles son, los determina el servicio y su propio tipo de datos, y no se pueden configurar en Omeka. Debe probar los servicios y los tipos de datos antes de decidir si desea utilizar estos URI y permitir que los usuarios vean los metadatos desreferenciados. Este módulo no le permite incluir o excluir propiedades específicas de la desreferencia.

Si el servicio proporciona información en varios idiomas, puede especificar qué campos de qué idioma deben mostrarse introduciendo una etiqueta de idioma de dos letras en el campo de idioma (el icono del globo terráqueo) al editar el valor de la propiedad. 

![Entradas URI en la página de edición del elemento, con códigos de idioma especificados.](modulesfiles/uri-language-item-editing.png)

Cuando se accede al elemento en una página pública, las URI se pueden expandir para mostrar la información en el idioma especificado. Si el idioma deseado no está disponible, las URI mostrarán el inglés por defecto. Consulte con el servicio específico para ver qué idiomas se ofrecen. Actualmente solo hay cuatro servicios que ofrecen traducciones: [Wikidata](https://www.wikidata.org/wiki/Wikidata:Main_Page){target=_blank}, [DBpedia](https://wiki.dbpedia.org/){target=_blank}, [Vocabularios de valores RDA](http://www.rdaregistry.info/termList/){target=_blank} y [Vocabularios Getty](https://www.getty.edu/research/tools/vocabularies/){target=_blank} (excluyendo ULAN).

![Las mismas entradas URI mostradas en la página de vista de elemento, ampliadas para mostrar la información en varios idiomas.](modulesfiles/uri-language-item-view.png)

Si tienes [valores de tipos de datos personalizados](../modules/customvocab.md) y deseas que sean dereferenciables, debes añadir la clase `uri-value-link` a la etiqueta de anclaje que contiene el URI.

## Servicios de datos enlazados

Los servicios de datos enlazados son objetos JavaScript que se encargan de desreferenciar los URI y devolver información sobre el recurso. Este módulo incluye varios servicios integrados:

- [DBpedia](https://wiki.dbpedia.org/){target=_blank}
- [Geonames](https://www.geonames.org/){target=_blank}
- [Vocabularios de Getty](https://www.getty.edu/research/tools/vocabularies/){target=_blank}
- [Servicio de datos enlazados de la LC](http://id.loc.gov/){target=_blank}
- [OCLC VIAF](https://www.oclc.org/en/viaf.html){target=_blank}
- [OCLC FAST](http://fast.oclc.org/){target=_blank}
- [Vocabularios de valores RDA](http://www.rdaregistry.info/termList/){target=_blank}
- [Wikidata](https://www.wikidata.org/wiki/Wikidata:Main_Page){target=_blank}
- [Gemeentegeschiedenis](https://www.gemeentegeschiedenis.nl/){target=_blank}.

Para obtener información sobre cómo añadir otros servicios, consulta el [Readme](https://omeka.org/s/modules/UriDereferencer/){target=_blank}.
