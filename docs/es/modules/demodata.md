# Datos de demostración

El [módulo «Datos de demostración»](https://omeka.org/s/modules/DemoData){target=_blank} importa conjuntos de datos de ejemplo de elementos de Omeka S para su desarrollo, prueba y evaluación. Los conjuntos de datos utilizan contenidos reales del patrimonio cultural para demostrar la amplitud del modelo de datos de Omeka S: vocabularios, clases de recursos, tipos de valores, medios y módulos que funcionan conjuntamente en cuatro ámbitos distintos. Los recursos de estos conjuntos de datos se recopilaron con la ayuda de modelos lingüísticos y de visión más amplios.

«Datos de demostración» proporciona datos en formatos compatibles con otros módulos. El módulo [Tipos de datos numéricos](numericdatatypes.md) es opcional; cuando está activo, los campos de fecha, duración, intervalo y números enteros se almacenan como valores numéricos estructurados en lugar de como texto sin formato. El módulo [Mapeo](mapping.md) es opcional; cuando está activo, las coordenadas geográficas se muestran como marcadores en el mapa.

La interfaz de este módulo solo está disponible para usuarios con los niveles de Administrador global y Supervisor. Los recursos creados estarán disponibles para todos los usuarios, pero la titularidad recaerá en el usuario que haya importado el conjunto de datos. 

## Uso de los datos de demostración

Tras la instalación y activación, «Datos de demostración» aparecerá como una opción en la sección «Módulos» de la barra lateral izquierda del panel de control administrativo. 

![La pantalla de administración de «Datos de demostración», que muestra los cuatro conjuntos de datos de muestra disponibles en recuadros, cada uno con un botón «Importar».](modulesfiles/demodata.png)

La pantalla de administración de «Datos de demostración» ofrece información sobre los cuatro conjuntos de datos de muestra disponibles. Cada uno se describe con un breve resumen y el número de elementos, archivos multimedia y conjuntos de elementos que se crearán en su instalación. Cada conjunto de datos tiene un botón «Importar». 

Al hacer clic en el botón «Importar» de cualquiera de los conjuntos de datos, aparecerá un indicador que muestra que el conjunto de datos se está importando. A continuación, puede hacer clic en los enlaces «Tarea» o «Registro» para realizar un seguimiento del proceso en segundo plano. Cada importación solo debería tardar uno o dos minutos. Puede actualizar esta página haciendo clic de nuevo en el enlace «Datos de demostración» de la barra lateral. 

![Un conjunto de datos en proceso de importación. Una barra verde en la parte superior de la pantalla indica que la importación está en curso. El cuadro del conjunto de datos muestra ahora «Importando...» junto al título de los datos, así como los enlaces «Tarea» y «Registro».](modulesfiles/demodata_import.png)

Cuando finalice la importación, el conjunto de datos mostrará «Importado» en verde junto al título de los datos. Ahora hay enlaces disponibles para ver los elementos y los conjuntos de elementos creados para este conjunto de datos. 

!!! Nota
  Los recursos importados no se añadirán a ningún sitio. Los usuarios pueden añadir manualmente los elementos a un sitio para ver cómo se muestran en la parte pública de Omeka. Recomendamos encarecidamente que solo añadas estos recursos a un sitio privado, para evitar que los motores de búsqueda indexen por error este contenido.

Ahora dispondrás de los botones «Reimportar» o «Purgar» para cada conjunto de datos importado. Al purgar un único conjunto de datos, se eliminarán los recursos relacionados de tu instalación, pero el módulo seguirá ocupando espacio de almacenamiento en tu servidor. La purga eliminará la plantilla de recursos relacionada con cada conjunto de datos, así como todos sus recursos. 

![La pantalla «Datos de demostración» mostrando la purga de un conjunto de datos.](modulesfiles/demodata_purge.png)

### Desinstalación

El módulo requiere un espacio de almacenamiento de más de 300 megabytes. Este es, con diferencia, el módulo más grande de Omeka Team. Su objetivo es proporcionar a los usuarios de Omeka S elementos de muestra para aprender diversas funciones. Cuando ya no lo necesites, debes desinstalarlo desde la interfaz y eliminarlo manualmente de la carpeta `/modules` de tu servidor para liberar espacio de almacenamiento. 

Ten en cuenta que el módulo importa un vocabulario denominado «Datos de demostración» cuando se instala por primera vez. Este vocabulario estará presente en tu instalación, independientemente de si has importado un conjunto de datos o no. Este vocabulario se elimina al desinstalar el módulo, junto con el resto de recursos y plantillas de recursos. No es necesario purgar los conjuntos de datos antes de desinstalar el módulo. 

## Conjuntos de datos

Cada conjunto de datos crea su propio conjunto o conjuntos de elementos y su plantilla de recursos al importarse. Al volver a importar un conjunto de datos, los datos anteriores se sustituyen por completo.

| Conjunto de datos | Elementos | Archivos multimedia |
|---|---|---|
| Obras de arte | 200 | 200 |
| Civilizaciones | 450 | 352 |
| Documentos | 50 | 67 |
| Personas | 100 | 85 |

Las plantillas de recursos creadas se encuentran bajo los nombres «Datos de demostración: [Conjunto de datos]».

![Elementos que se muestran en la página de exploración de elementos del conjunto de datos «Datos de demostración: Conjunto de datos de documentos». En las columnas de exploración se muestran miniaturas, clases de elementos y plantillas de recursos.](modulesfiles/demoData_items.png)

### Obras de arte

Este conjunto de datos ocupa aproximadamente 17 MB. 

Pinturas, esculturas, dibujos y manuscritos que abarcan desde la Antigüedad hasta el siglo XX, organizados por movimiento y período. Las plantillas de recursos incluyen etiquetas de propiedades alternativas, identificadores URI, valores numéricos de fecha, marcadores de mapa, enlaces entre elementos y archivos multimedia con valores de las propiedades «título» y «creador». 

### Civilizaciones

Este conjunto de datos ocupa aproximadamente 19 MB. 

Entidades políticas históricas (reinos, imperios, dinastías y períodos culturales) de todo el mundo antiguo, medieval y de la Edad Moderna. Es el conjunto de datos más grande, con 450 elementos. Permite practicar con los cuatro tipos de datos numéricos (marca de tiempo, duración, intervalo, entero), marcadores de mapa con cuadros delimitadores, enlaces entre elementos y archivos multimedia con valores de la propiedad «título».

### Documentos

Este conjunto de datos ocupa aproximadamente 286 MB. 

Documentos históricos manuscritos y mecanografiados, entre los que se incluyen cartas, diarios, periódicos y registros oficiales desde el siglo XV hasta el XX. Varios elementos cuentan con múltiples archivos multimedia que representan páginas individuales de un documento de varias páginas; cada página incluye un valor de la propiedad «título». Incluye archivos TIFF y PDF de gran tamaño.

### Personas

Este conjunto de datos ocupa aproximadamente 8 MB. 

Personajes históricos de los ámbitos de la ciencia, la literatura, la filosofía, la exploración y el liderazgo político, de diversas culturas y a lo largo de varios siglos. Incluye anotaciones de valor (fechas aproximadas de nacimiento y fallecimiento marcadas con un valor calificativo), valores de título etiquetados por idioma (nombres en lengua materna en 15 idiomas), identificadores URI, valores numéricos de fecha, marcadores de mapa y archivos multimedia con valores de la propiedad «título».
