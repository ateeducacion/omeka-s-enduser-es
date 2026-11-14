# Tareas

Cuando un usuario inicia un proceso que va a tardar un tiempo en completarse, como una importación de API, el progreso del proceso se muestra en la sección **Tareas** del panel de administración. La tabla también muestra las tareas completadas, detenidas e interrumpidas por un error.

La tabla «Tareas» muestra el **ID** de la tarea, su **clase**, su **estado** y el **propietario**, es decir, el usuario que inició la tarea.

!!! Nota
  Las actividades de edición por lotes a veces se muestran en el registro de Tareas. Aquí solo aparecen las operaciones «Editar todo» o «Eliminar todo». La edición por lotes de solo los elementos seleccionados, incluso si se trata de una página completa de elementos, no aparecerá aquí.

Solo los administradores globales y los supervisores pueden ver o acceder a la pestaña «Trabajos».

Puedes ordenar las filas de la tabla por ID, Clase, Estado o Propietario (en orden descendente o ascendente) utilizando los menús desplegables situados justo encima de la tabla, en la esquina superior derecha.

![Tabla de tareas con todos los mensajes de estado](adminfiles/jobstable.png)

Para ver los detalles de una tarea, haz clic en su número de ID. En la página de detalles de una tarea, verás la siguiente información: 

- **Estado** (En curso, Error, Completada, Detener)
- **Inicio** y **Fin** (fechas)
- **Clase** (origen del trabajo, por ejemplo, `DspaceConnector\Job\Import`)
- **Propietario**
- **Argumentos**
- **Registro**: haz clic en **ver registro** para ver cualquier error u otros mensajes. 

![El campo «Args» del registro con contenido, y con un enlace rojo «ver registro» debajo, con una flecha azul que apunta hacia él.](adminfiles/jobs_viewlog.png)

!!! Nota
  ¿Tus tareas se inician pero no se completan? Es posible que tengas que [configurar la ruta de PHP](../configuration.md#php-path) para que tu sistema pueda ejecutar el proceso en segundo plano.


