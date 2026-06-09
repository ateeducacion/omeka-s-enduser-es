# Resource Meta

El [módulo Resource Meta](https://omeka.org/s/modules/ResourceMeta/){target=_blank} permite a los usuarios que lo instalan mostrar metadatos de recursos (elementos, conjuntos de elementos y medios) como elementos `<meta>` en el HTML](https://www.w3schools.com/tags/tag_meta.asp){target=_blank} de las páginas de su sitio. Los valores meta se aplican a través de [plantillas de recursos](../content/resource-template.md): una propiedad de metadatos en una plantilla, como `dcterms:creator`, se puede configurar para que se muestre como una etiqueta meta, como `<meta name="dcterms.creator" content="Shakespeare, William">` dentro de la etiqueta `<head>` de la página pública. 

Los ajustes de Resource Meta pueden ser vistos por los usuarios de todos los niveles, y pueden ser modificados por los usuarios con permisos de Editor, Supervisor y Administrador global. 

![Una página de elemento público que muestra los valores de metadatos en la página y en el código HTML.](modulesfiles/resourcemeta.png)

Los elementos meta se utilizan para la optimización de motores de búsqueda y la indexación del contenido más relevante de la página. Este módulo ofrece elementos meta de uso común para la indexación y la visibilidad de recursos académicos, incluyendo BE Press, Highwire Press, EPrints y PRISM, así como elementos y términos de Dublin Core para otros tipos de recursos.

## Asignación de metadatos a metaetiquetas

Seleccione «Resource Meta» en la pestaña «Módulos» del menú de navegación de la izquierda. Verá todas las plantillas de recursos de la instalación enumeradas en una página, con una indicación del número de metaetiquetas que ya se han aplicado a las propiedades de cada plantilla (el «Recuento de nombres meta»). 

![La página de configuración que muestra las plantillas de recursos de una instalación y su configuración de metadatos actual.](modulesfiles/resourcemeta_homepage.png)

Haga clic en el icono del lápiz que aparece en cada plantilla para modificar su configuración de metadatos. Se le redirigirá a una pantalla con todas las propiedades de la plantilla de recursos, con un menú desplegable para seleccionar entre los elementos meta disponibles. 

![Configuración meta de una plantilla de recursos en proceso de edición, mostrando un menú desplegable con los elementos de BE Press.](modulesfiles/resourcemeta_edit1.png)

Cada campo de la plantilla de recurso se puede asignar a uno o más elementos meta. Las opciones disponibles son:

- BE Press
- Elementos Dublin Core
- Términos Dublin Core
- Highwire Press
- EPrints
- PRISM.

Puede asignar automáticamente las propiedades de Dublin Core Terms de sus plantillas de recursos a las metaetiquetas de Dublin Core Terms mediante el botón «Map dcterms» situado en la parte superior de la pantalla. De lo contrario, deberá seleccionar las metaetiquetas manualmente en el menú desplegable disponible. Puede asignar términos de Dublin Core automáticamente y luego añadir más etiquetas manualmente; por ejemplo, puede asignar el campo `dcterms:title` a otros campos de título, incluidos `bepress_citation_title` y `citation_title` de Highwire Press. Tenga en cuenta que al pulsar el botón «Map dcterms» se borrarán las asignaciones existentes. 

Para borrar todas las asignaciones actuales, pulse «Borrar». Para deshacer ese borrado, pulse «Restablecer». Asegúrese de guardar sus cambios. 

![Configuración de metadatos de una plantilla de recurso en proceso de edición, mostrando múltiples asignaciones en varias propiedades.](modulesfiles/resourcemeta_edit2.png)

Para comprobar que el módulo funciona según lo previsto, ve a una página pública de un elemento que utilice la plantilla de recurso con asignaciones. Visualiza el código fuente de la página y busca dentro de la etiqueta `<head`> los elementos `<meta>` que correspondan a tu configuración. 

![El código fuente de la página de un elemento con las asignaciones de metadatos como en la imagen anterior.](modulesfiles/resourcemeta_public.png)

## Usos

Si utiliza Omeka para poner a disposición recursos académicos, por ejemplo, con la intención de [que Google Scholar indexe los elementos](https://scholar.google.com/intl/en/scholar/inclusion.html#indexing){target=_blank}, es posible que desee seleccionar una de las cuatro opciones de publicación, todas ellas compatibles. [Puede encontrar más información sobre estas cuatro opciones y la visibilidad de los recursos académicos aquí](http://div.div1.com.au/div-thoughts/div-commentaries/66-div-commentary-metadata){target=_blank}.

Por poner otro ejemplo, si desea que sus elementos de Omeka sean [indexados e importados por Zotero](https://zotero-manual.github.io/adding-items/#generic-translators){target=_blank}, es posible que le interese utilizar Highwire Press, Dublin Core y PRISM. 

Para los metaelementos que sirven para mostrar los recursos de Omeka de forma dinámica en sitios web de redes sociales, instale el [módulo Sharing](sharing.md).