# Exportaciones

El [módulo de exportaciones](https://omeka.org/s/modules/ExtractText){target=_blank} permite generar una exportación de la información sobre los recursos, los activos y otros elementos de tu instalación de Omeka S. El módulo puede generar archivos CSV o JSON-LD con metadatos e información interna sobre tus elementos, conjuntos de elementos o archivos multimedia, así como plantillas de recursos, vocabularios, activos, tareas, sitios y páginas de sitio, usuarios e información añadida por los módulos. 

![La tabla «Exportaciones», que muestra información sobre exportaciones anteriores.](modulesfiles/exports_sidebar.png)

## Requisitos del sistema

El módulo requiere que dos carpetas de tu instalación tengan permisos de escritura. Una es una carpeta temporal donde se recopilan los archivos de exportación, y se configura en tus ajustes. La otra es la ubicación permanente donde se almacenarán los resultados de la exportación y estarán disponibles para su descarga. Esta carpeta se encontrará dentro de la carpeta `/files` de su instalación y se llamará «exports». 

El módulo no creará la carpeta `/files/exports` durante la instalación, sino cuando inicie su primera exportación. Si se encuentra con errores, es posible que tenga que cambiar los permisos de su directorio `/files` para permitir esta creación, o bien crear manualmente el directorio `/files/exports` y configurar sus permisos. 

### Permisos de usuario

Cualquier usuario con nivel de Autor o superior puede utilizar este módulo. Los usuarios con nivel de Investigador pueden ver la tabla de exportaciones anteriores, pero no pueden generar nuevas exportaciones. 
Los usuarios pueden exportar información sobre recursos privados (sitios, páginas, elementos, conjuntos de elementos, etc., sin visibilidad) mediante este módulo. 

## Configuración

![La pantalla de configuración del módulo, con un campo visible.](modulesfiles/exports_config.png)

En esta página debes especificar una carpeta en tu servidor, dentro del directorio de instalación de Omeka S, donde se crearán los archivos de exportación temporales. Introduce la ruta relativa a la ubicación de tu instalación. 

Debes crear primero el directorio en tu servidor y configurarlo con permisos de escritura antes de guardar esta página. El módulo comprobará que la carpeta existe y que es escribible cuando guardes la página, y mostrará un mensaje de error si hay algún problema. 

## Exportar recursos

![La página de inicio del módulo, recién instalado, que muestra que aún no se ha realizado ninguna exportación.](modulesfiles/exports_emptyTable.png)

Busca la entrada «Exportaciones» en la sección «Módulos» de la barra lateral y, a continuación, haz clic en «Crear una exportación» en la esquina superior derecha para configurar tu exportación. 

![La primera página del proceso de exportación te pide que selecciones «recursos» como tipo de exportación.](modulesfiles/exports_select.png)

En este momento, la pantalla solo ofrece una opción. Es posible que en futuras versiones de este módulo, o en versiones de terceros, se añadan más opciones de exportación. 

![La segunda página del módulo te permite configurar la exportación para elegir un tipo concreto de información.](modulesfiles/exports_create.png)

En la página siguiente, configurarás la exportación para extraer información de las entradas que hayas elegido en la base de datos de la instalación. 

**Etiqueta**: Aunque el módulo rellena un nombre por defecto para esta exportación, puedes especificar uno más fácil de recordar, como el tipo de información que estás exportando. 

**Tipo de recurso**: Selecciona un tipo de información para exportar. Los tres tipos principales de recursos entre los que puedes elegir son elementos, conjuntos de elementos o archivos multimedia. Puedes utilizar una consulta para filtrar tipos específicos de estos recursos, por ejemplo, por plantilla de recurso, clase, valor de metadatos, etc. 

También puede elegir otra información de la base de datos de su instalación, incluidos los datos almacenados por los módulos. Esto puede incluir información sobre importaciones anteriores realizadas mediante «CSV Import» o «Omeka S Item Importer», jerarquías de «Hierarchy», vocabularios, plantillas de recursos y mucho más. 

![La lista de información disponible para la exportación.](modulesfiles/exports_resourceTypes.png)

Las opciones, sin contar las opciones adicionales añadidas por los módulos, incluyen:

- Tipos principales:
  - Elementos
  - Conjuntos de elementos
  - Archivos multimedia
- Otros tipos:
  - Recursos de la API
  - Activos
  - Tipos de datos
  - Tareas
  - Asignaciones
  - Módulos
  - Propiedades
  - Clases de recursos
  - Plantillas de recursos
  - Recursos
  - Páginas del sitio
  - Sitios
  - Usuarios
  - Vocabularios.

**Consulta de elementos o consulta de recursos:** Una vez que hayas elegido una opción para exportar, puedes filtrar los resultados mediante consultas. Puedes crear una consulta utilizando la barra lateral de selección para recursos (elementos, tipos de elementos y archivos multimedia). Para otros tipos de recursos, puedes introducir manualmente una consulta de texto. Por ejemplo, puede introducir lo siguiente para filtrar sus activos según el propietario:

```
owner_id=2
```

**Formato**: Puede exportar la información a un archivo CSV o JSON-LD (extensiones de archivo `.csv` o `.json`). Cualquiera de las dos opciones se comprimirá en un archivo ZIP para su descarga. 

**Referencia por**: Este campo es una opción para las exportaciones CSV. En el caso de los recursos, puedes rellenar los campos con URL absolutas (como «https://yourinstallation.org/api/items/123») o solo con identificadores internos. Esto afectará a los campos de los archivos, como los relacionados con derivados multimedia (que podrían tener un aspecto similar a «https://yourinstallation.org/files/large/123abc.png»).

**Separador de valores múltiples**: Este campo es una opción para las exportaciones a CSV. El carácter predeterminado es la barra vertical (|). Puedes cambiarlo si lo deseas. Otros separadores habituales son las comas y los puntos y comas; recomendamos elegir un carácter que no aparezca en el conjunto de datos. 

![La tabla de exportaciones con una barra verde en la parte superior que indica que se está realizando una exportación.](modulesfiles/exports_inprogress.png)

Una vez iniciada la exportación, volverás a la tabla de exportaciones anteriores. Verás una barra verde en la parte superior de la pantalla que indica que la tarea ha comenzado, junto con un enlace para consultar el estado de la misma. Si actualizas esta página, verás la tabla con el estado de la exportación indicado. También puedes encontrar esta información en la página «Tareas», a la que se accede desde la barra lateral. 

## La tabla de exportaciones

![La tabla de exportaciones, con la barra lateral abierta, que muestra más información sobre una de las exportaciones anteriores.](modulesfiles/exports_sidebar.png)

Cuando se complete una exportación, verás un icono de descarga en la fila de la tabla que, al hacer clic en él, descargará un archivo ZIP que contiene la exportación que hayas especificado (un archivo CSV o JSON). 

Una vez que hayas creado las exportaciones, puedes ver información sobre ellas haciendo clic en el icono de los tres puntos en la fila de la tabla. Esto abrirá una barra lateral en la que podrás revisar la configuración que has utilizado. 

Puedes volver a ejecutar una exportación con el icono de copia (dos páginas idénticas) o eliminar su registro de la base de datos de la instalación (y cualquier archivo que haya creado) con el icono de eliminación (papelera). Esto abrirá una ventana de confirmación. 

## Archivos exportados

El módulo generará todos los metadatos asociados al tipo de recurso elegido, incluida información interna como el propietario del elemento y enlaces a todos los archivos multimedia adjuntos y sus derivados. 

Si exportas un archivo CSV, verás encabezados de columna como `dcterms:title:literal` (el vocabulario de metadatos, el campo y el tipo de datos), así como valores internos como `o:id`, `o:owner`, `o:is_public`, `o:created`, etc. 
