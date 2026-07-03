# Formatos de salida 

El [módulo «Formatos de salida»](https://omeka.org/s/modules/OutputFormats/){target=_blank} permite a los administradores y/o visitantes del sitio exportar conjuntos de datos de las colecciones. Las opciones de salida se añaden a las interfaces administrativas de los elementos, los medios y los conjuntos de elementos, y pueden añadirse a las páginas públicas del sitio para los elementos y los conjuntos de elementos. 

![Vista pública de los botones del módulo en la parte inferior de una página de exploración de elementos](modulesfiles/outputFormats_public.png)

Los formatos de salida disponibles para este módulo son:

- [JSON-LD](https://json-ld.org/){target=_blank}
- [Notation3](https://www.w3.org/wiki/NotationThree){target=_blank}
- [N-Triples](https://dbpedia.org/page/N-Triples){target=_blank}
- [RDF/XML](https://www.w3schools.com/XML/xml_rdf.asp){target=_blank}
- [Turtle](https://www.w3.org/TR/rdf12-turtle/){target=_blank}.

## Configuración

Este módulo no tiene opciones de configuración a nivel de instalación. Cuando está activo, aparece automáticamente en los siguientes lugares de las interfaces de administración: en la parte inferior de la página de exploración de elementos, de las páginas de exploración de medios y de las páginas de exploración de conjuntos de elementos; y en la barra lateral de las páginas de vista de elementos individuales, de las páginas de vista de medios y de las páginas de vista de conjuntos de elementos. 

![Los botones del módulo que aparecen en la barra lateral de una página de visualización de archivos multimedia](modulesfiles/outputFormats_admin.png)

El módulo debe activarse para cada sitio web individualmente. Para habilitar el selector de formatos en un sitio, ve a la página «Administración del sitio», haz clic en la pestaña «Configuración», busca la sección «Formatos de salida» y marca la casilla «Añadir selector de formatos de salida a las páginas de recursos».

![La configuración del módulo en la pestaña de configuración del sitio](modulesfiles/outputFormats_siteSettings.png)

Cuando el módulo está activado para un sitio, añadirá las opciones de descarga al final de las páginas de exploración y de resultados de búsqueda, así como en las páginas de visualización de elementos individuales y conjuntos de elementos. La opción no estará disponible en las páginas de visualización de medios públicas.

Cuando un visitante del sitio, o un usuario que haya iniciado sesión en una página de administración, realice una selección en el menú desplegable de una página de exploración, el conjunto de datos resultante contendrá los resultados de exploración o búsqueda correspondientes a una página. El número de recursos del conjunto de datos dependerá de la configuración de paginación de toda la instalación para las páginas de administración, o de la configuración de paginación del sitio para las páginas públicas.

Las opciones aparecen de la siguiente manera:

- JSON-LD (application/ld+json)
- Notation3 (text/n3)
- N-Triples (application/n-triples)
- RDF/XML (application/rdf+xml)
- Turtle (text/turtle).

El botón muestra el texto «Ver en el formato seleccionado».

![El menú desplegable del módulo que muestra todos los formatos disponibles](modulesfiles/outputFormats_public2.png)

Cuando se selecciona una salida, el usuario verá un archivo disponible para descargar o una nueva pestaña o ventana del navegador con los resultados.

## Problemas con los formatos de salida

La conversión de los datos de su sitio a estos formatos puede generar algunos errores. Por lo general, se trata de problemas de compatibilidad entre los metadatos de sus recursos y los formatos, o con la herramienta que utilizamos para crear dichos formatos. 

Recomendamos a los administradores que comprueben minuciosamente cada formato de salida y busquen errores antes de que los detecte el público. A continuación, edite los recursos según sea necesario para corregir los errores producidos. Algunos ejemplos son:

- Campos de metadatos con cadenas de texto demasiado largas para el formato de salida (como la captura del texto completo de [Extract Text](extracttext.md)). 
- Saltos de línea y otros caracteres no visibles que causan problemas con los formatos seleccionados.

También es posible que aparezca el error «Tiempo máximo de ejecución superado» en algunos formatos. En este caso, su servidor no es compatible con la generación de la cantidad de información contenida en el conjunto de datos en cuestión. Esto puede solucionarse reduciendo el número de recursos que se muestran en una página, en la configuración de paginación del sitio. En algunos casos, este problema puede ser inevitable. 

Puede resultar útil consultar la información disponible sobre la herramienta que utilizamos, [EasyRDF](https://github.com/sweetrdf/easyrdf){target=_blank}.