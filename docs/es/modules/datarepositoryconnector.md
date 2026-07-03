# Conector de repositorio de datos

El [módulo «Conector de repositorios de datos»](https://omeka.org/s/modules/DataRepositoryConnector/){target=_blank} permite a los usuarios importar registros y/o archivos de datos desde varias plataformas de repositorios de datos diferentes: Dataverse, Zenodo, Invenio y CKAN. Una vez importados, estos elementos se pueden actualizar en cualquier momento volviendo a ejecutar la importación original desde la página «Importaciones anteriores».

El conector de repositorios de datos añade una entrada en el menú «Módulos» de la izquierda. Al hacer clic en el nombre del módulo o en el icono del signo más situado a la izquierda, el menú se desplegará para mostrar los enlaces a las cuatro opciones de importación. El módulo se abre por defecto en la página «Importaciones anteriores».

![Menú de navegación que muestra las opciones del Conector de repositorio de datos](../modules/modulesfiles/datarepoconnect_tabs.png)

Este módulo está disponible para los usuarios con los niveles de «Administrador global» y «Supervisor».

## Importar datos

### Opciones compartidas

Independientemente del servicio que hayas seleccionado, dispondrás de las siguientes opciones:

+ **Límite**: El número máximo de resultados que se pueden recuperar en un solo lote. Si detectas errores o datos que faltan, prueba a reducir este número. Aumentarlo podría acelerar las importaciones. (Este campo es obligatorio. El valor por defecto es 100.)
+  **Importación de prueba**: Si se marca, el conector importará ÚNICAMENTE el número de resultados indicado en el campo «Límite» anterior. Esto resulta útil para obtener una vista previa de la correspondencia de metadatos entre la fuente y Omeka S, así como para garantizar que la conexión funciona.
+ **Importar archivos a Omeka S**: Si se marca, los archivos multimedia asociados a un registro se importarán a Omeka S. De lo contrario, no se incluirá ningún archivo multimedia en la importación.
+ **Comentario**: Una nota sobre el propósito o la fuente de esta importación. Aparecerá en la página «Importaciones anteriores» y puede resultar útil para realizar un seguimiento de tu progreso.
+ **Conjuntos de elementos**: Los conjuntos de elementos en los que se importarán los elementos.
+ **Sitios**: Los sitios en los que se importarán los elementos. Es posible que aquí aparezca un sitio predeterminado.

Una vez que hayas rellenado estos campos, así como los específicos de la opción que hayas seleccionado, haz clic en «Enviar».

### Dataverse

![La pantalla de importación de Dataverse mostrando las opciones que se enumeran a continuación.](../modules/modulesfiles/datarepoconnect_options.png)

Si seleccionas Dataverse, verás una pantalla con las siguientes opciones:

+ **URL principal de Dataverse**: La URL del sitio principal de Dataverse. (Este campo es obligatorio.)
+ **Identificador de Dataverse**: El identificador del Dataverse desde el que se va a importar. Si se deja en blanco, se importarán todos los conjuntos de datos de la **URL principal de Dataverse**, lo que podría suponer un volumen considerable.
+ **Formato de metadatos**: El formato de metadatos que se va a exportar desde Dataverse. Las opciones para Dataverse son «dcterms», «oai_dc» y «schema.org». El formato debe existir como [vocabulario](../content/vocabularies.md) en tu instancia de Omeka antes de la importación; puedes obtenerlo de [purl.org](http://purl.org/dc/elements/1.1/){target=_blank} y [schema.org](https://schema.org/docs/developers.html){target=_blank}. (Este campo es obligatorio.)

### Zenodo

Si seleccionas Zenodo, aparecerá una pantalla con las siguientes opciones:

+ **ID de la comunidad de Zenodo**: La cadena corta que identifica de qué comunidad de Zenodo se va a importar. Se encuentra en la URL después de «https://zenodo.org/communities/» y antes de cualquier parámetro de búsqueda. (Este campo es obligatorio.)
+ **Formato de metadatos**: El formato de metadatos que se va a exportar desde Zenodo. La única opción para Zenodo es «oai_dc». El formato debe existir como [vocabulario](../content/vocabularies.md) en tu instancia de Omeka antes de la importación; puedes obtenerlo en [purl.org](http://purl.org/dc/elements/1.1/){target=_blank}. (Este campo es obligatorio.)

### Invenio

![La pantalla de importación de Invenio, en la que se muestran las opciones que se enumeran a continuación.](../modules/modulesfiles/datarepoconnect_invenio.png)

Si seleccionas Invenio, verás una pantalla con las siguientes opciones:

+ **URL principal de Invenio**: La URL del sitio principal de Invenio. (Este campo es obligatorio.)
+ **Consulta de búsqueda**: un término que limitará los resultados importados. Si se deja en blanco, se importarán todos los conjuntos de datos de la **URL principal de Invenio**, lo que podría suponer un volumen considerable. Puedes utilizar la [sintaxis de consulta de ElasticSearch](https://www.elastic.co/guide/en/elasticsearch/reference/current/search-your-data.html){target=_blank}. Ejemplos: «oceanography», «access_right:open».

### CKAN

Si seleccionas CKAN, deberías ver una pantalla con las siguientes opciones:

+ **URL principal de CKAN**: La URL del sitio principal de Dataverse. (Este campo es obligatorio.)
+ **Organización CKAN**: El identificador de la organización CKAN desde la que se va a importar. Si se deja en blanco, se importarán todos los conjuntos de datos de la **URL principal de CKAN**, lo que podría suponer un volumen considerable.

### Comprobar el estado de la importación

Después de hacer clic en «Enviar», se te redirigirá a la página «Importaciones anteriores», donde tu tarea de importación más reciente aparecerá en una barra verde en la parte superior de la página. Puedes seguir el estado de la importación actualizando la página «Importaciones anteriores» o haciendo clic en la página «Tareas», que se encuentra en la sección «Admin» del menú de navegación de la izquierda.

!!! Nota
  ¿Tus tareas se inician pero no se completan? Es posible que tengas que [configurar la ruta de PHP](../configuration.md#php-path) para que tu sistema pueda ejecutar el proceso en segundo plano y crear los elementos.

## Revisar importaciones

Haz clic en «Conector del repositorio de datos» en el menú de navegación de la izquierda del panel de administración; se abrirá la página «Importaciones anteriores».

La tabla de importaciones anteriores incluye: 

- columnas para **deshacer** y *volver a ejecutar** tareas anteriores,
- el **ID de tarea** de la importación, 
- el enlace al **repositorio de datos** proporcionado originalmente (que muestra cuál de las cuatro fuentes se utilizó), 
- cualquier **comentario** realizado durante la importación, 
- el número de **elementos** afectados (separados en **añadidos** y **actualizados**), 
- la **fecha** de la importación, 
- el **estado** de la importación, y 
- el **propietario** que inició la importación.

![Pantalla que muestra las importaciones anteriores del conector del repositorio de datos](../modules/modulesfiles/datarepoconnect_pastimports.png)

Si una importación concreta se ha deshecho o se ha vuelto a ejecutar, la columna «Estado» lo indicará. Puedes ver un subconjunto de los elementos afectados de cada tarea haciendo clic en el enlace «Total» situado debajo de la columna «Elementos».

### Actualizar recursos importados

Para actualizar los recursos creados mediante el conector del repositorio de datos, basta con «volver a ejecutar» una importación desde la misma fuente. Los recursos se actualizarán, no se volverán a importar. Esto te permite utilizar el conector para sincronizar datos entre tus repositorios de datos y la instalación de Omeka S. 

Ve a la página «Importaciones anteriores». En la columna «Volver a ejecutar», marca la casilla correspondiente a cada importación que desees actualizar y, a continuación, pulsa «Enviar». 

!!! Nota
  Al volver a ejecutar una importación, se borrarán todas las modificaciones de metadatos que hayas realizado en los elementos desde la importación original.

### Deshacer una importación

Puedes deshacer una importación completada y eliminar todos los elementos asociados en cualquier momento. Esto borrará por completo dichos elementos y cualquier edición de metadatos que hayas realizado en ellos. 

Ve a la página «Importaciones anteriores». En la columna «Deshacer», marca la casilla correspondiente a cada importación que desees deshacer y, a continuación, haz clic en «Enviar».
