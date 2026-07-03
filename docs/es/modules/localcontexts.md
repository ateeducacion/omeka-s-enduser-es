# Contextos locales

El [módulo «Contextos locales»](https://omeka.org/s/modules/LocalContexts){target=_blank} permite a los usuarios aplicar [Contextos locales](https://localcontexts.org/){target=_blank} Avisos y Etiquetas de Contextos Locales a los sitios, páginas y recursos de Omeka S. Para ello, es necesario crear una cuenta en Contextos Locales y crear proyectos en el registro. A continuación, introduce la clave API en Omeka para importar los [Avisos](https://localcontexts.org/notices/about-the-notices/){target=_blank} y [Etiquetas](https://localcontexts.org/labels/about-the-labels/){target=_blank} y aplicarlas a elementos, sitios y páginas. 

![](modulesfiles/localcontexts_itemPublic.png)

## ¿Qué es Local Contexts?

Local Contexts es una iniciativa global que apoya a las comunidades indígenas con herramientas que permiten reafirmar la autoridad cultural sobre las colecciones y los datos patrimoniales. Local Contexts cuenta con tres componentes de interés para los usuarios de Omeka: Notices, Labels y Projects.

### Notices

Este texto procede de la [página web de Local Contexts](https://localcontexts.org/notices/about-the-notices/){target=_blank}:

> *Los Avisos son herramientas destinadas a instituciones e investigadores para identificar colecciones y datos indígenas y reconocer los derechos e intereses indígenas. Los avisos se desarrollaron para crear vías de asociación, colaboración y apoyo a la autoridad cultural indígena.*

> *Los avisos pueden aplicarse a sitios web, publicaciones, conjuntos de datos, exposiciones de museos, objetos de una colección, muestras genéticas y mucho más. Las instituciones y los investigadores pueden generar avisos utilizando el Local Contexts Hub.*

> *Existen tres categorías de avisos: de participación, de divulgación y de conservación de colecciones. Consulta a continuación más información sobre los diferentes tipos de avisos.*

![Imagen](modulesfiles/localcontexts_notices.png)

### Etiquetas

Este texto procede del [sitio web de Local Contexts](https://localcontexts.org/labels/about-the-labels/){target=_blank}:

> *Las etiquetas de Conocimiento Tradicional (TK) y Biocultural (BC) son herramientas destinadas a las comunidades indígenas y las organizaciones locales. Desarrolladas gracias a una colaboración sostenida y a pruebas realizadas en comunidades indígenas de varios países, las etiquetas permiten a las comunidades expresar condiciones locales y específicas para compartir y participar en futuras investigaciones y relaciones, de manera coherente con las normas, la gobernanza y los protocolos comunitarios ya existentes para el uso, el intercambio y la difusión de conocimientos y datos.*

> *Las etiquetas pueden aplicarse a sitios web, publicaciones, conjuntos de datos, exposiciones de museos, objetos de una colección, muestras genéticas y mucho más. Las comunidades pueden personalizar y aplicar sus etiquetas de CK y CC mediante el Centro de Contextos Locales.*

![Imagen](modulesfiles/localcontexts_labels.png)

### Proyectos

Este texto procede de la [página web de Local Contexts](https://localcontexts.org/support/getting-started-on-the-hub/){target=_blank}:

> *¿Qué es un proyecto de Local Contexts?*

> *Los proyectos de Local Contexts describen el contexto en el que se aplican las etiquetas o los avisos. Por ejemplo, un proyecto podría incluir: un sitio web, un programa de estudios universitario, una tesis, una publicación de investigación, un conjunto de datos, una exposición en un museo, un registro de archivo, un objeto de una colección, una base de datos bibliotecaria, una colección fotográfica, un espécimen de referencia y/o metadatos sobre un registro.*

> *Al crear un proyecto de «Contextos locales», se te solicitarán los detalles del proyecto y los datos de contacto, y tendrás la opción de añadir metadatos.*

> *La creación de proyectos permite a las instituciones y a los investigadores generar avisos e implicarse, reconocer y dar visibilidad a los intereses indígenas en las colecciones, la información y los datos. Las comunidades pueden entonces elegir cómo y cuándo añadir sus etiquetas.*

> *Las cuentas de las comunidades pueden aplicar etiquetas personalizadas a los proyectos que crean en el Hub, así como a los proyectos que les hayan enviado las cuentas de instituciones e investigadores. Puedes ver los proyectos que se han añadido públicamente al Hub en el tablero de proyectos.*

![Imagen](modulesfiles/localcontexts_hub.png)

## Preparación para utilizar el módulo «Contextos locales»

El módulo «Contextos locales» tiene como objetivo fomentar la participación de los miembros de las comunidades indígenas, mediante «Avisos» creados por las instituciones y «Etiquetas» creadas por la comunidad. Un «Aviso» de «Abierto a la colaboración», por ejemplo, indica que se agradece la colaboración. Por lo tanto, debes estar preparado para gestionar dicha colaboración. Si utilizas avisos, asegúrate de que tu sitio Omeka disponga de medios para que los miembros de las comunidades indígenas puedan participar: creación de cuentas para los miembros de las comunidades indígenas, la posibilidad de añadir proyectos y etiquetas de «Local Contexts» al sitio, un formulario de contacto, comentarios sobre los elementos o un plan para que el personal responda a las contribuciones. Piensa en el flujo de trabajo que pretendes seguir para mejorar tus colecciones de forma colaborativa antes de continuar.

### Cuenta de Local Contexts Hub

Para utilizar este módulo, debes tener una cuenta de Local Contexts Hub. Crear un perfil allí te permite tener uno o más proyectos, que luego pueden conectarse a tu instalación de Omeka mediante una clave API.

[Visita la página web de Local Contexts para obtener más información y configurar tus proyectos](https://localcontexts.org/support/getting-started-on-the-hub/#about-projects){target=_blank}. 

Un proyecto puede diseñarse para un único objeto, una colección, una exposición o para toda tu institución. Puede que tengas necesidades sencillas —como añadir un aviso de «Abierto a la colaboración» en el pie de página de tu sitio de Omeka— o complejas, como conjuntos de etiquetas distintos y únicos para cada uno de los cientos de elementos. Familiarízate con todas las opciones de avisos y etiquetas de Local Contexts, y planifica qué conjunto de proyectos necesitarás para reflejar la situación de tu organización. 

### Permisos

Los proyectos de Local Contexts pueden aplicarse a sitios en los que el usuario tenga permisos de gestor del sitio (o una cuenta de administrador global para toda la instalación); Los avisos y las etiquetas se pueden añadir a las páginas del sitio para las que el usuario tenga permiso (nivel de «Creador del sitio» o superior). Los proyectos de «Contextos locales» se pueden añadir a los recursos para los que el usuario tenga permisos de edición (ya sea el propietario del recurso o una cuenta con nivel de «Editor» o superior). 

## Cómo utilizar el módulo Local Contexts

### Importar proyectos

Una vez instalado y activado el módulo en tu sitio de Omeka, ve a la entrada del módulo «Local Contexts» en la barra lateral del panel de administración. Allí podrás introducir tu clave API del Local Contexts Hub. 

![Imagen](modulesfiles/localcontexts_api.png)

Si lo deseas, puedes seleccionar solo algunos de tus proyectos para importarlos, introduciendo sus ID. Si dejas el campo «Proyectos» en blanco, Omeka cargará todos los proyectos asociados a tu clave API de Local Contexts. 

Al guardar la página, los proyectos se cargarán en la pestaña «Asignar». Verás el nombre de cada proyecto y todos los avisos y etiquetas asociados a él. En esta pantalla, puedes marcar la casilla de cada proyecto que desees que esté disponible a través de la clave API que acabas de introducir. Si no marcas ninguno de estos proyectos antes de guardar la página, no se conservarán en el sitio de Omeka. Asignar los proyectos en esta fase no hará que aparezcan en tu sitio; aún tendrás que aplicarlos manualmente a los elementos y a las páginas del sitio, y colocarlos en el pie de página del sitio. 

![Imagen](modulesfiles/localcontexts_assign.png)

Omeka S no guardará la clave API ni creará una conexión permanente. Si actualizas el contenido en el sitio web de LC Hubs, tendrás que volver a introducir la clave API para actualizar la información de Omeka desde la fuente. A continuación, tendrás que volver a aplicar los proyectos modificados al pie de página, a los elementos y a las páginas del sitio, según corresponda. 

Otros usuarios de la instalación de Omeka pueden añadir más proyectos introduciendo otra clave API de LC (o introduciendo la misma clave y asignando otros proyectos). Los proyectos de todas las fuentes aparecerán juntos en la interfaz y cualquier usuario podrá acceder a ellos. 

Si vuelves a esta página después de haber introducido inicialmente una clave API, verás el mismo formulario para introducir una nueva clave API. Puedes ignorarlo y guardar la página si deseas ver la lista de proyectos ya importados a tu sitio. Esto aparecerá en la pestaña «Eliminar». 

Esta tabla te permitirá eliminar proyectos de tu sitio. Si deseas volver a añadir estos proyectos más adelante, tendrás que volver a importarlos introduciendo de nuevo la clave API. Esto no modificará ningún elemento ni exposición; todo lo que ya esté asignado deberá eliminarse manualmente. 

### Aplicar proyectos a los sitios

Los gestores de sitio o los administradores globales pueden elegir uno o varios proyectos de «Contextos locales» para que aparezcan en el pie de página de cada sitio de tu instalación de Omeka S. Ve a la pestaña «Sitios» de la barra lateral, selecciona un sitio y ve a «Administración del sitio». En la pestaña «Configuración» de la página de administración del sitio, busca la sección «Local Contexts». Desde aquí puedes elegir uno o varios de los proyectos que se hayan asignado a la instalación tras introducir una clave API. 

![Imagen](modulesfiles/localcontexts_site.png)

Puedes elegir mostrar uno o todos los idiomas de los «Avisos» y «Etiquetas» seleccionados en los proyectos elegidos. 

El contenido del pie de página de «Contextos locales» aparecerá dentro de un `div` al principio del contenido del `pie de página` en todas las páginas públicas. 

![Imagen](modulesfiles/localcontexts_sitePublic.png)

### Aplicar proyectos a los elementos

Se pueden asignar uno o varios proyectos de Local Contexts para completar un valor de metadatos, ya sea en uno o en todos los idiomas. Puedes elegir cualquier campo de metadatos proporcionado por cualquier vocabulario de tu instalación. 

Ve a la interfaz de edición del elemento y busca la pestaña «Avanzado» en la parte superior de la pantalla. En esta página verás una sección de Local Contexts que te permite asignar un proyecto de un menú desplegable a una propiedad de metadatos elegida de otro menú desplegable. 

![Imagen](modulesfiles/localcontexts_itemEdit.png)

Al guardar los cambios, verás los avisos y etiquetas visuales introducidos como valores independientes en la propiedad que hayas elegido, junto con una etiqueta de idioma de dos o cuatro letras extraída de los metadatos del proyecto de Local Contexts. 

![Imagen](modulesfiles/localcontexts_itemAdmin.png)

Los valores de metadatos se introducen en formato JSON:

![Imagen](modulesfiles/localcontexts_itemAdmin2.png)

Ten en cuenta que el [módulo Metadata Browse](metadatabrowse.md) puede entrar en conflicto con Local Contexts en las entradas de metadatos, al añadir enlaces al texto de los «Avisos» y las «Etiquetas». Puedes seguir utilizando «Metadata Browse» para permitir a los usuarios explorar todos los elementos que pertenezcan a los mismos proyectos, pero te recomendamos que desmarques la casilla «Enlaces directos» en la configuración del módulo. 

### Aplicar proyectos a las páginas del sitio

«Local Contexts» también se puede mostrar en una página del sitio mediante el uso de un bloque de página específico. Edita una página y, a continuación, selecciona el bloque «Contextos locales» en el panel lateral derecho. Dentro del bloque de la página, elige un proyecto del menú desplegable y un idioma, si lo deseas. 

![Imagen](modulesfiles/localcontexts_pageEdit.png)

Esto mostrará los proyectos de «Contextos locales» prácticamente con el mismo formato que el pie de página del sitio. 

### Eliminar proyectos 

Una vez que se ha añadido un proyecto a un elemento, una página del sitio o al pie de página del sitio, hay que eliminarlo manualmente. Edita el elemento, el sitio o la página y elimina el contenido a mano. 

Puedes eliminar un proyecto de la lista de proyectos que se mostrará en el futuro volviendo a la entrada del módulo «Contextos locales» en la barra lateral. Guarda el formulario vacío que se muestra en primer lugar; así verás la lista de proyectos que ya se han asignado. Puedes eliminar proyectos individuales marcando las casillas y guardando esta página. 

![Imagen](modulesfiles/localcontexts_remove.png)

Eliminar un proyecto de la lista de proyectos de la página del módulo «Contextos locales» **no** eliminará dicho proyecto de los recursos a los que se haya añadido. Solo eliminará la opción de añadirlo a recursos en el futuro. 