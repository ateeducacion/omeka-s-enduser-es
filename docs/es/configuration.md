# Opciones de configuración

A continuación se enumeran las opciones más solicitadas, que se pueden configurar en el archivo `local.config.php`, ubicado en el directorio `/config`. 

Para obtener una lista completa de las claves de configuración disponibles, consulta la [página de la documentación para desarrolladores sobre ajustes de configuración](https://omeka.org/s/docs/developer/configuration/){target=_blank}. 

## Ajustes de contraseña
Puedes modificar los requisitos de las contraseñas de los usuarios. Las opciones incluyen la longitud mínima, el número de letras mayúsculas y minúsculas, y la configuración de los símbolos permitidos.

```
    'password' => [
 'min_length' => 6,
 'min_lowercase' => null,
 'min_uppercase' => null,
        'min_number' => null,
 'min_symbol' => null,
 'symbol_list' => '`~!@#$%^&*()-=_+[]\{}|;:",./<>?\'',
    ],
```
Los requisitos se [mostrarán en las páginas de creación y edición de usuarios](admin/users.md#password).

## Miniaturas

La clave de configuración `thumbnails` contiene la mayoría de los ajustes relacionados con las miniaturas:

```
    'thumbnails' => [
 'types' => [
 'large' => ['constraint' => 800],
 'medium' => ['constraint' => 200],
            'square' => ['constraint' => 200],
 ],
 'thumbnailer_options' => [
 'imagemagick_dir' => null,
 ],
    ],
```

En `types`, configura las dimensiones máximas en píxeles de las imágenes derivadas de los archivos multimedia. Hay opciones independientes para «large», «medium» y «square». Los valores predeterminados son 800, 200 y 200 píxeles, respectivamente.

`thumbnailer_options` es una matriz de opciones que se pasan al generador de miniaturas específico que se esté utilizando. Por ejemplo, la opción de miniaturas `imagemagick_dir` establece la ruta a la carpeta donde se encuentra el comando `convert` de ImageMagick en el servidor. Esto puede resultar útil si Omeka S no puede detectar automáticamente la ruta correcta para ImageMagick.

Utiliza la [página de información del sistema](admin-dashboard.md#system-information) para comprobar la versión de ImageMagick de tu instalación. Si aparece un error al hacer clic en el botón, eso puede indicar que es necesario configurar los ajustes manualmente.

![Los botones de «Información del sistema» para obtener la ruta de PHP y la versión de ImageMagick.](files/systeminfo_buttons.png)

El generador de miniaturas que se va a utilizar se configura bajo la clave `service_manager`, estableciendo el
alias para `Omeka\File\Thumbnailer`:

```
    'service_manager' => [
 'aliases' => [
 'Omeka\File\Thumbnailer' => 'Omeka\File\Thumbnailer\ImageMagick',
 ],
    ],
```

El generador de miniaturas predeterminado es `Omeka\File\Thumbnailer\ImageMagick`. También están disponibles `Omeka\File\Thumbnailer\Imagick` (que utiliza la extensión PHP `imagick`) y `Omeka\File\Thumbnailer\Gd` (que utiliza la extensión PHP `gd`, de uso común).

También puedes configurar el generador de miniaturas como `Omeka\File\Thumbnailer\NoThumbnail`, lo que impedirá que tu instalación de Omeka S genere miniaturas. 

[GD](https://secure.php.net/manual/en/intro.image.php){target=_blank} es una biblioteca gráfica básica que se instala por defecto con PHP. Solo puede crear miniaturas para formatos de imagen comunes (jpeg, gif, png). 

[Imagick e ImageMagick](https://www.imagemagick.org){target=_blank} son la misma biblioteca y pueden crear miniaturas para más de 200 formatos. Imagick está integrado en PHP e ImageMagick es la versión de línea de comandos. 

Es posible que ImageMagick te pida que configures manualmente una ruta en `imagemagick_dir`, mientras que Imagick y GD no requieren rutas.

Puedes utilizar la [página «Información del sistema»](admin-dashboard.md#system-information), situada en la parte inferior de la interfaz de administración, para comprobar si GD e Imagick están habilitados como extensiones de PHP en tu servidor.

!!! Nota
  Algunos servidores no permiten que las aplicaciones ejecuten programas de línea de comandos a través de PHP. Es posible que aparezca un mensaje de error como 

  `Laminas\ServiceManager\Exception\ServiceNotCreatedException`

	`No se ha podido crear el servicio con el nombre «Omeka\Cli». Motivo: ni «proc_open()» ni «exec()» están disponibles.`

  En este caso, ImageMagick no funcionará, pero sí lo harán Imagick y GD.

## Ruta de PHP

Omeka S utiliza tareas en segundo plano para algunas operaciones de larga duración que se realizan sobre muchos elementos o que, por cualquier otro motivo, pueden tardar mucho tiempo. Omeka S utiliza la CLI de PHP (interfaz de línea de comandos) para ejecutar estas tareas, es decir, el comando `php`. Una ruta de PHP no válida puede causar diversos problemas en tu instalación de Omeka. 

Omeka 4.0 y versiones posteriores requieren PHP 7.4 o superior.

Por defecto, Omeka S intentará detectar automáticamente la ruta a la CLI de PHP en el servidor, pero en algunos servidores esta detección no funciona, o bien hay varios comandos `php` diferentes entre los que elegir. 

Utiliza la [página de información del sistema](admin-dashboard.md#system-information) para comprobar que tu instalación ha identificado la ruta correcta a PHP. Si aparece un error al hacer clic en el botón, esto puede indicar que debes configurar los ajustes manualmente.

![Los botones de «Información del sistema» para obtener la ruta de PHP y la versión de ImageMagick.](files/systeminfo_buttons.png)

Si empiezas a ver errores al comenzar a trabajar con Omeka, como «Error de PHP-CLI: ruta de PHP no válida», o si tienes [tareas](admin/jobs.md) que se inician pero no se completan, tendrás que configurar manualmente la ruta de PHP.

Quizá también te interese seleccionar manualmente una versión estable anterior de PHP, en lugar de una nueva versión que pueda estar provocando un comportamiento inesperado en tu sitio de Omeka.

Para configurar la ruta de PHP, necesitarás acceso al servidor donde se aloja tu sitio de Omeka S; la ruta se configura editando los archivos del sitio de Omeka. No es posible configurar la ruta de PHP desde el panel de administración.

Configura manualmente la ruta correcta en el archivo `local.config.php`, ubicado en el directorio `/config`:

```
    'cli' => [
 'phpcli_path' => null,
    ],
```

Sustituye la palabra «null» por una ruta, entre comillas simples ('usr/local/bin/php'). Esta ruta suele tener un formato similar a `/usr/local/php80/bin/php`, `/usr/local/bin/php` o `/usr/local/bin/ea-php74`.

Estos son solo ejemplos; la ruta correcta dependerá de tu servidor. Busca en la documentación de ayuda o en la base de conocimientos de tu proveedor de alojamiento la ruta correcta de PHP; se trata de una pregunta frecuente en relación con una gran variedad de instalaciones de software. Si no encuentras nada, ponte en contacto con tu proveedor de alojamiento o con el administrador del sistema y pregúntales.

Si has descargado el archivo para editarlo, asegúrate de volver a subir la versión modificada a tu instalación de Omeka.

## Correo electrónico

La clave `mail` se puede utilizar para configurar cómo Omeka S envía correos electrónicos. Omeka envía correos electrónicos a los [usuarios al registrarse](admin/users.md#create-a-user) y cuando restablecen sus contraseñas; los módulos pueden añadir otras funciones de correo electrónico, como la [confirmación de envíos](modules/collecting.md). 

Por defecto, se utiliza [sendmail](https://en.wikipedia.org/wiki/Sendmail){target=_blank}, donde el servidor se encarga de tener configurado y preparado el envío de correo. Sendmail no suele requerir ninguna configuración por parte de Omeka S. Otra opción para algunos servidores es configurar una conexión SMTP directa para el envío de correo. 

Un ejemplo de configuración, que debe añadirse al final del archivo `local.config.php`, tendría un aspecto similar al siguiente:

```
    'mail' => [
 'transport' => [
 'type' => 'smtp',
 'options' => [
 'name' => 'localhost',
 'host' => '127.0.0.1',
                'port' => 25, // 465 para «ssl» y 587 para «tls»
 'connection_class' => 'smtp', // «plain», «login» o «crammd5»
                'configuración_de_conexión' => [
 'nombre_de_usuario' => null,
 'contraseña' => null,
 'ssl' => null, // «ssl» o «tls»
 'use_complete_quit' => true,
 ],
 ],
 ],
    ],
```

Consulta la [documentación de lamas-mail](https://docs.laminas.dev/laminas-mail/transport/smtp-options/){target=_blank} para obtener más información.

Algunas configuraciones de correo solo permiten enviar mensajes con un encabezado «From» que utilice una dirección específica y autorizada. Para garantizar que todo el correo saliente utilice una dirección «From» específica, puedes utilizar `default_message_options`:

```
    'mail' => [
 'default_message_options' => [
 'from' => 'email@example.com',
 ],
    ],
```

## Recolección de basura

A partir de Omeka 4.2, la recolección de basura de las sesiones está activada por defecto, incluso en servidores que, de otro modo, la desactivarían.

Si deseas desactivarla manualmente, puedes configurar 

```
  'session' => [
    'allow_no_gc' => true,
  ],
``` 