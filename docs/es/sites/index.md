#  Gestión de sitios

Los sitios son la parte visible para el público de una instalación de Omeka S. Con los sitios, puedes crear contenido e interpretaciones en torno a un conjunto de elementos de tu instalación. 

Los sitios se gestionan y se accede a ellos a través del enlace «Sitios» situado en la parte izquierda del panel de administración. 

![Vista de gestión de sitios, que muestra el enlace del botón Sitios a la izquierda, el botón Añadir nuevo y la tabla de sitios con ocho sitios listados](../sites/sitesfiles/sites_admin.png)

La página Sitios muestra una tabla con todos los sitios de la instalación, indicando el título y el propietario de cada sitio. 

Utilice los dos menús desplegables situados a la derecha, encima de la tabla, para ordenar sus sitios. Puede ordenarlos por **título**, **slug de URL** o **propietario**, ya sea en orden ascendente o descendente. Haga clic en el botón «Ordenar» para aplicar sus elecciones. 

Encima de la tabla de sitios, a la izquierda, se encuentra la paginación de la tabla de sitios.

Cada fila muestra el título de un sitio a la izquierda, la URL en el centro y el nombre de visualización del propietario del sitio a la derecha. Cada sitio tiene opciones para **ver** (el cuadro con la flecha hacia fuera), **editar** (el lápiz) o **eliminar** (la papelera). **Solo los administradores globales y los propietarios de los sitios pueden eliminar un sitio.**

Los sitios que no son públicos mostrarán el icono **privado** (un ojo tachado) a la derecha del título del sitio. 

Al hacer clic en el título del sitio, accederás a una página de resumen del sitio que muestra el **slug de la URL**, el **título**, el **tema** y la **imagen en miniatura** asociados al sitio. Puede volver a la lista de sitios, o «Editar» o «Ver» el sitio utilizando los botones de la esquina superior derecha. También verá que el menú de la izquierda se expande para mostrar las opciones de gestión del sitio.

![Mostrar página del sitio «Importer Testing» indicando que el tema es el predeterminado y que el slug es «importer-testing».](../sites/sitesfiles/sites_quickshow.png)

## Añadir un sitio
Para crear un sitio, haz clic en el botón «Añadir nuevo sitio» situado en la esquina superior derecha de la página de exploración de sitios.

La página «Nuevo sitio» tiene dos pestañas: **Información** y **Tema**.

### Pestaña Info

* Asigna un **título** a tu sitio (obligatorio).
* Crea un **slug** para la URL del sitio (opcional). La URL de este sitio será `youromekainstall.org/s/slug`. Si dejas este campo en blanco, Omeka S creará un slug basado en el título del sitio.
* Crea un **resumen** para tu sitio: una breve descripción de su contenido (opcional). El texto del resumen aparecerá en la página de inicio de tu instalación y en el bloque de página [lista de sitios](site_pages.md#list-of-sites).
* Sube una **miniatura** para tu sitio o selecciona una de los recursos de tu instalación (opcional). Esta aparecerá junto al texto del resumen en la página de inicio y en el [bloque de la página de lista de sitios](site_pages.md#list-of-sites). Recomendamos utilizar una imagen pequeña, de no más de 240 píxeles de ancho (el tamaño máximo que se mostrará en la página de inicio). También puedes [configurar un favicon para tu sitio más adelante](site_settings.md#general-settings).

![Pestaña de administración de un nuevo sitio sin nada introducido](../sites/sitesfiles/siteadd_admin.png)

### Pestaña «Tema»
Selecciona uno de los [temas instalados](site_theme.md). Cada tema aparece como un mosaico con una captura de pantalla del tema, el nombre del tema y un enlace a su creador. Cuando se selecciona un tema, se resalta en gris y aparece una casilla de verificación en la esquina inferior derecha del mosaico.

![Pestaña «Tema» con el tema predeterminado seleccionado](../sites/sitesfiles/siteadd_theme.png)

### Publicación
En la esquina superior derecha de la pantalla, junto al botón «Añadir», puedes configurar la visibilidad de tu sitio haciendo clic en el icono del ojo para que el sitio sea público o privado.

El sitio es público: ![botón para hacer público que muestra un icono de ojo](../content/contentfiles/item_public.png){style="display:inline;"}

El sitio es privado: ![botón para hacer privado que muestra un icono de ojo tachado con una barra diagonal](../content/contentfiles/item_private.png){style="display:inline;"}

Los sitios se crean como públicos de forma predeterminada. Probablemente querrá hacer que el sitio sea privado hasta que haya terminado de configurarlo y haya añadido algo de contenido.

Cuando esté listo, haga clic en el botón «Añadir» situado en la esquina superior derecha. No puede guardar un borrador del sitio, pero puede hacer que el sitio sea privado mientras termina de trabajar en él. Una vez creado el sitio, se le redirigirá a la pestaña «Información» del sitio. 

Si decides que no quieres crear este sitio, haz clic en el botón «Cancelar» situado en la esquina superior derecha, junto al botón «Añadir».

## Gestionar sitios
Para gestionar un sitio, ve a la pantalla **Sitios** desde el panel de administración. Haz clic en el título del sitio o en el botón de edición (icono del lápiz) en la lista de sitios. 

Esto le llevará a la pestaña «Información» del sitio y abrirá el menú contextual de ese sitio en el panel de navegación de la izquierda. 

El menú contextual de cada sitio muestra el título del sitio en la parte superior, con un icono de un ordenador (el icono del sitio) a la izquierda. A la derecha del título del sitio hay un botón de vista (cuadro con una flecha de salida). Al hacer clic en el botón de vista, se abrirá la parte pública del sitio en una nueva pestaña o ventana.

![Menú contextual del sitio «Mysteries», con dos módulos instalados](../sites/sitesfiles/sites_menu.png)

Las opciones de navegación de la barra lateral izquierda del administrador del sitio son: 

- [Administrador del sitio](../sites/site_settings.md)
- [Páginas](../sites/site_pages.md)
- [Navegación](../sites/site_navigation.md) 
- [Recursos](../sites/site_resources.md)
- [Permisos de usuario](../sites/site_users.md)
- [Tema](../sites/site_theme.md)
- Ajustes añadidos por los módulos, si están instalados.
