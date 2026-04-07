# Usuarios

Las cuentas de usuario en una instalación de Omeka S permiten a tu personal y a tu público realizar acciones como añadir elementos, [crear y moderar envíos](../modules/collecting.md), subir archivos multimedia, crear exposiciones virtuales y editar metadatos.

Los roles de usuario definidos a nivel de instalación son independientes de los [roles de usuario específicos del sitio](../sites/site_users.md). Se debe crear un usuario para la instalación y, a continuación, asignarle roles del sitio. Esto le permite otorgar permisos mínimos a nivel de toda la instalación a alguien que vaya a redactar y publicar una exposición virtual como un único sitio.

Los administradores gestionan y crean usuarios desde la sección Usuarios del panel de control administrativo principal (con el icono de la cabeza y los hombros). La sección Usuarios muestra el correo electrónico del usuario seguido de su nombre completo entre paréntesis, así como su rol y la fecha en que se creó la cuenta.

Hay seis roles de usuario en Omeka S:

- **Administrador global**: privilegios completos de la instalación.
- **Supervisor**: amplios privilegios sobre el sitio y el contenido.
- **Editor** (Experto en contenido): privilegios completos para la creación de contenido.
- **Revisor**: amplios privilegios sobre el contenido, pero solo puede eliminar su propio contenido.
- **Autor**: crea su propio contenido.
- **Investigador**: solo privilegios de búsqueda y lectura.

Entre bastidores, los valores de los roles utilizan los siguientes slugs:

- `global_admin`
- `site_admin`
- `editor`
- `reviewer`
- `author`
- `researcher`.

Un ejemplo de cómo podría gestionar los usuarios de su sitio:

- Un usuario **Administrador global** que instala, gestiona y actualiza los módulos y temas, y controla la configuración básica de la instalación y las utilidades del servidor.
- Un **supervisor** que gestiona las cuentas de usuario en la instalación y los sitios.
- Uno o varios **editores** responsables del diseño y la gestión de elementos, conjuntos de elementos y plantillas de recursos.
- Miembros del personal **revisores** responsables de añadir manualmente elementos digitalizados o recopilados y describirlos de acuerdo con las directrices institucionales, así como de editar las aportaciones de otros.
- **Autores** que pueden añadir y editar sus propios elementos, y a quienes también se les conceden permisos específicos del sitio para crear exposiciones y publicar sus investigaciones utilizando elementos de la colección.
- **Investigadores** a quienes se les pueden otorgar permisos específicos del sitio, pero que no pueden añadir elementos.

Recuerda que estas funciones son independientes de las [funciones de usuario asignadas a nivel específico del sitio](../sites/site_users.md), que permiten a los usuarios registrados de la instalación tener acceso al sitio para crear páginas de exposiciones.

## Crear un usuario

Solo los supervisores y los administradores globales pueden crear, editar y eliminar usuarios.

Para crear un nuevo usuario, seleccione el botón «Añadir nuevo usuario» situado en la esquina superior derecha de la sección Usuarios del panel de administración.

![El formulario «Añadir nuevo usuario» con los campos que se describen a continuación.](adminfiles/users_addnew.png)

En la página Añadir usuario, introduzca lo siguiente:

- **Dirección de correo electrónico**
- **Nombre** (nombre completo o nombre de usuario)
- Una **función** del menú desplegable (consulte más arriba los privilegios de las funciones de usuario)
- Marque la casilla **Está activo** para confirmar que el usuario está activo. Un usuario inactivo no puede iniciar sesión.

También dispone de opciones para personalizar otros ajustes; [consulte más abajo para obtener más detalles sobre la configuración de usuario](#user-settings).

A continuación, se envía al usuario un correo electrónico de notificación para que configure su cuenta y contraseña. El correo electrónico parecerá provenir de la dirección de correo electrónico del administrador configurada en la [configuración general de la instalación](settings.md#general). Cada correo electrónico caducará 14 días después de su envío. Si el correo electrónico caduca, un administrador puede configurar manualmente una contraseña temporal para el usuario y enviársela por correo electrónico.

> *¡Saludos!*
>
> *Se ha creado una cuenta para usted en Omeka en [sitio web]*
>
> *Tu nombre de usuario es tu correo electrónico: [correo electrónico]*
>
> *Haz clic en este enlace para establecer una contraseña y empezar a utilizar Omeka S: [enlace único del sitio web]*
>
> *Tu enlace de activación caducará el [fecha y hora]. Si no has completado el proceso de activación de usuario antes de que caduque el enlace, tendrás que solicitar otro correo electrónico de activación al administrador de tu sitio.*

!!! nota
	Si tiene problemas para enviar correos electrónicos desde su instalación de Omeka S, consulte con su proveedor de alojamiento. Algunas configuraciones de alojamiento pueden requerir que el nombre de dominio del correo electrónico del administrador coincida con el nombre de dominio de la instalación (si su dominio es `yourinstall.org`, el correo electrónico del administrador debe ser `user@yourinstall.org`). Omeka S utiliza la utilidad `sendmail` del servidor para enviar correos electrónicos; consulta la [sección Correo de la página de configuración](../configuration.md#mail) para obtener más información.

## Gestionar usuarios

Para gestionar un usuario existente, ve a la sección Usuarios.

Todos los usuarios pueden editar su propia información mediante esta pantalla y pueden ver a otros usuarios de la instalación (y sus direcciones de correo electrónico). Solo los supervisores y los administradores globales pueden editar a otros usuarios.

![La tabla «Usuarios». Se muestran cinco usuarios, con las direcciones de correo electrónico ocultas. Hay dos administradores globales, un supervisor, un autor y un investigador. El panel está abierto para mostrar el recuento de elementos y conjuntos de elementos de un usuario.](adminfiles/users_table.png)

Para ver los elementos y conjuntos de elementos que posee un usuario, haz clic en los tres puntos situados entre el botón de eliminar (papelera) y la etiqueta del rol de usuario. Esto abrirá un panel en el lado derecho de la pantalla con esta información; puedes hacer clic en el número de elementos o conjuntos de elementos para explorar los elementos o conjuntos de elementos creados por ese usuario.

### Editar usuario

Para editar la información de un usuario, cambiar su contraseña o acceder a sus claves API, vaya a la sección Usuarios. Busque al usuario en la tabla y haga clic en el botón de edición (lápiz) de su fila en la tabla.

![Una sola fila de la tabla de usuarios, con el correo electrónico del usuario ocultado. Un círculo azul resalta el icono de edición, representado como un lápiz rojo.](adminfiles/users_editbutton.png)

La página Editar usuario tiene cuatro pestañas: **Información del usuario**, **Configuración del usuario**, **Contraseña** y **Claves API**. Después de realizar cambios en cualquiera de estas pestañas, asegúrate de hacer clic en el botón Guardar situado en la esquina superior derecha de la ventana del navegador. En cualquier momento puedes cancelar tus ediciones haciendo clic en el botón Cancelar situado junto al botón Guardar.

### Información del usuario
En esta pestaña, puede editar el **Nombre** y el **Correo electrónico** que se muestran para el usuario, seleccionar o cambiar el **Rol** del usuario y marcar la casilla para confirmar que el usuario **Está activo** (o desmarcar la casilla para desactivar al usuario). Un usuario que se desactive será desconectado inmediatamente.

![Pestaña de información del usuario para el usuario Omeka Devs con los campos de correo electrónico, nombre de usuario y rol rellenados, y la casilla «Está activo» marcada](adminfiles/users_info.png)

### Configuración del usuario
Esta pestaña permite a un usuario o al administrador global configurar lo siguiente:

- **Configuración regional**: seleccione de un menú desplegable los idiomas disponibles. Esto cambiará el idioma de las interfaces de administración y pública de la instalación para ese usuario. (Esto depende de [cuántas cadenas de la interfaz se hayan traducido](../translateOmekaS.md). Las cadenas sin traducir se muestran por defecto en inglés.)
- **Plantilla de recursos predeterminada**: seleccione una de las plantillas existentes para que se cargue automáticamente cada vez que el usuario cree un nuevo elemento. El elemento tendrá la clase asociada a la plantilla elegida.
- **Conjuntos de elementos predeterminados**: seleccione uno de los conjuntos de elementos disponibles para adjuntar automáticamente los nuevos elementos a dicho conjunto o conjuntos cuando los cree el usuario. El [conjunto de elementos debe estar abierto a nuevos elementos](../content/item-sets.md#access-settings) para que se aplique esta configuración. El usuario podrá eliminar sus elementos de estos conjuntos de elementos. 
- **Sitios predeterminados para elementos**: seleccione entre los sitios disponibles para adjuntar automáticamente los nuevos elementos a los sitios cuando los cree el usuario. Configurar esto no otorgará al usuario un rol específico del sitio. El usuario **no** podrá eliminar sus elementos de estos sitios (a menos que [también tenga permisos específicos del sitio](../sites/site_users.md)).  
- **Columnas de navegación de administrador**: configura vistas personalizadas para los paneles de control administrativos de este usuario. Consulta más abajo para obtener más detalles.

![Configuración de usuario con opciones predeterminadas seleccionadas](adminfiles/users_settings.png)

#### Columnas de navegación de administración
Los usuarios pueden decidir qué columnas de información componen sus vistas de navegación de recursos dentro de la interfaz de administración. Esto puede resultar útil, por ejemplo, si un usuario está auditando y mejorando un campo concreto para un gran número de elementos, o comparando información entre dos o más campos.

Las columnas se pueden añadir, eliminar y reordenar. Para añadir una columna, selecciónela del menú desplegable disponible y, a continuación, pulse el botón con el signo más (+) situado a la derecha del menú desplegable.

La mayoría de los campos de metadatos se pueden añadir seleccionando «Valor» en el menú desplegable y, a continuación, eligiendo la propiedad de vocabulario concreta en el panel que se abre a la derecha. Se puede tener cualquier número de columnas de Valor.

Las columnas se pueden reordenar arrastrando y soltando, y se pueden eliminar haciendo clic en el botón de eliminar (icono de la papelera).

Las vistas tienen las siguientes columnas predeterminadas:

- Columnas de navegación de [Elemento](../content/items.md):
  - Título (no modificable)
  - Clase de recurso
  - Propietario
  - Creado (fecha de creación del elemento).
- Columnas de navegación de [Conjunto de elementos](../content/item-sets.md):
  - Título (no modificable)
  - Clase de recurso
  - Propietario
  - Creado (fecha de creación del elemento).
- Columnas de navegación de [Medios](../content/media.md):
  - Título (no modificable)
  - Clase de recurso
  - Propietario
  - Creado (fecha de creación del elemento).
- Columnas de navegación de [Sitio](../sites/index.md):
  - Título (no modificable)
  - URL slug
  - Propietario
  - Creado (fecha de creación del elemento).

![Interfaz de navegación de columnas de administración en el área principal de la interfaz con el menú desplegable «Añadir una columna» para la columna de navegación de elementos abierto](adminfiles/users_settings_browsecolumns.png)

Las columnas de navegación disponibles incluyen:

- Columnas de navegación de elementos:
  - ID
  - Es público
  - Modificado (fecha de última modificación del elemento)
  - Plantilla de recurso
  - Valor(es).
- Columnas de navegación de conjuntos de elementos:
  - ID
  - Está abierto
  - Es público
  - Modificado (fecha de última modificación del elemento)
  - Plantilla de recurso
  - Valor(es).
- Columnas de navegación de medios:
  - ID
  - Es público
  - Tipo de medio
  - Modificado (fecha de última modificación del elemento)
  - Plantilla de recurso
  - Tamaño
  - Valor(es).
- Columnas de navegación de sitios:
  - Es público
  - Modificado (fecha de última modificación del elemento)
  - Tema.

Una vez guardadas las selecciones de columnas, el usuario podrá ver las vistas de navegación personalizadas cuando acceda a Elementos, Medios, Conjuntos de elementos o Sitios:

![La página Elementos en el panel de administración, con las columnas personalizadas mostradas según la configuración de la imagen anterior.](adminfiles/users_settings_browsecolumns-result.png)

Cada columna se edita haciendo clic en el icono del lápiz, lo que desplegará un panel a la derecha. Allí, los usuarios pueden rellenar el campo de texto «Encabezado» para anular el título predeterminado de la columna (por ejemplo, «Identificador» en lugar de «ID»).

El campo de texto «Predeterminado» permite al usuario decidir qué información se muestra en una celda de la columna si no hay datos disponibles. Normalmente estas celdas están vacías, pero se puede utilizar esta opción para mostrar, por ejemplo, «[null]» en su lugar, si se buscan celdas que contengan solo espacios u otros caracteres invisibles.

Al editar la opción de la columna «Valor», los usuarios seleccionarán una propiedad para añadirla como columna (obligatorio) y también podrán establecer el número máximo de valores de esa propiedad que se mostrarán en la columna (opcional).

Debe hacer clic en «Establecer columna» antes de guardar la página para asegurarse de que no se pierdan sus modificaciones.

![Barra lateral derecha con la interfaz de edición de la columna Valores, que muestra un formulario para definir el encabezado, la salida predeterminada, la selección de propiedades y el número máximo de valores.](adminfiles/users_settings_edit_browsecolumn.png)

#### Valores predeterminados de navegación del administrador
Además de configurar las columnas que serán visibles en las interfaces de navegación de recursos, un usuario puede establecer la columna de ordenación predeterminada para cada navegación. Los usuarios pueden seleccionar una columna por la que ordenar los resultados y elegir entre un orden ascendente o descendente.

Deberá guardar primero los cambios en las columnas de navegación y, a continuación, volver a esta página para seleccionar una columna predeterminada para la ordenación entre las opciones actuales.

### Contraseña
En esta pestaña, cree una nueva contraseña. Debe introducirse dos veces, tanto en el campo «Nueva contraseña» como en el de «Confirmar nueva contraseña», para que se guarde correctamente.

![Se está editando un usuario en la pestaña «Contraseña», donde los campos de texto «Nueva contraseña» y «Confirmar nueva contraseña» están vacíos.](adminfiles/users_password.png)

Para ver los requisitos de la contraseña, haz clic en la flecha situada junto al campo «Nueva contraseña». Se mostrará una lista de [requisitos](../configuration.md) si se ha configurado alguno.

### Claves API
Utiliza esta pestaña para generar una clave API para el usuario. Para generar una, debes proporcionar una etiqueta para la clave; puede ser una fecha o la finalidad de la clave. Guarda la página para generar la clave.

Para eliminar claves API existentes, marque la casilla «¿Eliminar?» en la fila de esa clave y haga clic en «Guardar».

![Pestaña API para el usuario Omeka Devs con una clave API generada pero oculta, y debajo la opción de crear una nueva clave](adminfiles/users_apikey.png)

### Eliminar usuario
En la página «Usuario» del panel de administración, haz clic en el icono de la papelera en la fila del usuario, a la izquierda de la información sobre su rol, para eliminar al usuario. Confirma la eliminación en el cuadro de diálogo que aparecerá a la derecha de la pantalla.

![Confirmación de eliminación para la usuaria Megan2, indicando el número de elementos y conjuntos de elementos que ha creado; en este caso, cero en ambos casos.](adminfiles/users_delete.png)

## Edición por lotes

Los supervisores y los administradores globales pueden editar varios usuarios a la vez. Utilice el menú desplegable de acciones por lotes para editar o eliminar todos, o utilice las casillas de verificación situadas a la izquierda del correo electrónico de cada usuario en la tabla de usuarios para seleccionar a las personas que desea editar o eliminar por lotes.

También puede seleccionar todos utilizando la casilla situada en la parte superior de la tabla.

![La tabla de usuarios muestra solo las casillas de selección y la columna de correo electrónico, con los correos electrónicos de tres usuarios. Dos de las casillas de los usuarios están marcadas y la tercera no lo está.](adminfiles/users_batch1.png)

El menú desplegable situado justo encima de la tabla ofrece las siguientes opciones:

- Editar seleccionados (usuarios)
- Editar todos (usuarios)
- Eliminar seleccionados (usuarios)
- Eliminar todos (usuarios).

Para editar solo los usuarios cuyas casillas de verificación haya marcado, elija «Editar seleccionados» en el menú desplegable y, a continuación, haga clic en «Ir». Se le redirigirá a la página de edición masiva de usuarios.

![Página de edición masiva de usuarios](adminfiles/users_batch2.png)

En la parte derecha de la página se muestran los correos electrónicos de los usuarios que está editando y a quienes se aplicarán los cambios que realice.

En esta página puede:

- Establecer rol: seleccione de un menú desplegable con todos los roles (véase más abajo) para cambiar el rol de todos los usuarios seleccionados.
- Establecer actividad: establezca a los usuarios seleccionados como activos, inactivos o sin cambios.
- Eliminar de [permisos del sitio](../sites/site_users.md): seleccione de un menú desplegable los sitios de la instalación de Omeka S, o utilice la opción «todos los sitios» para eliminar a los usuarios seleccionados de todos los sitios.
- Añadir a [permisos del sitio](../sites/site_users.md): seleccione de un menú desplegable los sitios de la instalación de Omeka S, o utilice la opción «todos los sitios» para añadir los usuarios seleccionados a todos los sitios.
- Añadir a [permisos del sitio](../sites/site_users.md) como: un menú desplegable con opciones para visitante, administrador o creador; seleccione qué rol tendrán los usuarios en los sitios a los que los haya añadido.

Una vez que haya terminado, guarde los cambios.

Si eliges «Editar todo» en lugar de «Editar seleccionados», podrás aplicar los cambios a todos los usuarios —excepto a ti mismo— de la instalación de Omeka S. ¡Utiliza esta función con precaución!

### Eliminación masiva de usuarios
Para eliminar varios usuarios a la vez, marca las casillas de verificación junto a sus nombres en la tabla Usuarios.

En el menú desplegable situado justo encima de la columna de correo electrónico, selecciona «Eliminar seleccionados» y haz clic en «Ir».

![Una flecha roja señala el menú desplegable donde se muestra «Eliminar seleccionados»](adminfiles/users_batchdel1.png)

Esto abrirá un panel en la parte derecha de la pantalla con un mensaje que le indicará el número de usuarios que está a punto de eliminar. Esta acción **no se puede deshacer**.

Para eliminar definitivamente a estos usuarios, haga clic en el botón rojo «Confirmar eliminación». Para cancelar, haga clic en la «X» situada en la esquina superior derecha del panel.

![Mensaje de confirmación de eliminación para 5 usuarios](adminfiles/users_batchdel2.png)

La acción «Eliminar todo» del menú desplegable eliminará a todos los usuarios excepto a usted mismo. Esta acción **no se puede deshacer** y debe utilizarse con extrema precaución.

Para eliminar permanentemente a todos los usuarios, debe marcar la casilla «¿Está seguro?» antes de hacer clic en el botón «Confirmar eliminación». Para cancelar, haz clic en la «X» situada en la esquina superior derecha del panel.

## Roles y permisos

A continuación se ofrece un desglose detallado de los permisos para cada rol de usuario:

| Categoría | Permiso | Administrador global | Supervisor | Editor | Revisor | Autor | Investigador |
|-----|-----|---|---|---|---|---|---|
| Elementos y medios | Añadir | Sí | Sí | Sí | Sí | Sí | No |
| | Editar | Todos | Todos | Todos | Todos | Los propios | No |
| | Eliminar | Todos | Todos | Todos | Los propios | Los propios | No |
| Anotaciones de valores | Añadir/Editar | Sí | Sí | Sí | Sí | Sí | No |
| Conjuntos de elementos | Añadir | Sí | Sí | Sí | Sí | Sí | No |
| | Editar | Todos | Todos | Todos | Todos | Los propios | No |
| | Eliminar | Todos | Todos | Todos | Los propios | Los propios | No |
| Vocabularios | Importar | Sí | Sí | No | No | No | No |
|  | Editar/Eliminar | Sí | Los propios | No | No | No | No |
| Plantillas de recursos | Añadir | Sí | Sí | Sí | No | Sí | No |
| | Editar/Eliminar  | Todos | Todos | Todos | No | Los suyos propios | No |
| Objetos privados | Ver | Sí | Sí | Sí | Sí | No | No |
| Usuarios | Añadir | Sí | Sí | No | No | No | No |
|  | Editar | Todos | Todos | El propio | El propio | El propio | El propio |
|  | Eliminar | Sí | Sí | No | No | No | No |
| Módulos | Instalar/Configurar | Sí | No | No | No | No | No |
|  | Usar | Sí | Sí | No | No | No | No |
| Trabajos | Ver | Sí | Sí | No | No | No | No |
| Ajustes | Ver/Cambiar | Sí | No | No | No | No | No |
| Activos | Ver | Sí | Sí | Sí | Sí | Sí | Sí |
| | Editar | Todos | Todos | Todos | Todos | Los propios | No |
| | Eliminar | Todos | Todos | Todos | Los propios | Los propios | No |
| Sitios¹ | Crear | Sí | Sí | Sí | No | No | No |
| | Editar/Eliminar | Todos | Todos | Los propios | | | |
| Roles de usuario del sitio | Modificar | Todos | Todos | Los propios | | | |

1. A menudo, un administrador global, un supervisor o un editor creará sitios y luego asignará gestores y creadores de entre los usuarios (por ejemplo, una tarea de clase o exposiciones virtuales de miembros del personal). La propiedad del sitio no se puede reasignar a otros usuarios, y el propietario de un sitio siempre tiene acceso de nivel de gestor a los sitios que posee, incluso si se cambia su rol en toda la instalación. Consulte la [página de usuarios del sitio](../sites/site_users.md) para obtener más información.

**Administrador global**

- Privilegios completos (crear, editar, eliminar) sobre elementos, conjuntos de elementos, medios, plantillas de recursos, páginas del sitio, sitios y usuarios.
- Privilegios completos sobre módulos: instalar, activar, configurar y utilizar.
- Privilegios de búsqueda, lectura, importación y eliminación de vocabularios.

**Supervisor**

- Privilegios completos (crear, editar, eliminar) sobre elementos, conjuntos de elementos, medios y plantillas de recursos.
- Control total sobre todos los sitios, incluyendo añadir usuarios, cambiar la navegación y los temas, utilizar utilidades de módulos específicas del sitio y editar recursos.
- Crear, editar y eliminar usuarios de niveles inferiores; no puede crear otros Supervisores ni Administradores globales.
- Utilizar módulos activos que aparecen en la categoría de la barra lateral «Módulos» (como «Importación CSV»).
- Privilegios de solo lectura para los módulos de la pestaña «Admin > Módulos».
- Privilegios de solo lectura para los vocabularios.

**Editor**

- Privilegios completos (crear, editar, eliminar) sobre elementos, conjuntos de elementos, medios, plantillas de recursos y páginas del sitio.
- Puede buscar, ver y crear sitios, así como editar o eliminar los sitios de su propiedad.
- Privilegios de solo lectura para los vocabularios. Puede ver todos los registros.
- No tiene acceso a los módulos, a la configuración de la instalación ni a las tareas.
- Puede ver a otros usuarios de la instalación y sus direcciones de correo electrónico, pero no puede añadir usuarios.

**Revisor**

- Puede buscar, ver, crear y editar todos los elementos, conjuntos de elementos y archivos multimedia. Solo puede eliminar aquellos elementos, conjuntos de elementos y archivos multimedia de los que es propietario.
- No tiene acceso a los sitios a menos que se le haya añadido como usuario específico de un sitio.
- Privilegios de solo lectura para vocabularios y plantillas de recursos. Puede ver todos los registros.
- No tiene acceso a los módulos.
- Puede ver a otros usuarios de la instalación y sus direcciones de correo electrónico.

**Autor**

- Puede buscar, ver y crear elementos, conjuntos de elementos, plantillas de recursos y archivos multimedia. Solo puede editar o eliminar el contenido que le pertenece.
- No puede ver los objetos marcados como privados, a menos que el objeto sea un sitio para el que tenga permisos específicos.
- No tiene acceso a los sitios a menos que haya sido añadido como usuario específico de un sitio.
- Privilegios de búsqueda y visualización para vocabularios y sitios. No puede ver los registros de otros usuarios.
- No tiene acceso a los módulos.
- Puede ver a otros usuarios de la instalación y sus direcciones de correo electrónico.

**Investigador**

- Privilegios de búsqueda y visualización para todos los elementos públicos, conjuntos de elementos, plantillas de recursos y archivos multimedia.
- No puede ver objetos marcados como privados, a menos que el objeto sea un sitio para el que tenga permisos específicos.
- Sin acceso a módulos.
- Puede ver a otros usuarios de la instalación y sus direcciones de correo electrónico.

Recuerda que un usuario con cualquier rol puede [añadirse a un sitio en cualquier nivel (Visor, Creador, Administrador)](../sites/site_users.md). Esto determinará si, por ejemplo, un usuario de nivel Investigador añadido a un sitio como Administrador puede ver información privada sobre ese sitio.
