# Trabajos

Cuando un usuario inicia un proceso que va a tardar algún tiempo, como una importación de API, el progreso del proceso se muestra en la sección **Trabajos** del panel de administración. La tabla también muestra los trabajos completados, detenidos e interrumpidos por un error.

La tabla de Trabajos muestra el número de **ID** del trabajo, la **Clase** del trabajo, el **Estado** y el **Propietario**, es decir, el usuario que inició el trabajo.

!!! nota
  Las actividades de edición por lotes a veces se muestran en el registro de Trabajos. Aquí solo aparecen las operaciones «Editar todo» o «Eliminar todo». La edición por lotes de solo los elementos seleccionados, incluso una página completa de elementos, no aparecerá aquí.

Solo los administradores globales y los supervisores pueden ver o acceder a la pestaña Trabajos.

Puedes ordenar las filas de la tabla por ID, Clase, Estado o Propietario (descendente o ascendente) utilizando los menús desplegables situados justo encima de la tabla, en la parte superior derecha.

![Tabla de trabajos que incluye todos los mensajes de estado](adminfiles/jobstable.png)

Para ver los detalles de un trabajo, haga clic en su número de ID. En la página de detalles de un trabajo, verá la siguiente información: 

- **Estado** (En curso, Error, Completado, Detenido)
- **Inicio** y **Fin** (fechas)
- **Clase** (origen del trabajo, por ejemplo, `DspaceConnector\Job\Import`)
- **Propietario**
- **Argumentos**
- **Registro**: haga clic en **ver registro** para ver cualquier error u otros mensajes. 

![El campo «Args» del registro con contenido, y con un enlace rojo «ver registro» debajo, con una flecha azul apuntando hacia él.](adminfiles/jobs_viewlog.png)

!!! nota
  ¿Tus trabajos se inician pero no se completan? Es posible que tengas que [configurar la ruta para PHP](../configuration.md#php-path) para que tu sistema pueda ejecutar el proceso en segundo plano.


