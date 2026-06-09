# Compartir

El [módulo «Compartir»](https://omeka.org/s/modules/Sharing){target=_blank} te permite añadir botones a las páginas del sitio web que los visitantes pueden utilizar para compartir e incrustar contenido de tu sitio en redes sociales o por correo electrónico. Compartir también incluye los metaelementos [Open Graph](https://ogp.me/){target=_blank} y [oEmbed](https://oembed.com/){target=_blank} en el `<head>` de cada página de elemento de tu sitio, de modo que se muestren tarjetas de vista previa cuando se comparta en redes sociales. 

Actualmente, Compartir admite las siguientes opciones:

- Facebook
- Twitter
- Tumblr
- Pinterest
- Correo electrónico
- Códigos de incrustación.

Una vez que se ha instalado y activado la función de compartir para una instalación de Omeka S, estará disponible para todos los sitios de la instalación.

Sharing añade un nuevo [bloque de página](../sites/site_pages.md#page-blocks) a las páginas del sitio, y un [bloque de recursos para configurar](../sites/site_theme.md#configure-resource-pages) en el tema del sitio; estos bloques son opcionales, dependiendo de la configuración del sitio.

## Configuración

![Sección «Sharing» en la configuración del sitio](../modules/modulesfiles/sharing.png)

La configuración de Sharing se realiza sitio por sitio. Ve a un sitio y haz clic en «Configuración del sitio». Habrá una sección denominada «Compartir» con tres opciones:

**Botones para compartir**: ofrece una serie de casillas de verificación, una para cada servicio u opción (Facebook, Twitter, etc.). Puedes desmarcar todas las casillas de los servicios para desactivar la función de compartir en un solo sitio. 

**Ubicación de los botones para compartir**: Establece la ubicación de los botones para compartir, ya sea en la parte superior del contenido (debajo de la navegación y el encabezado de la página) o en la parte inferior (justo encima del pie de página). También puede optar por mostrar los botones para compartir únicamente a través de bloques: [bloques de página para páginas individuales](../sites/site_pages.md#page-blocks) y bloques de recursos configurados en la [página de configuración de recursos](../sites/site_theme.md#configure-resource-pages) del tema del sitio. 

**Botón único**: En lugar de mostrar botones con los logotipos de cada servicio seleccionado anteriormente, muestra un único botón con un icono de «Compartir» que, al hacer clic en él, abre las opciones del servicio. Esto sustituirá todas las instancias de los botones para compartir en todo el sitio. 

Asegúrate de que las casillas correctas estén marcadas para tu sitio. Asegúrate de guardar los cambios. 

### Bloques de página y de recursos

Si has optado por mostrar los botones de compartir mediante bloques, puedes configurarlos en dos lugares: en cada página utilizando un bloque de página, y en los elementos y medios en «Configurar páginas de recursos». Coloca estos bloques en las ubicaciones que elijas. 

Si tiene la opción de compartir configurada para mostrarse en la «Parte superior» o en la «Parte inferior» de su sitio, aún puede utilizar los bloques. Tenga en cuenta que esto hará que los botones para compartir aparezcan dos veces: una vez en la parte superior o inferior de cada página según su configuración, y otra vez dondequiera que estén los bloques. 

### Elementos incrustados

El módulo enviará metaetiquetas Open Graph y oEmbed independientemente de la configuración de tu sitio. 

En el caso de Open Graph, tendrá un aspecto similar a este:

```
<meta property="og:site_name" content="Mi sitio Omeka S">
```

Las etiquetas pueden incluir: 

- `og:description`, que refleja el contenido de `dcterms:description` de cualquier recurso, si procede, o el [campo utilizado para la descripción del recurso](../content/resource-template.md#other-options)
- `og:title`, que refleja `dcterms:title` o el campo utilizado para el título del recurso
- `og:image`, ya sea el medio principal o la miniatura predeterminada según el tipo de medio
- `og:type`, siempre `content="website"` en este momento
- `og:url`, la URL de la página actual.

Estos campos no se envían en páginas de conjuntos de elementos o de medios. No se enviarán archivos multimedia (audio y vídeo), solo una imagen en miniatura. 

oEmbed aparecerá como una única etiqueta en el `<head>` de todas las páginas públicas de Omeka S, incluidas las páginas de elementos, medios, búsqueda y navegación: 

```
<link rel="alternate" type="application/json+oembed" title="[El título de tu página aquí]"> 
```

Este elemento contendrá un valor `href` que refleja la API de oEmbed de su sitio, que se encuentra en `suURLdeInstalaciónaquí/oembed`, y la URL de la página específica de su sitio, algo así como `suURLdeInstalaciónaquí/s/site-one/item/item1`. 

## Parte pública

Los iconos para compartir de los servicios y opciones habilitados se mostrarán en las páginas que crees, así como en las páginas de elementos individuales de tu sitio. No aparecerán en las páginas añadidas por módulos, como la [página de exploración de mapas](mapping.md) o las [páginas de exploración por facetas](facetedbrowse.md). 

![Todos los botones de compartir disponibles se muestran encima del título de un elemento, justo debajo del encabezado de la página](../modules/modulesfiles/sharing_buttons.png)

Ten en cuenta que si tienes la opción «Compartir» configurada para mostrarse en la «Parte superior» o en la «Parte inferior» de tu sitio, y además utilizas la página «Compartir» y/o bloques de recursos, los botones para compartir aparecerán dos veces: una vez en la parte superior o inferior de cada página según tu configuración, y otra vez dondequiera que se encuentren los bloques. 

Si ha elegido la opción «Botón único», el botón se mostrará según los colores y la configuración del tema. Puede modificar el tamaño y el color con el [Editor CSS](csseditor.md). Aquí se muestra en la barra lateral derecha, como un botón negro con un icono blanco, encima del resto de la información:

![Compartir como un único botón en la página de un elemento público, en la barra lateral derecha, encima del resto de la información.](../modules/modulesfiles/sharing_singleButton.png)

Por defecto, el módulo compartirá el título de la página, el nombre del sitio y el nombre de la instalación, y luego un enlace en el que los visitantes pueden hacer clic para acceder al recurso compartido. 

![Un ejemplo de tuit para la página, en el que se muestra el título de la página seguido de un punto, luego el título del sitio seguido de un punto, a continuación el título de la instalación y, por último, la URL del sitio](../modules/modulesfiles/sharing_tweet.png)
