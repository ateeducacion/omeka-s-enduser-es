# Opciones de Configuración

Las siguientes son opciones solicitadas frecuentemente que pueden configurarse en el archivo `local.config.php`, ubicado en el directorio `/config`.

Para una lista completa de las claves de configuración disponibles, por favor consulte la [página de documentación para desarrolladores sobre ajustes de configuración](https://omeka.org/s/docs/developer/configuration/){target=_blank}.

## Ajustes de contraseña
Puede cambiar los requisitos para las contraseñas de los usuarios. Las opciones incluyen longitud mínima, número de letras mayúsculas y minúsculas, y la definición de símbolos permitidos.

```php
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

La clave de configuración `thumbnails` contiene la mayoría de los ajustes para las miniaturas:

```php
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

Bajo `types`, establezca las dimensiones máximas en píxeles para las imágenes derivadas de los archivos de medios. Hay opciones separadas para grande, mediana y cuadrada. Los valores por defecto son 800, 200 y 200 píxeles respectivamente.

`thumbnailer_options` es un array de opciones que se pasan al generador de miniaturas específico en uso. Por ejemplo, la opción `imagemagick_dir` establece la ruta a la carpeta donde se puede encontrar el comando `convert` de ImageMagick en el servidor. Esto puede ser útil si Omeka S no puede autodetectar la ruta correcta para ImageMagick.

Use la página de [Información del Sistema](admin-dashboard.md#system-information) para verificar la versión de ImageMagick de su instalación. Si hay un error al hacer clic en el botón, eso puede indicar si necesita establecer la configuración manualmente.

![Los botones de Información del Sistema para obtener la ruta de PHP y la versión de ImageMagick.](files/systeminfo_buttons.png)

El generador de miniaturas a utilizar se establece bajo la clave `service_manager`, asignando el alias para `Omeka\File\Thumbnailer`:

```php
    'service_manager' => [
        'aliases' => [
            'Omeka\File\Thumbnailer' => 'Omeka\File\Thumbnailer\ImageMagick',
        ],
    ],
```

El generador de miniaturas por defecto es `Omeka\File\Thumbnailer\ImageMagick`. También están disponibles `Omeka\File\Thumbnailer\Imagick` (que usa la extensión `imagick` de PHP) y `Omeka\File\Thumbnailer\Gd` (que usa la extensión `gd` de PHP, comúnmente disponible).

También puede establecer el generador de miniaturas a `Omeka\File\Thumbnailer\NoThumbnail`, lo que evitará que su instalación de Omeka S genere miniaturas.

[GD](https://secure.php.net/manual/en/intro.image.php){target=_blank} es una biblioteca gráfica básica instalada por defecto con PHP. Solo puede crear miniaturas para formatos de imagen comunes (jpeg, gif, png).

[Imagick e ImageMagick](https://www.imagemagick.org){target=_blank} son la misma biblioteca y pueden crear miniaturas para más de 200 formatos. Imagick está integrado en PHP e ImageMagick es la versión de línea de comandos.

ImageMagick puede requerir que establezca manualmente una ruta en `imagemagick_dir`, mientras que Imagick y GD no requieren rutas.

Puede usar la página de ["Información del sistema"](admin-dashboard.md#system-information) en la parte inferior de la interfaz administrativa para verificar si GD e Imagick están habilitados como extensiones de PHP en su servidor.

!!! note
	Algunos servidores no permiten que las aplicaciones ejecuten programas de línea de comandos a través de PHP. Puede ver un mensaje de error como:

	`Laminas\ServiceManager\Exception\ServiceNotCreatedException`

	`El servicio con el nombre “Omeka\Cli” no pudo ser creado. Razón: Ni “proc_open()” ni “exec()” están disponibles.`

	En este caso, ImageMagick no funcionará, pero Imagick y GD sí lo harán.

## Ruta de PHP

Omeka S utiliza tareas de sistema en segundo plano para algunas operaciones de larga duración que actúan sobre muchos elementos o que, de otro modo, podrían tardar mucho tiempo. Omeka S utiliza la CLI (interfaz de línea de comandos) de PHP para ejecutar estas tareas, a través del comando `php`. Una ruta de PHP no válida puede causar varios problemas en su instalación de Omeka.

Omeka 4.0 y posteriores requieren PHP versión 7.4 o superior.

Por defecto, Omeka S intentará detectar automáticamente la ruta a la CLI de PHP en el servidor, pero para algunos servidores esta detección no funciona, o hay múltiples comandos `php` diferentes entre los que elegir.

Use la página de [Información del sistema](admin-dashboard.md#system-information) para verificar que su instalación ha identificado la ruta de PHP correcta. Si aparece un error al hacer clic en el botón, eso puede indicar si necesita establecer la configuración manualmente.

![Los botones de Información del Sistema para obtener la ruta de PHP y la versión de ImageMagick.](files/systeminfo_buttons.png)

Si comienza a ver errores una vez que empieza a trabajar con Omeka, con mensajes como "Error de PHP-CLI: ruta de PHP no válida", o tiene [tareas de sistema](admin/jobs.md) que se inician pero no finalizan, necesitará establecer manualmente la ruta de PHP.

También puede que desee seleccionar manualmente una versión estable anterior de PHP, en lugar de una nueva versión que pueda estar causando un comportamiento inesperado en su sitio de Omeka.

Para establecer su ruta de PHP necesitará acceso al servidor donde reside su sitio de Omeka S; la ruta se establece editando archivos en el sitio de Omeka. No puede establecer la ruta de PHP desde el panel de administración.

Configure manualmente la ruta correcta en el archivo `local.config.php`, ubicado en el directorio `/config`:

```php
    'cli' => [
        'phpcli_path' => null,
    ],
```

Reemplace la palabra "null" por una ruta, contenida en comillas simples (por ejemplo, '/usr/local/bin/php'). Esta ruta comúnmente se ve como `/usr/local/php80/bin/php`, `/usr/local/bin/php`, o `/usr/local/bin/ea-php74`.

Estos son solo ejemplos; la ruta adecuada será específica para su servidor. Busque en la documentación de ayuda o en la base de conocimientos de su proveedor de hosting la ruta de PHP correcta; esta es una pregunta frecuente para una gran variedad de instalaciones de software. Si no encuentra nada, contacte a su proveedor de hosting o administrador de sistemas y pregúnteles.

Si ha descargado el archivo para editarlo, asegúrese de volver a subir la versión modificada a su instalación de Omeka.

## Correo

La clave `mail` se puede usar para configurar cómo Omeka S envía correos electrónicos. Omeka envía correos a los [usuarios al registrarse](admin/users.md#create-a-user) y cuando restablecen sus contraseñas; los módulos pueden añadir otras funciones de correo electrónico, como la [confirmación de envíos](modules/collecting.md).

El valor por defecto es usar [sendmail](https://en.wikipedia.org/wiki/Sendmail){target=_blank}, donde el servidor es responsable de tener la entrega de correo configurada. Sendmail generalmente no requiere configuración por parte de Omeka S. Otra opción para algunos servidores es configurar una conexión SMTP directa para enviar correo.

Un ejemplo de configuración, para añadir al final de `local.config.php`, se vería así:

```php
    'mail' => [
        'transport' => [
            'type' => 'smtp',
            'options' => [
                'name' => 'localhost',
                'host' => '127.0.0.1',
                'port' => 25, // 465 para 'ssl', y 587 para 'tls'
                'connection_class' => 'smtp', // 'plain', 'login', o 'crammd5'
                'connection_config' => [
                    'username' => null,
                    'password' => null,
                    'ssl' => null, // 'ssl' o 'tls'
                    'use_complete_quit' => true,
                ],
            ],
        ],
    ],
```

Consulte la [documentación de laminas-mail](https://docs.laminas.dev/laminas-mail/transport/smtp-options/){target=_blank} para más aclaraciones.

Algunas configuraciones de correo solo permiten enviar correos con una cabecera `From` que use una dirección específica y autorizada. Para asegurarse de que todo el correo saliente use una dirección `From` específica, puede usar `default_message_options`:

```php
    'mail' => [
       'default_message_options' => [
           'from' => 'correo@ejemplo.com',
        ],
    ],
```