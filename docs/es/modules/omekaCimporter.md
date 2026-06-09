# Importador de Omeka Classic

El [módulo Importador de Omeka Classic](https://omeka.org/s/modules/Omeka2Importer){target=_blank} (también conocido como Omeka 2 Importer) te permite importar elementos y colecciones desde un sitio Omeka Classic 2.x a una instalación de Omeka S. El sitio de origen debe ser la versión Classic 2 o superior para poder ofrecer un punto final de API que este módulo pueda utilizar. 

Este módulo solo importa elementos y sus metadatos (incluidas las etiquetas), archivos adjuntos y colecciones (como conjuntos de elementos). *No* importará contenido de Simple Page ni de Exhibit Builder.

Si hay plugins o módulos instalados tanto en el sitio de origen como en el de destino, Omeka Classic Importer puede importar metadatos específicos de los módulos. Por ejemplo, los datos de geolocalización facilitados por el módulo Mapping en S y el plugin Geolocation en Classic se importarán automáticamente. Los elementos de texto PDF se pueden importar y asignar a los campos «Extract Text». Es posible que los datos no se asignen automáticamente de forma correcta, así que asegúrate de comprobar las asignaciones manualmente.

!!! nota
  Dado que las propiedades de los recursos en Omeka S no tienen formato HTML, cualquier código HTML presente en las propiedades de los elementos de Omeka Classic (enlaces, formato de texto, etc.) se eliminará durante el proceso de importación. En su lugar, puede conservar cualquier elemento como un archivo multimedia, con «HTML» como tipo de medio.

## Importar

Una vez instalado, el módulo Omeka Classic Importer debería aparecer en la parte inferior del menú de navegación de la izquierda, en el panel de control de administración principal. Al seleccionarlo, aparecerán los elementos del submenú **Importar** e **Importaciones anteriores**. 

![Opciones del menú de Omeka Classic Importer: Importar e Importaciones anteriores](../modules/modulesfiles/oCi_menu.png)

Desde la pestaña Importar puedes iniciar nuevas importaciones. 

Debe tener la API habilitada en la instalación de origen de Omeka Classic para que el importador funcione. Para ello, el propietario de la instalación de origen de Omeka Classic debe ir a la pestaña API en Configuración, a la que se accede a través de la barra de navegación superior del panel de control administrativo. Asegúrese de que la casilla «Habilitar API» esté marcada.

Para encontrar el punto final de la API de la instalación original de Omeka Classic, vaya a la página de inicio de dicha instalación. Añada `/api` al final de la URL. Debería ver una página con el mensaje «Esta es la URL del punto final para [nombre del sitio de origen]» y enlaces a la información del sitio y a los recursos de la API disponibles. Para confirmar que la API está habilitada, haz clic en el enlace de recursos de API disponibles. Si ves `{"message":"API is disabled"}`, no podrás importar desde este sitio.

### Introduce la API

En la primera página del importador, introduce el **punto final de la API de Omeka Classic**: la URL del sitio de la API a la que deseas acceder (debe terminar en «api»). Asegúrate de introducir la URL completa, comenzando por «http», de lo contrario el importador no podrá acceder a los elementos de ese sitio. Haz clic en «Siguiente».

![Campo de importación de la API](../modules/modulesfiles/oCi_enterapi.png)

Si ha introducido un punto final de API válido, la página siguiente se cargará sin problemas. Si ha introducido un punto final no válido, el módulo mostrará el mensaje de error «Advertencia: argumento no válido».

### Configuración de importación y asignación de metadatos
En la segunda página del importador hay tres pestañas: **Configuración básica de importación**, **Asignar a propiedades de Omeka S**, **Asignar a clases de Omeka S** y **Asignar a plantillas de Omeka S**. 

Al hacer clic en el botón «Empezar de nuevo» volverá a la primera página, donde podrá introducir un punto final de API diferente.

A partir de la versión 1.3, este módulo conservará la visibilidad de los elementos de Classic a S (pública o privada). 

#### Ajustes básicos de importación
* **Clave API de Omeka Classic**: Este campo puede dejarse en blanco o rellenarse, dependiendo de si dispone de una clave API para el sitio desde el que está intentando importar datos.  
* **Comentario**: Puede añadir un comentario como «API de Jane Doe, sin clave» para ayudar a identificar la importación específica al ver importaciones anteriores.  
* **Importar a**: Esta opción le permite seleccionar uno o varios conjuntos de elementos en los que importar los elementos. Tenga en cuenta que solo puede importar a conjuntos de elementos de su propiedad. No puede crear un nuevo conjunto de elementos desde esta página. Es posible que desee importar colecciones en lugar de, o además de, importar a un conjunto de elementos aquí.
* **Por página**: Introduzca un número para limitar el número de registros recuperados por solicitud. Útil para sitios que puedan tener un gran número de elementos.
* **Actualizar una importación anterior**: Para actualizar —y sobrescribir— una importación anterior procedente de la misma fuente.
* **Importar colecciones**: Para importar las colecciones del sitio Omeka Classic al sitio Omeka S, como conjuntos de elementos.
* **Importar etiqueta como**: Para importar etiquetas de Omeka Classic, seleccione una propiedad a la que asignarlas.

![Configuración básica para una importación, tal y como se indica arriba.](../modules/modulesfiles/oCi_basic.png)

#### Asignar a propiedades de Omeka S
Esta pestaña incluye una tabla para la asignación entre elementos de Omeka Classic y propiedades de Omeka S. 

El módulo de importación asignará automáticamente muchas propiedades, pero debes revisar la asignación por si necesitas añadir más o editar la asignación automática. Es posible que los elementos de tipos de elemento personalizados deban asignarse manualmente. 

Para borrar la asignación predeterminada, haz clic en el botón «Borrar valores predeterminados». 

Las columnas de la tabla son **Elemento de Omeka Classic**, **Propiedades asignadas** y una casilla de verificación para **Conservar HTML como medio**. Cualquier campo que contenga HTML que desee conservar en su instalación de Omeka S, como saltos de línea y estilo de texto en el campo de descripción, se puede importar como un archivo HTML adjunto al elemento. El campo se importará en texto sin formato a los metadatos y con su formato como un medio.

![La pestaña «Asignar a propiedades de Omeka S», que muestra un botón «Borrar valores predeterminados» en la parte superior y una tabla de propiedades de Dublin Core a continuación. Cada línea de la tabla tiene una propiedad coincidente rellenada automáticamente, un icono de papelera y una casilla de verificación para «Conservar HTML como medio». El panel de la derecha está abierto y muestra todos los vocabularios con sus propiedades.](../modules/modulesfiles/oCi_mapprop.png)

El primer conjunto de la tabla es Dublin Core, seguido de los metadatos de tipo de elemento. La importación también incluirá cualquier conjunto de elementos heredados o adicionales (por ejemplo, Omeka Legacy File), o elementos creados por plugins de Classic (como una sección de texto PDF para texto extraído). Estos elementos basados en plugins pueden asignarse automáticamente si tienes instalado el módulo equivalente de Omeka S (como Extract Text en este caso). 

Para asignar:

1. Seleccione el elemento o el tipo de elemento en la tabla haciendo clic en su fila o etiqueta.
1. En el panel de la derecha, haga clic o busque la propiedad S a la que desea asignar su elemento Classic. 
1. Haga clic en la propiedad del panel para asignarla. 

![Asignación del elemento «Fecha de nacimiento» a la propiedad FOAF «birthday», mostrando la relación asignada.](../modules/modulesfiles/oCi_mapping.png)

Para eliminar una asignación, haz clic en el icono de la papelera en la fila del elemento o la propiedad.

#### Asignar a clases de Omeka S
En esta pestaña puede asignar tipos de elementos de Omeka Classic a clases de recursos de Omeka S. Puede seleccionar entre las clases de cualquiera de los vocabularios instalados.  

Para asignar:

1. Seleccione el tipo de elemento en la tabla haciendo clic en su fila o etiqueta.
1. En el panel de la derecha, haga clic o busque la clase de recurso a la que desea asignar su elemento. 
1. Haga clic en la clase de recurso en el panel para asignarla.

Los elementos con el tipo de elemento Classic original se importarán con la nueva clase S. 

![Pestaña de asignación de clases, con un botón «Borrar valores predeterminados» en la parte superior y una tabla con «Tipo de elemento» a la izquierda y «Clase de recurso» a la derecha. Cada entrada de la tabla tiene un icono de papelera. Muchos de los tipos de Dublin Core se asignan automáticamente; «Historia oral» no está asignado.](../modules/modulesfiles/oCi_mapclass.png)

#### Asignar a plantillas de Omeka S

Esta pestaña le permite asignar los elementos que está importando a una plantilla de recursos específica en su instalación de Omeka S. Todas tus plantillas de recursos existentes en S aparecerán en el panel de la derecha. 

Para asignar:

1. Selecciona el tipo de elemento en la tabla haciendo clic en su fila o etiqueta.
1. En el panel de la derecha, navega o busca la plantilla de recursos a la que deseas asignar tu elemento. 
1. Haz clic en la plantilla de recursos del panel para asignarla.

Los elementos con el tipo de elemento clásico original se importarán con la nueva plantilla de recursos de S.

![Pestaña de asignación de plantillas, con un botón «Borrar valores predeterminados» en la parte superior y una tabla con los encabezados «Tipo de elemento» y «Plantilla de recursos» debajo. No se ha asignado nada automáticamente.](../modules/modulesfiles/oCi_mapresource.png)

### Importación completa
Cuando haya terminado de personalizar la asignación, haga clic en el botón «Importar» situado en la esquina superior derecha de la ventana.

!!! nota
	¿Sus tareas se inician pero no se completan? Es posible que tenga que [configurar la ruta de PHP](../configuration.md#php-path) para que su sistema pueda ejecutar el proceso en segundo plano para crear los elementos.

## Importaciones anteriores

La sección de importaciones anteriores del módulo le permite ver las importaciones de API anteriores.

Cada importación es una fila. La tabla tiene las siguientes columnas:

* **Deshacer**: Marca esta casilla si deseas deshacer la importación. Una vez que hagas clic en Enviar, el estado de esa importación específica cambiará a «deshacida».    
* **ID de trabajo**: Un valor numérico asignado a cada importación de API específica. También puede ver el trabajo en la [pestaña Trabajos del panel de administración](../admin/jobs.md).  
* **Comentario**: Si introdujo un comentario al configurar la importación, ese comentario aparecerá aquí.
* **Elementos**: Muestra el número de elementos añadidos y actualizados con cada importación.   
* **Fecha**: La fecha en la que se realizó la importación.   
* **Estado**: Será «en_curso», «completada» o «deshacida».  
* **Propietario**: El usuario que solicitó la importación.

![Tabla de importaciones anteriores que muestra la fila de encabezado y una fila de una importación anterior.](../modules/modulesfiles/oCi_past.png)
