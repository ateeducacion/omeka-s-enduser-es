# Página de Inicio

Omeka S permite a los usuarios construir múltiples sitios distintos dentro de una misma instalación, los cuales no están necesariamente conectados entre sí. Cada instalación tiene, por defecto, una página de inicio que lista todos los sitios de la instalación. Se accede a esta página yendo a la URL principal de su instalación de Omeka S; si su [panel de administración](admin-dashboard.md) estuviera en `su-dominio.org/omeka-s/admin`, entonces encontraría esta página en `su-dominio.org/omeka-s/`.

La página muestra todos los sitios que un usuario tiene permiso para ver, junto con los resúmenes y miniaturas de los sitios, si existen. Si alguien no ha iniciado sesión, solo verá los sitios públicos. Un Administrador Global que haya iniciado sesión, por el contrario, verá todos los sitios existentes en la instalación.

![Página de inicio de la instalación para "Stackable Sandbox" mostrando siete sitios, tres de los cuales tienen resúmenes.](files/frontpage-basic.png)

Si desea que esta página de índice permanezca oculta para los visitantes, un Administrador Global puede seleccionar un sitio público de su instalación al cual los visitantes serán redirigidos cuando naveguen a la URL base (`su-dominio.net/omeka-s/`). Para hacerlo:

- Vaya a Ajustes (el icono del engranaje), y luego a la pestaña General.
- Bajo la opción "Sitio por defecto", use el menú desplegable para seleccionar uno de sus sitios actuales.
- Para eliminar un sitio seleccionado y volver a la página de índice, haga clic en la pequeña "X" a la derecha del menú desplegable.

Puede personalizar un índice de sitios con su propia marca para su instalación creando un sitio, creando una página, y luego usando el bloque de página ["Lista de sitios"](sites/site_pages.md#page-blocks) para generar una lista de todos los sitios en la instalación. Después, use la opción "Sitio por defecto" para apuntar a ese sitio.