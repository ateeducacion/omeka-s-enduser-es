# Opciones de configuración Las siguientes son opciones solicitadas con frecuencia que se pueden configurar en el archivo `local.config.php`, ubicado en el directorio `/config`. Para obtener una lista completa de las claves de configuración disponibles, consulte la [página de documentación para desarrolladores sobre ajustes de configuración](https://omeka.org/s/docs/developer/configuration/){target=_blank}. 

## Ajustes de contraseña Puede cambiar los requisitos para las contraseñas de usuario. Las opciones incluyen la longitud mínima, el número de letras mayúsculas y minúsculas, y la configuración de los símbolos permitidos. ``` 'password' => [ 'min_length' => 6,
        'min_lowercase' => null, 'min_uppercase' => null, 'min_number' => null, 'min_symbol' => null, 'symbol_list' => '`~!@#$%^&*()-=_+[]\{}|;:",./<>?\'', ], ```
Los requisitos se mostrarán en las páginas de creación y edición de usuarios (admin/users.md#password). ## Miniaturas La clave de configuración `thumbnails` contiene la mayoría de los ajustes de miniaturas: ``` 'thumbnails' => [ 'types' => [ 'large' => ['constraint' => 800],
            'medium' => ['constraint' => 200], 'square' => ['constraint' => 200], ], 'thumbnailer_options' => [ 'imagemagick_dir' => null, ], ], ```

En «types», establezca las dimensiones máximas en píxeles para las imágenes derivadas de los archivos multimedia. Hay opciones separadas para grande, mediano y cuadrado. Los valores predeterminados para estos son 800, 200 y 200 píxeles, respectivamente.

`thumbnailer_options` es una matriz de opciones que se pasan al generador de miniaturas específico que se está utilizando. Por ejemplo, la opción de miniatura `imagemagick_dir` establece la ruta a la carpeta donde se encuentra el comando `convert` de ImageMagick en el servidor. Esto puede ser útil si Omeka S no puede detectar automáticamente la ruta correcta para ImageMagick.

Utilice la [página de información del sistema](admin-dashboard.md#system-information) para verificar la versión de ImageMagick de su instalación. Si se produce un error al hacer clic en el botón, eso puede indicar que es necesario establecer la configuración manualmente. ![Los botones de información del sistema para recuperar la ruta de PHP y la versión de ImageMagick.](files/systeminfo_buttons.png)

El generador de miniaturas que se va a utilizar se configura en la clave `service_manager`, estableciendo el alias para `Omeka\File\Thumbnailer`: ``` 'service_manager' => [ 'aliases' => [ 'Omeka\File\Thumbnailer' => 'Omeka\File\Thumbnailer\ImageMagick', ], ], ```

El generador de miniaturas predeterminado es `Omeka\File\Thumbnailer\ImageMagick`. También están disponibles `Omeka\File\Thumbnailer\Imagick` (que utiliza la extensión PHP `imagick`) y `Omeka\File\Thumbnailer\Gd` (que utiliza la extensión PHP `gd`, comúnmente disponible).

También puede configurar el generador de miniaturas como `Omeka\File\Thumbnailer\NoThumbnail`, lo que impedirá que su instalación de Omeka S genere miniaturas. [GD](https://secure.php.net/manual/en/intro.image.php){target=_blank} es una biblioteca gráfica básica que se instala por defecto con PHP. Solo puede crear miniaturas para formatos de imagen comunes (jpeg, gif, png). [Imagick e ImageMagick](https://www.imagemagick.org){target=_blank} son la misma biblioteca y pueden crear miniaturas para más de 200 formatos. Imagick está integrado en PHP e ImageMagick es la versión de línea de comandos. 

ImageMagick puede requerir que se establezca manualmente una ruta en `imagemagick_dir`, mientras que Imagick y GD no requieren rutas. Puede utilizar la página ["Información del sistema"](admin-dashboard.md#system-information) en la parte inferior de la interfaz administrativa para comprobar si GD e Imagick están habilitados como extensiones PHP en su servidor.

!!! Nota Algunos servidores no permiten que las aplicaciones ejecuten programas de línea de comandos a través de PHP. Es posible que aparezca un mensaje de error como `Laminas\ServiceManager\Exception\ServiceNotCreatedException` `No se pudo crear el servicio con el nombre «Omeka\Cli». Motivo: Ni «proc_open()» ni «exec()» están disponibles.`

	En este caso, ImageMagick no funcionará, pero Imagick y GD sí. ## Ruta de PHP Omeka S utiliza tareas en segundo plano para algunas tareas de larga duración que operan en muchos elementos o que, de otro modo, podrían llevar mucho tiempo. Omeka S utiliza la CLI (interfaz de línea de comandos) de PHP para ejecutar estas tareas, el comando «php». Una ruta de PHP no válida puede causar una serie de problemas en su instalación de Omeka. 

Omeka 4.0 y versiones posteriores requieren PHP versión 7.4 y posteriores. Omeka S, por defecto, intentará detectar automáticamente la ruta a la CLI de PHP en el servidor, pero en algunos servidores esta detección no funciona, o hay varios comandos `php` diferentes entre los que elegir. 

Utilice la [página de información del sistema](admin-dashboard.md#system-information) para verificar que su instalación ha identificado la ruta PHP correcta. Si se produce un error al hacer clic en el botón, eso puede indicar que es necesario configurar manualmente. ![Los botones de información del sistema para recuperar la ruta PHP y la versión de ImageMagick.](files/systeminfo_buttons.png)

Si empieza a ver errores al trabajar con Omeka, como «Error PHP-CLI: ruta PHP no válida», o si hay [tareas](admin/jobs.md) que se inician pero no se completan, tendrá que configurar manualmente la ruta PHP. También es posible que desee seleccionar manualmente una versión PHP estable anterior, en lugar de una nueva versión que pueda estar causando un comportamiento inesperado en su sitio Omeka.

Para configurar la ruta de PHP, necesitará acceder al servidor donde se encuentra su sitio Omeka S; la ruta se configura editando los archivos del sitio Omeka. No se puede configurar la ruta de PHP desde el panel de administración. Configure manualmente la ruta correcta en el archivo `local.config.php`, ubicado en el directorio `/config`: ``` 'cli' => [ 'phpcli_path' => null, ], ```

Reemplace la palabra «null» por una ruta, entre comillas simples («usr/local/bin/php»). Esta ruta suele tener el siguiente aspecto: `/usr/local/php80/bin/php`, `/usr/local/bin/php` o `/usr/local/bin/ea-php74`.

Estos son solo ejemplos; la ruta correcta será específica de su servidor. Busque la ruta PHP correcta en la documentación de ayuda o en la base de conocimientos de su proveedor de alojamiento; esta es una pregunta frecuente para una gran variedad de instalaciones de software. Si no encuentra nada, póngase en contacto con su proveedor de alojamiento o administrador del sistema y pregúnteles. Si ha descargado el archivo para editarlo, asegúrese de volver a cargar la versión modificada en su instalación de Omeka.

## Correo La clave `mail` se puede utilizar para configurar cómo Omeka S envía los correos electrónicos. Omeka envía correos electrónicos a los [usuarios al registrarse](admin/users.md#create-a-user) y cuando restablecen sus contraseñas; los módulos pueden añadir otras funciones de correo electrónico, como [confirmar envíos](modules/collecting.md). 

El valor predeterminado es utilizar [sendmail](https://en.wikipedia.org/wiki/Sendmail){target=_blank}, donde el servidor es responsable de configurar y establecer la entrega del correo. Sendmail generalmente no requiere ninguna configuración por parte de Omeka S. Otra opción para algunos servidores es configurar una conexión SMTP directa para enviar correo. 

Un ejemplo de configuración, que se añadirá al final de `local.config.php`, será similar a este: ``` 'mail' => [ 'transport' => [ 'type' => 'smtp', 'options' => [ 'name' => 'localhost', 'host' => '127.0.0.1',
                'port' => 25, // 465 para 'ssl' y 587 para 'tls' 'connection_class' => 'smtp', // 'plain', 'login' o 'crammd5' 'connection_config' => [ 'username' => null, 'password' => null, 'ssl' => null, // 'ssl' o 'tls' 'use_complete_quit' => true, ], ], ], ], ``` Consulte la [documentación de laminas-mail](https://docs.laminas.dev/laminas-mail/transport/smtp-options/){target=_blank} para obtener más información.

Algunas configuraciones de correo solo permiten enviar correos con un encabezado «De» que utilice una dirección específica y autorizada. Para garantizar que todos los correos salientes utilicen una dirección «De» específica, puede utilizar «default_message_options»: ``` 'mail' => [ 'default_message_options' => [ 'from' => 'email@example.com', ], ], ```

## Recolección de basura A partir de Omeka 4.2, la recolección de basura de las sesiones ahora está activada de forma predeterminada, incluso para los servidores que de otro modo la desactivan. Si desea desactivarla manualmente, puede configurar ``` 'session' => [ 'allow_no_gc' => true, ], ``` 