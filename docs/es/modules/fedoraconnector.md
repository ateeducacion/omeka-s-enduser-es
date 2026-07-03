# Fedora Connector

El [módulo Fedora Connector](https://omeka.org/s/modules/FedoraConnector){target=_blank} te permite conectar una instancia de Omeka S a un [repositorio de Fedora](https://duraspace.org/fedora/){target=_blank} 4 con el fin de importar elementos de los contenedores de dicho repositorio. Además de importar la información, el elemento de Omeka S mantendrá una conexión con el elemento original. Esto te permite actualizar la información desde la fuente cuando lo desees.

Ten en cuenta que Fedora Connector solo funciona con la versión 4 de Fedora.

## Configuración
Hay dos opciones para configurar Fedora Connector, y ambas permiten la creación de [vocabularios](../content/vocabularies.md) en tu instalación de Omeka S.

![Dos casillas de selección: la primera es «Importar vocabulario de Fedora» y la segunda «Importar vocabulario de la Plataforma de Datos Enlazados»](../modules/modulesfiles/fc_config.png)

La primera casilla de selección ofrece la opción de importar el vocabulario de Fedora a los vocabularios de tu instalación de Omeka S. La segunda casilla de selección ofrece la opción de importar el vocabulario de Linked Data Platform a los vocabularios de tu instalación de Omeka S. Si lo haces, los datos de estos vocabularios también se importarán a Omeka S.

Puedes marcar estas casillas al instalar Fedora Connector por primera vez, o más adelante a través del botón «Configurar» de la lista de [Módulos](../modules/index.md).

## Importar datos
Para utilizar Fedora Connector, ve a la sección denominada «Fedora Connector» dentro de «Módulos», en el panel de navegación de la izquierda del panel de administración. Esto te llevará automáticamente a la página de importación.

![Opción de navegación de Fedora Connector con dos opciones: «Importar» e «Importaciones anteriores»](../modules/modulesfiles/fc_nav.png)

Deberías ver una pantalla con las siguientes opciones:

* **URI del contenedor de Fedora** para el repositorio, la colección o el recurso que desees importar (obligatorio).
* Casilla de verificación **Importar archivos a Omeka**: marca «Sí» si deseas importar archivos multimedia y otros archivos adjuntos al contenido (opcional, recomendado).
* Casilla de verificación **Ignorar contenedor principal**: márcala si solo quieres importar los descendientes del contenedor principal indicado en la URI del contenedor, no el contenedor principal en sí (opcional).
* Casilla de verificación **Importar solo descendientes directos**: márquela si desea importar únicamente los descendientes directos del contenedor indicado en **URI del contenedor** (no los hijos de los hijos). Si no se marca, se importarán de forma recursiva todos los recursos situados por debajo del contenedor (opcional).
* **Comentario**: añade información sobre esta tarea que se mostrará en la página «Importaciones anteriores» (opcional).
* **Conjuntos de elementos**: añade los elementos importados a un [conjunto de elementos](../content/item-sets.md) seleccionado, si lo deseas (opcional; ten en cuenta que el conjunto de elementos debe existir ya para poder importar en él).
* **Sitios**: añade los elementos importados al sitio o sitios especificados. Aquí aparecerán preseleccionados los sitios predeterminados globales y específicos del usuario (opcional).

![Las opciones de los campos de Fedora Connector, tal y como se enumeran arriba.](../modules/modulesfiles/fc_options.png)

Cuando los datos estén completos, pulsa «Enviar». Puedes seguir el estado de la importación accediendo a la página Fedora Connector > Importaciones anteriores, o en la sección [Tareas](../admin/jobs.md).

!!! Nota
  ¿Tus tareas se inician pero no se completan? Es posible que tengas que [configurar la ruta de PHP](../configuration.md#php-path) para que tu sistema pueda ejecutar el proceso en segundo plano y crear los elementos.

## Revisar importaciones

La página «Importaciones anteriores de Fedora» muestra una tabla con las importaciones anteriores de Fedora, con una casilla de selección para **Deshacer**, otra para **Volver a ejecutar**, el **Contenedor** de la importación (ID con hipervínculo al contenedor), cualquier **comentario** realizado durante la importación, el número de **elementos** importados con un enlace a los resultados de la búsqueda avanzada, la **fecha** de la importación, el **estado** de la importación y el **propietario**, es decir, el usuario que inició la importación.

![Tabla de importaciones anteriores que muestra una importación completada, una importación que dio lugar a un error y una importación deshecha](../modules/modulesfiles/fedora_past.png)

## Deshacer una importación
Para deshacer una importación completada y eliminar todos los elementos asociados, ve a la sección «Fedora Connector» en «Módulos» y, a continuación, haz clic en la página «Importaciones anteriores».

Marca la casilla correspondiente a cada importación que desees deshacer y haz clic en «Enviar».
