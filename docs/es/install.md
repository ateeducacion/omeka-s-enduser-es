# Instalación

## Requisitos del sistema
Para instalar Omeka S (última versión 4.2), necesitarás un servidor que ejecute lo siguiente:

- Linux
- Apache (con [AllowOverride](https://httpd.apache.org/docs/2.4/mod/core.html#allowoverride){target=_blank} configurado en «All» y [mod_rewrite](http://httpd.apache.org/docs/current/mod/mod_rewrite.html){target=_blank} habilitado)
- MySQL, versión mínima 5.7.9 **o** MariaDB, versión mínima 10.2.6
- PHP, versión mínima 8.1, con las siguientes extensiones instaladas:
  - [PDO](https://www.php.net/manual/en/book.pdo.php){target=_blank}
	- [pdo_mysql](http://php.net/manual/en/ref.pdo-mysql.php){target=_blank}
	- [mbstring](https://www.php.net/manual/en/book.mbstring.php){target=_blank}, y
  - [xml](https://www.php.net/manual/en/book.xml.php){target=_blank}. 
- **PHP 8.4 no es compatible con Omeka S 4.1 ni versiones anteriores**, pero sí lo es a partir de Omeka S 4.2 y versiones posteriores. 
- Opcional, para crear miniaturas: una de las siguientes opciones:
  - ImageMagick, versión mínima 6.7.5
	- la extensión `imagick` de PHP, o
  - la extensión `gd` de PHP.

[Imagick e ImageMagick](https://www.imagemagick.org){target=_blank} son la misma biblioteca y pueden crear miniaturas para más de 200 formatos. [GD](https://secure.php.net/manual/en/book.image.php){target=_blank} es una biblioteca gráfica básica que se instala por defecto con PHP. Solo puede crear miniaturas para formatos de imagen comunes (jpeg, gif, png). Para obtener más información, consulta la [página de configuración](configuration.md#thumbnails).

## Métodos de instalación

### Instalación desde la descarga

!!! nota
  Antes de instalar Omeka S, debes crear una base de datos MySQL y un usuario. Omeka S debe tener una base de datos dedicada; no puedes utilizar un prefijo para una base de datos utilizada por otro sistema o por una instalación de Omeka S o Classic. Para obtener más información sobre cómo crear una base de datos y un usuario, consulta la documentación de soporte de tu proveedor de alojamiento o habla con tu administrador de sistemas.

1. [Descarga la última versión desde la página de versiones](https://omeka.org/s/download/){target=_blank}.
1. Extrae el archivo zip descargado en tu ordenador.
1. Dentro del directorio, abre el archivo `config/database.ini` y añade tu nombre de usuario de MySQL, contraseña, nombre de la base de datos y nombre del servidor. El usuario y la base de datos deben haberse creado antes de este paso.
1. Sube todo este directorio a tu servidor, en la carpeta que elijas. Por ejemplo, si tu servidor es `https://yourwebsite.org/`, quizá quieras instalar Omeka S en una carpeta situada en `https://yourwebsite.org/myomekas/`. Asegúrate de que contiene tu archivo `database.ini` actualizado (no subas el archivo zip original que descargaste).
1. Asegúrate de que Apache tenga permisos de escritura en el directorio `files/` del servidor.
1. En tu navegador web, accede a la página `admin` de tu instalación de Omeka S, donde podrás completar la instalación. Por ejemplo, si has subido el contenido del directorio a `https://yourwebsite.org/myomekas/`, accede a `https://yourwebsite.org/myomekas/admin`.

### Instalación desde GitHub

Las instrucciones básicas para instalar y actualizar desde GitHub se pueden encontrar en el [ReadMe](https://github.com/omeka/omeka-s/blob/develop/README.md){target=_blank} del repositorio de Omeka S en GitHub.

A continuación, en tu navegador web, accede a la página de administración de tu instalación de Omeka S (`https://yourwebsite.org/myomekas/admin`), donde podrás completar la instalación.

### Instalación con un solo clic

Las empresas de alojamiento que utilizan [Softaculous](https://softaculous.com/){target=_blank} e [Installatron](https://installatron.com/){target=_blank} deberían ofrecer la instalación con un solo clic de Omeka Classic y Omeka S. Consulta sus catálogos de aplicaciones:

- [Omeka Classic](https://www.softaculous.com/softaculous/apps/educational/Omeka){target=_blank} y [Omeka S](https://www.softaculous.com/softaculous/apps/others/Omeka_S){target=_blank} en Softaculous
- [Omeka Classic](https://installatron.com/omeka?locale=en){target=_blank} y [Omeka S](https://installatron.com/omekas?locale=en){target=_blank} en Installatron.

El proceso de instalación con un solo clic a través de Softaculous te permite crear una base de datos y un usuario al mismo tiempo, y edita por ti el archivo `config/database.ini`.

Entre las sugerencias de alojamiento de nuestros usuarios se incluyen:

-   [Reclaim Hosting](https://reclaimhosting.com/){target=_blank}: ofrece [instalaciones de Omeka S](https://support.reclaimhosting.com/hc/en-us/sections/204007617-Omeka){target=_blank} mediante Installatron, con algunos pasos (entre ellos, [configurar manualmente la ruta de PHP](#test-and-set-the-php-path))
-   [Dotblock](http://www.dotblock.com){target=_blank} - utiliza Softaculous
-   [HostGator](http://hostgator.com){target=_blank} - utiliza Softaculous
-   [TMD Hosting](https://www.tmdhosting.com){target=_blank}: utiliza Softaculous
-   [Webuzo](http://webuzo.com){target=_blank}: utiliza Softaculous.

## Configuración inicial

Una vez que hayas instalado correctamente Omeka S y hayas configurado el archivo `database.ini`, debes acceder a la URL de administración de tu instalación de Omeka S (algo así como `https://yourwebsite.org/myomekas/admin`).

La primera vez que accedas con tu navegador al sitio recién instalado, tendrás que introducir los datos del primer usuario, junto con la información básica de tu instalación. En esta página hay dos secciones: **Crear el primer usuario** y **Configuración**.

En la sección **Crear el primer usuario**:

- Introduce una dirección de **correo electrónico** y vuelve a escribirla para confirmarla
- Confirma la **contraseña** y vuelve a escribirla en el siguiente campo para confirmarla
- Introduce un **nombre de usuario** para el usuario.

Ten en cuenta que puedes modificar todos estos datos más adelante en la sección de gestión de [Usuarios](admin/users.md) de tu instalación.

![Sección del primer usuario con los campos descritos](files/installOmekaS1.png)

En la sección **Configuración**, introduce:

- Un **título de la instalación** que se mostrará en el sitio de administración
- La **zona horaria** de la instalación (selecciona una opción del menú desplegable)
- Selecciona una **configuración regional** para el idioma del panel de administración de la instalación.

![Sección «Configuración» con los campos descritos](files/installOmekaS2.png)

Puedes modificar estos ajustes en cualquier momento en la sección [Configuración](admin/settings.md) de tu [panel de administración](admin-dashboard.md).

### Probar y configurar la ruta de PHP

Omeka S utiliza tareas en segundo plano para algunas operaciones de larga duración que se realizan sobre muchos elementos o que, por cualquier otro motivo, pueden tardar mucho tiempo. Omeka S utiliza la CLI de PHP (interfaz de línea de comandos) para ejecutar estas tareas, es decir, el comando `php`. Una ruta de PHP no válida puede causar diversos problemas en tu instalación de Omeka Classic. 

Por defecto, Omeka S intentará detectar automáticamente la ruta a la CLI de PHP en el servidor, pero en algunos servidores esta detección no funciona, o bien hay varios comandos `php` diferentes entre los que elegir. 

Si [utilizas Reclaim Hosting](#one-click-installation), tendrás que configurar manualmente la ruta de PHP durante la instalación. Consulta [sus instrucciones aquí](https://support.reclaimhosting.com/hc/en-us/articles/1500005620481#omeka-s){target=_blank}.

Utiliza la [página de información del sistema](admin-dashboard.md#system-information) para comprobar que tu instalación ha identificado la ruta correcta de PHP. Si aparece un error al hacer clic en el botón, eso puede indicar que necesitas configurar los ajustes manualmente. 

![Los botones de «Información del sistema» para obtener la ruta de PHP y la versión de ImageMagick.](files/systeminfo_buttons.png)

Consulta [Opciones de configuración](configuration.md) para obtener información sobre cómo modificar la generación de miniaturas, configurar manualmente la ruta de PHP y mucho más. 

### Trabajar con tu instalación

Una vez que hayas configurado correctamente todos los componentes técnicos de tu instalación de Omeka S, lo primero que querrás hacer es: añadir otros usuarios; crear plantillas de recursos, vocabularios y conjuntos de elementos; crear uno o más sitios; y, a continuación, añadir elementos y asignar esos recursos a tus sitios. Continúa leyendo el manual de usuario para obtener más información sobre estas partes de Omeka S.

!!! nota
  Si ya tienes una instalación de Omeka Classic o S, quizá te interese echar un vistazo a módulos como el [Omeka Classic Importer](modules/omekaCimporter.md), el [Omeka S Item Importer](modules/ositemimporter.md) o el [módulo de importación CSV](modules/csvimport.md), que pueden ayudarte a copiar otros tipos de datos.

## Actualización

### Actualización manual

1. Descarga la última versión desde la página de versiones.
1. Haz una copia de tu directorio `/config`. Tendrás que restaurar tus archivos `local.config.php` y `database.ini` a partir de esa copia.
1. Haz una copia de tu archivo `.htaccess` (en el directorio raíz) si lo has modificado, por ejemplo, al [activar el registro de errores](errorLogging.md).
1. Haz una copia de tus directorios `/modules` y `/themes`.
1. Haz una copia de tu directorio `/files`.
1. Elimina todos los archivos de Omeka S y sustitúyelos por los archivos del archivo zip actualizado.
1. Sustituye tus archivos originales `/config/local.config.php`, `/config/database.ini` y `.htaccess`.
1. Sustituye tus directorios originales `/modules`, `/themes` y `/files`.
    - En el caso de actualizaciones de versión importantes, es posible que también tengas que instalar una versión actualizada de tus módulos y temas. Las notas de la versión del núcleo indicarán si es probable que se requieran esas actualizaciones. Una vez que completes las migraciones mediante tu navegador, los módulos y temas que requieran nuevas versiones aparecerán claramente marcados en sus respectivas páginas. La página «Módulos» de tu instalación te indicará qué hay que actualizar; la página «Temas», dentro de cualquiera de tus sitios, mostrará los temas activos que necesitan actualizarse. 
1. En tu navegador web, ve a la página de administración de tu sitio (`/myomekas/admin`) y ejecuta las migraciones que sean necesarias.

### Actualización desde GitHub

Las instrucciones básicas para instalar y actualizar desde GitHub se pueden encontrar en el [ReadMe](https://github.com/omeka/omeka-s/blob/develop/README.md){target=_blank} del repositorio de GitHub de Omeka S.

## Instalación en Windows o Mac OS (solo para desarrollo)
Omeka S no es compatible con sistemas operativos propietarios o de código cerrado. Sin embargo, para **fines básicos de desarrollo** o para una formación rápida, Omeka puede ejecutarse con [WAMP](http://www.wampserver.com){target=_blank}, [MAMP](https://www.mamp.info){target=_blank} o herramientas similares.

Sigue las instrucciones de instalación estándar. Para que funcione, tendrás que realizar los siguientes cambios de [configuración](configuration.md) en el archivo `config/local.config.php`.

En primer lugar, es posible que tengas que configurar la ruta de PHP si Omeka S no detecta automáticamente la ubicación de tus utilidades de PHP en tu servidor local. Abre el archivo `local.config.php` y busca la línea 12:
```
    'cli' => [
 'phpcli_path' => null,
    ],
```

Introduce en `phpcli_path` la ruta adecuada para tu sistema operativo. Por ejemplo, si utilizas un entorno MAMP, encontrarás las utilidades de PHP dentro de la carpeta de instalación de MAMP en `MAMP\bin\php\php74`.

En segundo lugar, debes configurar Omeka S para que utilice la utilidad de generación de miniaturas disponible en tu servidor local. Abre el archivo `local.config.php` y busca la siguiente sección:
```
    'service_manager' => [
 'aliases' => [
 'Omeka\File\Store' => 'Omeka\File\Store\Local',
            'Omeka\File\Thumbnailer' => 'Omeka\File\Thumbnailer\ImageMagick',
 ],
    ],
```
Modifica el valor de `Omeka\File\Thumbnailer` como se indica a continuación, en función de lo que esté disponible en tu sistema:

- Sustituye el generador de miniaturas predeterminado por `Omeka\File\Thumbnailer\Gd`.
- Sustituye el generador de miniaturas predeterminado por `Omeka\File\Thumbnailer\Imagick` y habilita Imagick en el archivo `php.ini` de tu servidor a través de la interfaz de administración del servidor o directamente en el propio archivo.
- Mantén el generador de miniaturas predeterminado `Omeka\File\Thumbnailer\ImageMagick`, pero instala la herramienta de línea de comandos `imagemagick` y cambia el valor de `imagemagick_dir` por su directorio. Para instalar ImageMagick, consulta la documentación de tu servidor.

Si aparece el error «no input file specified», es posible que tengas que editar el archivo `.htaccess`. Comenta la línea 8: `RewriteRule !\.(php[0-9]?|phtml|phps)$ - [NC,C]`. Es posible que también tengas que comentar las líneas que siguen al bloque de comentarios de la línea 17 («The following rewrites») y sustituirlas por `RewriteRule ^(.*)$ index.php`. 
