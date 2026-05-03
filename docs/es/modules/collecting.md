# Recopilación

El [módulo Recopilación](https://omeka.org/s/modules/Collecting/){target=_blank} te permite recopilar contribuciones públicas a través de tus sitios. Los usuarios pueden subir archivos o enviar entradas de texto junto con algunos metadatos identificativos, que los administradores de tu sitio pueden moderar y aprobar para su inclusión.

Una vez activado en la pestaña [Módulos](index.md) del panel de administración, Recopilación se configura para cada sitio individualmente. Añade una sección a la página de Configuración del sitio y añade un enlace debajo de cada sitio para los formularios de Recopilación. Los formularios se añaden a las páginas del sitio mediante [bloques de página](../sites/site_pages.md#page-blocks).

Collecting se integra con los módulos [Custom Vocab](../modules/customvocab.md), [Mapping](../modules/mapping.md) y [Numeric Data Types](../modules/numericdatatypes.md).

## Añadir un formulario

Si Collecting está activo, aparecerá una pestaña de Collecting en el menú contextual de cada sitio.

![Una flecha roja señala la pestaña de Collecting del sitio Parques Nacionales](modulesfiles/collecting_nav.png)

Al hacer clic en ella, accederás a una lista de tus formularios de Collecting para ese sitio. Si acaba de instalar el módulo, la página Formularios de recopilación mostrará el mensaje «Este sitio no tiene formularios de recopilación». Para añadir un nuevo formulario, haga clic en el botón «Añadir nuevo formulario» situado en la esquina superior derecha de la ventana.

![Pestaña Recopilación, sin formularios, la flecha roja señala el botón Añadir nuevo](modulesfiles/collecting_addnew.png)

La página «Añadir formulario de recopilación» tiene dos secciones: la primera contiene un conjunto de campos y opciones que debe completar; la segunda es donde añade y edita las preguntas que conformarán el formulario que verán y rellenarán los visitantes del sitio.

![Página «Añadir formulario de recopilación»](modulesfiles/collecting_addform.png)

### Campos y ajustes
- **Etiqueta**: asigna un nombre al formulario de recopilación. La etiqueta aparecerá como encabezado encima del formulario en la vista pública, por lo que debe ser descriptiva y útil tanto para ti como para los visitantes del sitio.
- **Conjunto de elementos**: selecciona el conjunto de elementos al que deseas añadir los elementos recopilados.
- **Tipo de anonimato**: un menú desplegable con tres opciones:
 - «El usuario establece su propio anonimato»: los usuarios pueden decidir si contribuyen de forma anónima y si sus elementos pueden publicarse).
 - «Los campos de nombre de usuario y información pública del usuario son visibles públicamente»: tanto el nombre del usuario como sus elementos se harán públicos.
 - «Los campos de nombre de usuario y información pública del usuario son privados»: ambos campos permanecen privados.
- **Texto de éxito**: el mensaje que se muestra en una nueva página si el elemento se recopila correctamente.
- **Texto de correo electrónico**: si recopila una dirección de correo electrónico del usuario en el formulario, este recibirá un mensaje de confirmación sobre el envío de su elemento.

### Solicitudes
Las solicitudes se enumeran en una tabla que indica su **Tipo** y el **Texto** que se muestra en el formulario público. Estas solicitudes conforman el formulario que verán los visitantes del sitio (además de la etiqueta, mencionada anteriormente).

Para añadir una nueva indicación, haz clic en el botón «Añadir indicación» situado justo debajo del encabezado Indicaciones. Esto abrirá un panel lateral con un menú desplegable para seleccionar un tipo de indicación.

Al seleccionarlo, las opciones de ese tipo se cargarán en la barra lateral para que las edites, con un botón «Guardar cambios» en la parte inferior de las opciones.

![Menú desplegable Añadir indicación](modulesfiles/collecting_prompts.png)

El módulo Collecting dispone de tipos de indicaciones con las siguientes opciones:

**Propiedad del elemento**: seleccione una propiedad de los vocabularios de la instalación para que el visitante la utilice al describir el elemento.

- Propiedad: seleccione una propiedad de los vocabularios (ejemplo: Descripción).
- Texto de la indicación: si desea que la indicación sea diferente de la etiqueta de la propiedad.
- Tipo de entrada: longitud y tipo de cuadro de entrada. Elija entre:
  - Cuadro de texto (una línea).
  - Cuadro de texto (varias líneas).
  - Menú de selección (desplegable): introduzca las opciones para el menú en el campo «Seleccionar opciones de menú» que aparecerá, con una opción por línea.
  - Recurso de elemento (desplegable): ofrecerá al usuario la posibilidad de elegir entre elementos existentes para añadirlos como valor de la propiedad. Puede pegar cualquier cosa después de `admin/` en la URL de una búsqueda avanzada para cargar elementos específicos.
  - Si tiene instalado [Custom Vocab](../modules/customvocab.md), un menú desplegable adicional le permitirá seleccionar entre sus vocabularios personalizados existentes. Esto se cargará como un menú desplegable para los usuarios en la parte pública del formulario.
	- Si tiene instalado [Numeric Data Types](../modules/numericdatatypes.md), también dispondrá de las siguientes opciones:
 - Marca de tiempo numérica
 - Intervalo numérico
 - Duración numérica
 - Número (entero o decimal).
 - Marque la casilla «¿Obligatorio?» si el campo es obligatorio.

**Elemento multimedia** permite a los visitantes añadir archivos multimedia a su envío.

Tipo de multimedia:

- Un menú desplegable para el tipo de multimedia, con las siguientes opciones:
  - Subir uno, que permite a los usuarios subir un archivo
  - Subir varios, que permite a los usuarios subir varios archivos a la vez utilizando el selector de archivos nativo del navegador (con las teclas Mayús o Ctrl)
	- Si tienes instalado [Mapping](../modules/mapping.md), puedes añadir un mapa que permite a los usuarios indicar ubicaciones haciendo clic directamente en el mapa y escribiendo una etiqueta en el campo situado justo debajo. Si el campo debajo del mapa se deja en blanco, el marcador se etiquetará con el contenido del campo «Título».
![La página de recopilación visible para el público incluye un mapa para seleccionar una ubicación. Un campo situado justo debajo del mapa permite a los usuarios introducir la etiqueta del marcador.](modulesfiles/collecting_map.png)
  - URL
  - HTML.
- Texto de la solicitud: si desea que el texto de la solicitud sea distinto de la etiqueta de la propiedad.
- Marque la casilla «¿Obligatorio?» si la solicitud es obligatoria.

**Información complementaria del elemento** añade información adicional sobre el elemento, sin estar vinculada a ningún vocabulario o propiedad en particular.

- Texto de la solicitud: si desea que el texto de la solicitud sea distinto de la etiqueta de la propiedad.
- Tipo de entrada: longitud y tipo de cuadro de entrada. Elija entre:
 - Cuadro de texto (una línea)
 - Cuadro de texto (varias líneas)
 - Menú de selección (desplegable): introduzca las opciones del menú en el campo «Seleccionar opciones de menú» que aparecerá, con una opción por línea.
 - Marque la casilla «¿Obligatorio?» si el campo es obligatorio.

**Nombre de usuario** para convertirse en el propietario del elemento. Si la persona que utiliza el formulario es un usuario que ha iniciado sesión en la instalación de Omeka S, este campo se rellenará automáticamente.

- Texto de la indicación: si desea que la indicación sea diferente de la etiqueta de la propiedad.
- Marque la casilla «¿Obligatorio?» si el campo es obligatorio.

**Correo electrónico del usuario**: donde la persona que añade el elemento puede indicar su correo electrónico. Si se deja en blanco, no recibirá un correo electrónico con el texto del campo «Texto del correo electrónico».

- Texto de la solicitud: si desea que el texto de la solicitud sea diferente de la etiqueta de la propiedad.
- Marque la casilla «¿Obligatorio?» si la solicitud es obligatoria.

**Información privada del usuario**: recopila información adicional del usuario que se mantendrá privada.

- Texto del mensaje: si desea que el mensaje sea diferente de la etiqueta de la propiedad.
- Tipo de entrada: longitud y tipo de cuadro de entrada. Elija entre:
 - Cuadro de texto (una línea)
 - Cuadro de texto (varias líneas)
 - Menú de selección (desplegable): introduzca las opciones del menú en el campo «Opciones del menú de selección» que aparecerá, con una opción por línea.
 - Marque la casilla «¿Obligatorio?» si el mensaje de solicitud es obligatorio.

**Público del usuario** recopila información adicional del usuario que puede hacerse pública

- Texto del mensaje: si desea que el mensaje de solicitud sea diferente de la etiqueta de la propiedad.
- Tipo de entrada: longitud y tipo de cuadro de entrada. Elija entre:
 - Cuadro de texto (una línea)
 - Cuadro de texto (varias líneas)
 - Menú desplegable: introduzca las opciones del menú en el campo «Seleccionar opciones de menú» que aparecerá, con una opción por línea.
 - Marque la casilla «¿Obligatorio?» si el mensaje es obligatorio.

**HTML**: inserte un bloque de texto HTML en el formulario para ofrecer orientación adicional, información, etc. El campo «Texto del mensaje» para este mensaje cuenta con opciones de formato WYSIWYG.

## Gestionar formularios

Una vez que tenga al menos un formulario de recopilación, aparecerá en la página Formularios de recopilación. Haga clic en el botón de edición (lápiz) para editar el formulario. Haga clic en la etiqueta del formulario para ver más información sobre el mismo y consultar los elementos recopilados.

La página del formulario tiene dos pestañas: Información del formulario y Elementos recopilados.

La pestaña de información del formulario le muestra los datos existentes sobre la etiqueta, el tipo de anonimato y el conjunto de elementos, junto con una tabla de todas las solicitudes, en orden, con su tipo, texto y si la solicitud es obligatoria.

![Página de información del formulario «Compartir una cita»](modulesfiles/collecting_forminfo.png)

Para editar el formulario, haz clic en el botón «Editar formulario» situado en la esquina superior derecha. Las opciones de la página de edición del formulario son las mismas que al añadir un formulario. Para editar una pregunta, haz clic en el botón de edición (lápiz) de la pregunta. Esto abrirá el panel lateral de esa pregunta.


![Indicaciones con una flecha roja apuntando a la columna de botones de edición](modulesfiles/collecting_edit2.png)

Puedes reorganizar el orden de las indicaciones arrastrándolas y soltándolas con el icono de tres líneas situado en el extremo izquierdo de la etiqueta «Tipo de indicación».

![Indicaciones con una flecha roja apuntando al icono para arrastrar y soltar](modulesfiles/collecting_dragthis.png)

## Configuración del sitio

Collecting añade una sección a la [configuración del sitio](../sites/site_settings.md) donde puedes gestionar los términos de servicio y los correos electrónicos de los formularios de recopilación de este sitio.

![La sección Collecting en la configuración del sitio con dos campos, tal y como se describe a continuación.](modulesfiles/collecting_settingsSite.png)

En esta sección hay dos campos:

**Condiciones de servicio** es un campo de varias líneas donde puedes introducir las condiciones de servicio para el material recopilado a través de este sitio. Este texto está enlazado desde el formulario justo encima del botón de enviar:

![Desde el formulario de Collecting, las palabras «Acepto las condiciones de servicio» sobre un botón que dice «Enviar». La frase «Condiciones de servicio» es un enlace.](modulesfiles/collecting-ToSlink.png)

Al hacer clic en la frase «Términos de servicio» se abrirá una nueva ventana para que las personas que rellenan el formulario no pierdan la información que han introducido.

**URL de los términos de servicio** es un campo de entrada para un enlace a una página externa de términos de servicio ya existente.

**Dirección de correo electrónico de envío** le permite establecer una dirección personalizada desde la que se enviarán los correos electrónicos de envío. Si se deja en blanco, estos correos electrónicos se enviarán desde la dirección de correo electrónico del administrador que figura en la [Configuración global](../admin/settings.md) de la instalación de Omeka S.

**Dirección de correo electrónico de notificación** te permite establecer una dirección de correo electrónico de un miembro del personal a la que se enviarán las notificaciones de nuevos envíos. Si se deja en blanco, no se enviará ningún correo electrónico de notificación.

!!! nota
  Si tiene problemas para enviar correos electrónicos desde su instalación de Omeka S, consulte con su proveedor de alojamiento. Algunas configuraciones de alojamiento pueden requerir que el nombre de dominio del correo electrónico del administrador coincida con el nombre de dominio de la instalación (si su dominio es `yourinstall.org`, el correo electrónico del administrador debe ser `user@yourinstall.org`). Omeka S utiliza la utilidad `sendmail` subyacente del servidor para enviar correos electrónicos.

## Configuración global

Collecting requerirá que los usuarios completen un formulario reCaptcha para poder enviarlo, si ha añadido una clave reCaptcha en la [Configuración global](../admin/settings.md). Esto puede ser una forma útil de evitar el spam.

## Añadir a las páginas del sitio

Para añadir un formulario de Collecting a una página:

1. Vaya a la página en la que desea que aparezca el formulario (o añada una nueva página para el formulario).
1. En la barra lateral **Añadir nuevo bloque**, seleccione el bloque **Recopilación**.
1. En el bloque Recopilación, haga clic en la casilla del formulario que desea incluir. Puede añadir más de un formulario a la página marcando más de una casilla. O bien, puede separar los formularios añadiendo bloques de página independientes, un formulario por bloque.

![Bloque «Recopilación» con un formulario, con su casilla marcada](modulesfiles/collecting_pageblock.png)

En la página pública, el bloque del formulario aparecerá como un elemento `<form>` con un ID de `collecting_form_X`, donde X es el ID del formulario. Las preguntas aparecen en elementos `<div class="field">`; las preguntas obligatorias también tendrán la clase «required». Dentro de cada pregunta hay un `<div class="field-meta">` para el texto de la pregunta y un `<div class="inputs">` para el campo de respuesta. Puedes utilizar el [módulo Editor CSS](../modules/csseditor.md) para controlar cómo se muestran estos elementos.

A continuación se muestra una captura de pantalla del [formulario de recopilación de covid19-archive.org](https://covid-19archive.org/s/archive/page/Share){target=_blank}: 

![Un ejemplo de formulario de recopilación titulado «Comparte tu historia». Enlaza a otro formulario en español y a uno para la recopilación de audio o vídeo. Los campos son: título (obligatorio), carga de archivos y un campo de texto que pregunta «¿Qué tipo de objeto es este?» (obligatorio).](modulesfiles/collecting_publicformexample.png)


## Gestión de los elementos recopilados

Los elementos añadidos a través de un formulario de recopilación aparecerán en la sección Elementos del panel de administración, pero quizá te resulte más fácil gestionarlos a través de la pestaña Recopilación del sitio web a través del cual se recopilaron.

Para ver los elementos recopilados con un formulario específico, ve a la pestaña Recopilación en el menú contextual del sitio web y haz clic en la etiqueta del formulario. A continuación, haz clic en la pestaña **Elementos recopilados**.

![Pestaña «Elementos recopilados» con varios elementos](modulesfiles/collecting_items.png)

Esta pestaña contiene una tabla de elementos recopilados ordenados por Título, Fecha de envío, Revisado por, Estado y tres puntos suspensivos.

Para ver la información recopilada, incluyendo el nombre de usuario, el correo electrónico, etc., de cualquier elemento, haz clic en los tres puntos suspensivos de «Más información». Al hacer clic en el título de un elemento, accederás a la página de edición del mismo (en la sección Elementos, no en Recopilación).

Un elemento recopilado puede tener uno de estos tres estados: Necesita revisión, Público y Privado. Para cambiar el estado de un elemento, selecciona el estado deseado en el menú desplegable y, a continuación, haz clic en el botón «Actualizar estados» situado en la esquina superior derecha.

Cuando actualices el estado de un elemento de «Necesita revisión» a «Público» o «Privado», tu nombre aparecerá en la fila de ese elemento como el usuario que lo ha revisado. Si hay varias personas trabajando en un sitio, esto puede ayudarte a llevar un registro de quién ha aprobado los elementos recopilados.
