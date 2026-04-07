# Importador de elementos de Omeka S

El [módulo Importador de elementos de Omeka S](https://omeka.org/s/modules/Osii){target=_blank} permite importar elementos de una instalación de Omeka S a otra. Este importador puede duplicar elementos, sus archivos multimedia y sus conjuntos de elementos, pero no puede duplicar la información del sitio ni de las páginas. 

La transferencia de datos de una instalación a otra crea una situación en la que existe un riesgo significativo de pérdida de datos, pero una planificación y preparación cuidadosas por parte del usuario de la instalación receptora pueden evitar que eso suceda.

## Preparación para la importación

Para minimizar la pérdida de datos, la instalación local debe prepararse cuidadosamente para aceptar los datos de la instalación de origen. En la medida de lo posible, el administrador de la instalación receptora debe esforzarse por recrear el modelo de datos de la instalación remota. Para ello, el administrador debe:

- Importar cualquier [vocabulario](../content/vocabularies.md) de datos enlazados que utilicen los elementos de la instalación remota.
- [Instalar y configurar módulos](../modules/index.md) que controlen los tipos de datos utilizados como valores en los elementos de la instalación remota, tales como: 
 - [Custom Vocab](customvocab.md): además de instalar este módulo, el administrador tendrá que crear listas de valores de vocabulario personalizadas que coincidan con las utilizadas en la instalación remota.
     - [Tipos de datos numéricos](numericdatatypes.md)
 - [Sugerencia de valores](valuesuggest.md)
- [Importar cualquier plantilla de recursos](../content/resource-template.md#import-a-resource-template) utilizada por la instalación remota.
- Instalar y activar los ingesters de medios utilizados originalmente por la instalación remota, como [File Sideload](filesideload.md).
- [Verificar que los módulos que consumen muchos recursos, como Extract Text, estén configurados para una importación masiva](extracttext.md) (es decir, desactivar Tesseract para el reconocimiento de imágenes y otros extractores hasta que finalice la ingesta, y luego utilizarlos en lotes más pequeños posteriormente). 

Una vez que toda esa infraestructura esté en su sitio, la instalación local estará lista para comenzar a importar elementos.

## Añadir una importación

Inicie el proceso de importación haciendo clic en el botón «Añadir una importación» en la página de inicio del módulo en la interfaz de administración. A continuación, se le presentarán dos tipos de ajustes de configuración: remoto y local.

### Configuración remota

**Punto final raíz (obligatorio)**: Introduzca el punto final de la API de la instalación desde la que desea importar. Para encontrar el «punto final raíz», deberá navegar hasta la instalación y sustituir la parte de la URL que incluye y viene después de «/s/» por «/api».

Por ejemplo, cambie esta URL: 

`http://your-domain-name.edu/omeka-s/s/sitename/page/home`

por 

`http://your-domain-name.edu/omeka-s/api/`

Si hace clic en una URL de API, es posible que vea algo como esto:

```
{"errors":{"error":"El recurso de la solicitud de API debe ser una cadena. Se ha introducido \u0022NULL\u0022."}}
```

Aunque se trate de un error, esta URL es el punto final raíz. 

**Consulta**: Tienes la opción de incluir una «Consulta» para filtrar los elementos que se van a importar. Si no proporciona una consulta, el módulo importará todos los elementos **públicos** de la instalación remota; esto incluirá elementos que no forman parte de un sitio público. Una forma de generar una consulta es realizando una búsqueda avanzada en el sitio remoto. Una vez que se hayan cargado los resultados, puede seleccionar la parte de la URL situada a la derecha del «?» para obtener la cadena de consulta. 

**Identidad de clave** y **Credencial de clave**: Si desea importar recursos marcados como **privados**, deberá proporcionar una «Identidad de clave» y una «Credencial de clave» generadas por la instalación base. La única forma de obtener estas cadenas es tener una cuenta en la instalación remota o pedir a alguien que tenga una cuenta que se las facilite.

### Configuración local

**Etiqueta de importación (obligatorio)**: Introduzca una etiqueta identificativa para la importación. Puede ser el nombre de la organización remota u otra forma que le ayude a recordar esta conexión.

**Conjunto de elementos**: Si lo desea, seleccione uno o varios conjuntos de elementos a los que se asignarán los elementos importados.

**Excluir medios**: Marque esta casilla si desea que la importación excluya los medios. Si no se marca, los medios se importarán de forma normal. Si decide cambiar esta configuración más adelante, deberá realizar una nueva instantánea y procesar una nueva importación para que dichos cambios surtan efecto. No existe la posibilidad de sincronización automática continua de datos.

**Excluir conjuntos de elementos**: Marque esta casilla si desea que la importación excluya conjuntos de elementos (dentro de los parámetros de su consulta, si se ha definido una consulta). Si no se marca, los conjuntos de elementos de la instalación remota se importarán con normalidad. 

**Conservar recursos eliminados**: Marque esta casilla si, durante la importación, desea conservar los recursos locales de una importación anterior que se hayan eliminado de la instantánea remota actual. Si se marca, los recursos eliminados permanecerán localmente, pero ya no serán gestionados por esta importación. Si no se marca, los recursos eliminados se borrarán localmente como de costumbre.

**Añadir URL del sitio remoto**: Si desea indicar la fuente general del elemento importado, introduzca la URL del sitio del que proceden los recursos importados. Si se introduce, se añadirá a cada recurso importado y se guardará como un valor utilizando la propiedad `osii:source_site`. Es posible que desee utilizar una URL específica del sitio Omeka, como `http://your-domain-name.edu/omeka-s/s/sitename/`, en lugar de la URL de instalación base aquí; pero tenga en cuenta que todos los elementos se importarán con este enlace, independientemente de si forman parte de algún sitio concreto o no. 

**Añadir URL del recurso remoto**: Marque esta opción si desea añadir la URL canónica del elemento remoto a cada elemento importado, guardada como un valor mediante la propiedad `osii:source_resource`. Esto proporcionará un enlace directo al elemento original a través de la API, en el formato `http://your-domain-name.edu/omeka-s/api/items/1234`, en lugar de un enlace a la página de visualización del elemento en un sitio concreto. 

Guarde sus opciones de configuración haciendo clic en el botón «Enviar» situado en la esquina superior derecha de la interfaz. Una vez configurada esta importación, se guarda para su futura edición y actualización. 

![Formulario de configuración de importación con datos rellenados para el punto final raíz, la consulta, la etiqueta de importación, el conjunto de elementos y la URL del sitio remoto](../modules/modulesfiles/osii_ConfigureImportFormWithData.png)

## Gestionar importaciones

Una vez configurada una importación, el usuario accede a una interfaz con tres áreas:

- **Área de asignación**: ofrece opciones para asignar los datos de la instalación remota a la instalación local
- **Acciones de importación**: ofrece las opciones de acción para el proceso de importación y permite acceder a los resultados de dichas acciones
- **Metadatos de importación**: muestra las opciones de configuración de la importación.

Tras la configuración inicial de una importación, el usuario encontrará un mensaje en el área principal de la interfaz que dice «La preparación de la importación no está disponible en este momento». 

![Pantalla de resultado de importación añadida correctamente con las secciones Acciones de importación y Metadatos de importación en la barra lateral derecha](../modules/modulesfiles/osii_ImportSuccessfullyAdded.png)

### Realizar la instantánea

Vaya a la sección «Acciones de importación» de la barra lateral. La sección «Acciones de importación» contiene la mayoría de las acciones que necesitará para ejecutar correctamente una importación y solucionar los problemas que surjan. Haga clic en el enlace **Realizar instantánea** y, a continuación, en el botón de confirmación para tomar una instantánea de los recursos actuales de la instalación remota. Esto recopilará los datos necesarios para importar los recursos y sincronizar la instalación local con la remota. 

![Sección «Acciones de importación» de la barra lateral derecha con el enlace «Tomar instantánea» resaltado con un rectángulo rojo](../modules/modulesfiles/osii_TakeS.png)

El indicador de estado de la instantánea cambiará de «[n/a]» a «En curso». La importación puede tardar algún tiempo dependiendo del alcance del universo que se vaya a examinar. Puede hacer clic en el enlace «Actualizar estado» para comprobar el progreso. Si el estado cambia a «Error», puede hacer clic en «Ver tarea» para inspeccionar el procesamiento de la instantánea.

![Sección de acciones de importación con el estado de la instantánea como En curso](../modules/modulesfiles/osii_SnapshotInProgress.png)

Tiene la opción de «Detener instantánea» si lo desea. El estado de la instantánea cambiará a «Deteniéndose». Haga clic en «Actualizar estado» hasta que el estado haya cambiado a «Detenido».

Una vez que haya tomado correctamente una instantánea, el estado cambiará a «Completado», y el panel principal de la interfaz contendrá una gran cantidad de metadatos sobre la instantánea. Utilícelos para conciliar las diferencias entre las instalaciones remotas y locales, en la medida que desee.

### Preparar la importación

Situada en el panel principal de la interfaz, el área de asignación proporciona a los usuarios una interfaz para especificar los elementos de los datos que se van a importar. La interfaz con pestañas ofrece una comparación entre la información sobre la instalación remota y la configuración de datos local. Aprovecha este tiempo entre la instantánea y la importación completa para perfeccionar tu instalación local y capturar toda la información posible de la importación. 

- **Pestaña Recursos**: Esta vista ofrece una visión general de los recursos dentro del universo de importación, tanto en la instalación remota como en la local.

![Tabla de resumen de gestión de importación con pestañas para Recursos, Tipos de datos, Plantillas, Ingestores de medios, Propiedades y Clases](../modules/modulesfiles/osii_ManageImportOverview.png)

- **Pestaña Tipos de datos**: Esta vista ofrece una visión de los tipos de datos remotos y su recuento de valores. El usuario puede seleccionar en un menú desplegable los tipos de datos disponibles localmente (por ejemplo, literal, recurso, URI, `numeric:timestamp`) para asignar la instalación local a la instalación remota. Si detecta que hay tipos de datos disponibles de forma remota que no lo están localmente, deberá añadirlos a su instalación antes de continuar para evitar la pérdida de datos. Si un tipo de datos remoto no está mapeado a uno local, los valores no se importarán. Se pueden añadir tipos de datos mediante módulos como [Tipos de datos numéricos](numericdatatypes.md) y [Sugerencia de valores](valuesuggest.md).

- **Pestaña Plantillas**: Esta vista muestra las plantillas de recursos remotas y su recuento. El usuario puede seleccionar de un menú desplegable las plantillas de recursos disponibles localmente para asignar la instalación local a la instalación remota. Tenga en cuenta que la instalación local puede duplicar las plantillas remotas realizando [exportaciones e importaciones](../content/resource-template.md#share-resource-templates). Este puede ser un buen momento para crear o modificar plantillas que reflejen mejor los elementos que desea importar. 

- **Pestaña Ingestores de medios**: Esta vista muestra una lista de los ingestores de medios remotos y si están disponibles en la instalación local. Los medios solo se importarán si su ingestor está disponible. Tenga en cuenta que algunos de estos ingestores se pueden añadir instalando y activando módulos, como [File Sideload](filesideload.md). 

- **Pestaña Propiedades**: Esta vista incluye una lista de las propiedades remotas y si están presentes en la instalación local. Los valores solo se importarán si sus respectivas propiedades están en la instalación local. Si encuentra que hay propiedades disponibles de forma remota que no están disponibles localmente, deberá [añadir sus vocabularios a su instalación](../content/vocabularies.md#add-a-vocabulary) antes de continuar para evitar la pérdida de datos. Tenga en cuenta que es posible que vea algunas propiedades en rojo en la instalación remota: aquellas que no estaban disponibles en versiones anteriores o que han quedado obsoletas en versiones posteriores del vocabulario. Es posible que tenga que buscar e instalar la misma versión específica de ese vocabulario en su instalación local. 

![Gestionar la tabla de importación con la tabla de inventario de propiedades, con dos recuadros rectangulares en rojo que muestran las propiedades presentes y ausentes en la instalación local](../modules/modulesfiles/osii_PropertyInventory.png)

- **Pestaña Clases**: Esta vista muestra una lista de las clases remotas y si están instaladas en la instalación local. Si no es así, los elementos se importarán sin clases. Si detecta que hay clases disponibles de forma remota que no están disponibles localmente, deberá añadirlas a su instalación antes de continuar para evitar la pérdida de datos. Las clases se añaden a través de [vocabularios](../content/vocabularies.md). Tenga en cuenta que es posible que vea algunas clases en rojo en la instalación remota: aquellas que no estaban disponibles en versiones anteriores o que han quedado obsoletas en versiones posteriores del vocabulario. Es posible que tengas que buscar e instalar la misma versión específica de ese vocabulario en tu instalación local. 

Después de asignar los elementos del modelo de datos, haz clic en el botón «Enviar» situado en la esquina superior derecha de la página. Recibirás un mensaje de confirmación indicando que la importación se ha preparado correctamente. 

### Modifique la instantánea según sea necesario

Una vez que haya consultado los recursos remotos, puede modificar la instantánea si lo desea, volviendo a la primera página de configuración. 

Por ejemplo, si desea importar solo los elementos de un conjunto de elementos concreto que aparecía en la instantánea, utilice el campo «Consulta» para limitar los elementos encontrados en ese conjunto. Puede construir estas consultas de filtrado utilizando la búsqueda avanzada que se encuentra en los sitios remotos. 

Una vez hecho esto, toma una nueva instantánea. Deberías ver un número diferente de recursos en el «Recuento de valores remotos». 

### Importa la instantánea

En la sección Información de la instantánea del panel Acciones de importación, encontrarás la información de importación. Inicialmente, el Estado de la importación debería indicar [n/a]. Haz clic en el enlace «Importar instantánea» para iniciar la importación. Al igual que con el proceso de creación de instantáneas, el estado de la importación cambiará a «En curso» y puede tardar algún tiempo en completarse. Haga clic en el enlace «Actualizar estado» para comprobar el progreso. Del mismo modo, puede detener una importación que esté en curso haciendo clic en «Detener importación». Si el estado cambia a «Error», puede hacer clic en el enlace «Ver trabajo» para revisar el problema y cualquier mensaje de registro.

![Sección de acciones de importación de la barra lateral derecha con el enlace Importar instantánea resaltado con un rectángulo rojo](../modules/modulesfiles/osii_ImportSnapshot.png)

Una vez que el estado de la importación alcance «Completada», podrá hacer clic en «Ver elementos», «Ver medios» o «Ver conjuntos de elementos» de la importación. Además, la importación completada recibirá una marca de tiempo que indica el momento de la importación.

## Volver a revisar una importación

Una vez que haya iniciado correctamente una importación, la pantalla principal del módulo mostrará esa acción en una tabla de importaciones intentadas. Esa tabla incluye la etiqueta de la importación, el punto final raíz, el estado de la instantánea, el estado de la importación y el propietario de la importación.

### Editar una importación

Aunque una importación pueda haber tenido éxito técnicamente, es posible que haya sufrido alguna pérdida de datos debido a la asignación entre la instalación remota y la instalación local. Puede editar la importación para subsanar esa pérdida de datos. Inicie el proceso de edición haciendo clic en el icono del lápiz situado a la derecha de la etiqueta de la importación que desee. A continuación, tendrá la oportunidad de actualizar sus configuraciones, volver a tomar la instantánea, actualizar sus asignaciones y volver a ejecutar la importación.

### Repetir una importación

Es posible que tenga una importación que deba volver a ejecutarse para capturar nuevos recursos de la instalación remota. En este caso, puede editar la importación para volver a tomar la instantánea y ejecutar una nueva importación.

La importación no es una sincronización bidireccional, por lo que los cambios realizados en los elementos locales no se transfieren a los elementos remotos. Tenga en cuenta también que el módulo no conserva los cambios locales tras importaciones posteriores. Los elementos importados siempre reflejarán su estado en la instalación remota en el momento de la instantánea. **No ejecute una importación posterior si necesita conservar los cambios locales.**

Puede iniciar el nuevo proceso de importación haciendo clic en el icono del lápiz situado a la derecha de la etiqueta de la importación que desee.

A continuación, tendrá la oportunidad de actualizar sus configuraciones. En esta situación, le conviene considerar cuidadosamente la opción «Conservar recursos eliminados» si se han eliminado recursos de la instalación remota.

Tras enviar sus configuraciones, puede seguir los pasos del proceso para realizar una nueva instantánea de la instalación remota, actualizar o confirmar sus asignaciones y volver a ejecutar la importación. Esta nueva importación de la instantánea importará nuevos recursos y actualizará los recursos existentes con los cambios de la instalación remota.
