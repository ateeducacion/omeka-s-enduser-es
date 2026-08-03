# Resource Meta

El [módulo Resource Meta](https://omeka.org/s/modules/ResourceMeta/){target=_blank} permite a los usuarios que lo hayan instalado mostrar los metadatos de los recursos (elementos, conjuntos de elementos y contenidos multimedia) como elementos [`<meta>` en el código HTML](https://www.w3schools.com/tags/tag_meta.asp){target=_blank} de las páginas de su sitio web. Los valores de metadatos se aplican a través de [plantillas de recursos](../content/resource-template.md): una propiedad de metadatos de una plantilla, como `dcterms:creator`, puede configurarse para que se muestre como una etiqueta meta, por ejemplo, `<meta name="dcterms.creator" content="Shakespeare, William">` dentro de la etiqueta `<head>` de la página pública. 

Los usuarios de cualquier nivel pueden ver la configuración de Resource Meta, y los usuarios con permisos de Editor, Supervisor y Administrador global pueden modificarla. 

![Una página de elemento pública que muestra los valores de metadatos en la página y en el código HTML.](modulesfiles/resourcemeta.png)

Los elementos meta se utilizan para la optimización en motores de búsqueda y la indexación del contenido más relevante de la página. Este módulo ofrece elementos meta de uso común para la indexación y la visibilidad de los recursos académicos, incluidos BE Press, Highwire Press, EPrints y PRISM, así como elementos y términos de Dublin Core para otros tipos de recursos.

## Asignación de metadatos a etiquetas meta

Selecciona «Resource Meta» en la pestaña «Módulos» del menú de navegación de la izquierda. Verás una lista de todas las plantillas de recursos de la instalación en una página, con una indicación del número de etiquetas meta que ya se han aplicado a las propiedades de cada plantilla (el «Recuento de nombres meta»). 

![La página de configuración que muestra las plantillas de recursos de una instalación y su configuración actual de metadatos.](modulesfiles/resourcemeta_homepage.png)

Haz clic en el icono del lápiz que aparece en cada plantilla para modificar su configuración de metadatos. Se le redirigirá a una pantalla con todas las propiedades de la plantilla de recursos, con un menú desplegable para seleccionar entre los elementos meta disponibles. 

![Configuración meta de una plantilla de recursos en proceso de edición, mostrando un menú desplegable con los elementos de BE Press.](modulesfiles/resourcemeta_edit1.png)

Cada campo de la plantilla de recurso se puede asignar a uno o varios elementos meta. Las opciones disponibles son:

- BE Press
- Elementos Dublin Core
- Términos Dublin Core
- Highwire Press
- EPrints
- PRISM.

Puedes asignar automáticamente las propiedades de Dublin Core Terms de tus plantillas de recursos a las metaetiquetas de Dublin Core Terms mediante el botón «Asignar dcterms» situado en la parte superior de la pantalla. De lo contrario, deberás seleccionar las metaetiquetas manualmente en el menú desplegable disponible. Puede asignar los términos de Dublin Core automáticamente y, a continuación, añadir más etiquetas manualmente; por ejemplo, puede asignar el campo `dcterms:title` a otros campos de título, incluidos `bepress_citation_title` y `citation_title` de Highwire Press. Tenga en cuenta que al pulsar el botón «Asignar dcterms» se borrarán las asignaciones existentes. 

Para borrar todas las asignaciones actuales, pulsa «Borrar». Para deshacer ese borrado, pulsa «Restablecer». Asegúrate de guardar los cambios. 

![Configuración de metadatos de una plantilla de recurso en proceso de edición, en la que se muestran múltiples asignaciones en varias propiedades.](modulesfiles/resourcemeta_edit2.png)

Para comprobar que el módulo funciona según lo previsto, ve a una página pública de un elemento que utilice la plantilla de recurso con asignaciones. Visualiza el código fuente de la página y busca dentro de la etiqueta `<head`> los elementos `<meta>` que correspondan a tu configuración. 

![El código fuente de la página de un elemento con las asignaciones de metadatos tal y como se muestra en la imagen anterior.](modulesfiles/resourcemeta_public.png)

## Usos

Si utilizas Omeka para poner a disposición recursos académicos, por ejemplo, con la intención de [que Google Scholar indexe los elementos](https://scholar.google.com/intl/en/scholar/inclusion.html#indexing){target=_blank}, quizá te interese seleccionar una de las cuatro opciones de publicación, todas ellas compatibles. [Puedes encontrar más información sobre estas cuatro opciones y la visibilidad de los recursos académicos aquí](http://div.div1.com.au/div-thoughts/div-commentaries/66-div-commentary-metadata){target=_blank}.

Por poner otro ejemplo, si deseas que tus elementos de Omeka sean [indexados e importados por Zotero](https://zotero-manual.github.io/adding-items/#generic-translators){target=_blank}, quizá te interese utilizar Highwire Press, Dublin Core y PRISM. 

Para los metaelementos que facilitan los recursos de Omeka para su visualización dinámica en redes sociales, instala el [módulo Sharing](sharing.md).