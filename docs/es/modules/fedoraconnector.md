# Conector Fedora

El [módulo Conector Fedora](https://omeka.org/s/modules/FedoraConnector){target=_blank} te permite conectar una instancia de Omeka S al [repositorio Fedora](https://duraspace.org/fedora/){target=_blank} 4 con el fin de importar elementos de los contenedores de dicho repositorio. Además de importar la información, el elemento de Omeka S mantendrá una conexión con el elemento original. Esto te permite actualizar la información desde la fuente cuando lo desees.

Ten en cuenta que Fedora Connector solo funciona con la versión 4 de Fedora.

## Configuración
Hay dos opciones para configurar Fedora Connector, y ambas permiten la creación de [vocabularios](../content/vocabularies.md) en tu instalación de Omeka S.

![Dos opciones de casillas de verificación: la primera es «Importar vocabulario de Fedora» y la segunda «Importar vocabulario de la Plataforma de Datos Enlazados»](../modules/modulesfiles/fc_config.png)

La primera casilla de verificación ofrece la opción de importar el vocabulario de Fedora a los vocabularios de su instalación de Omeka S. La segunda casilla de verificación ofrece la opción de importar el vocabulario de la Plataforma de Datos Enlazados a los vocabularios de su instalación de Omeka S. Si lo hace, los datos de estos vocabularios también se importarán a Omeka S.

Puede marcar estas casillas al instalar Fedora Connector por primera vez, o más adelante a través del botón «Configurar» en la lista de [Módulos](../modules/index.md).

## Importar datos
Para utilizar Fedora Connector, ve a la sección denominada «Fedora Connector» en Módulos, en el panel de navegación de la izquierda del panel de administración. Esto te llevará automáticamente a la página Importar.

![Opción de navegación de Fedora Connector con dos opciones para Importar e Importaciones anteriores](../modules/modulesfiles/fc_nav.png)

Deberías ver una pantalla con las siguientes opciones:

* **URI del contenedor de Fedora** para el repositorio, la colección o el recurso que desea importar (obligatorio).
* Casilla de verificación **Importar archivos a Omeka**: marque «Sí» si desea importar archivos multimedia y otros archivos adjuntos al contenido (opcional, recomendado).
* Casilla de verificación **Ignorar contenedor principal**: marque «Sí» para importar solo los descendientes del contenedor principal indicado en la URI del contenedor, no el contenedor principal en sí (opcional).
* Casilla de verificación **Importar solo descendientes directos**: marque «Sí» para importar únicamente los descendientes directos del contenedor indicado en la URI del contenedor (sin hijos de hijos). Si no se marca, se importarán recursivamente todos los recursos por debajo del contenedor (opcional).
* **Comentario**: añade información sobre esta tarea que se mostrará en la página Importaciones anteriores (opcional).
* **Conjuntos de elementos**: añada los elementos importados a un [Conjunto de elementos](../content/item-sets.md) seleccionado, si lo desea (opcional; tenga en cuenta que el Conjunto de elementos debe existir ya para poder importar en él).
* **Sitios**: añade los elementos importados al sitio o sitios especificados. Los sitios predeterminados globales y específicos del usuario aparecerán preseleccionados aquí (opcional).

![Las opciones de campo para Fedora Connector, tal y como se enumeran arriba.](../modules/modulesfiles/fc_options.png)

Cuando los datos estén completos, pulse «Enviar». Puede realizar un seguimiento del estado de la importación accediendo a la página Fedora Connector > Importaciones anteriores, o en la sección [Tareas](../admin/jobs.md).

!!! nota
  ¿Sus tareas se inician pero no se completan? Es posible que tenga que [configurar la ruta de PHP](../configuration.md#php-path) para que su sistema pueda ejecutar el proceso en segundo plano para crear los elementos.

## Revisar importaciones

La página «Importaciones anteriores de Fedora» muestra una tabla con las importaciones anteriores de Fedora, con una casilla de verificación para **Deshacer**, otra para **Volver a ejecutar**, el **Contenedor** de la importación (ID con hipervínculo al contenedor), cualquier **Comentario** realizado durante la importación, el número de **Elementos** importados con un enlace a los resultados de la búsqueda avanzada, la **Fecha** de la importación, el **Estado** de la importación y el **Propietario**, o el usuario que inició la importación.

![Tabla de importaciones anteriores que muestra una importación completada, una importación que dio lugar a un error y una importación deshecha](../modules/modulesfiles/fedora_past.png)

## Deshacer una importación
Para deshacer una importación completada y eliminar todos los elementos asociados, vaya a la sección «Fedora Connector» en «Módulos» y, a continuación, haga clic en la página «Importaciones anteriores».

Marque la casilla de cada importación que desee deshacer y haga clic en «Enviar».
