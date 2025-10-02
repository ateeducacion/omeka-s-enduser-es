# Instalación

## Requisitos del sistema
Para instalar Omeka S, necesitará un servidor que ejecute lo siguiente:

- Linux
- Apache (con `AllowOverride` configurado en "All" y `mod_rewrite` habilitado)
- MySQL, versión mínima 5.7.9 (o MariaDB, versión mínima 10.2.6)
- PHP, versión mínima 7.4, con las extensiones `PDO`, `pdo_mysql`, y `xml` instaladas. PHP 8.4 no es compatible actualmente.
- Opcional, para crear miniaturas: ImageMagick versión 6.7.5 o superior, la extensión `imagick` de PHP, o la extensión `gd` de PHP.

[GD](https://secure.php.net/manual/en/intro.image.php){target=_blank} es una biblioteca gráfica básica instalada por defecto con PHP. Solo puede crear miniaturas para formatos de imagen comunes (jpeg, gif, png). [Imagick e ImageMagick](https://www.imagemagick.org){target=_blank} son la misma biblioteca y pueden crear miniaturas para más de 200 formatos. Para más información, consulte la [página de Configuración](configuration.md#thumbnails).

## Métodos de instalación

### Instalar desde el archivo descargado

!!! note
	Antes de instalar Omeka S, necesita crear una base de datos y un usuario de MySQL. Omeka S debe tener una base de datos dedicada; no puede usar un prefijo para una base de datos utilizada por otro sistema u otra instalación de Omeka S u Omeka Classic. Para más información sobre cómo crear una base de datos y un usuario, por favor, consulte la documentación de soporte de su hosting o hable con su administrador de sistemas.

1. [Descargue la última versión desde la página de lanzamientos](https://omeka.org/s/download/){target=_blank}.
2. Extraiga este archivo zip descargado en su ordenador.
3. Dentro del directorio, abra el archivo `config/database.ini` y añada su nombre de usuario, contraseña, nombre de la base de datos y nombre de host de MySQL. El usuario y la base de datos deben haber sido creados antes de este paso.
4. Suba este directorio completo a su servidor, en la carpeta de su elección. Por ejemplo, si su servidor es `https://su-sitio-web.org/`, puede que desee instalar Omeka S en una carpeta ubicada en `https://su-sitio-web.org/mi-omeka-s/`. Asegúrese de que tiene su archivo `database.ini` actualizado (no suba el archivo zip original que descargó).
5. Asegúrese de que el directorio `files/` en el servidor tenga permisos de escritura para Apache.
6. En su navegador web, navegue a la página de `admin` de su instalación de Omeka S, donde podrá completar la instalación. Por ejemplo, si subió el contenido del directorio a `https://su-sitio-web.org/mi-omeka-s/`, entonces navegue a `https://su-sitio-web.org/mi-omeka-s/admin`.

### Instalar desde GitHub

Puede encontrar instrucciones básicas para instalar y actualizar desde GitHub en el archivo [ReadMe](https://github.com/omeka/omeka-s/blob/develop/README.md){target=_blank} del repositorio de Omeka S en GitHub.

A continuación, en su navegador web, navegue a la página de administración de su instalación de Omeka S (`https://su-sitio-web.org/mi-omeka-s/admin`), donde podrá completar la instalación.

### Instalación con un clic

Las empresas de hosting que utilizan [Softaculous](https://softaculous.com/){target=_blank} deberían ofrecer una instalación en un clic de [Omeka Classic](https://www.softaculous.com/softaculous/apps/educational/Omeka){target=_blank} y [Omeka S](https://www.softaculous.com/softaculous/apps/others/Omeka_S){target=_blank}. El proceso de instalación con un clic a través de Softaculous puede permitirle crear una base de datos y un usuario al mismo tiempo, y editará el archivo `config/database.ini` por usted.

Sugerencias de nuestros usuarios incluyen:

-   [Reclaim Hosting](https://reclaimhosting.com/){target=_blank} - ofrece [instalaciones sencillas de Omeka S](https://support.reclaimhosting.com/hc/en-us/sections/204007617-Omeka){target=_blank} con algunos pasos (incluyendo [establecer manualmente la ruta de PHP](#probar-y-establecer-la-ruta-de-php)), y soporte para otras plataformas de software de código abierto.
-   [Dotblock](http://www.dotblock.com){target=_blank} - utiliza Softaculous.
-   [HostGator](http://hostgator.com){target=_blank} - utiliza Softaculous.
-   [TMD Hosting](https://www.tmdhosting.com){target=_blank} - utiliza Softaculous.
-   [Webuzo](http://webuzo.com){target=_blank} - utiliza Softaculous.

## Configuración inicial

Una vez que haya instalado Omeka S y configurado el archivo `database.ini` correctamente, debe navegar a la URL de administración de su instalación de Omeka S (algo como `https://su-sitio-web.org/mi-omeka-s/admin`).

La primera vez que apunte su navegador al sitio recién instalado, deberá introducir la información para el primer usuario, junto con información básica para su instalación. Hay dos secciones en esta página: **Crear el primer usuario** y **Ajustes**.

En la sección **Crear el primer usuario**:

- Introduzca una dirección de **correo electrónico** y vuelva a escribirla para confirmar.
- Confirme la **contraseña** y vuelva a escribirla en el siguiente campo para confirmar.
- Introduzca un **nombre de usuario** para mostrar.

Tenga en cuenta que puede cambiar todos estos datos más tarde en la sección de gestión de [Usuarios](admin/users.md) de su instalación.

![Sección del primer usuario con los campos descritos](files/installOmekaS1.png)

En la sección de **Ajustes**, introduzca:

- Un **título de la instalación** que se mostrará en el sitio de administración.
- La **zona horaria** de la instalación (seleccione del menú desplegable).
- Seleccione un **idioma** para la interfaz de administración de la instalación.

![Sección de Ajustes con los campos descritos](files/installOmekaS2.png)

Puede cambiar estos ajustes en cualquier momento en la sección de [Ajustes](admin/settings.md) de su [panel de administración](admin-dashboard.md).

### Probar y establecer la ruta de PHP

Omeka S utiliza tareas de sistema en segundo plano para algunas operaciones de larga duración que actúan sobre muchos elementos o que, de otro modo, podrían tardar mucho tiempo. Omeka S utiliza la CLI (interfaz de línea de comandos) de PHP para ejecutar estas tareas, a través del comando `php`. Una ruta de PHP no válida puede causar varios problemas en su instalación de Omeka S.

Por defecto, Omeka S intentará detectar automáticamente la ruta a la CLI de PHP en el servidor, pero para algunos servidores esta detección no funciona, o hay múltiples comandos `php` diferentes entre los que elegir.

Si está [usando Reclaim Hosting](#instalación-con-un-clic), tendrá que establecer manualmente la ruta de PHP cuando realice la instalación. Consulte [sus instrucciones aquí](https://support.reclaimhosting.com/hc/en-us/articles/1500005620481#omeka-s){target=_blank}.

Use la página de [Información del sistema](admin-dashboard.md#system-information) para verificar que su instalación ha identificado la ruta de PHP correcta. Si aparece un error al hacer clic en el botón, eso puede indicar si necesita establecer la configuración manualmente.

![Botones de Información del Sistema para obtener la ruta de PHP y la versión de ImageMagick.](files/systeminfo_buttons.png)

Consulte las [Opciones de configuración](configuration.md) para aprender a modificar la generación de miniaturas, establecer la ruta de PHP manualmente y más.

### Trabajar con su instalación

Una vez que haya configurado correctamente todos los componentes técnicos de su instalación de Omeka S, querrá comenzar por: añadir otros usuarios; crear plantillas de recursos, vocabularios y conjuntos de elementos; crear uno o más sitios; y luego añadir elementos y asignar esos recursos a sus sitios. Continúe con el manual de usuario para aprender más sobre estas partes de Omeka S.

!!! note
	Si tiene una instalación existente de Omeka Classic o S, puede que le interese examinar módulos como el [Importador de Omeka Classic](modules/omekaCimporter.md), el [Importador de Elementos de Omeka S](modules/ositemimporter.md), o el módulo de [Importación CSV](modules/csvimport.md), que pueden ayudarle a copiar otros tipos de datos.

## Actualización

### Actualizar manualmente

1. Descargue la última versión desde la página de lanzamientos.
2. Haga una copia de su directorio `/config`. Necesitará restaurar sus archivos `local.config.php` y `database.ini` desde esa copia.
3. Haga una copia de sus directorios `/modules` y `/themes`.
4. Haga una copia de su directorio `/files`.
5. Elimine todos los archivos de Omeka S y reemplácelos con los archivos del zip actualizado.
6. Restaure su archivo original `/config/local.config.php` y `/config/database.ini`, y los directorios `/modules`, `/themes` y `/files` que copió.
    - Para actualizaciones de versiones significativas, es posible que también tenga que instalar una versión actualizada de sus módulos y temas. Las notas de la versión indicarán si es probable que esas actualizaciones sean necesarias. Además, una vez que complete las migraciones usando su navegador, los módulos y temas que requieran nuevas versiones estarán claramente marcados en sus respectivas páginas.
7. En su navegador web, vaya a la página de administración de su sitio (`/mi-omeka-s/admin`) y ejecute cualquier migración que sea necesaria.

### Actualizar desde GitHub

Puede encontrar instrucciones básicas para instalar y actualizar desde GitHub en el archivo [ReadMe](https://github.com/omeka/omeka-s/blob/develop/README.md){target=_blank} del repositorio de Omeka S en GitHub.

## Instalación en Windows o Mac OS (solo para desarrollo)
Omeka S no es compatible con sistemas operativos propietarios o de código cerrado. Sin embargo, para **fines de desarrollo básicos** o para una formación rápida, Omeka puede funcionar con [WAMP](http.wampserver.com){target=_blank}, [MAMP](https://www.mamp.info){target=_blank}, o herramientas similares.

Siga las instrucciones de instalación estándar. Necesitará realizar los siguientes cambios de [configuración](configuration.md) en el archivo `config/local.config.php` para que funcione.

Primero, es posible que deba establecer la ruta de PHP si Omeka S no puede detectar automáticamente la ubicación de sus utilidades PHP en su servidor local. Abra el archivo `local.config.php` y busque la línea 12:
```
    'cli' => [
        'phpcli_path' => null,
    ],
```

Complete el valor `phpcli_path` con la ruta apropiada para su sistema operativo. Por ejemplo, si está usando un entorno MAMP, puede encontrar las utilidades de PHP dentro de la carpeta de instalación de MAMP en `MAMP\bin\php\php74`.

Segundo, necesita configurar Omeka S para que use la utilidad de generación de miniaturas disponible en su servidor local. Abra el archivo `local.config.php` y busque la siguiente sección:
```
    'service_manager' => [
        'aliases' => [
            'Omeka\File\Store' => 'Omeka\File\Store\Local',
            'Omeka\File\Thumbnailer' => 'Omeka\File\Thumbnailer\ImageMagick',
        ],
    ],
```
Edite el valor de `Omeka\File\Thumbnailer` a lo siguiente, según lo que esté disponible en su sistema:

- Reemplace el generador de miniaturas por defecto con `Omeka\File\Thumbnailer\Gd`.
- Reemplace el generador de miniaturas por defecto con `Omeka\File\Thumbnailer\Imagick`, y habilite Imagick en el archivo `php.ini` de su servidor a través de la interfaz de administración del servidor o directamente en el archivo.
- Mantenga el generador de miniaturas por defecto `Omeka\File\Thumbnailer\ImageMagick`, pero instale la herramienta de línea de comandos `imagemagick` y cambie el valor `imagemagick_dir` a su directorio. Para instalar imagemagick, consulte la documentación de su servidor.

Si ve el error `no input file specified`, puede que necesite editar el archivo `.htaccess`. Comente la línea 8, `RewriteRule !\.(php[0-9]?|phtml|phps)$ - [NC,C]`. También puede que necesite comentar las líneas que siguen al bloque de comentario en la línea 17 (“The following rewrites”) y reemplazarlas con `RewriteRule ^(.*)$ index.php`.