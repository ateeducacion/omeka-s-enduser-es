# Importación de Zotero

El [módulo de importación de Zotero](https://omeka.org/s/modules/ZoteroImport){target=_blank} te permite conectar una instancia de Omeka S a una biblioteca de Zotero e importar elementos desde dicha biblioteca.

## Prepara tu biblioteca de Zotero
Para poder importar desde una biblioteca de Zotero, debes tener acceso a la API de dicha biblioteca. Para utilizar la importación de Zotero, necesitarás el ID del grupo o del usuario:

  * Los ID individuales se encuentran en la pestaña «Feeds/API» de la configuración de Zotero; hay una frase que dice: «Tu ID de usuario para utilizar en llamadas a la API es».
  * Los ID de grupo se encuentran en la página de la biblioteca del grupo de Zotero, fijándote en la URL de la biblioteca: será `zotero.org/groups/<número>`. Si accedes a `https://api.zotero.org/groups/<número>`, deberías obtener información al respecto en esa página.

Es posible que también necesites el ID de una colección específica y una clave API para importar archivos. 

* Las claves de colección aparecen en la URL de la página de una colección; son la secuencia alfanumérica al final de la URL, después de «collections/».
* Para generar una clave API, ve a «Configuración» en tu cuenta de Zotero, a la pestaña «Fuentes/API», y haz clic en el enlace *Crear nueva clave privada*.

## Importar datos

Para importar, ve a la sección «Importación de Zotero» en el menú de navegación de la izquierda del panel de administración de tu instalación de Omeka S. Esto te llevará automáticamente a la subsección «Importación», también en el menú de navegación de la izquierda.

![Opciones de importación de Zotero, tal y como se enumeran a continuación.](modulesfiles/zoteroimport_new.png)

Para importar desde una biblioteca de Zotero:

* Elige un conjunto de elementos al que se añadirán los elementos importados (obligatorio). 
* Elige entre bibliotecas de **Usuario** o de **Grupo** mediante los botones de opción (obligatorio). 
* Introduce el ID de la biblioteca (que es el número de identificación del grupo o del usuario, tal y como se ha explicado anteriormente). 
* Si se importa una colección, introduce la clave de la colección.
* Introduce tu clave API para importar datos privados y/o archivos (opcional para la importación, pero necesario para importar archivos).
* Marca la casilla para importar archivos. La clave API es necesaria para importar archivos.
	* Las capturas de pantalla de páginas HTML se importarán como archivos zip. 
*  La opción «Añadidos después de» te permite importar únicamente aquellos elementos de Zotero añadidos a la biblioteca después de la fecha y hora que elijas. Puedes utilizar esta opción para actualizar una importación anterior sin volver a añadir los archivos que ya habías importado.

Cuando hayas rellenado el formulario, haz clic en «Enviar» en la esquina superior derecha de la ventana del navegador.

!!! Nota
  ¿Tus tareas se inician pero no se completan? Es posible que tengas que [configurar la ruta de PHP](../configuration.md#php-path) para que tu sistema pueda ejecutar el proceso en segundo plano para crear los elementos.

Nota sobre los archivos: Las reglas para importar un elemento son las mismas que para crear uno en Omeka, por lo que, si tu biblioteca de Zotero contiene archivos de un tipo multimedia no permitido, dichos elementos no se importarán.

La página se cargará en la subsección «Importaciones anteriores» con el mensaje «Importando desde Zotero». Para comprobar el estado de la importación, actualiza la página o haz clic en la [sección «Tareas» del panel de administración](../admin/jobs.md).

Gestión de importaciones anteriores
---------------------------------
Para ver y gestionar las importaciones anteriores, haz clic en la sección «Importación de Zotero» en el menú de navegación de la izquierda y, a continuación, haz clic en la subsección «Importaciones anteriores» que aparece al desplegar el menú.

La página «Importaciones anteriores» muestra una tabla con las importaciones anteriores, tanto las que se han realizado con éxito como las que han fallado por error o las que se han deshecho. La tabla contiene las siguientes columnas:

- **Biblioteca de Zotero**: indica el nombre de la biblioteca del usuario o del grupo.
- El botón **Deshacer**: una flecha curvada en sentido antihorario.
- **Elementos añadidos antes**: la fecha de la importación.
- **Estado de la tarea**: estado actual de la tarea. Al hacer clic en el texto del estado de una tarea, se accederá a la página de dicha tarea.
- **Recuento de elementos**: el número de elementos añadidos en la importación.

Para deshacer una importación, haz clic en el botón «Deshacer» situado a la izquierda de la marca de tiempo **Elementos añadidos antes**. Se abrirá un cuadro de diálogo en la barra lateral en el que se te pedirá que confirmes que deseas deshacer la importación y eliminar todos los elementos importados. Haz clic en «Confirmar» para continuar. 

![Página de importaciones anteriores con la barra lateral abierta para confirmar la anulación](modulesfiles/zoteroimport_undo.png)

Las importaciones anteriores que ya se hayan anulado tendrán un estado de tarea de «Importación anulada».
