# Página de inicio

Omeka S permite a los usuarios crear varios sitios independientes dentro de una misma instalación, que no tienen por qué estar conectados entre sí. Cada instalación cuenta, por defecto, con una página de inicio que muestra todos los sitios de la instalación. Se accede a esta página yendo a la URL principal de tu instalación de Omeka S; si tu [panel de administración](admin-dashboard.md) estaba en `tudominio.org/omekas/admin`, entonces encontrarás esta página en `tudominio.org/omekas/`.

La página muestra todos los sitios que un usuario tiene permiso para ver, junto con los resúmenes y las miniaturas de los sitios, si existen. Si alguien no ha iniciado sesión, solo verá los sitios públicos. Por el contrario, un administrador global que haya iniciado sesión verá todos los sitios existentes en la instalación.

![Página principal de la instalación de «Stackable Sandbox» que muestra siete sitios, tres de los cuales tienen resúmenes.](files/frontpage-basic.png)

Si desea que esta página de índice quede oculta a los visitantes del sitio, un administrador global puede seleccionar un sitio público de su instalación al que se redirigirá a los visitantes cuando accedan a su URL base (de `yourdomain.org/omekas/` a `yourdomain.org/omekas/s/yourmainsite/`). Para ello:

- Vaya a Configuración (el icono de engranaje) y, a continuación, a la pestaña General.
- En la opción «Sitio predeterminado», utiliza el menú desplegable para seleccionar uno de tus sitios actuales.
- Para eliminar un sitio seleccionado y volver a la página de índice, haz clic en la pequeña «X» situada a la derecha del menú desplegable.

Puedes personalizar un índice de sitios con tu marca para tu instalación creando un sitio, creando una página y, a continuación, utilizando el ["bloque de página Lista de sitios"](sites/site_pages.md#page-blocks) para generar una lista de todos los sitios de la instalación. A continuación, utiliza la opción «Sitio predeterminado» para apuntar a ese sitio.