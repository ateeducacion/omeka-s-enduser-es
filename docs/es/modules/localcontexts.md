# Contextos locales

El [módulo Contextos locales](https://omeka.org/s/modules/LocalContexts){target=_blank} permite a los usuarios aplicar [Contextos locales](https://localcontexts.org/){target=_blank} Avisos y Etiquetas a los sitios, páginas y recursos de Omeka S. Para ello, es necesario crear una cuenta en Contextos Locales y crear Proyectos en el registro. A continuación, introduzca la clave API en Omeka para importar los [Avisos](https://localcontexts.org/notices/about-the-notices/){target=_blank} y [Etiquetas](https://localcontexts.org/labels/about-the-labels/){target=_blank} y aplicarlas a elementos, sitios y páginas. 

![](modulesfiles/localcontexts_itemPublic.png)

## ¿Qué es Local Contexts?

Local Contexts es una iniciativa global que apoya a las comunidades indígenas con herramientas que permiten reafirmar la autoridad cultural sobre las colecciones y los datos patrimoniales. Local Contexts tiene tres componentes de interés para los usuarios de Omeka: Notices, Labels y Projects.

### Notices

Este texto procede del [sitio web de Local Contexts](https://localcontexts.org/notices/about-the-notices/){target=_blank}:

> *Los Avisos son herramientas para que las instituciones y los investigadores identifiquen las colecciones y los datos indígenas y reconozcan los derechos e intereses indígenas. Los avisos se desarrollaron para crear vías de asociación, colaboración y apoyo a la autoridad cultural indígena.*

> *Los avisos pueden aplicarse a sitios web, publicaciones, conjuntos de datos, exposiciones de museos, objetos de una colección, muestras genéticas y mucho más. Las instituciones y los investigadores pueden generar avisos utilizando el Local Contexts Hub.*

> *Existen tres categorías de avisos: Avisos de participación, de divulgación y de cuidado de colecciones. Consulte a continuación para obtener más información sobre los diferentes tipos de avisos.*

![Imagen](modulesfiles/localcontexts_notices.png)

### Etiquetas

Este texto procede del [sitio web de Local Contexts](https://localcontexts.org/labels/about-the-labels/){target=_blank}:

> *Las etiquetas de Conocimiento Tradicional (TK) y Biocultural (BC) son herramientas para las comunidades indígenas y las organizaciones locales. Desarrolladas a través de una colaboración sostenida y pruebas realizadas en comunidades indígenas de múltiples países, las etiquetas permiten a las comunidades expresar condiciones locales y específicas para compartir y participar en futuras investigaciones y relaciones de manera coherente con las normas, la gobernanza y los protocolos comunitarios ya existentes para el uso, el intercambio y la difusión de conocimientos y datos.*

> *Las etiquetas pueden aplicarse a sitios web, publicaciones, conjuntos de datos, exposiciones de museos, objetos de una colección, muestras genéticas y mucho más. Las comunidades pueden personalizar y aplicar sus etiquetas de CC y CC utilizando el Centro de Contextos Locales.*

![Imagen](modulesfiles/localcontexts_labels.png)

### Proyectos

Este texto procede del [sitio web de Local Contexts](https://localcontexts.org/support/getting-started-on-the-hub/){target=_blank}:

> *¿Qué es un proyecto de Local Contexts?*

> *Los proyectos de Local Contexts describen el contexto en el que se aplican las etiquetas o los avisos. Por ejemplo, un proyecto podría incluir: un sitio web, un programa de estudios universitario, una tesis, una publicación de investigación, un conjunto de datos, una exposición en un museo, un registro de archivo, un objeto de una colección, una base de datos de biblioteca, una colección fotográfica, un espécimen de referencia y/o metadatos sobre un registro.*

> *Al crear un proyecto de Contextos Locales, se le solicitarán los detalles del proyecto y los datos de contacto, y tendrá la opción de añadir metadatos.*

> *La creación de proyectos permite a las instituciones y a los investigadores generar avisos e involucrar, reconocer y dar visibilidad a los intereses indígenas en las colecciones, la información y los datos. Las comunidades pueden entonces elegir cómo y cuándo añadir sus etiquetas.*

> *Las cuentas de la comunidad pueden aplicar etiquetas personalizadas a los proyectos que crean en el Hub, así como a los proyectos que les han enviado las cuentas de instituciones e investigadores. Puedes ver los proyectos que se han añadido al Hub de forma pública en el tablero de proyectos.*

![Imagen](modulesfiles/localcontexts_hub.png)

## Preparación para utilizar el módulo de Contextos Locales

El módulo Contextos Locales tiene como objetivo fomentar la participación de los miembros de las comunidades indígenas, mediante Avisos creados por las instituciones y Etiquetas creadas por la comunidad. Un Aviso de «Abierto a la colaboración», por ejemplo, indica que se agradece la colaboración. Por lo tanto, debe estar preparado para gestionar dicha colaboración. Si utiliza avisos, asegúrese de que su sitio Omeka disponga de medios para que los miembros de las comunidades indígenas puedan participar: creación de cuentas para los miembros de las comunidades indígenas, la posibilidad de añadir proyectos y etiquetas de Contextos Locales al sitio, un formulario de contacto, comentarios sobre los elementos o un plan para que el personal responda a las contribuciones. Piensa en el flujo de trabajo que pretendes seguir para mejorar tus colecciones en colaboración antes de continuar.

### Cuenta de Local Contexts Hub

Para utilizar este módulo, debes tener una cuenta de Local Contexts Hub. Crear un perfil allí te permite tener uno o más proyectos, que luego se pueden conectar a tu instalación de Omeka con una clave API.

[Visita el sitio web de Local Contexts para obtener más información y configurar tus proyectos](https://localcontexts.org/support/getting-started-on-the-hub/#about-projects){target=_blank}. 

Un proyecto puede diseñarse para un único objeto, una colección, una exposición o para toda su institución. Puede que tenga necesidades sencillas —como añadir un aviso de «Abierto a la colaboración» en el pie de página de su sitio Omeka— o complejas, como conjuntos de etiquetas separados y únicos para cada uno de los cientos de elementos. Familiarícese con todas las opciones de avisos y etiquetas de Local Contexts, y planifique qué conjunto de proyectos necesitará para expresar la situación de su organización. 

### Permisos

Los proyectos de Local Contexts se pueden aplicar a sitios en los que el usuario tenga permisos de administrador del sitio (o una cuenta de administrador global para toda la instalación); Los avisos y las etiquetas se pueden añadir a las páginas del sitio para las que el usuario tenga permiso (nivel de creador del sitio o superior). Los proyectos de Local Contexts se pueden añadir a los recursos en los que el usuario tenga permisos de edición (ya sea el propietario del recurso o una cuenta con nivel de editor o superior). 

## Cómo utilizar el módulo Local Contexts

### Importar proyectos

Con el módulo instalado y activo en su sitio Omeka, vaya a la entrada del módulo «Local Contexts» en la barra lateral del panel de administración. Allí podrá introducir su clave API desde el Local Contexts Hub. 

![Imagen](modulesfiles/localcontexts_api.png)

Opcionalmente, puede seleccionar solo algunos de sus proyectos para importarlos, introduciendo sus ID. Si deja el campo «Proyectos» en blanco, Omeka cargará todos los proyectos asociados a su clave API de Local Contexts. 

Al guardar la página, los proyectos se cargarán en la pestaña «Asignar». Verás el nombre de cada proyecto y todos sus avisos y etiquetas asociados. En esta pantalla puedes marcar la casilla de cada proyecto que desees que esté disponible a través de la clave API que acabas de introducir. Si no marca ninguno de estos proyectos antes de guardar la página, no se conservarán en el sitio de Omeka. Asignar los proyectos en esta fase no hará que aparezcan en su sitio; aún tendrá que aplicarlos manualmente a los elementos y páginas del sitio, y colocarlos en el pie de página del sitio. 

![Imagen](modulesfiles/localcontexts_assign.png)

Omeka S no guardará la clave API y no establece una conexión permanente. Si actualizas el contenido en el sitio web de LC Hubs, tendrás que volver a introducir la clave API para actualizar la información de Omeka desde la fuente. A continuación, deberá volver a aplicar los proyectos modificados al pie de página, a los elementos y a las páginas del sitio, según corresponda. 

Otros usuarios de la instalación de Omeka pueden añadir más proyectos introduciendo otra clave API de LC (o introduciendo la misma clave y asignando otros proyectos). Los proyectos de todas las fuentes aparecerán juntos en la interfaz y cualquier usuario podrá acceder a ellos. 

Si vuelve a esta página después de haber introducido inicialmente una clave API, verá el mismo formulario para introducir una nueva clave API. Puede ignorarlo y guardar la página si desea ver la lista de proyectos ya importados a su sitio. Esto aparecerá en la pestaña «Eliminar». 

Esta tabla le permitirá eliminar proyectos de su sitio. Si desea volver a añadir estos proyectos más adelante, tendrá que volver a importarlos introduciendo la clave API de nuevo. Esto no modificará ningún elemento ni exposición; todo lo que ya esté asignado deberá eliminarse manualmente. 

### Aplicar proyectos a los sitios

Los gestores de sitio o los administradores globales pueden elegir uno o más proyectos de Contextos Locales para que aparezcan en el pie de página de cada sitio de su instalación de Omeka S. Vaya a la pestaña «Sitios» en la barra lateral, seleccione un sitio y vaya a «Administración del sitio». En la pestaña «Configuración» de la página de administración del sitio, busca la sección Local Contexts. Desde aquí puedes elegir uno o varios de los proyectos que se han asignado a la instalación tras introducir una clave API. 

![Imagen](modulesfiles/localcontexts_site.png)

Puedes elegir mostrar uno o todos los idiomas de los Avisos y Etiquetas seleccionados en los Proyectos elegidos. 

El contenido del pie de página de Local Contexts aparecerá dentro de un `div` al principio del contenido del `pie de página` en todas las páginas públicas. 

![Imagen](modulesfiles/localcontexts_sitePublic.png)

### Aplicar proyectos a elementos

Se pueden asignar uno o más proyectos de Local Contexts para completar un valor de metadatos, en uno o en todos los idiomas. Puede elegir cualquier campo de metadatos proporcionado por cualquier vocabulario de su instalación. 

Ve a la interfaz de edición del elemento y busca la pestaña «Avanzado» en la parte superior de la pantalla. En esta página verás una sección de Local Contexts que te permite asignar un proyecto de un menú desplegable a una propiedad de metadatos elegida de otro menú desplegable. 

![Imagen](modulesfiles/localcontexts_itemEdit.png)

Al guardar los cambios, verá los avisos y etiquetas visuales introducidos como valores independientes en la propiedad que haya elegido, junto con una etiqueta de idioma de dos o cuatro letras extraída de los metadatos del proyecto de Local Contexts. 

![Imagen](modulesfiles/localcontexts_itemAdmin.png)

Los valores de metadatos se introducen como JSON:

![Imagen](modulesfiles/localcontexts_itemAdmin2.png)

Ten en cuenta que el [módulo Metadata Browse](metadatabrowse.md) puede entrar en conflicto con Local Contexts en las entradas de metadatos, añadiendo enlaces al texto de los avisos y las etiquetas. Puede seguir utilizando Metadata Browse para permitir a los usuarios explorar todos los elementos con los mismos proyectos, pero recomendamos desmarcar la casilla «Enlaces directos» en la configuración del módulo. 

### Aplicar proyectos a las páginas del sitio

Los contextos locales también se pueden mostrar en una página del sitio mediante el uso de un bloque de página específico. Edite una página y, a continuación, seleccione el bloque «Contextos locales» en el panel de la derecha. Dentro del bloque de página, elija un proyecto del menú desplegable y un idioma, si lo desea. 

![Imagen](modulesfiles/localcontexts_pageEdit.png)

Esto mostrará los proyectos de Contextos locales básicamente con el mismo formato que el pie de página del sitio. 

### Eliminar proyectos 

Una vez que se ha añadido un proyecto a un elemento, una página del sitio o al pie de página del sitio, debe eliminarse manualmente. Edita el elemento, el sitio o la página y elimina el contenido a mano. 

Puede eliminar un proyecto de la lista de proyectos que se mostrará en el futuro volviendo a la entrada del módulo Local Contexts en la barra lateral. Guarde el formulario vacío que se muestra al principio; esto le mostrará la lista de proyectos que ya se han asignado. Puede eliminar proyectos individuales marcando las casillas y guardando esta página. 

![Imagen](modulesfiles/localcontexts_remove.png)

Eliminar un proyecto de la lista de proyectos de la página del módulo Contextos locales **no** eliminará dicho proyecto de los recursos a los que se haya añadido. Solo eliminará la opción de añadirlo a recursos en el futuro. 