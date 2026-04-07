# Panel de control administrativo

El panel de control administrativo gestiona el contenido compartido por todos los sitios de Omeka S y las funcionalidades básicas de la instalación de Omeka S. 

Este [vídeo tutorial](https://vimeo.com/455708039){target=_blank} te guía a través de las principales funciones del panel de control y te muestra cómo navegar por tu instalación de Omeka S:

<div style="padding:56.25% 0 0 0;position:relative;"><iframe src="https://player.vimeo.com/video/455708039?h=438143f0d3" style="position:absolute;top:0;left:0;width:100%;height:100%;" frameborder="0" allow="autoplay; fullscreen; picture-in-picture" allowfullscreen></iframe></div><script src="https://player.vimeo.com/api/player.js"></script>
<p><a href="https://vimeo.com/455708039">Navegando por Omeka S</a> de <a href="https://vimeo.com/omeka">Omeka</a> en <a href="https://vimeo.com">Vimeo</a>.</p>

## Página principal de administración

Cuando un usuario inicia sesión, la primera página que ve es el panel de control de administración. 

!!! nota
  Dependiendo del rol del usuario, es posible que no veas exactamente las mismas opciones en el menú de navegación de la izquierda. Consulta [más abajo](#left-hand-navigation) para obtener más detalles. 

![Vista completa del panel de control de administración](files/admindashfullview.png)

Además de la barra de navegación de la izquierda presente en todas las páginas (véase más abajo), el panel de control de administración muestra a los usuarios dos cuadros: **Gestionar recursos** y **Gestionar sitios**.

El cuadro **Gestionar recursos** muestra los siguientes recursos con su recuento total: [Elementos](content/items.md), [Conjuntos de elementos](content/item-sets.md), [Vocabularios](content/vocabularies.md) y [Plantillas de recursos](content/resource-template.md). Al hacer clic en la etiqueta del recurso, se le redirigirá a la página de exploración; al hacer clic en el botón con el símbolo de más situado a la derecha de la etiqueta, se le redirigirá a la página de añadir para ese tipo de recurso. 

El cuadro **Gestionar sitios** muestra los [Sitios](sites/index.md) de la instalación. Al hacer clic en el nombre del sitio, accederás a la pestaña de administración del sitio; al hacer clic en el pequeño icono de flecha situado a la derecha, accederás a la vista pública del sitio (en una nueva ventana o pestaña). 

## Navegación de la izquierda

El siguiente contenido aparece en el lado izquierdo del panel de administración y en todas las páginas administrativas. 

![Vista de la navegación de la izquierda en el panel de administración, que también aparece de forma coherente en toda la interfaz de administración, con las opciones que se describen a continuación](files/leftnav.png)

En la esquina superior izquierda de la pantalla hay un enlace que muestra el título de la instalación y que siempre te llevará de vuelta al panel de administración. 

Justo debajo del título de la instalación aparece el mensaje «Iniciado sesión como [Usuario]», donde [Usuario] es el nombre de usuario de la persona que ha iniciado sesión. Junto al nombre de usuario hay un icono de engranaje que [le llevará a su página de configuración de usuario](admin/users.md#user-settings). 

Cerca del nombre de usuario (debajo o a la derecha, dependiendo del ancho de la ventana) se encuentra el botón para **Cerrar sesión**. 

Debajo de la información del usuario hay un campo de búsqueda que cuenta con una opción de búsqueda avanzada (tres puntos) además del botón de búsqueda (lupa). Utilízalo para buscar todos los elementos de la instalación. 

Las opciones de búsqueda avanzada (los tres puntos) te permiten refinar la búsqueda por Tipo de recurso, limitándola a **Elementos**, **conjuntos de elementos** o **medios** haciendo clic en el botón de opción junto al tipo de recurso que desee buscar. 

![Opciones de búsqueda avanzada](files/search.png)

La barra de navegación de la izquierda del panel de control se divide en secciones relacionadas con la función y el acceso de los usuarios:

- [Sitios](sites/index.md): muestra y proporciona acceso a todos los sitios de la instalación de OmekaS. (Icono de ordenador)
- Recursos: creación de contenido y gestión de metadatos.
    - [Elementos](content/items.md): gestiona los recursos individuales de tu instalación. (Icono de caja)
    - [Conjuntos de elementos](content/item-sets.md): gestiona grupos agregados de elementos. (Icono de varias cajas)
    - [Vocabularios](content/vocabularies.md): gestiona los estándares de metadatos de tu instalación. (Icono de libro cerrado)
    - [Plantillas de recursos](content/resource-template.md): gestiona conjuntos predefinidos de propiedades (campos) para usar al crear elementos. (Icono de lápiz en un cuadrado)
- Admin: administración a nivel de instalación (tenga en cuenta que es posible que algunas de estas pestañas no sean visibles para todos los niveles de usuario).
    - [Usuarios](admin/users.md): gestiona los usuarios de toda la instalación y de sitios individuales. (Icono de silueta humana)
    - [Módulos](modules/index.md): añade funcionalidad a sus sitios. (Icono de signo más dentro de un cuadrado)
    - [Tareas](admin/jobs.md): muestra las tareas activadas por el usuario que se están ejecutando actualmente. Nota: las tareas solo se muestran cuando se están ejecutando. (Icono de tres barras)
    - [Configuración](admin/settings.md): gestiona la configuración global de todos los sitios, el panel de administración y los paneles de los sitios. (Icono de engranajes)

Si ha instalado módulos, es posible que aparezcan en la sección de administración del menú de navegación de la izquierda, debajo de «Configuración».

Tenga en cuenta que los usuarios con permisos más limitados solo verán algunas de estas opciones de navegación.

## Información del sistema

En la esquina inferior derecha de cada página del panel de administración se encuentra la versión actual de Omeka S, junto con algunos enlaces útiles. Haga clic en el enlace «Información del sistema» para ver una página completa con detalles sobre su instalación.

![Página de ejemplo de información del sistema](files/systeminfo.png)

En esta página puede verificar las versiones de las dependencias que utiliza Omeka, como PHP, ImageMagick y MySQL. Si un módulo concreto requiere que su servidor proporcione algo como una utilidad PHP, puede buscarlo aquí. También puede consultar esta página para verificar si su instalación de Omeka reconoce un módulo que ha intentado instalar.

Ten en cuenta que la sección de PHP te indicará el «Límite de carga de archivos», que es el número que se refleja en la interfaz de carga de medios y en la interfaz de carga de activos. Ten en cuenta también que Omeka S te indicará de cuánto espacio libre en el servidor dispone. 

Es posible que se le pida que facilite la información de esta página cuando solicite asistencia técnica en los [Foros](https://forum.omeka.org/){target=_blank} o cuando publique un problema en GitHub. 

Hacer clic en los dos botones situados cerca de la parte inferior de la página puede ayudarte a verificar que PHP e ImageMagick funcionan correctamente en tu sitio. Hazlo justo después de la instalación para asegurarte de que no te encuentres con problemas más adelante, como al importar elementos por lotes o al ejecutar otras tareas que dependen de PHP.

![Ejemplo de resultados del botón de versión de PHP CLI y del botón de versión de ImageMagick](files/systeminfo_buttons.png)
