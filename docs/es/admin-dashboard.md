# Panel de Administración

El panel de administración gestiona el contenido compartido por todos los sitios de Omeka S y las funcionalidades principales de la instalación.

Este [videotutorial](https://vimeo.com/455708039){target=_blank} le guía a través de las características principales del panel y la navegación de su instalación de Omeka S:

<div style="padding:56.25% 0 0 0;position:relative;"><iframe src="https://player.vimeo.com/video/455708039?h=438143f0d3" style="position:absolute;top:0;left:0;width:100%;height:100%;" frameborder="0" allow="autoplay; fullscreen; picture-in-picture" allowfullscreen></iframe></div><script src="https://player.vimeo.com/api/player.js"></script>
<p><a href="https://vimeo.com/455708039">Navegando en Omeka S</a> from <a href="https://vimeo.com/omeka">Omeka</a> on <a href="https://vimeo.com">Vimeo</a>.</p>

## Página principal de Administración

Cuando un usuario inicia sesión, la primera página que ve es el Panel de Administración.

!!! note
	Dependiendo del rol del usuario, es posible que no vea exactamente las mismas opciones en el menú de navegación izquierdo. Consulte [abajo](#navegación-izquierda) para más detalles.

![Vista completa del panel de administración](files/admindashfullview.png)

Además del menú de navegación izquierdo presente en todas las páginas (ver más abajo), el panel de administración presenta a los usuarios dos recuadros: **Gestionar Recursos** y **Gestionar Sitios**.

El recuadro **Gestionar Recursos** muestra los siguientes recursos con su contador total: [Elementos](content/items.md), [Conjuntos de elementos](content/item-sets.md), [Vocabularios](content/vocabularies.md) y [Plantillas de recursos](content/resource-template.md). Al hacer clic en la etiqueta del Recurso, se le dirigirá a la página de exploración; al hacer clic en el botón con el símbolo de más a la derecha de la etiqueta, se le dirigirá a la página para añadir ese tipo de recurso.

El recuadro **Gestionar Sitios** lista los [Sitios](sites/index.md) de la instalación. Al hacer clic en el nombre del sitio, se le dirigirá a la pestaña administrativa del sitio; al hacer clic en el pequeño icono de flecha a la derecha, se le dirigirá a la vista pública del sitio (en una nueva ventana o pestaña).

## Navegación izquierda

El siguiente contenido aparece en el lado izquierdo del panel de administración y en todas las páginas administrativas.

![Vista del menú de navegación izquierdo en el panel de administración, que aparece de forma consistente en toda la interfaz de administración, con las opciones descritas a continuación](files/leftnav.png)

En la esquina superior izquierda de la pantalla hay un enlace que muestra el título de la instalación, el cual siempre le llevará de vuelta al panel de administración.

Directamente debajo del título de la instalación está el mensaje “Sesión iniciada como [Usuario]”, donde [Usuario] es el nombre de pila de la persona conectada. Junto al nombre de usuario hay un icono de engranaje que le [llevará a la página de ajustes de su usuario](admin/users.md#user-settings).

Cerca del nombre de usuario (debajo o a la derecha, según el ancho de la ventana) se encuentra el botón para **Cerrar sesión**.

Debajo de la información del usuario hay un campo de búsqueda que tiene una opción para búsqueda avanzada (puntos suspensivos) además del botón para buscar (lupa). Use esto para buscar en todos los elementos de la instalación.

Las opciones de búsqueda avanzada (los puntos suspensivos) le permiten refinar la búsqueda por Tipo de Recurso, limitándola a **Elementos**, **Conjuntos de elementos**, o **Medios** haciendo clic en el botón de opción junto al Tipo de Recurso que desea buscar.

![Opciones de búsqueda avanzada](files/search.png)

El menú de navegación izquierdo del panel se divide en secciones relacionadas con la función y el acceso del usuario:

- [Sitios](sites/index.md): lista y proporciona acceso a todos los sitios de la instalación de Omeka S. (Icono de ordenador)
- Recursos: creación de contenido y gestión de metadatos.
    - [Elementos](content/items.md): gestione los recursos individuales de su instalación. (Icono de caja)
    - [Conjuntos de elementos](content/item-sets.md): gestione grupos agregados de elementos. (Icono de múltiples cajas)
    - [Vocabularios](content/vocabularies.md): gestione los estándares de metadatos para su instalación. (Icono de libro cerrado)
    - [Plantillas de Recursos](content/resource-template.md): gestione conjuntos predefinidos de propiedades (campos) para usar al crear elementos. (Icono de lápiz en un cuadrado)
- Admin: administración a nivel de instalación (tenga en cuenta que algunas de estas pestañas pueden no ser visibles para todos los niveles de usuario).
    - [Usuarios](admin/users.md): gestione usuarios para toda la instalación y sitios individuales. (Icono de silueta humana)
    - [Módulos](modules/index.md): añada funcionalidad a sus sitios. (Icono de signo más en un cuadrado)
    - [Tareas de sistema](admin/jobs.md): muestra las tareas activadas por el usuario que se están ejecutando actualmente. NB: las tareas solo se muestran mientras se están ejecutando. (Icono de tres barras)
    - [Ajustes](admin/settings.md): gestione los ajustes globales para todos los sitios, el panel de administración y los paneles de los sitios. (Icono de engranajes)

Si ha instalado módulos, pueden aparecer en la sección de administración de la navegación izquierda, debajo de ajustes.

Tenga en cuenta que los usuarios con permisos más limitados solo verán algunas de estas opciones de navegación.

## Información del sistema

En la esquina inferior derecha de cada página del lado de administración se encuentra la versión actual de Omeka S, junto con algunos enlaces útiles. Haga clic en el enlace etiquetado como "Información del sistema" para ver una página completa con detalles sobre su instalación.

![Ejemplo de página de Información del sistema](files/systeminfo.png)

En esta página puede verificar las versiones de las dependencias que Omeka está utilizando, como PHP, ImageMagick y MySQL. Si un módulo en particular requiere que su servidor proporcione algo, como una utilidad de PHP, puede buscarlo aquí. También puede consultar aquí para verificar si su instalación de Omeka reconoce un módulo que ha intentado instalar.

Tenga en cuenta que la sección de PHP le indicará el "Límite de subida de archivos", que es el número que se refleja en la interfaz de carga de medios y en la interfaz de carga de activos. Note también que Omeka S le informará de cuánto espacio libre en el servidor tiene acceso.

Es posible que se le pida que proporcione la información de esta página al solicitar soporte técnico en los [Foros](https://forum.omeka.org/){target=_blank} o al publicar un problema en GitHub.

Hacer clic en los dos botones cerca de la parte inferior de la página puede ayudarle a verificar que PHP e ImageMagick funcionan correctamente para su sitio. Haga esto justo después de la instalación para asegurarse de no encontrar problemas más adelante, como al importar elementos por lotes o ejecutar otras tareas dependientes de PHP.

![Ejemplo de resultados del botón de versión de PHP CLI y del botón de versión de ImageMagick](files/systeminfo_buttons.png)