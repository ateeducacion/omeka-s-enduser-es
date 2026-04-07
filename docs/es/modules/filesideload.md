# Carga lateral de archivos

El [módulo File Sideload](https://omeka.org/s/modules/FileSideload){target=_blank} permite importar archivos multimedia que ya están almacenados en el servidor donde se encuentra tu instalación de Omeka S. Al subir archivos multimedia a tus elementos, aparecerán nuevas opciones: «Carga lateral» para seleccionar archivos individuales de tu servidor, o «Carga lateral de directorio» para seleccionar carpetas llenas de archivos. 

La carga lateral de archivos es compatible con la [importación CSV](../modules/csvimport.md). Una vez instalado, las opciones de importación CSV incluirán la posibilidad de añadir archivos multimedia mediante nombres de archivo en tu directorio de carga lateral. Asegúrate de desactivar la eliminación de archivos en el módulo File Sideload cuando lo utilices con la importación CSV.

## Crear un directorio

Crea un directorio (carpeta) en tu servidor. Puede estar dentro del directorio del módulo File Sideload o en el mismo nivel que la instalación de Omeka S. 

!!! nota
  Si coloca su directorio de sideload en cualquier lugar dentro de su instalación de Omeka, incluso dentro del directorio del módulo (`youromekainstall/modules/FileSideload/yourdirectory`), tenga cuidado de no eliminarlo ni moverlo al actualizar la instalación o el módulo. Es posible que vea mensajes de error al editar elementos o archivos multimedia si no se encuentra el directorio de sideload. Vuelva a la página de configuración del módulo para solucionar este problema.

Sube o mueve archivos a este directorio. Todos los archivos y carpetas deben estar en este directorio para que sean accesibles.

Ten en cuenta que, al explorar estos archivos desde el módulo para añadirlos como medios, solo verás los nombres de los archivos y las carpetas, por lo que debes nombrar los recursos de la forma más clara posible (por ejemplo, «StudyInScarlet_coverpage.jpg» será más útil que «img001.jpg»).

## Configuración

Tras instalar el módulo, deberá configurarlo para indicarle dónde se encuentra el directorio.

En la página Módulos del menú de navegación de la izquierda, desplácese hasta File Sideload en la lista y haga clic en el botón «Configurar».

El módulo File Sideload tiene dos opciones de configuración.

![Una pantalla de configuración de ejemplo, con los campos que se enumeran a continuación. El directorio Sideload se rellena con una ruta relativa que termina en la carpeta «/sideloadFiles». La casilla «¿Eliminar el archivo sideload?» está marcada.](../modules/modulesfiles/filesideload_config2.png)

**Directorio de carga lateral**: la ruta, **relativa a la raíz del servidor**, del directorio en el que se almacenan los archivos. Debería tener un aspecto similar a:

- `/var/www/html/tu-ruta-de-instalación/omeka-s/sideload-media`
- `/home/tu-nombre-de-usuario/tu-sitio-web.org/omeka-s/sideload-files` (una ruta típica para alojamiento compartido)
- `/home/tu_nombre_de_usuario/public_html/omeka-s/modules/FileSideload/sideload` (una ruta típica para usuarios de cPanel).

Si tienes acceso al directorio a través del terminal, puedes copiar y pegar el resultado del comando `pwd`.

Si utilizas una aplicación FTP, copia la ruta del sitio remoto que aparece en la barra de direcciones de la aplicación.

**¿Eliminar el archivo sideload?**

- Si está marcado, cualquier archivo añadido a un elemento como medio se eliminará del directorio Sideload, ya que el archivo ahora se guarda como medio en la instalación de Omeka S.
- Si no está marcado, los archivos permanecerán en el directorio y estarán disponibles para añadirlos como medios a cualquier elemento, hasta que los elimines manualmente.


Añadir un archivo sideload a un elemento
------------------------------
Con File Sideload instalado y configurado, y los archivos en el directorio, ya puede utilizar el módulo para añadir medios a los elementos.

Al editar un elemento, vaya a la pestaña Medios. La barra lateral «Añadir medios» incluye ahora dos botones para Sideload (debajo de las opciones principales).

![Se muestra la pestaña de medios de un elemento en el modo de edición. Ya se han añadido al campo principal dos entradas de la barra lateral de Sideload.](../modules/modulesfiles/filesideload_browse.png)

Al hacer clic en cualquiera de los botones se añade un bloque multimedia de Sideload. Al añadir un solo archivo se crean dos campos:

- **Título**: Asigna un nuevo título al archivo multimedia (opcional).
- **Archivo**: Selecciona un archivo en este menú desplegable. El menú cargará los nombres de los archivos tal y como aparecen en el directorio. Selecciona uno del menú desplegable y guarda los cambios.

![Opciones multimedia de Sideload tal y como se enumeran arriba, con el menú desplegable abierto, mostrando los nombres de los archivos. Algunas opciones se muestran como si estuvieran en una subcarpeta, lo que se indica por su formato; por ejemplo, «item123/24750.jpg».](../modules/modulesfiles/filesideload_addfile.png)

Al añadir archivos multimedia por directorio se crean tres campos:

- **Título**: Asigna un nuevo título al archivo multimedia (opcional). Este título se aplicará de forma idéntica a todos los archivos multimedia añadidos.
- **Directorio**: Seleccione una carpeta de este menú desplegable. El menú cargará los nombres de las carpetas tal y como aparecen en el directorio. 
- **Importar directorio de forma recursiva**: Al marcar esta casilla, se incluirán tanto todos los archivos multimedia de la carpeta de carga lateral que haya elegido como todos los archivos multimedia de todas las carpetas que se encuentren dentro de esa carpeta. 

![Opciones multimedia del directorio de carga lateral tal y como se enumeran arriba, con el menú desplegable abierto, mostrando los nombres de los directorios. Se muestra un directorio como «item234/item234b», lo que indica una carpeta dentro de otra carpeta.](../modules/modulesfiles/filesideload_directory_addfile.png)

Recuerda que File Sideload tiene una configuración a nivel de módulo para eliminar archivos cuando se importan a través de este proceso. Cuando esté seguro de que la configuración es correcta, guarde los cambios en el elemento. Debería ver el archivo o archivos añadidos como medios en la sección de medios de la barra lateral.

## Integración de la importación CSV

Con la importación CSV, puede añadir medios a los elementos a través de File Sideload. Proporcione una columna con los nombres de archivo, no las URL completas, que apunte a los archivos de su directorio Sideload. Añada la asignación a Fuente de medios > Sideload.

Al utilizar la importación CSV con su directorio de carga lateral, le recomendamos que desmarque la configuración de eliminación de archivos en la configuración del módulo de carga lateral de archivos. La importación CSV puede eliminar archivos de su directorio de carga lateral incluso si una tarea de importación ha fallado o se ha detenido. Siempre debe comprobar manualmente los resultados de la importación CSV antes de eliminar los archivos que ha importado. 
