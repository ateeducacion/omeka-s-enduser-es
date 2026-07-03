# Recuperación de mensajes de error

Si tienes problemas con tu instalación de Omeka S, puedes activar el seguimiento de errores para desarrolladores.

Existen dos opciones diferentes para capturar los mensajes de error. Tendrás que editar los archivos `.htaccess` y/o `local.config.php`, dependiendo de la opción que elijas. Para ello, debes utilizar un cliente FTP o de terminal; si no estás seguro de cómo hacerlo, ponte en contacto con tu administrador del sistema o con tu proveedor de alojamiento. 

## Mostrar detalles de los errores

Una opción es habilitar la visualización de los detalles de los errores en la propia página. Esto hará que las páginas del tipo «Omeka S ha detectado un error» muestren el mensaje de error y sus detalles en lugar de un mensaje genérico, y también mostrará en las páginas los errores y advertencias a nivel de PHP si se producen.

Para habilitar esta visualización, edita tu archivo `.htaccess`. El archivo `.htaccess` se encuentra en la carpeta principal de tu instalación de Omeka S.

Cambia la línea 1 de ese archivo de 

`SetEnv APPLICATION_ENV "production"`

por 

`SetEnv APPLICATION_ENV "development"`

## Registrar errores

Otra opción para obtener información detallada sobre los errores es habilitar el registro en Omeka S. Con el registro habilitado, Omeka S escribirá los detalles de todos los errores en un archivo. Cualquier página del tipo «Omeka S ha detectado un error» tendrá sus detalles registrados, y también se podrá registrar información adicional de depuración o advertencias. 

Es posible que desees elegir esta opción si quieres obtener información detallada sobre los errores, pero no quieres que los mensajes de error sean visibles para los visitantes u otros usuarios.

Para habilitar el registro de errores, edita tu archivo `local.config.php`. El archivo `local.config.php` se encuentra en la carpeta `config`.

Cambia la línea 4 de ese archivo de 

`'log' => false,`

a 

`'log' => true,`

Los errores se registrarán en el archivo `logs/application.log`. Si deseas cambiar esta ruta por otra, añade una línea debajo de `'log' => true,` con el siguiente formato

```
'path' => '/a/local/path',
```

Asegúrate de que tu servidor web tenga permisos de escritura en este archivo (o en la ubicación, si el archivo aún no existe). 

A continuación, podrás ver o descargar ese archivo en cualquier momento para comprender los errores a medida que se registren. 
