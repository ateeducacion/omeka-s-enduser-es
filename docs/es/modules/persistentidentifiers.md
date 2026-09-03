# Identificadores persistentes 

El [módulo «Identificadores persistentes»](https://omeka.org/s/modules/PersistentIdentifiers/){target=_blank} permite a los usuarios crear o importar identificadores persistentes (PID) y asignarlos a los elementos de Omeka S. Estos PID pueden generarse («acuñarse») y asignarse al crear un elemento, a través de la pantalla de edición del elemento o durante ediciones por lotes. Pueden eliminarse de forma individual o por lotes. Los PID existentes pueden extraerse de los metadatos del elemento. 

Una vez asignado, al acceder al PID de un elemento en el navegador se redirige a una página de destino estable, no específica del sitio, que contiene los metadatos del elemento, los archivos multimedia y los sitios a los que está asignado.

Los servicios de PID disponibles actualmente en este módulo son:

+ [Claves de recursos de archivo (ARK)](https://arks.org){target=_blank}, generadas dentro de Omeka
+ [Identificadores de objetos digitales (DOI)](https://datacite.org/create-dois/){target=_blank}, generados y gestionados por DataCite 
+ [Claves de recursos de archivo (ARK)](https://arks.org/){target=_blank}, generadas y gestionadas por [EZID](https://ezid.cdlib.org/){target=_blank} (solo para usuarios existentes).

!!! Nota
	Este módulo se creó originalmente para utilizar el servicio EZID con el fin de generar y gestionar [claves de recursos de archivo (ARK)](https://arks.org/){target=_blank}. Actualmente, EZID no admite nuevos miembros. A partir de la versión 1.2, este módulo genera y almacena las ARK de forma local. Los usuarios actuales de EZID pueden seguir utilizando sus cuentas; los nuevos usuarios de ARK deben solicitar un número de autoridad de asignación de nombres (NAAN) (gratuito) mediante el [formulario de solicitud de NAAN de Ark Alliance](https://docs.google.com/forms/d/e/1FAIpQLSf_847hNXtLGikR-XeDy1uT1AKd24DpHnt5UQh2i8ORRu7u-w/viewform){target=_blank} e introducirlo en Omeka.

## Configuración general

Tras la instalación, «Identificadores persistentes» aparecerá en el menú de navegación de la izquierda, en la sección «Módulos». Este enlace está disponible para los usuarios con permisos de administrador global y supervisor. 

La página «Configuración» que se encuentra aquí contiene ajustes generales:

+ **Servicio de PID**: Selecciona cuál de los servicios de PID disponibles deseas utilizar para la generación o extracción. Solo se puede utilizar un servicio de PID a la vez para generar y asignar PID a los elementos. 
+ **Asignar PID a nuevos elementos**: Marque esta casilla para que se aplique automáticamente a todos los nuevos elementos en Omeka S, tanto si se crean en Omeka S como si se importan. Esto generará nuevos PID o extraerá los PID existentes y los asignará, dependiendo de su configuración.
+ **Campos con PID existentes**: Una lista de campos de metadatos que pueden contener valores de PID. Cuando se crea o se importa un elemento, el módulo comprobará si hay PID en estos campos. Si los encuentra, se asignará el PID existente al elemento (en lugar de generar uno nuevo). Utiliza el formato `dcterms:identifier,bibframe:identifier`, etc.
+ **Campo opcional para almacenar PID**: si se activa, el PID también se escribirá en esta propiedad de metadatos de cada elemento correspondiente cuando se genere o se encuentre. 

![Opciones de configuración para los ajustes generales tal y como se enumeran más arriba.](../modules/modulesfiles/PID_settings.png)

!!! nota
  En función de la configuración anterior, debes ajustar tu flujo de trabajo y el de los demás usuarios: al crear un elemento, asegúrate de introducir el PID existente antes de guardarlo por primera vez. Es posible que te interese mantener desactivada la opción «Asignar PID a nuevos elementos», salvo en circunstancias especiales. Recuerda que los usuarios con un nivel inferior al de «Supervisor» no tendrán acceso a esta configuración y no podrán desactivarla; además, dejarla activada podría generar PID de forma involuntaria. 

## Configuración de EZID

El proceso de configuración de EZID requiere:

+ **NAAN y espacio de nombres «Shoulder»**: el número de la Autoridad de Asignación de Nombres (NAAN) y el valor «Shoulder» del ARK, asignados de forma única a una organización, que aparecerán en cada ARK generado. 
+ **Nombre de usuario de EZID**: El usuario de EZID que tiene permiso para crear y actualizar identificadores para el espacio de nombres anterior. 
+ **Contraseña de EZID**: La contraseña del usuario de EZID mencionado anteriormente. Ten en cuenta que, por motivos de seguridad, esta contraseña no se guarda en el formulario, por lo que, si se realizan cambios en el **NAAN y el espacio de nombres asociado** o en el **nombre de usuario de EZID**, también deberás volver a introducir la contraseña antes de pulsar «Enviar».

![Opciones de configuración específicas de EZID tal y como se enumeran más arriba.](../modules/modulesfiles/PID_EZIDconfig.png)

## Configuración de DataCite

La configuración de DataCite requiere:

+ **Prefijo DOI del repositorio**: el prefijo asignado al repositorio de generación y gestión de DOI de una institución. 
+ **ID del repositorio de DataCite**: el identificador único asignado al repositorio de DOI de una institución. 
+ **Contraseña de DataCite**: La contraseña asociada al **ID del repositorio de DataCite** anterior. Ten en cuenta que, por motivos de seguridad, esta contraseña no se guarda en el formulario, por lo que, si se realizan cambios en cualquier campo de la pantalla de configuración de DataCite, también deberás volver a introducir la contraseña antes de pulsar «Enviar».

![Opciones de configuración específicas de DataCite, tal y como se enumeran más arriba.](../modules/modulesfiles/PID_DataCiteconfig.png)

### Metadatos obligatorios de DataCite

DataCite requiere cinco valores de metadatos descriptivos para generar un DOI: Título, Creador, Editor, Año de publicación y Tipo de recurso. 

Todos estos campos deben asignarse a un campo de metadatos existente que se seleccione de la lista de vocabularios disponibles en su instancia de Omeka S. La propiedad «Tipo de recurso general» debe ajustarse exactamente al [`ResourceTypeGeneral` vocabulario controlado](https://support.datacite.org/docs/datacite-metadata-schema-v44-mandatory-properties#101-resourcetypegeneral){target=_blank} exactamente.

![Opciones de configuración específicas de DataCite, tal y como se enumeran más arriba.](../modules/modulesfiles/PID_DataCiteconfig2.png)

### Metadatos opcionales de DataCite

DataCite permite añadir campos adicionales para metadatos opcionales. Asigna cualquiera o todos los siguientes: Tema, Descripción, Idioma, Versión, Derechos, Tamaño, Formato. Ten en cuenta que «Idioma» requiere una [etiqueta de idioma BCP-47](https://en.wikipedia.org/wiki/IETF_language_tag){target=_blank}.

![Opciones de configuración específicas de DataCite, tal y como se enumeran más arriba.](../modules/modulesfiles/PID_DataCiteconfig3.png)

## Configuración del ARK local

![Campos de configuración del ARK local, tal y como se describen a continuación.](modulesfiles/PID_localARK.png)

Para generar ARK de forma local, deberá solicitar un número de autoridad de asignación de nombres (NAAN) (gratuito) mediante el [formulario de solicitud de NAAN de Ark Alliance](https://docs.google.com/forms/d/e/1FAIpQLSf_847hNXtLGikR-XeDy1uT1AKd24DpHnt5UQh2i8ORRu7u-w/viewform){target=_blank}. Para obtener más información, consulta la [página web de ARKS sobre cómo empezar](https://arks.org/about/getting-started-implementing-arks/){target=_blank}. Esto generará enlaces permanentes y estables utilizando el servicio de resolución «Name-to-Thing», con el formato «https://n2tn.net/[ARK]`. 

En el módulo, introduce la información de tu registro NAAN: 

+ **NAAN**: El número de autoridad de asignación de nombres (NAAN) de tu organización, asignado por la ARK Alliance.
+ **Shoulder**: Prefijo betanumérico opcional de dos caracteres que se añade tras el NAAN. Resulta útil para subdividir el ARK, por ejemplo, por proyecto o unidad. Se genera automáticamente si se deja en blanco. El «shoulder» también se puede modificar en el futuro, o volver a generar borrando el campo, para permitir múltiples subdivisiones del «shoulder».

Una vez generados, estos ARK creados localmente deben redirigir inmediatamente a una página de destino estable, genérica e independiente del sitio web para su recurso Omeka correspondiente, con metadatos y cualquier contenido multimedia. Ejemplo: `http://n2t.net/ark:/99999/ABC123456789`.

## Acuñar PID

Para acuñar un PID desde la página de edición del elemento, ve a la pestaña «Avanzado» y haz clic en «Acuñar PID». 

![Acuñar PID a través de la pestaña «Avanzado» de Editar elemento](../modules/modulesfiles/PID_mint.png)

Al cabo de unos instantes, debería aparecer el ARK o el DOI. 

El botón «Generar PID» debería aparecer ahora como «Eliminar PID». Haz clic ahí para eliminar el PID si lo deseas.

![Eliminación de PID a través de la pestaña «Avanzado» de la edición de un elemento](../modules/modulesfiles/PID_remove.png)

Si seleccionas «Eliminar PID», se abrirá un panel a la derecha advirtiéndote de que esto eliminará el PID y romperá cualquier enlace entrante. Haz clic en «Confirmar eliminación de PID» para eliminar el PID.

![Ventana emergente solicitando la confirmación de la eliminación del PID](../modules/modulesfiles/PID_confirmremove.png)

Haz clic en «Guardar» antes de salir de la página, tanto al crear como al eliminar PID.

## Acciones por lotes

Puedes editar por lotes los PID desde la página «Elementos». Selecciona los elementos que desees editar y, a continuación, ve a la pantalla de edición por lotes.

Cerca de la parte inferior de la pantalla, deberías ver una fila titulada «Identificadores persistentes». Aquí puedes «crear» o «eliminar» PID para todos los elementos seleccionados. Si estás realizando una edición en bloque de otros campos y deseas que los PID no se vean afectados, puedes seleccionar «[sin acción]».

![Pantalla de edición en bloque de elementos, con campos de varios módulos. Cerca de la parte inferior hay una entrada «Identificadores persistentes» con tres opciones de botones de opción: «Generar PID», «Eliminar PID» y «[Sin acción]». Una flecha azul señala esta entrada.](../modules/modulesfiles/PID_batchoptions.png)

Cuando hayas realizado todas las modificaciones deseadas, haz clic en «Guardar» en la esquina superior derecha.