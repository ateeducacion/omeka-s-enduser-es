# Registro de actividad

El [módulo «Registro de actividad»](https://omeka.org/s/modules/ActivityLog/){target=_blank} te permite recopilar en una sola tabla la información sobre los cambios realizados en la interfaz de Omeka. El módulo mostrará todos los cambios realizados en los recursos, los sitios, la configuración de la instalación, los usuarios y los puntos de datos añadidos por los módulos. 

![La tabla de eventos del módulo «Registro de actividad».](modulesfiles/activityLog.png)

Una vez activado en la pestaña [Módulos](index.md) del panel de administración, el Registro de actividad no requiere ninguna configuración. Añade una entrada a la lista de módulos de la barra lateral izquierda, que lleva a los usuarios a la tabla de eventos. 

Solo los usuarios con los niveles de administrador global y supervisor pueden acceder al Registro de actividad. Solo el «Administrador global» puede borrar los datos del «Registro de actividad».  

## Ver eventos

El «Registro de actividad» registrará los eventos cuando esté activo. La tabla reflejará todos los cambios realizados en la instalación por todos los usuarios. La tabla se muestra en orden cronológico inverso (los eventos más recientes aparecen en la parte superior). Solo muestra los eventos que modifican (crear, actualizar y eliminar). No incluye eventos de solo lectura (como las búsquedas). 

La tabla incluye las siguientes columnas:

- **ID**: El identificador interno del evento
- **Fecha**: La fecha y hora del evento, según la zona horaria de la instalación
- **Usuario**: El usuario que provocó el evento y su rol. Cuando no haya ningún usuario conectado (como en el caso de las contribuciones realizadas mediante los formularios públicos del módulo [Collecting](collecting.md)), este campo aparecerá en blanco. 
- **IP**: La dirección IP del usuario en el momento del evento
- **Nombre del evento**: El tipo de evento que ha desencadenado el usuario
- **Recurso**: El ID del recurso que ha modificado el usuario. Si se trata de varios recursos, como en una acción masiva, se mostrarán en los datos los ID de todos los recursos afectados. 
- **Mensajes**: Cualquier mensaje que describa el evento, en forma de lista.

Se puede ver un evento con más detalle haciendo clic en el enlace «Ver datos del evento» en cada entrada de la tabla. Esto abrirá el panel lateral derecho para mostrar una versión técnica de los datos guardados en la base de datos correspondientes al evento. 

![La tabla de eventos del módulo «Registro de actividad», con los datos del evento mostrados en el panel lateral derecho.](modulesfiles/activityLog_eventData.png)

Por ejemplo, un evento en el que se eliminan varios elementos (ID 123, 124 y 125) de un sitio (ID 01) dirá:


```
{
    "request_options": {
 "collectionAction": "remove",
    },
    "request_content": {
 "o:site": [
 "01"
 ]
    },
    "request_ids": [
 "123",
 "124",
 "125"])
```

Algunos eventos, cuando están relacionados con un recurso específico, proporcionarán un enlace a dicho recurso, así como un enlace para ver más información.

![La tabla de eventos del módulo «Registro de actividad», con los datos de los eventos mostrados en el panel lateral derecho.](modulesfiles/activityLog_events.png)

### Filtrar eventos

Los usuarios con permiso para ver el «Registro de actividad» pueden filtrar los eventos. Haz clic en el botón «Ver filtros» situado en la parte superior de la tabla para abrir el panel lateral derecho: 

![La tabla de eventos del módulo «Registro de actividad», con el panel lateral derecho mostrando las opciones de filtrado de la tabla.](modulesfiles/activityLog_filter.png)

- El filtrado por nombre de evento te permitirá acotar los resultados según los tipos de cambios realizados: creación, eliminación, actualización, actualización por lotes, cambios en la configuración, etc.

![La tabla de eventos del módulo «Registro de actividad», con el panel lateral derecho mostrando las opciones de filtrado de eventos para la tabla.](modulesfiles/activityLog_filterName.png)

- El filtrado por recurso te permitirá seleccionar entre los recursos de la instalación: elemento, medio, conjunto de elementos, sitio, página, etc.

![La tabla de eventos del módulo «Registro de actividad», con el panel deslizante de la derecha mostrando las opciones de filtrado por recurso para la tabla.](modulesfiles/activityLog_filterResource.png)

- El filtrado por usuario te permitirá elegir entre la lista de usuarios que han realizado cambios en la instalación dentro del intervalo de recopilación del «Registro de actividad».

![La tabla de eventos del módulo «Registro de actividad», con el panel lateral derecho mostrando las opciones de filtrado por usuario para la tabla.](modulesfiles/activityLog_filterUser.png)

- El filtrado por fecha te permitirá seleccionar una o dos fechas en el calendario: una fecha de inicio para los eventos (a partir de esa fecha) y una fecha de fin.

![La tabla de eventos del módulo «Registro de actividad», con el panel lateral derecho mostrando las opciones de filtrado por fecha de la tabla.](modulesfiles/activityLog_filterDate.png)

Los usuarios pueden filtrar los eventos utilizando los distintos filtros disponibles (verás el recuento de cada entrada entre paréntesis):

- **ID**: Filtrar eventos por ID de evento
- **Usuario**: Filtrar eventos por usuario
- **Rol de usuario**: Filtrar eventos por rol de usuario 
- **IP**: Filtrar eventos por dirección IP
- **Nombre del evento**: Filtrar eventos por nombre del evento
- **Recurso**: Filtrar eventos por nombre de recurso
- **ID de recurso**: Filtrar eventos por ID de recurso
- **Desde**: Filtrar eventos por fecha a partir de (a partir de)
- **Antes de**: Filtrar eventos por fecha anterior a.

Configure los filtros y haga clic en «Aplicar filtros». La página resultante mostrará los resultados filtrados. Haga clic en «Borrar filtros» para volver a la lista predeterminada.

#### Eventos capturados

De forma predeterminada, el módulo registrará los siguientes tipos de eventos. Los módulos pueden añadir más eventos, pero no se enumeran aquí.

- `user.login`
- `user.logout`
- `setting.insert`
    - para el recurso «setting»
    - para el recurso «site_setting»
    - para el recurso «user_setting»
- `setting.update`
    - para el recurso «setting»
    - para el recurso «site_setting»
    - para el recurso «user_setting»
- `setting.delete`
    - para el recurso «setting»
    - para el recurso «site_setting»
    - para el recurso «user_setting»
- `api.create.post` para todos los recursos de la API
- `api.update.post` para todos los recursos de la API
- `api.delete.post` para todos los recursos de la API
- `api.batch_create.post` para todos los recursos de la API
- `api.batch_update.post` para todos los recursos de la API
- `api.batch_delete.post` para todos los recursos de la API
- `entity.persist.post`
    - para el recurso «Omeka\Entity\Media»
    - para el recurso «Omeka\Entity\ApiKey»
    - para el recurso «Omeka\Entity\Module»
- `entity.update.post`
    - para el recurso «Omeka\Entity\User»
    - para el recurso «Omeka\Entity\Module»
- `entity.remove.post`
    - para el recurso «Omeka\Entity\ApiKey»
    - para el recurso «Omeka\Entity\Module».

#### Exportar eventos

Los administradores pueden exportar los datos mediante la API REST:

```

/api-local/activity_log_event

```

## Eliminar eventos

Desde la página «Módulos», un usuario con permisos de administrador global puede seleccionar «Configurar» en la entrada del Registro de actividad. Esto permite eliminar todas las entradas del registro de actividad anteriores a una fecha determinada. 

![La página de configuración del registro de actividad, con la opción de eliminar eventos ocurridos antes de una fecha introducida.](modulesfiles/activityLog_config.png)

