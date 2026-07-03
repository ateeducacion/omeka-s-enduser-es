# Conector DSpace

El [módulo DSpace Connector](https://omeka.org/s/modules/DspaceConnector){target=_blank} te permite conectar una instancia de Omeka S a un [repositorio DSpace](https://duraspace.org/dspace/){target=_blank} para importar elementos desde dicho repositorio. Además de importar la información, el elemento de Omeka S mantendrá una conexión con el elemento original. Esto te permite [actualizar la información desde la fuente cuando lo desees](#update-imported-resources).

Ten en cuenta que el conector DSpace solo funciona con las versiones 5.6 y superiores de DSpace, incluida la versión 7.x. Este conector se basa en la API de DSpace y en su configuración específica para cada sitio.

## Importar datos

Accede a la sección denominada «DSpace Connector» en la sección Módulos.

![Las opciones de importación de DSpace Connector. Los campos se enumeran en el texto a continuación.](../modules/modulesfiles/dspace_import.png)

En el primer formulario, introduce la siguiente información:

* **URL del sitio DSpace** del repositorio: la URL completa, incluyendo `http://`. Debe ser la URL base del repositorio DSpace sin añadir al final la información `/rest/` ni `/server/`.
* **Punto final** de la API (las versiones de DSpace anteriores a la 7 probablemente utilicen `rest` como punto final; este es el valor por defecto. Las versiones de DSpace 7 y superiores probablemente utilicen `server/api` como punto final; tendrás que cambiarlo manualmente).
* **Límite** o número máximo de resultados que se pueden recuperar de una sola vez.
* **Importación de prueba** SOLO si deseas importar el número de resultados indicado en el campo «Límite» anterior desde la colección seleccionada en la siguiente pantalla. Útil para realizar pruebas y ajustes.

Haz clic en el botón «Obtener colecciones y comunidades». Si la información anterior se ha introducido correctamente, pasarás a la página de opciones de importación del conector de DSpace. Esta página contiene las pestañas «Configuración básica de importación» y «Colecciones».

Si no aparece ninguna colección o el conector se bloquea, [comprueba que tu API sea de acceso público](#check-the-api).

### Configuración básica de importación
Esta pestaña contiene cinco opciones:

* **Importar archivos a Omeka S**: marca esta casilla para importar archivos además de los metadatos.
* **Conjunto de elementos**: selecciona en el menú desplegable un conjunto de elementos al que importar los elementos, o crea un nuevo conjunto de elementos con el nombre de la colección de DSpace importada.
* **Sitios**: añade los elementos importados al sitio o sitios especificados. Aquí aparecerán preseleccionados los sitios predeterminados globales y específicos del usuario.
* **Campos ignorados**: campos de metadatos de DSpace que se deben ignorar durante la importación, separados por comas.
* **Comentario**: comentarios que se adjuntarán al lote de importación y que aparecerán en la página «Importaciones anteriores de DSpace».

![La pantalla de configuración básica de importación con los campos mencionados anteriormente, sin nada introducido y sin casillas marcadas.](../modules/modulesfiles/dspace_importset.png)

### Colecciones
Esta pestaña muestra la lista de colecciones del repositorio de DSpace, organizadas por la comunidad a la que pertenecen. Puedes importar una colección cada vez o todo el repositorio de DSpace.

Para importar una sola colección, haz clic en el botón «Importar» situado a la izquierda de su nombre. De este modo, se iniciará automáticamente la importación.

![La pestaña «Colecciones» muestra algunas colecciones de ejemplo importadas del repositorio DSpace de mars.gmu.edu, incluida una agrupación denominada «Colecciones administrativas» con las colecciones «GMU Dark Archive», «Materiales de conservación» y «Artes visuales». En la parte superior de la pantalla hay un botón para «Importar todo el repositorio» y, en cada colección, un botón que indica «Importar colección». También hay botones para «Expandir todo» y «Contraer todo» en las agrupaciones.](../modules/modulesfiles/dspace_coll.png)

Para importar todo el repositorio, haz clic en «Importar todo el repositorio» en la parte superior del formulario.

!!! Nota
  La importación de un repositorio completo de DSpace con un gran número de elementos (más de 5.000) probablemente saturará el servidor que aloja DSpace con solicitudes hasta provocar un fallo. Considera la posibilidad de importar colección por colección. Si aún así desea importar un repositorio grande al completo de una sola vez, lo siguiente podría resultarle útil:

  * En el menú inicial «Configuración de importación», establezca el **Límite** en un número menor, como 50 o 25.
	* Prueba la importación marcando la casilla **Prueba de importación** en el menú inicial «Configuración de importación».
  * Ejecuta la importación por la noche y/o en cualquier momento en que haya menos tráfico en el servidor de DSpace.
	* Considera la posibilidad de insertar temporalmente [una función `sleep()`](https://www.w3schools.com/php/func_misc_sleep.asp){target=_blank} entre la importación de cada registro en `Import.php` para ralentizar ligeramente el proceso (no recomendado para entornos de producción).

Puedes seguir el estado de las importaciones accediendo a la pestaña «Importaciones anteriores» de DSpace Connector, o en la página [Tareas](../admin/jobs.md) del panel de administración.

!!! Nota
  ¿Tus tareas se inician pero no se completan? Es posible que tengas que [configurar la ruta de PHP](../configuration.md#php-path) para que tu sistema pueda ejecutar el proceso en segundo plano para crear los elementos.

## Revisar importaciones

La página «Importaciones anteriores de DSpace» muestra una tabla con las importaciones anteriores de DSpace, con una casilla de selección para **Deshacer**, otra para **Volver a ejecutar**, el **ID de la tarea** de la importación, el **enlace a la colección de DSpace** del repositorio (que se muestra como nombre de la colección si se encuentra), cualquier **comentario** realizado durante la importación, el número de **elementos** importados con un enlace a los resultados de la búsqueda avanzada, la **fecha** de la importación, el **estado** de la importación, y el **propietario**, es decir, el usuario que inició la importación.

![Tabla de importaciones anteriores que muestra dos importaciones completadas y una importación que dio lugar a un error al importar colecciones diferentes](../modules/modulesfiles/dspace_past.png)

Los elementos de DSpace se importarán con cualquier campo de metadatos reconocido en la fuente (como `dc.title` o `dc.description.abstract`), y utilizarán `bibo:uri` para cargar el URI tal y como figura en el elemento de origen como `dc.identifier.uri`. Se tratará de un enlace en el que se puede hacer clic que aparecerá en las páginas públicas de los elementos y permitirá a los usuarios ver la fuente del elemento en su repositorio DSpace de origen. Si los campos contienen una o más etiquetas de idioma, los campos importados a Omeka también utilizarán esa etiqueta de idioma.

## Actualizar recursos importados

Para actualizar los recursos creados mediante el conector de DSpace, basta con marcar «Re-run» (Volver a ejecutar) y, a continuación, hacer clic en «Submit» (Enviar) en la página «Past DSpace Imports» (Importaciones anteriores de DSpace). Los recursos se actualizarán, no se volverán a importar. Esto te permite utilizar el conector para sincronizar datos entre instalaciones de DSpace y Omeka S.

## Deshacer una importación

Puede ver las importaciones anteriores en la página «Importaciones anteriores de DSpace». Para deshacer una importación completada y eliminar todos los elementos asociados, marque la casilla correspondiente a cada importación que desee deshacer y haga clic en el botón «Enviar».

## Comprobar la API

Es posible que primero quieras comprobar que la instancia de DSpace a la que te diriges sea de acceso público. Para ello, utiliza tu navegador y comprueba el punto final de la API:

- Toma la URL del repositorio de DSpace y añade `/rest/collections` (para versiones anteriores a la 7.0) 
- Toma la URL del repositorio de DSpace y añade `/server/api/core/collections/` (para las versiones 7.x y posteriores).

Si recibes un error al cargar la página en tu navegador, la API de DSpace no está disponible para la importación; comprueba la configuración de la API REST de tu instancia de DSpace.
