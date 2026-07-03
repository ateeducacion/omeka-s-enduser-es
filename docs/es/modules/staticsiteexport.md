# Exportación de sitio estático

El [módulo de exportación de sitio estático](https://omeka.org/s/modules/StaticSiteExport){target=_blank} te permite exportar una copia «aplanada» de un sitio de tu instalación de Omeka S. Mediante [Hugo](https://gohugo.io/){target=_blank}, puedes reconstruir una versión simplificada de tu sitio web que conservará la mayoría de los elementos de tus páginas y todos tus recursos.  

Los sitios estáticos no contienen los elementos habituales de los sitios web dinámicos, como la búsqueda, ni las páginas y bloques de página que utilizan consultas de búsqueda. Algunos bloques de página no se mostrarán en absoluto, y otros se mostrarán sin su configuración original. Actualmente, el módulo SSE solo admite contenido de [Mapping](mapping.md) y no de otros módulos. Los sitios estáticos se generarán con una versión del tema «predeterminado» para S.

![La página del módulo que se encuentra en cada sitio, donde se crean y gestionan las exportaciones.](modulesfiles/sse_siteTable.png)

Una vez generada una exportación, puedes editar su CSS u otro código para personalizarla y que se ajuste mejor a tu sitio web original. Para este y otros usos avanzados de las exportaciones, consulta la documentación para desarrolladores incluida en el archivo «Readme» del paquete del módulo. 

Los sitios estáticos pueden resultar útiles como copia de seguridad y registro del contenido de tu sitio, así como para reducir la carga del servidor en proyectos web heredados. 

### Requisitos y permisos

Cualquier usuario con permisos específicos para el sitio puede crear y gestionar exportaciones. 

!!! Nota
  Si utilizas la versión 1.0.0 de Static Site Export, debes usar una versión de Hugo anterior a la v0.146.0. Para las versiones de Static Site Export posteriores a la 1.0.0, debes usar Hugo v0.146.0 o posterior.

## Configuración

Tras instalar este módulo, deberás añadir una «Ruta al directorio de sitios» en la página de configuración del módulo. Esta es la ruta al directorio donde se guardarán tus sitios estáticos en el servidor. La ruta debe existir y el servidor web debe tener permisos de escritura en ella.

![La página de configuración del módulo, donde el administrador global establecerá el directorio en el que se guardarán las exportaciones de los sitios.](modulesfiles/sse_config.png)

## Exportar un sitio

Tras instalar y configurar este módulo, acceda a un sitio de Omeka en la interfaz de administración, haga clic en «Exportación de sitio estático» en el menú de navegación y pulse el botón «Exportar nuevo sitio estático».

En esta página configurarás la exportación de la siguiente manera: 

- introduciendo una «URL base»: si tienes previsto publicar el sitio simplificado en línea, 
- seleccionando un «Tema»: por el momento, Omeka S solo ofrece un tema plano que se asemeja a nuestro tema «Predeterminado». 
- indicando si se desea «Incluir recursos privados»: si esta opción no se marca, tu sitio solo incluirá los recursos disponibles para los visitantes que no hayan iniciado sesión. Si se marca, los recursos incluidos en el sitio pero visibles únicamente para los usuarios que hayan iniciado sesión también estarán disponibles en la exportación (como si fueran públicos). 


Tras configurar la exportación, haz clic en el botón «Iniciar exportación». La nueva exportación será la primera de la lista. Haz clic en el icono «Detalles» para obtener información sobre la exportación, incluido el estado de la tarea de exportación. La exportación habrá finalizado cuando el estado aparezca como «Completada».

![La página del módulo que se encuentra en cada sitio, donde se crean y gestionan las exportaciones.](modulesfiles/sse_exporting.png)

Ten en cuenta que una exportación puede tardar bastante tiempo, dependiendo del tamaño del sitio.

Ten en cuenta que la exportación ejecuta varios comandos de uso común en tu servidor: cd, cp, rm, unzip y zip. Aunque estos comandos son necesarios durante la exportación, es probable que ya estén instalados en tu servidor, por lo que no tienes que hacer nada.

![La tabla de exportaciones con la barra lateral abierta, en la que se muestra la información de la exportación.](modulesfiles/sse_info.png)

La exportación se guardará como un archivo ZIP en la carpeta que hayas establecido en la configuración del módulo. Esta será relativa a la ruta de instalación. Puedes acceder al archivo ZIP de la exportación y descargarlo mediante tu navegador o desde la línea de comandos. 

![La tabla de exportaciones con la barra lateral abierta, mostrando una confirmación de la eliminación de una exportación.](modulesfiles/sse_delete.png)

## Implementa tu sitio con Hugo

Puedes descomprimir la exportación y generar tu sitio con Hugo, ya sea de forma local o en línea. 

Tras exportar un sitio estático, puedes descomprimir el archivo ZIP resultante y utilizar inmediatamente [Hugo](https://gohugo.io/){target=_blank} para generar el sitio, ejecutar un servidor de pruebas local y visualizar el sitio:

```
cd /ruta/a/sitios-estáticos/
unzip <nombre-de-la-exportación>.zip
cd <nombre-de-la-exportación>/
hugo server
```

Una vez completada la compilación, sigue las instrucciones que aparecen en tu terminal y accede al servidor web especificado desde tu navegador. Si tu sitio web es muy grande, es posible que tengas que desactivar el comportamiento predeterminado de «vigilar los cambios y volver a generar» ejecutando `hugo server --watch=false`.

Cuando estés listo para implementar tu sitio, ejecuta `hugo` en el directorio de tu proyecto. Consulta la documentación de Hugo para obtener más información sobre cómo utilizar la  [interfaz de línea de comandos (CLI)](https://gohugo.io/commands/){target=_blank} para gestionar tu sitio web, y cómo [alojar y publicar](https://gohugo.io/host-and-deploy/){target=_blank} tu sitio web.
