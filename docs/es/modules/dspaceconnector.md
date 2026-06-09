# Conector DSpace

El [módulo Conector DSpace](https://omeka.org/s/modules/DspaceConnector){target=_blank} te permite conectar una instancia de Omeka S a un [repositorio DSpace](https://duraspace.org/dspace/){target=_blank} para importar elementos de dicho repositorio. Además de importar la información, el elemento de Omeka S mantendrá una conexión con el elemento original. Esto le permite [actualizar la información de la fuente cuando lo desee](#update-imported-resources).

Ten en cuenta que DSpace Connector solo funciona con las versiones 5.6 y superiores de DSpace, incluida la 7.x. Este conector se basa en la API de DSpace y en su configuración específica para cada sitio.

## Importar datos

Vaya a la sección denominada «DSpace Connector» en Módulos.

![Las opciones de importación de DSpace Connector. Los campos se enumeran en el texto a continuación.](../modules/modulesfiles/dspace_import.png)

En el primer formulario, introduzca la siguiente información:

* **URL del sitio DSpace** del repositorio: la URL completa, incluyendo `http://`. Debe ser la URL base del repositorio DSpace sin añadir al final la información `/rest/` o `/server/`.
* **Punto final** de la API (las versiones de DSpace anteriores a la 7 probablemente utilicen `rest` como punto final; este es el valor predeterminado. Las versiones de DSpace 7 y superiores probablemente utilicen `server/api` como punto final; tendrá que cambiarlo manualmente).
* **Límite** o número máximo de resultados que se pueden recuperar de una sola vez.
* **Importación de prueba** SOLO si desea importar el número de resultados indicado en el campo Límite anterior desde la colección elegida en la siguiente pantalla. Útil para realizar pruebas y ajustes.

Haga clic en el botón «Obtener colecciones y comunidades». Si la información anterior se ha introducido correctamente, pasará a la página de opciones de importación del conector de DSpace. Esta página contiene las pestañas «Configuración básica de importación» y «Colecciones».

Si no aparece ninguna colección o el conector se bloquea, [compruebe que su API sea de acceso público](#check-the-api).

### Configuración básica de importación
Esta pestaña tiene cinco opciones:

* **Importar archivos a Omeka S**: marque esta casilla para importar archivos además de metadatos.
* **Conjunto de elementos**: seleccione un conjunto de elementos del menú desplegable en el que importar los elementos, o cree un nuevo conjunto de elementos con el nombre de la colección de DSpace importada.
* **Sitios**: añade los elementos importados al sitio o sitios especificados. Los sitios predeterminados globales y específicos del usuario aparecerán preseleccionados aquí.
* **Campos ignorados**: campos de metadatos de DSpace que se deben ignorar durante la importación, separados por comas.
* **Comentario**: comentarios que se adjuntarán al lote de importación, los cuales aparecerán en la página «Importaciones anteriores de DSpace».

![La pantalla de configuración básica de importación con los campos enumerados anteriormente, sin nada introducido y sin casillas marcadas.](../modules/modulesfiles/dspace_importset.png)

### Colecciones
Esta pestaña mostrará la lista de colecciones del repositorio DSpace, organizadas por la comunidad a la que pertenecen. Puede importar una colección cada vez o todo el repositorio DSpace.

Para importar una sola colección, haga clic en el botón «Importar» situado a la izquierda de su nombre. Esto iniciará automáticamente la importación.

![La pestaña Colecciones muestra algunas colecciones de ejemplo importadas del repositorio DSpace de mars.gmu.edu, incluida una agrupación denominada «Colecciones administrativas» con las colecciones «GMU Dark Archive», «Materiales de conservación» y «Artes visuales». Hay un botón en la parte superior de la pantalla para «Importar todo el repositorio» y un botón en cada colección que muestra «Importar colección». Hay botones para «Expandir todo» y «Contraer todo» en las agrupaciones.](../modules/modulesfiles/dspace_coll.png)

Para importar todo el repositorio, haga clic en «Importar todo el repositorio» en la parte superior del formulario.

!!! nota
  Importar un repositorio DSpace completo con un gran número de elementos (más de 5000) probablemente saturará el servidor de alojamiento de DSpace con solicitudes hasta provocar un fallo. Considere la posibilidad de importar colección por colección. Si aún así desea importar un repositorio grande completo de una sola vez, lo siguiente podría serle de ayuda:

  * En el menú inicial «Configuración de importación», establezca **Límite** en un número menor, como 50 o 25.
	* Pruebe la importación marcando la casilla **Probar importación** en el menú inicial «Configuración de importación».
  * Ejecute la importación por la noche o en cualquier momento en que haya menos tráfico en el servidor de DSpace.
	* Considere la posibilidad de insertar temporalmente [una función `sleep()`](https://www.w3schools.com/php/func_misc_sleep.asp){target=_blank} entre la importación de cada registro en `Import.php` para ralentizar ligeramente el proceso (no recomendado para producción).

Puede realizar un seguimiento del estado de las importaciones accediendo a la pestaña «Importaciones anteriores» de DSpace Connector, o en la página [Tareas](../admin/jobs.md) del panel de administración.

!!! nota
  ¿Sus trabajos se inician pero no se completan? Es posible que tenga que [configurar la ruta de PHP](../configuration.md#php-path) para que su sistema pueda ejecutar el proceso en segundo plano para crear los elementos.

## Revisar importaciones

La página «Importaciones pasadas de DSpace» muestra una tabla con las importaciones pasadas de DSpace, con una casilla de verificación para **Deshacer**, otra para **Volver a ejecutar**, el **ID de la tarea** de la importación, el **enlace a la colección de DSpace** del repositorio (que se muestra como nombre de la colección si se encuentra), cualquier **comentario** realizado durante la importación, el número de **elementos** importados con un enlace a los resultados de la búsqueda avanzada, la **fecha** de la importación, el **estado** de la importación, y el **Propietario**, o el usuario que inició la importación.

![Tabla de importaciones anteriores que muestra dos importaciones completadas y una importación que dio lugar a un error al importar diferentes colecciones](../modules/modulesfiles/dspace_past.png)

Los elementos de DSpace se importarán con cualquier campo de metadatos reconocido en la fuente (como `dc.title` o `dc.description.abstract`), y utilizarán `bibo:uri` para cargar el URI tal y como aparece en el elemento de origen como `dc.identifier.uri`. Este será un enlace en el que se podrá hacer clic que se mostrará en las páginas públicas de los elementos y permitirá a los usuarios ver la fuente del elemento en su repositorio DSpace de origen. Si los campos tienen una o más etiquetas de idioma, los campos importados a Omeka también utilizarán esa etiqueta de idioma.

## Actualizar recursos importados

Para actualizar los recursos creados con el Conector DSpace, simplemente marque «Re-run» y haga clic en «Submit» en la página «Past DSpace Imports». Los recursos se actualizarán, no se volverán a importar. Esto le permite utilizar el Conector para sincronizar datos entre las instalaciones de DSpace y Omeka S.

## Deshacer una importación

Puede ver las importaciones anteriores en la página «Importaciones anteriores de DSpace». Para deshacer una importación completada y eliminar todos los elementos asociados, marque la casilla de cada importación que desee deshacer y haga clic en el botón «Enviar».

## Comprobar la API

Es posible que desee comprobar primero que la instancia de DSpace que desea utilizar sea de acceso público. Para ello, utilice su navegador y compruebe el punto final de la API:

- Tome la URL del repositorio de DSpace y añada `/rest/collections` (para versiones anteriores a la 7.0) 
- Tome la URL del repositorio DSpace y añada `/server/api/core/collections/` (para las versiones 7.x y posteriores).

Si recibe un error al cargar la página en su navegador, la API de DSpace no está disponible para la importación; compruebe la configuración de la API REST de su instancia de DSpace.
