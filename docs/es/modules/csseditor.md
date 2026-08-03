# Editor de CSS

El [módulo Editor de CSS](https://omeka.org/s/modules/CSSEditor){target=_blank} te permite escribir código CSS desde la interfaz de administración de Omeka S.

Una vez activado en la sección [Módulos](https://omeka.org/s/docs/user-manual/modules/){target=_blank} del panel de administración, el Editor de CSS se utiliza de forma individual para cada sitio web.

Si eres nuevo en el uso de CSS, te recomendamos los siguientes recursos gratuitos para dar tus primeros pasos:

* [«Aprende CSS» de Mozilla](https://developer.mozilla.org/en-US/docs/Web/CSS){target=_blank}
* [Curso «Aprende CSS» de Codecademy](https://www.codecademy.com/learn/learn-css){target=_blank}
* [«Conceptos básicos de CSS» de Marksheet](https://marksheet.io/css-basics.html){target=_blank}

La forma más sencilla de familiarizarse con los componentes de página de Omeka S a efectos de la edición de CSS es utilizar la herramienta «Inspeccionar» de tu navegador mientras visualizas el tema que hayas elegido.

## Aplicar CSS específico del sitio

Si el Editor de CSS está activo, aparecerá un enlace al Editor de CSS en el menú contextual de cada sitio.

![Menú contextual de un sitio de Omeka S con la entrada del Editor de CSS mostrada como página activa.](modulesfiles/csseditor_contextmenu.jpg)

El primer área de texto grande es donde debes escribir tus estilos personalizados. Utiliza esa área de texto como si fuera un archivo de hoja de estilos. Esto cargará una línea en cada página pública de tu sitio de Omeka S seleccionado, en la sección «head», que tendrá este aspecto:

` <link href="/yoursiteslug/css-editor" media="screen" rel="stylesheet" type="text/css"> `

Esta línea aparecerá después de las hojas de estilo que provienen de la configuración predeterminada de Omeka y del tema que hayas elegido. Por lo tanto, las entradas que introduzcas aquí anularán otros estilos definidos en esos archivos, a menos que se hayan marcado como `!important`. Es posible que haya otros CSS personalizados cargándose en el encabezado debajo de esta línea, especialmente procedentes de configuraciones del tema, como el color de acento principal o la altura del banner, que a su vez podrían anular tu CSS personalizado.

![Interfaz del módulo Editor de CSS.](modulesfiles/csseditor_interface.jpg)

El Editor de CSS también te permite incluir hojas de estilo externas introduciendo sus URL. No hay límite en el número de URL de hojas de estilo externas que puedes introducir. Cada campo de texto admite una sola URL, y se pueden crear campos adicionales haciendo clic en el botón «Añadir otra hoja de estilo».

Para eliminar hojas de estilo externas, borra el contenido de los campos de texto o haz clic en el icono de la papelera si hay varios campos de hojas de estilo.

![Campo de hoja de estilo externa en la interfaz del módulo Editor de CSS, con el botón de eliminación (icono de la papelera) resaltado.](modulesfiles/csseditor_remove.jpg)

## Tutorial: Cómo utilizar una fuente web de Google

Puedes hacer que tu sitio de Omeka S sea más distintivo utilizando una fuente personalizada. [Google ofrece una biblioteca gratuita de fuentes web](https://fonts.google.com/){target=_blank}, y este tutorial te mostrará cómo aplicar una fuente web a un sitio de Omeka S utilizando el tema «Predeterminado» a través de la interfaz del Editor de CSS.

A modo de referencia, el tema «Predeterminado» tiene este aspecto inicialmente, utilizando la fuente «Open Sans».

![Sitio de Omeka S con el tema «Predeterminado». Todo el texto utiliza «Open Sans».](modulesfiles/csseditor_before.jpg)

Este tutorial sustituirá «Open Sans» por la familia tipográfica «Lato».

1. Accede a [Google Fonts](https://fonts.google.com/){target=_blank}. Busca la familia tipográfica «Lato» y haz clic en el botón naranja «+» para seleccionarla.
  ![Página principal de Google Fonts con la familia tipográfica «Lato» resaltada](modulesfiles/csseditor_tutorial1.jpg)<br>
2. Aparecerá una barra con el texto «1 familia seleccionada» en la esquina inferior derecha. Haz clic en esta barra.
  ![Barra de la familia tipográfica seleccionada resaltada en la página de Google Fonts](modulesfiles/csseditor_tutorial2.jpg)<br>
3. La barra abrirá un panel con la información que necesitarás para utilizar Lato en tu sitio web. La primera sección, «Incrustar esta fuente», contiene la URL de la hoja de estilos externa que necesitas. Selecciona la URL en el atributo `href`, tal y como se muestra en la imagen.
  ![Sección «Incrustar esta fuente» con la URL de la hoja de estilos externa («https://fonts.googleapis.com/css?family=Lato&display=swap») resaltada.](modulesfiles/csseditor_tutorial3.jpg)<br>
4. Copia esta URL en uno de los campos «Hojas de estilo externas» del Editor de CSS.
  ![Campo de hoja de estilo externa en la interfaz del módulo Editor de CSS, con la URL de la hoja de estilo pegada.](modulesfiles/csseditor_tutorial4.jpg)<br>
5. De vuelta en el panel de Google Fonts, aparece la segunda sección titulada «Especificar en CSS». Copia la regla `font-family`.
  ![Sección «Especificar en CSS» con la regla `font-family` («font-family: 'Lato', sans-serif;») resaltada.](modulesfiles/csseditor_tutorial5.jpg)<br>
6. Para este tutorial, vas a establecer Lato como la fuente predeterminada del sitio. Para ello, en el área de texto grande «CSS» del Editor de CSS, configura la familia de fuentes del elemento `body` utilizando la regla que acabas de copiar.
  ![Área de texto CSS dentro de la interfaz del módulo Editor de CSS, con la regla de familia de fuentes del elemento `body` pegada («body {font-family: "Lato", sans-serif;}»).](modulesfiles/csseditor_tutorial6.jpg)<br>
7. Haz clic en el botón «Guardar» situado en la esquina superior derecha. Ahora el tema «Predeterminado» debería tener este aspecto.
![Sitio de Omeka S con el tema «Predeterminado», con todo el texto mostrado en la fuente «Lato»](modulesfiles/csseditor_after.jpg)
