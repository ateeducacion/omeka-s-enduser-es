# Usuarios de los sitios

Los sitios tienen una configuración de usuarios específica, independiente de los [roles de usuario definidos a nivel de toda la instalación](../admin/users.md). Los usuarios deben añadirse a nivel de la instalación y, a continuación, añadirse individualmente a cada sitio al que se desee que tengan acceso. 

Los administradores globales y los supervisores tienen todos los permisos en todos los sitios. Los demás roles de usuario en Omeka S (editor, revisor, autor, investigador) no guardan relación con los roles de usuario específicos de cada sitio (administrador, creador, visitante). Por ejemplo, un usuario designado como investigador en la instalación puede, no obstante, ser designado como administrador de un sitio, lo que significa que puede eliminar ese sitio. 

Configurar a un usuario (a nivel de instalación) para que tenga un sitio predeterminado para sus elementos no le otorgará un rol de sitio. 

Para añadir un usuario a un sitio concreto, vaya a la pestaña **Permisos de usuario** después de seleccionar el sitio deseado.

![Pestaña de permisos de usuario sin usuarios añadidos y un directorio alfabético a la derecha](../sites/sitesfiles/sites_users.png)

Un panel situado en la parte derecha de la pantalla muestra todos los usuarios de su instalación, ordenados por la primera letra de su nombre de usuario. 

Para añadir un usuario, haga clic en su nombre. A continuación, seleccione su rol en el menú desplegable:

* **Visor**: Puede ver la entrada de un sitio en la lista de sitios, incluso si la visibilidad del sitio está configurada como privada, pero no puede realizar modificaciones.
* **Creador**: Puede acceder y editar todas las propiedades del sitio, es decir, todo lo disponible en el submenú específico del sitio. (Este rol se denominaba «Editor» en las versiones 1.x-2.x de Omeka S.)
* **Administrador**: Tiene privilegios administrativos completos sobre el sitio, incluyendo añadir/eliminar usuarios y borrar el sitio. (Este rol se denominaba «Admin» en las versiones 1.x-2.x de Omeka S.)

Puede añadir o revocar privilegios a los usuarios volviendo a la pestaña Permisos de usuario, marcando o desmarcando las casillas y haciendo clic en «Guardar». Los usuarios se pueden eliminar del sitio haciendo clic en el icono de la papelera de la fila correspondiente y confirmando la eliminación en el cuadro de diálogo que aparece.

Una vez que haya añadido uno o más usuarios, haga clic en el botón «Guardar» situado en la esquina superior derecha. Para cancelar los cambios, haga clic en el botón «Cancelar» en la esquina superior derecha. 

También puede utilizar la interfaz «Admin > Usuarios» para [editar opciones de usuario por lotes](../admin/users.md#batch-editing), lo que incluye añadir o eliminar uno o más usuarios de un sitio y cambiar el rol específico del sitio.

## Vistas de usuario

Los usuarios de nivel inferior, en un principio, solo verán los sitios para los que tengan algún tipo de permiso establecido. Pueden optar por ver todos los sitios de la instalación de Omeka S haciendo clic en el enlace «Ver todos los sitios» de la barra gris. Tenga en cuenta que, en la imagen de ejemplo que aparece a continuación, el usuario tiene permisos de edición para un sitio (indicado por el icono del lápiz) y solo privilegios de visualización para el otro (sin icono del lápiz). 

![Un usuario llamado «Autor» —con un rol de Autor para toda la instalación— solo puede ver dos sitios. Hay un enlace para que pueda ver todos los sitios de la instalación.](../sites/sitesfiles/sites_userView.png)

Puede optar por ver todos los sitios de la instalación de Omeka S haciendo clic en el enlace «Ver todos los sitios» de la barra gris. Tenga en cuenta que no verá los sitios cuya visibilidad esté configurada como privada, si aún no tiene acceso a ellos. 