# Gestión de módulos

Los módulos amplían la funcionalidad de tu instalación y tus sitios de Omeka S. En el [Directorio de módulos](https://omeka.org/s/modules/){target=_blank} encontrarás una lista de los módulos disponibles para su descarga. Las instrucciones se encuentran en la página de documentación de cada módulo.

!!! Nota
    No todos los módulos funcionarán con todas las versiones de Omeka, especialmente los módulos más recientes en instalaciones antiguas. Es posible que haya versiones anteriores de los módulos disponibles en sus páginas de Github. Utilice el Directorio de módulos para encontrar el enlace «Github» situado en la parte derecha de la pantalla de cada complemento y, a continuación, busque la sección «Versiones» en la parte derecha de la página de Github.

![Captura de pantalla del panel de administración mostrando la pestaña Módulos activa.](modulesfiles/modules_browse.png)

Para gestionar los módulos instalados en su sitio Omeka S, haga clic en la sección **Módulos** en el panel de navegación de la izquierda de su [panel de administración](../admin-dashboard.md).

Ten en cuenta que solo los [administradores globales](../admin/users.md) pueden instalar y gestionar módulos; los supervisores pueden explorar los módulos instalados, pero no modificarlos. El resto de usuarios no tienen acceso a esta pestaña.

| Categoría | Permiso | Administrador global | Supervisor | Editor | Revisor | Autor | Investigador |
|-----|-----|---|---|---|---|---|---|
| Módulos | Instalar/Configurar | Sí | No | No | No | No | No |
|  | Usar | Sí | Sí | No | No | No | No |

Cualquier módulo que se haya subido a la carpeta `/modules` de la instalación debería aparecer en la lista de módulos. Cada módulo muestra su nombre junto con el número de versión, el creador y un resumen de su función.

Pueden aparecer varios botones a la derecha de la etiqueta de un módulo. Cada botón tiene un icono y una etiqueta que describe su acción:

- **Configurar** (icono de llave inglesa): algunos módulos tienen ajustes que se pueden modificar. Haga clic en este icono para ajustar la configuración del módulo de esta fila.
- **Activar/Desactivar** (interruptor deslizante): cuando un módulo está activo, el fondo del área del deslizador es transparente y el interruptor está a la izquierda. Cuando está inactivo, el fondo del área del deslizador es opaco y el interruptor está a la derecha.
- **Instalar/Desinstalar** (flecha y rectángulo): utiliza este botón para instalar o desinstalar un módulo. Cuando el botón es verde y la flecha apunta hacia abajo, puedes instalar el módulo. Cuando el botón es rojo y la flecha apunta hacia arriba, puedes desinstalar el módulo.

Cuando un módulo tiene una nueva versión, aparecerá en la página de exploración con un mensaje en verde que indica «Hay una nueva versión disponible de este módulo. Obtenga la nueva versión». Habrá un enlace a la página de descarga del módulo. [Sigue los pasos que se indican a continuación para actualizar un módulo](#updating-a-module). Estas advertencias solo aparecen en los módulos instalados y activados. Puedes [activar o desactivar estas notificaciones en la página de configuración](../admin/settings.md#general).

![Una lista de módulos en diferentes estados. Uno está desinstalado, otro está instalado pero no activo, dos están activos pero solo uno muestra un botón «Configurar». El último módulo de la lista tiene un banner de «nueva versión» en verde.](modulesfiles/modules_updatemsg.png)

## Añadir módulos a Omeka S
Para que aparezcan en la sección **Módulos** del panel de administración de tu instalación de Omeka S, los archivos de los módulos deben añadirse manualmente a la carpeta `/modules` de la instalación, utilizando un programa FTP o una conexión SSH.

Los módulos registrados en Omeka están disponibles en el directorio [Módulos](https://omeka.org/s/modules/){target=_blank} del sitio de Omeka S. Es posible que los autores de otros módulos los pongan a disposición en otras ubicaciones.

Para añadir un módulo al sitio mediante FTP:

1. Descarga el módulo comprimido en tu ordenador.
1. Abre tu cliente FTP, inicia sesión en el servidor que aloja la instalación de Omeka S y navega hasta la carpeta `/modules` (debería estar ubicada en la carpeta principal de la instalación).
1. Sube el módulo comprimido a la carpeta `/modules`.
1. Descomprime el módulo.

!!! nota
  La carpeta que aparece en la carpeta `/modules` debe mostrar el nombre del módulo, sin ningún número de versión. Si tienes problemas para instalar un módulo, comprueba que lo has descomprimido correctamente, sin crear niveles de carpetas adicionales.

Ten en cuenta que si descargas la carpeta de un módulo desde GitHub en lugar de desde el [Directorio de módulos](https://omeka.org/s/modules/){target=_blank}, debes asegurarte de descargar la [última versión](https://help.github.com/en/articles/linking-to-releases){target=_blank} en lugar de la versión en desarrollo activo. Si no estás seguro de cómo hacerlo, consulta los [archivos de ayuda de GitHub](https://help.github.com/en){target=_blank}.

También puedes utilizar SSH para clonar un módulo directamente desde el repositorio Git de ese módulo. Hazlo solo si te sientes cómodo con Git, GitHub y el uso de SSH.

### Instalación de módulos
Para instalar un módulo, ve a la pestaña Módulos en el panel de navegación de la izquierda del panel de administración de tu instalación de Omeka S.

Busca el módulo en la tabla y haz clic en el botón «Instalar». El módulo ya está instalado y se activará automáticamente. En el caso de los módulos con opciones de configuración, se te redirigirá a la página de configuración de ese módulo. En el caso de los módulos sin opciones de configuración, la página Módulos simplemente se recargará, con un mensaje de éxito en la parte superior.

![Mensaje de éxito resaltado en verde que dice «El módulo se ha instalado correctamente»](modulesfiles/modules_insuccess.png)

### Activación de un módulo

Si tienes un módulo instalado pero inactivo, haz clic en el botón «Activar» para utilizarlo. Deberías ver un mensaje de éxito una vez que se recargue la página. El botón «Activar» ahora dirá «Desactivar».

![Mensaje de éxito resaltado en verde que dice «El módulo se ha activado correctamente»](modulesfiles/modules_acsuccess.png)

## Configuración de un módulo
Algunos módulos, aunque no todos, incluyen la opción de configurar sus ajustes. Si un módulo activo muestra el botón «Configurar» con un icono de llave inglesa, debe hacer clic en él para conocer los ajustes de configuración de ese módulo.

La información relativa a las opciones de configuración de cada módulo se puede encontrar en la página de documentación de dichos módulos.

## Desinstalar un módulo

Si un módulo se elimina correctamente de una instalación de Omeka, se borrarán todas las tablas que haya creado en la base de datos y se perderán todos los datos que se hayan generado en relación con ese módulo mientras estuvo instalado. Por ejemplo, si utiliza el módulo Mapping para añadir datos de geolocalización a todos sus elementos, todos esos campos se eliminarán si desinstala Mapping. 

Eliminar un módulo es, en esencia, el proceso inverso a la instalación:

1. Desactive el módulo haciendo clic en el botón «Desactivar».
1. Desinstala el módulo haciendo clic en el botón «Desinstalar».
1. Se abrirá un panel en la parte derecha de la ventana pidiéndote que confirmes que deseas desinstalar el módulo. Haz clic en «Confirmar desinstalación» para continuar.

![Cuadro de diálogo de desinstalación del módulo con el mensaje «¿Está seguro de que desea desinstalar este módulo?»](modulesfiles/modules_confirmuninstall.png)

El módulo desinstalado seguirá apareciendo en su página de Módulos (con la opción de instalarlo) a menos que se elimine la carpeta del módulo de la carpeta `/modules` de la instalación de Omeka S, lo cual se puede hacer a través de FTP o SSH.

## Actualización de un módulo
Para actualizar un módulo mediante FTP:

1. Descarga la última versión del módulo en tu ordenador.
1. Abre tu cliente FTP e inicia sesión en el servidor que aloja la instalación de Omeka S.
1. Navega hasta la carpeta `/modules` (debería estar ubicada en la carpeta principal de la instalación).
1. Mueva la copia antigua del módulo a su ordenador.
1. Suba la carpeta comprimida de la última versión del módulo a la carpeta `/modules`.
1. En su cliente FTP, descomprima la nueva versión del módulo.
1. En el panel de control de la instalación de Omeka S, ve a la pestaña Módulos y haz clic en el botón Actualizar del módulo.
1. Comprueba que se han conservado tus ajustes y que no hay errores. A continuación, puedes eliminar con total seguridad la carpeta del módulo antiguo que guardaste en tu ordenador.

Si te preocupa que surjan problemas con la actualización, asegúrate de conservar la versión anterior del módulo en tu equipo local por si tienes que volver a ella. Sigue los mismos pasos de actualización con la versión anterior del módulo.

Si tienes problemas durante la actualización, activa el [registro de errores](../errorLogging.md) y publica un mensaje en el [foro de Omeka](https://forum.omeka.org/c/omeka-s/modules){target=_blank}.
