# Carga lateral de archivos

El [módulo «Carga lateral de archivos»](https://omeka.org/s/modules/FileSideload){target=_blank} permite importar archivos multimedia que ya se encuentran almacenados en el servidor donde está instalada tu versión de Omeka S. Al subir archivos multimedia a tus elementos, aparecerán nuevas opciones: «Carga lateral» para seleccionar archivos individuales de tu servidor, o «Carga lateral de directorio» para seleccionar carpetas con varios archivos. 

La carga lateral de archivos es compatible con la [importación CSV](../modules/csvimport.md). Una vez instalado, las opciones de importación CSV incluirán la posibilidad de añadir archivos multimedia mediante los nombres de archivo de tu directorio de carga lateral. Asegúrate de desactivar la eliminación de archivos en el módulo de carga lateral de archivos cuando lo utilices con la importación CSV.

## Crear un directorio

Crea un directorio (carpeta) en tu servidor. Puede estar dentro del directorio del módulo File Sideload o al mismo nivel que la instalación de Omeka S. 

!!! Nota
  Si colocas tu directorio de sideload en cualquier lugar dentro de tu instalación de Omeka, incluso dentro del directorio del módulo (`tuinstalaciónomeka/modules/FileSideload/tudirectorio`), ten cuidado de no eliminarlo ni moverlo al actualizar la instalación o el módulo. Es posible que aparezcan mensajes de error al editar elementos o archivos multimedia si no se encuentra el directorio de sideload. Vuelve a la página de configuración del módulo para solucionar este problema.

Sube o mueve los archivos a este directorio. Todos los archivos y carpetas deben estar en este directorio para que sean accesibles.

Ten en cuenta que, al explorar estos archivos desde el módulo para añadirlos como recursos multimedia, solo verás los nombres de los archivos y de las carpetas, por lo que debes nombrar los recursos de la forma más clara posible (por ejemplo, «StudyInScarlet_coverpage.jpg» será más útil que «img001.jpg»).

## Configuración

Tras instalar el módulo, tendrás que configurarlo para indicarle dónde se encuentra el directorio.

Desde la página «Módulos» del menú de navegación de la izquierda, desplázate hasta «File Sideload» en la lista y haz clic en el botón «Configurar».

El módulo «File Sideload» tiene dos opciones de configuración.

![Una pantalla de configuración de ejemplo, con los campos que se enumeran a continuación. El campo «Directorio de carga lateral» se rellena con una ruta relativa que termina en la carpeta «/sideloadFiles». La casilla «¿Eliminar el archivo cargado lateralmente?» está marcada.](../modules/modulesfiles/filesideload_config2.png)

**Directorio de carga lateral**: la ruta, **relativa a la raíz del servidor**, del directorio en el que se almacenan los archivos. Debería tener un aspecto similar a este:

- `/var/www/html/tu-ruta-de-instalación/omeka-s/sideload-media`
- `/home/tu_nombre_de_usuario/tu-sitio-web.org/omeka-s/sideload-files` (una ruta típica para alojamiento compartido)
- `/home/tu_nombre_de_usuario/public_html/omeka-s/modules/FileSideload/sideload` (una ruta típica para usuarios de cPanel).

Si tienes acceso al shell del directorio a través de la terminal, puedes copiar y pegar el resultado del comando `pwd`.

Si utilizas una aplicación FTP, copia la ruta del sitio remoto que aparece en la barra de direcciones de la aplicación.

**¿Eliminar el archivo cargado externamente?**

- Si está marcado, cualquier archivo añadido a un elemento como contenido multimedia se eliminará del directorio «Sideload», ya que el archivo ahora se guarda como contenido multimedia en la instalación de Omeka S.
- Si no está marcada, los archivos permanecerán en el directorio y estarán disponibles para añadirlos como contenido multimedia a cualquier elemento, hasta que los elimines manualmente.


Añadir un archivo de sideload a un elemento
------------------------------
Con el módulo «File Sideload» instalado y configurado, y los archivos en el directorio, ya puedes utilizar el módulo para añadir contenido multimedia a los elementos.

Al editar un elemento, ve a la pestaña «Multimedia». La barra lateral «Añadir contenido multimedia» incluye ahora dos botones para Sideload (debajo de las opciones principales).

![Se muestra la pestaña «Multimedia» de un elemento en el modo de edición. Ya se han añadido al campo principal dos entradas de Sideload en la barra lateral.](../modules/modulesfiles/filesideload_browse.png)

Al hacer clic en cualquiera de los botones se añade un bloque multimedia de Sideload. Al añadir un único archivo se crean dos campos:

- **Título**: Asigna un nuevo título al archivo multimedia (opcional).
- **Archivo**: Selecciona un archivo de este menú desplegable. El menú cargará los nombres de los archivos tal y como aparecen en el directorio. Selecciona uno del menú desplegable y guarda los cambios.

![Opciones multimedia de Sideload tal y como se enumeran arriba, con el menú desplegable abierto, mostrando los nombres de los archivos. Algunas opciones se muestran como si estuvieran en una subcarpeta, lo que se indica por su formato; por ejemplo, «item123/24750.jpg».](../modules/modulesfiles/filesideload_addfile.png)

Al añadir archivos multimedia por directorio se crean tres campos:

- **Título**: Asigna un nuevo título al archivo multimedia (opcional). Este título se aplicará de forma idéntica a todos los archivos multimedia añadidos.
- **Directorio**: Selecciona una carpeta en este menú desplegable. El menú cargará los nombres de las carpetas tal y como aparecen en el directorio. 
- **Importar directorio de forma recursiva**: Al marcar esta casilla, se incluirán tanto todos los archivos multimedia de la carpeta de sideload que hayas elegido como todos los archivos multimedia de todas las carpetas que contenga dicha carpeta. 

![Opciones multimedia del directorio de carga lateral tal y como se enumeran arriba, con el menú desplegable abierto, mostrando los nombres de los directorios. Se muestra un directorio como «item234/item234b», lo que indica una carpeta dentro de otra carpeta.](../modules/modulesfiles/filesideload_directory_addfile.png)

Recuerda que «Carga lateral de archivos» cuenta con una configuración a nivel de módulo para eliminar archivos cuando se importan mediante este proceso. Cuando estés seguro de que tu configuración es correcta, guarda los cambios en el elemento. Deberías ver el archivo o los archivos añadidos como contenido multimedia en la sección de contenido multimedia de la barra lateral.

## Integración con la importación CSV

Con la importación CSV, puedes añadir archivos multimedia a los elementos a través de File Sideload. Incluye una columna con los nombres de los archivos —no las URL completas— que apunten a los archivos de tu directorio de Sideload. Añade la asignación en Fuente multimedia > Sideload.

Al utilizar la importación CSV con tu directorio de carga lateral, te recomendamos que desmarques la opción de eliminación de archivos en la configuración del módulo «Carga lateral de archivos». La importación CSV puede eliminar archivos de tu directorio de carga lateral incluso si una tarea de importación ha fallado o se ha bloqueado. Siempre debes comprobar manualmente los resultados de la importación CSV antes de eliminar los archivos que haya importado. 
