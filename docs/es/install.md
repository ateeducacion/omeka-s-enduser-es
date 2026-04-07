# Instalación

## Requisitos del sistema
Para instalar Omeka S (última versión 4.2), necesitarás un servidor que ejecute lo siguiente:

- Linux
- Apache (con [AllowOverride](https://httpd.apache.org/docs/2.4/mod/core.html#allowoverride){target=_blank} configurado en «All» y [mod_rewrite](http://httpd.apache.org/docs/current/mod/mod_rewrite.html){target=_blank} habilitado)
- MySQL, versión mínima 5.7.9 (o MariaDB, versión mínima 10.2.6)
- PHP, versión mínima 8.1, con [PDO](http://php.net/manual/en/intro.pdo.php){target=_blank}, [pdo_mysql](http://php.net/manual/en/ref.pdo-mysql.php){target=_blank} y [xml](http://php.net/manual/en/intro.xml.php){target=_blank} instaladas. 
	- PHP 8.4 no es compatible con Omeka S 4.1 o versiones anteriores, pero sí lo es a partir de Omeka S 4.2 y versiones posteriores.
- Opcional, para crear miniaturas: ImageMagick versión 6.7.5 o superior, la extensión PHP `imagick` o la extensión PHP `gd`.

[GD](https://secure.php.net/manual/en/intro.image.php){target=_blank} es una biblioteca gráfica básica que se instala por defecto con PHP. Solo puede crear miniaturas para formatos de imagen comunes (jpeg, gif, png). [Imagick e ImageMagick](https://www.imagemagick.org){target=_blank} son la misma biblioteca y pueden crear miniaturas para más de 200 formatos. Para obtener más información, consulta la [página de configuración](configuration.md#thumbnails).

## Métodos de instalación

### Instalación desde la descarga

!!! nota
  Antes de instalar Omeka S, debe crear una base de datos MySQL y un usuario. Omeka S debe tener una base de datos dedicada; no puede utilizar un prefijo para una base de datos utilizada por otro sistema o por una instalación de Omeka S o Classic. Para obtener más información sobre cómo crear una base de datos y un usuario, consulte la documentación de soporte de su proveedor de alojamiento o hable con su administrador de sistemas.

1. [Descargue la última versión desde la página de versiones](https://omeka.org/s/download/){target=_blank}.
1. Extraiga el archivo zip descargado en su ordenador.
1. Dentro del directorio, abra el archivo `config/database.ini` y añada su nombre de usuario de MySQL, contraseña, nombre de la base de datos y nombre del servidor. El usuario y la base de datos deben crearse antes de este paso.
1. Sube todo este directorio a tu servidor, en la carpeta que elijas. Por ejemplo, si tu servidor es `https://yourwebsite.org/`, es posible que desees instalar Omeka S en una carpeta ubicada en `https://yourwebsite.org/myomekas/`. Asegúrate de que contenga tu archivo `database.ini` actualizado (no subas el archivo zip original que descargaste).
1. Asegúrate de que el directorio `files/` del servidor sea escribible por Apache.
1. En tu navegador web, ve a la página `admin` de tu instalación de Omeka S, donde podrás completar la instalación. Por ejemplo, si has subido el contenido del directorio a `https://yourwebsite.org/myomekas/`, ve a `https://yourwebsite.org/myomekas/admin`.

### Instalar desde GitHub

Las instrucciones básicas para instalar y actualizar desde GitHub se pueden encontrar en el [ReadMe](https://github.com/omeka/omeka-s/blob/develop/README.md){target=_blank} del repositorio de GitHub de Omeka S.

A continuación, en tu navegador web, ve a la página de administración de tu instalación de Omeka S (`https://yourwebsite.org/myomekas/admin`), donde podrás completar la instalación.

### Instalación con un solo clic

Las empresas de alojamiento que utilizan [Softaculous](https://softaculous.com/){target=_blank} e [Installatron](https://installatron.com/){target=_blank} deberían ofrecer una instalación con un solo clic de Omeka Classic y Omeka S. Consulte sus bases de datos de aplicaciones:

- [Omeka Classic](https://www.softaculous.com/softaculous/apps/educational/Omeka){target=_blank} y [Omeka S](https://www.softaculous.com/softaculous/apps/others/Omeka_S){target=_blank} en Softaculous
- [Omeka Classic](https://installatron.com/omeka?locale=en){target=_blank} y [Omeka S](https://installatron.com/omekas?locale=en){target=_blank} en Installatron.

El proceso de instalación con un solo clic a través de Softaculous te permite crear una base de datos y un usuario al mismo tiempo, y editará el archivo `config/database.ini` por ti.

Entre las sugerencias de alojamiento de nuestros usuarios se incluyen:

-   [Reclaim Hosting](https://reclaimhosting.com/){target=_blank} - ofrece [instalaciones de Omeka S](https://support.reclaimhosting.com/hc/en-us/sections/204007617-Omeka){target=_blank} utilizando Installatron, con algunos pasos (incluida la [configuración manual de la ruta de PHP](#test-and-set-the-php-path))
-   [Dotblock](http://www.dotblock.com){target=_blank} - utiliza Softaculous
-   [HostGator](http://hostgator.com){target=_blank} - utiliza Softaculous
-   [TMD Hosting](https://www.tmdhosting.com){target=_blank} - utiliza Softaculous
-   [Webuzo](http://webuzo.com){target=_blank} - utiliza Softaculous.

## Configuración inicial

Una vez que hayas instalado correctamente Omeka S y configurado el archivo `database.ini`, debes dirigirte a la URL de administración de tu instalación de Omeka S (algo así como `https://yourwebsite.org/myomekas/admin`).

La primera vez que accedas con tu navegador al sitio recién instalado, tendrás que introducir los datos del primer usuario, junto con la información básica de tu instalación. Hay dos secciones en esta página: **Crear el primer usuario** y **Configuración**.

En la sección **Crear el primer usuario**:

- Introduce una dirección de **correo electrónico** y vuelve a escribirla para confirmarla
- Confirma la **contraseña** y vuelve a escribirla en el siguiente campo para confirmarla
- Introduce un **nombre de usuario** para el usuario.

Ten en cuenta que puedes cambiar todos estos datos más adelante en la sección de gestión de [Usuarios](admin/users.md) de tu instalación.

![Sección del primer usuario con los campos descritos](files/installOmekaS1.png)

En la sección **Configuración**, introduce:

- Un **título de la instalación** que se mostrará en el sitio de administración
- La **zona horaria** de la instalación (seleccione en el menú desplegable)
- Seleccione una **configuración regional** para el idioma del panel de administración de la instalación.

![Sección de configuración con los campos descritos](files/installOmekaS2.png)

Puede cambiar estos datos en cualquier momento en la sección [Configuración](admin/settings.md) de su [panel de administración](admin-dashboard.md).

### Prueba y configura la ruta de PHP

Omeka S utiliza tareas en segundo plano para algunas operaciones de larga duración que se realizan sobre muchos elementos o que, de otro modo, podrían tardar mucho tiempo. Omeka S utiliza la CLI de PHP (interfaz de línea de comandos) para ejecutar estas tareas, el comando `php`. Una ruta de PHP no válida puede causar varios problemas en tu instalación de Omeka Classic. 

Por defecto, Omeka S intentará detectar automáticamente la ruta a la CLI de PHP en el servidor, pero en algunos servidores esta detección no funciona, o hay varios comandos `php` diferentes entre los que elegir. 

Si estás [utilizando Reclaim Hosting](#one-click-installation), tendrás que configurar manualmente la ruta de PHP al realizar la instalación. Consulte [sus instrucciones aquí](https://support.reclaimhosting.com/hc/en-us/articles/1500005620481#omeka-s){target=_blank}.

Utilice la [página de información del sistema](admin-dashboard.md#system-information) para verificar que su instalación ha identificado la ruta de PHP correcta. Si aparece un error al hacer clic en el botón, eso puede indicar que es necesario configurar los ajustes manualmente. 

![Los botones de Información del sistema para recuperar la ruta de PHP y la versión de ImageMagick.](files/systeminfo_buttons.png)

Consulte [Opciones de configuración](configuration.md) para obtener información sobre cómo modificar la generación de miniaturas, configurar la ruta de PHP manualmente y mucho más. 

### Trabajar con su instalación

Una vez que haya configurado correctamente todos los componentes técnicos de su instalación de Omeka S, querrá comenzar por: añadir otros usuarios; crear plantillas de recursos, vocabularios y conjuntos de elementos; crear uno o más sitios; y, a continuación, añadir elementos y asignar esos recursos a sus sitios. Continúe con el manual de usuario para obtener más información sobre estas partes de Omeka S.

!!! nota
	Si ya tienes una instalación de Omeka Classic o S, quizá te interese echar un vistazo a módulos como el [Omeka Classic Importer](modules/omekaCimporter.md), el [Omeka S Item Importer](modules/ositemimporter.md) o el [módulo CSV Import](modules/csvimport.md), que pueden ayudarte a copiar otros tipos de datos.

## Actualización

### Actualizar manualmente

1. Descarga la última versión desde la página de versiones.
1. Haz una copia de tu directorio `/config`. Tendrás que restaurar tus archivos `local.config.php` y `database.ini` a partir de esa copia.
1. Haz una copia de tu archivo `.htaccess` (en el directorio raíz) si lo has modificado, por ejemplo, al [activar el registro de errores](errorLogging.md).
1. Haz una copia de tus directorios `/modules` y `/themes`.
1. Haz una copia de tu directorio `/files`.
1. Elimina todos los archivos de Omeka S y sustitúyelos por los archivos del archivo zip actualizado.
1. Reemplaza tus archivos originales `/config/local.config.php`, `/config/database.ini` y `.htaccess`.
1. Reemplaza tus directorios originales `/modules`, `/themes` y `/files`.
    - En el caso de actualizaciones de versión importantes, es posible que también tengas que instalar una versión actualizada de tus módulos y temas. Las notas de la versión del núcleo indicarán si es probable que se necesiten esas actualizaciones. Una vez completadas las migraciones mediante el navegador, los módulos y temas que requieran nuevas versiones aparecerán claramente marcados en sus respectivas páginas. La página Módulos de su instalación le indicará qué es lo que hay que actualizar; la página Temas, dentro de cualquiera de sus sitios, le mostrará los temas activos que necesitan actualizarse.
1. En su navegador web, vaya a la página de administración de su sitio (`/myomekas/admin`) y ejecute las migraciones que sean necesarias.

### Actualización desde GitHub

Las instrucciones básicas para instalar y actualizar desde GitHub se pueden encontrar en el [ReadMe](https://github.com/omeka/omeka-s/blob/develop/README.md){target=_blank} del repositorio de GitHub de Omeka S.

## Instalación en Windows o Mac OS (solo para desarrollo)
Omeka S no es compatible con sistemas operativos propietarios o de código cerrado. Sin embargo, para **fines de desarrollo básico** o para una formación rápida, Omeka puede ejecutarse con [WAMP](http://www.wampserver.com){target=_blank}, [MAMP](https://www.mamp.info){target=_blank} o herramientas similares.

Sigue las instrucciones de instalación estándar. Tendrás que realizar los siguientes cambios de [configuración](configuration.md) en el archivo `config/local.config.php` para que funcione.

En primer lugar, es posible que tengas que configurar la ruta de PHP si Omeka S no puede detectar automáticamente la ubicación de tus utilidades PHP en tu servidor local. Abre el archivo `local.config.php` y busca la línea 12:
```
    'cli' => [
 'phpcli_path' => null,
    ],
```

Rellene el valor `phpcli_path` con la ruta adecuada para su sistema operativo. Por ejemplo, si utiliza un entorno MAMP, encontrará las utilidades PHP dentro de la carpeta de instalación de MAMP en `MAMP\bin\php\php74`.

En segundo lugar, debe configurar Omeka S para que utilice la utilidad de generación de miniaturas disponible en su servidor local. Abra el archivo `local.config.php` y busque la siguiente sección:
```
    'service_manager' => [
 'aliases' => [
 'Omeka\File\Store' => 'Omeka\File\Store\Local',
 'Omeka\File\Thumbnailer' => 'Omeka\File\Thumbnailer\ImageMagick',
 ],
    ],
```
Edita el valor de `Omeka\File\Thumbnailer` con lo siguiente, según lo que esté disponible en tu sistema:

- Reemplaza el generador de miniaturas predeterminado por `Omeka\File\Thumbnailer\Gd`.
- Sustituya el generador de miniaturas predeterminado por `Omeka\File\Thumbnailer\Imagick` y habilite Imagick en el archivo `php.ini` de su servidor a través de la interfaz de administración del servidor o directamente en el archivo.
- Mantenga el generador de miniaturas predeterminado `Omeka\File\Thumbnailer\ImageMagick`, pero instale la herramienta de línea de comandos `imagemagick` y cambie el valor de `imagemagick_dir` a su directorio. Para instalar imagemagick, consulte la documentación de su servidor.

Si ve el error `no input file specified`, es posible que tenga que editar el archivo `.htaccess`. Comente la línea 8, `RewriteRule !\.(php[0-9]?|phtml|phps)$ - [NC,C]`. Es posible que también tenga que comentar las líneas que siguen al bloque de comentarios de la línea 17 («The following rewrites») y sustituirlas por `RewriteRule ^(.*)$ index.php`. 
