# Vocabularios

Los vocabularios son un conjunto de clases y propiedades de metadatos RDF publicadas que sirven para describir tus recursos. Los vocabularios abiertos enlazados se crean fuera de Omeka y, al estar disponibles de forma abierta, pueden importarse (con algunas limitaciones) a Omeka S para su uso en toda la instalación. Si dispones de tipos de elementos o clases especiales y poco comunes, quizá te interese buscar e importar un vocabulario abierto enlazado para estandarizar la descripción de esos elementos concretos. A veces, estos vocabularios se denominan «ontologías». 

Por ejemplo, puedes encontrar ontologías para describir [señales de audio](https://lov.linkeddata.es/dataset/lov/vocabs/af), [datos de tráfico aéreo](https://lov.linkeddata.es/dataset/lov/vocabs/atd) y [algoritmos](https://lov.linkeddata.es/dataset/lov/vocabs/algo), proporcionando campos de metadatos específicos para esos tipos de objetos. 

> *«Un vocabulario en LOV reúne definiciones de un conjunto de clases y propiedades (denominadas conjuntamente, de forma sencilla, términos del vocabulario), útiles para describir tipos específicos de cosas, o cosas de un ámbito o sector determinado, o cosas en general pero para un uso específico». (Fuente: <https://lov.linkeddata.es/dataset/lov/about>)*

El [Vocabulario Abierto Enlazado](https://lov.linkeddata.es/dataset/lov/about){target=_blank} más utilizado para las **propiedades** es Dublin Core Terms (`dcterms:`). Este proporciona 55 propiedades (términos) a Omeka S, como «Creador» y «Título», que puedes completar con valores. También proporciona 22 clases, que puedes utilizar para clasificar tus recursos. 

El vocabulario más utilizado para las **clases** podría ser Dublin Core Types (`dctype:`), que incorporamos en todas las instalaciones de Omeka Classic y S. Estas 12 clases incluyen «Imagen», «Imagen en movimiento», «Sonido», «Texto», «Objeto físico», etc.

!!! Nota
  Los vocabularios de Omeka S no son lo mismo que los vocabularios controlados o los archivos de autoridad, que consisten en términos y conceptos, en lugar de clases y propiedades. En Omeka S, los vocabularios controlados se pueden gestionar mediante los módulos [Value Suggest](../modules/valuesuggest.md) y [Custom Vocab](../modules/customvocab.md).  

Los administradores globales pueden gestionar los vocabularios de su instalación desde la pestaña **Vocabularios**, situada en el panel de navegación izquierdo del panel de administración. Los supervisores pueden añadir, editar y eliminar sus propios vocabularios. 

Omeka S viene precargado con los siguientes vocabularios: [Dublin Core](http://purl.org/dc/terms/){target=_blank}; [Dublin Core Type](http://purl.org/dc/dcmitype/){target=_blank}; [Ontología bibliográfica](https://bibliontology.com/){target=_blank}; y [Amigo de un amigo](https://en.wikipedia.org/wiki/FOAF_(ontology)){target=_blank}. 

Este [vídeo tutorial](https://vimeo.com/449764902){target=_blank} explica cómo gestionar y añadir vocabularios:

<div style="padding:56.25% 0 0 0;position:relative;"><iframe src="https://player.vimeo.com/video/449764902?h=4c03af586c" style="position:absolute;top:0;left:0;width:100%;height:100%;" frameborder="0" allow="autoplay; fullscreen; picture-in-picture" allowfullscreen></iframe></div><script src="https://player.vimeo.com/api/player.js"></script>
<p><a href="https://vimeo.com/449764902">Vocabularios de Omeka S</a> de <a href="https://vimeo.com/omeka">Omeka</a> en <a href="https://vimeo.com">Vimeo</a>.</p>

## Permisos de los vocabularios

Los vocabularios solo pueden ser modificados por los administradores globales y los supervisores. Los vocabularios precargados se pueden editar o eliminar, excepto los términos DC y el tipo DC, que no se pueden editar ni eliminar.

| Categoría | Permiso | Administrador global | Supervisor | Editor | Revisor | Autor | Investigador |
|-----|-----|---|---|---|---|---|---|
| Vocabularios | Importar | Sí | Sí | No | No | No | No |
|  | Editar/Eliminar | Sí | Los propios | No | No | No | No |

Si se cambia el nivel de un usuario, por ejemplo, de «Supervisor» a «Editor», este perderá la capacidad de editar los vocabularios que haya importado, pero el vocabulario no se modificará.

## Ver vocabularios
La vista principal de la pestaña **Vocabularios** en el panel de administración muestra los vocabularios existentes para la instalación de Omeka S. 

![Vista principal de los vocabularios, con columnas para la etiqueta, el prefijo, las clases y el recuento e información de las propiedades](contentfiles/vocabularies.png)

Los vocabularios se muestran en una tabla con los encabezados **Etiqueta** (nombre del vocabulario), **Prefijo** (utilizado por la base de datos), **Clases** (número de clases en el vocabulario) y **Propiedades** (número de propiedades en el vocabulario). Puedes ordenar los vocabularios por estas columnas utilizando las flechas arriba y abajo situadas en el extremo derecho de cada columna. 

Puede utilizar los iconos situados a la derecha del campo **Etiqueta** para gestionar cada vocabulario de forma individual. El icono de edición (lápiz) le lleva a la página de edición de ese vocabulario, el icono de eliminación (papelera) abre una barra lateral para eliminar el vocabulario y el icono de detalles (tres puntos) abre una barra lateral con información sobre el vocabulario.

Al editar un vocabulario, puedes realizar cambios en la **etiqueta** y añadir **comentarios**. 

## Añadir un vocabulario
Los nuevos vocabularios deben importarse desde una fuente estándar de metadatos ya existente. Para importar un nuevo vocabulario, debes disponer de un archivo de vocabulario o de un enlace estable a un vocabulario.

La página «Nuevo vocabulario» tiene tres secciones: Información básica, Archivo y Avanzado. 

Ten en cuenta que es posible que tengas que investigar para encontrar el prefijo, el URI del espacio de nombres y la etiqueta del vocabulario, ya que estos no están estandarizados. Además de la página web del vocabulario, puede consultar <https://lov.linkeddata.es/dataset/lov/vocabs>{target=_blank}.

Una vez importado el vocabulario, puede utilizar la función «Editar» para modificar la etiqueta y el comentario del vocabulario, así como para cargar un archivo RDF actualizado del vocabulario. 

### Información básica
Esta sección contiene la información básica del vocabulario

- Etiqueta (obligatoria): el nombre que se mostrará para el vocabulario en las listas (por ejemplo, «Dublin Core», «Friend of a Friend»).
- Comentario: cualquier comentario que desees añadir. 
- URI del espacio de nombres (obligatorio): debe ser facilitado por el propio vocabulario.
- Prefijo del espacio de nombres (obligatorio): se mostrará antes de la propiedad, indicando a qué vocabulario pertenece (por ejemplo, el prefijo de Dublin Core es dcterms).

![Configuración básica de un nuevo vocabulario, sin datos introducidos](contentfiles/vocab_addBasicInfo.png)

### Archivo
Esta sección trata sobre el archivo del vocabulario.

- Archivo del vocabulario: sube un archivo desde tu ordenador *o*
- URL del vocabulario: introduce aquí la URL del vocabulario. 
- Formato de archivo: menú desplegable, selecciona entre:
  - Detección automática
  - JSON-LD (.jsonld)
  - N-Triples (.nt)
	- RDF/XML (.rdf)
  - Turtle (.ttl).

![Nueva configuración del archivo de vocabulario, sin datos introducidos y sin archivo seleccionado](contentfiles/vocab_addFile.png)

### Avanzado

Esta sección contiene ajustes avanzados del vocabulario.

- Idioma: Introduce el idioma preferido para las etiquetas y los comentarios utilizando una etiqueta de idioma de la IETF. 
- Propiedad de la etiqueta: si este vocabulario utiliza una propiedad no convencional para las etiquetas, introduce el URI completo de la propiedad entre corchetes angulares (`<`, `>`) en este campo.
- Propiedad del comentario: si utilizas la propiedad de etiqueta anterior, introduce el URI de la propiedad correspondiente entre corchetes angulares (`<`, `>`) en este campo. 

![Configuración avanzada de un nuevo vocabulario, sin datos introducidos](contentfiles/vocab_addAdvanced.png)

## Editar un vocabulario
Puedes editar los vocabularios existentes haciendo clic en el botón de edición (icono del lápiz) de la tabla de vocabularios.

También puedes actualizar el vocabulario subiendo un nuevo archivo de vocabulario o introduciendo la URL del vocabulario y guardando los cambios. Podrás revisar cualquier cambio al actualizar un vocabulario.
Si decides que no deseas guardar los cambios, o has hecho clic en el botón de edición por error, puedes hacer clic en el botón «Cancelar» situado junto al botón «Guardar».

![Página de edición del vocabulario para la ontología OWL-Time.](contentfiles/vocab_edit.png)

### Importación de vocabulario
Omeka S importará vocabularios y ontologías con el formato adecuado. Estarán disponibles los datos `rdfs:Class` y `rdfs:Property`. 

En el caso de los datos del Lenguaje de Ontología Web (OWL), Omeka S almacenará únicamente las superpropiedades y superclases RDF/S. Omeka S no aplica ninguna regla de declaración o inferencia de OWL. Así, por ejemplo, una `owl:Class` se trata en Omeka S como una `rdfs:Class`.

Del mismo modo, todos los siguientes elementos se tratan únicamente como `rdfs:Property`. Tampoco se aplican ni se almacenan los dominios y rangos de OWL:

* `owl:ObjectProperty`
* `owl:DatatypeProperty`
* `owl:SymmetricProperty`
* `owl:TransitiveProperty`
* `owl:FunctionalProperty`
* `owl:ObjectProperty`
* `owl:DatatypeProperty`
* `owl:SymmetricProperty`
* `owl:TransitiveProperty`
* `owl:FunctionalProperty`
* `owl:InverseFunctionalProperty`.

Por ejemplo, una ontología importada que contenga una `owl:ObjectProperty` no está limitada a que sus objetos sean URI; Omeka S aceptará un valor literal sin generar ningún error. Puedes utilizar la configuración de la [plantilla de recursos](../content/resource-template.md) para exigir un tipo de datos en las propiedades, de modo que quien rellene, por ejemplo, el campo `owl:ObjectProperty` en una plantilla esté obligado a introducir un valor URI.

Depende de la persona que introduzca los metadatos cumplir con los estándares lo mejor que pueda.

## Eliminar un vocabulario

A excepción de Dublin Core y Dublin Core Type, los administradores globales pueden eliminar cualquier vocabulario de la instalación de Omeka S, ya sea desde la página de exploración de vocabularios o desde la página de edición de vocabularios. Los supervisores pueden eliminar los vocabularios que hayan importado, pero no los vocabularios de otros usuarios ni los predeterminados incluidos con Omeka S.

En la página de exploración de vocabularios, haz clic en el icono de la papelera/eliminar situado en la fila del vocabulario que deseas eliminar (marcado con el número 1 en la imagen siguiente). Se abrirá un panel deslizante en la parte derecha del navegador en el que se le pedirá que confirme que desea eliminar el vocabulario (marcado con el número 2 en la imagen siguiente). Para eliminarlo, haga clic en el botón «Confirmar eliminación»; para cancelar la operación, simplemente cierre el panel deslizante. 

![Vista de la página de exploración de vocabularios, con un panel abierto a la izquierda en el que se pide al usuario que confirme la eliminación. Hay un número 1 azul junto al icono de la papelera y un número 2 azul justo a la izquierda del botón rojo «Confirmar eliminación».](contentfiles/vocab-delete1.png)

Desde la página «Editar vocabulario», puede hacer clic en el gran botón rojo «Eliminar» situado en la esquina superior derecha de la página. Esto abrirá un panel deslizante que le pedirá que confirme la eliminación. Para eliminar, haga clic en el botón «Confirmar eliminación»; para cancelar, simplemente cierre el panel deslizante. 

![Página de edición del vocabulario de «Datos generales vinculados». No hay datos en el campo de comentarios. Una flecha roja señala un botón de color rojo pálido con la etiqueta «Eliminar»](contentfiles/vocab-delete2.png)

