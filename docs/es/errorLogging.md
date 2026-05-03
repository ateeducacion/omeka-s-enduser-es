# Recuperación de mensajes de error

Si tienes problemas con tu instalación de Omeka S, puedes activar el seguimiento de errores para desarrolladores.

Existen dos opciones diferentes para capturar los mensajes de error. Tendrás que editar los archivos `.htaccess` y/o `local.config.php`, dependiendo de la opción que elijas. Para ello, debe utilizar un cliente FTP o de terminal; si no está seguro de cómo hacerlo, póngase en contacto con su administrador del sistema o su proveedor de alojamiento. 

## Mostrar detalles de los errores

Una opción es habilitar la visualización de los detalles de los errores en la propia página. Esto hará que las páginas «Omeka S ha detectado un error» muestren el mensaje de error y los detalles en lugar de un mensaje genérico, y también mostrará los errores y advertencias a nivel de PHP en las páginas si se producen.

Para habilitar esta visualización, edite su archivo `.htaccess`. El archivo `.htaccess` se encuentra en la carpeta principal de su instalación de Omeka S.

Cambie la línea 1 de ese archivo de 

`SetEnv APPLICATION_ENV "production"`

a 

`SetEnv APPLICATION_ENV "development"`

## Registrar errores

Otra opción para obtener información detallada sobre los errores es habilitar el registro en Omeka S. Con el registro habilitado, Omeka S escribirá los detalles de todos los errores en un archivo. Cualquier página del tipo «Omeka S ha encontrado un error» tendrá sus detalles registrados, y también se puede registrar información adicional de depuración o advertencias. 

Es posible que desee elegir esta opción si desea obtener información detallada sobre los errores, pero no quiere mostrar los mensajes de error a los visitantes u otros usuarios.

Para habilitar el registro de errores, edite su archivo `local.config.php`. El archivo `local.config.php` se encuentra en la carpeta `config`.

Cambie la línea 4 de ese archivo de 

`'log' => false,`

a 

`'log' => true,`

Los errores se registrarán en el archivo `logs/application.log`. Si desea cambiar esto a otra ruta, añada una línea debajo de `'log' => true,` con el formato

```
'path' => '/a/local/path',
```

Asegúrese de que su servidor web tenga permisos de escritura en este archivo (o en la ubicación, si el archivo aún no existe). 

A continuación, podrá ver o descargar ese archivo en cualquier momento para comprender los errores a medida que se registran. 
