# Importador de Omeka Classic

El [módulo Importador de Omeka Classic](https://omeka.org/s/modules/Omeka2Importer){target=_blank} (también conocido como «Omeka 2 Importer») te permite importar elementos y colecciones desde un sitio de Omeka Classic 2.x a una instalación de Omeka S. El sitio de origen debe ser la versión 2 o superior de Classic para poder ofrecer un punto final de API que este módulo pueda utilizar. 

Este módulo solo importa elementos y sus metadatos (incluidas las etiquetas), archivos adjuntos y colecciones (como conjuntos de elementos). *No* importará el contenido de Simple Page ni el de Exhibit Builder.

Si hay complementos o módulos instalados tanto en el sitio de origen como en el de destino, el importador de Omeka Classic puede importar metadatos específicos de dichos módulos. Por ejemplo, los datos de geolocalización proporcionados por el módulo «Mapping» en S y el complemento «Geolocation» en Classic se importarán automáticamente. Los elementos de texto de los archivos PDF se pueden importar y asignar a los campos «Extract Text». Es posible que los datos no se asignen automáticamente de forma correcta, así que asegúrate de comprobar las asignaciones manualmente.

!!! Nota
  Dado que las propiedades de los recursos en Omeka S no tienen formato HTML, cualquier código HTML presente en las propiedades de los elementos de Omeka Classic (enlaces, formato de texto, etc.) se eliminará durante el proceso de importación. En su lugar, puedes conservar cualquier elemento como un archivo multimedia, con «HTML» como tipo de medio.

## Importación

Una vez instalado, el módulo Omeka Classic Importer debería aparecer en la parte inferior del menú de navegación izquierdo del panel de control principal de administración. Al seleccionarlo, aparecerán las opciones del submenú **Importar** e **Importaciones anteriores**. 

![Opciones del menú de Omeka Classic Importer: Importar e Importaciones anteriores](../modules/modulesfiles/oCi_menu.png)

Desde la pestaña Importar puedes iniciar nuevas importaciones. 

Para que el importador funcione, debe tener la API habilitada en la instalación de origen de Omeka Classic. Para ello, el propietario de la instalación de origen de Omeka Classic debe ir a la pestaña «API» en «Configuración», a la que se accede a través de la barra de navegación superior del panel de control administrativo. Asegúrese de que la casilla «Habilitar API» esté marcada.

Para encontrar el punto final de la API de la instalación original de Omeka Classic, ve a la página de inicio de dicha instalación. Añade `/api` al final de la URL. Deberías ver una página con el mensaje «Esta es la URL del punto final para [nombre del sitio de origen]» y enlaces a la información del sitio y a los recursos de la API disponibles. Para confirmar que la API está habilitada, haz clic en el enlace de los recursos de la API disponibles. Si ves `{"message":"La API está deshabilitada"}`, no podrás realizar la importación desde este sitio.

### Introduce la API

En la primera página del importador, introduce el **punto final de la API de Omeka Classic**: la URL del sitio para la API a la que deseas acceder (debe terminar en «api»). Asegúrate de introducir la URL completa, comenzando por «http»; de lo contrario, el importador no podrá acceder a los elementos de ese sitio. Haz clic en «Siguiente».

![Campo de importación de la API](../modules/modulesfiles/oCi_enterapi.png)

Si has introducido un punto final de la API válido, la página siguiente se cargará sin problemas. Si has introducido un punto final no válido, el módulo mostrará el mensaje de error «Advertencia: argumento no válido».

### Configuración de la importación y asignación de metadatos
En la segunda página del importador hay tres pestañas: **Configuración básica de la importación**, **Asignar a propiedades de Omeka S**, **Asignar a clases de Omeka S** y **Asignar a plantillas de Omeka S**. 

Al hacer clic en el botón «Empezar de nuevo», volverás a la primera página, donde podrás introducir un punto final de la API diferente.

A partir de la versión 1.3, este módulo conservará la visibilidad de los elementos de Classic a S (pública o privada). 

#### Configuración básica de importación
* **Clave API de Omeka Classic**: Este campo puede dejarse en blanco o rellenarse, dependiendo de si dispone de una clave API para el sitio desde el que está intentando importar datos.  
* **Comentario**: Puede añadir un comentario como «API de Jane Doe, sin clave» para ayudar a identificar la importación específica al consultar importaciones anteriores.  
* **Importar a**: Esta opción le permite seleccionar uno o varios conjuntos de elementos en los que importar los elementos. Tenga en cuenta que solo puede importar a conjuntos de elementos de los que sea propietario. No puedes crear un nuevo conjunto de elementos desde esta página. Quizás te interese importar colecciones en lugar de, o además de, importar a un conjunto de elementos desde aquí.
* **Por página**: Introduce un número para limitar el número de registros recuperados por solicitud. Resulta útil para sitios que puedan tener un gran número de elementos.
* **Actualizar una importación anterior**: Para actualizar —y sobrescribir— una importación anterior procedente de la misma fuente.
* **Importar colecciones**: Para importar las colecciones del sitio de Omeka Classic al sitio de Omeka S, como conjuntos de elementos.
* **Importar etiqueta como**: Para importar etiquetas de Omeka Classic, selecciona una propiedad a la que asignarlas.

![Configuración básica para una importación, tal y como se indica arriba.](../modules/modulesfiles/oCi_basic.png)

#### Asignar a propiedades de Omeka S
Esta pestaña incluye una tabla para la asignación entre los elementos de Omeka Classic y las propiedades de Omeka S. 

El módulo de importación asignará automáticamente muchas propiedades, pero debes revisar la asignación por si necesitas añadir más o editar la asignación automática. Es posible que los elementos de tipos de elemento personalizados deban asignarse manualmente. 

Para borrar la asignación predeterminada, haz clic en el botón «Borrar valores predeterminados». 

Las columnas de la tabla son **Elemento de Omeka Classic**, **Propiedades asignadas** y una casilla de selección para **Conservar HTML como medio**. Cualquier campo que contenga código HTML que desees conservar en tu instalación de Omeka S, como saltos de línea y formato de texto en el campo de descripción, puede importarse como un archivo HTML adjunto al elemento. El campo se importará como texto sin formato a los metadatos y con su formato como archivo multimedia.

![La pestaña «Asignar a propiedades de Omeka S», que muestra un botón «Borrar valores predeterminados» en la parte superior y una tabla de propiedades de Dublin Core a continuación. Cada línea de la tabla tiene una propiedad correspondiente rellenada automáticamente, un icono de papelera y una casilla de selección para «Conservar HTML como archivo multimedia». El panel de la derecha está abierto y muestra todos los vocabularios con sus propiedades.](../modules/modulesfiles/oCi_mapprop.png)

El primer conjunto de la tabla es Dublin Core, seguido de los metadatos de tipo de elemento. La importación también incluirá cualquier conjunto de elementos heredados o adicionales (por ejemplo, «Omeka Legacy File»), o elementos creados por complementos de Classic (como una sección de «Texto de PDF» para texto extraído). Estos elementos basados en complementos pueden asignarse automáticamente si tienes instalado el módulo equivalente de Omeka S (como «Extract Text» en este caso). 

Para asignar:

1. Selecciona el elemento o el tipo de elemento en la tabla haciendo clic en su fila o etiqueta.
1. En el panel de la derecha, navega o busca la propiedad S a la que deseas asignar tu elemento de Classic. 
1. Haz clic en la propiedad del panel para asignarla. 

![Asignación del elemento «Fecha de nacimiento» a la propiedad FOAF «birthday», mostrando la relación asignada.](../modules/modulesfiles/oCi_mapping.png)

Para eliminar una asignación, haz clic en el icono de la papelera en la fila del elemento o la propiedad.

#### Asignar a clases de Omeka S
En esta pestaña puedes asignar los tipos de elemento de Omeka Classic a las clases de recurso de Omeka S. Puedes seleccionar entre las clases de cualquiera de los vocabularios instalados.  

Para realizar la asignación:

1. Selecciona el tipo de elemento en la tabla haciendo clic en su fila o en su etiqueta.
1. En el panel de la derecha, navega o busca la clase de recurso a la que deseas asignar tu elemento. 
1. Haz clic en la clase de recurso del panel para asignarla.

Los elementos con el tipo de elemento Classic original se importarán con la nueva clase S. 

![Pestaña «Asignación de clases», con un botón «Borrar valores predeterminados» en la parte superior y una tabla con «Tipo de elemento» a la izquierda y «Clase de recurso» a la derecha. Cada entrada de la tabla tiene un icono de papelera. Muchos de los tipos de Dublin Core se asignan automáticamente; «Historia oral» no está asignado.](../modules/modulesfiles/oCi_mapclass.png)

#### Asignar a plantillas de Omeka S

Esta pestaña te permite asignar los elementos que estás importando a una plantilla de recursos específica de tu instalación de Omeka S. Todas tus plantillas de recursos existentes en S aparecerán en el panel de la derecha. 

Para asignar:

1. Selecciona el tipo de elemento en la tabla haciendo clic en su fila o etiqueta.
1. En el panel de la derecha, navega o busca la plantilla de recurso a la que deseas asignar tu elemento. 
1. Haz clic en la plantilla de recurso del panel para asignarla.

Los elementos con el tipo de elemento clásico original se importarán con la nueva plantilla de recurso de S.

![Pestaña de asignación de plantillas, con un botón «Borrar valores predeterminados» en la parte superior y una tabla con los encabezados «Tipo de elemento» y «Plantilla de recurso» debajo. No se ha asignado nada automáticamente.](../modules/modulesfiles/oCi_mapresource.png)

### Finalizar la importación
Cuando hayas terminado de personalizar la asignación, haz clic en el botón «Importar» situado en la esquina superior derecha de la ventana.

!!! Nota
	¿Tus tareas se inician pero no se completan? Es posible que tengas que [configurar la ruta de PHP](../configuration.md#php-path) para que tu sistema pueda ejecutar el proceso en segundo plano para crear los elementos.

## Importaciones anteriores

La sección de importaciones anteriores del módulo te permite ver las importaciones de API anteriores.

Cada importación corresponde a una fila. La tabla contiene las siguientes columnas:

* **Deshacer**: Marca esta casilla si deseas deshacer la importación. Una vez que hagas clic en «Enviar», el estado de esa importación concreta cambiará a «deshacida».    
* **ID de tarea**: Un valor numérico asignado a cada importación de la API específica. También puedes ver la tarea en la [pestaña «Tareas» del panel de administración](../admin/jobs.md).  
* **Comentario**: Si introdujiste un comentario al configurar la importación, dicho comentario aparecerá aquí.
* **Elementos**: Muestra el número de elementos añadidos y actualizados con cada importación.   
* **Fecha**: La fecha en la que se llevó a cabo la importación.   
* **Estado**: Será «en_curso», «completada» o «deshacida».  
* **Propietario**: El usuario que solicitó la importación.

![Tabla de importaciones anteriores que muestra la fila de encabezado y una fila de una importación anterior.](../modules/modulesfiles/oCi_past.png)
