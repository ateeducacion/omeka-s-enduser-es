# Tipos de datos numéricos

El [módulo «Tipos de datos numéricos»](https://omeka.org/s/modules/NumericDataTypes){target=_blank} te permite configurar determinadas propiedades como datos numéricos mediante plantillas de recursos. Puedes designar propiedades como fechas y horas o como números.

## Crear propiedades numéricas
Para implementar el módulo, tendrás que crear o editar una [plantilla de recursos](../content/resource-template.md) para establecer que determinadas propiedades tengan tipos de datos numéricos. 

Al crear o editar una plantilla de recurso, busca en la barra lateral derecha la propiedad que deseas configurar como numérica. Haz clic en la propiedad para añadirla a la plantilla si es necesario.

Una vez incluida la propiedad en la plantilla, haz clic en el icono del lápiz para editarla. En el panel lateral derecho que se abre, busca el menú desplegable «Tipo de datos» bajo el encabezado «Otras opciones».

![Primer plano de la sección «Otras opciones», en el que se muestra un menú desplegable para el tipo de datos. Una flecha roja señala el encabezado de los tipos de datos numéricos](../modules/modulesfiles/ndt-selectdata.png)

En el menú desplegable, selecciona una de las siguientes opciones bajo el encabezado «Numérico»:

- Marca de tiempo, que puede abarcar un periodo tan amplio como un año o estar formateada como fecha y hora
- Número, que puede ser negativo o positivo, y puede incluir decimales
- Duración, para indicar cuánto tiempo duró algo, con opciones que van desde años hasta segundos
- Intervalo, un rango basado en fechas con fechas de inicio y fin en cada instancia de la propiedad.

Asegúrate de hacer clic en «Aplicar cambios» en la parte inferior del panel para guardar esta configuración.

Al guardar los cambios en tu plantilla de recurso, el tipo numérico que hayas elegido debería aparecer en la columna «Tipo de datos» de la plantilla.

![Plantilla de recurso recién creada con un mensaje de actualización correcta resaltado en verde. Hay cuatro propiedades: Título, Descripción, Fecha y Cobertura espacial. En la columna «Tipo de datos», Fecha tiene el tipo «Marca de tiempo» y Cobertura espacial tiene el tipo «Número».](../modules/modulesfiles/ndt-review.png)

!!! Nota
  Estos campos mostrarán únicamente los datos numéricos introducidos; es decir, mostrarán «200» si lo que quieres indicar es «200 metros». Si quieres indicar a qué corresponden tus valores numéricos (segundos, minutos, metros, píxeles, pulgadas, etc.), te recomendamos utilizar la etiqueta alternativa de la propiedad para incluir la escala que estés utilizando; por ejemplo, utiliza «Cobertura espacial» y cámbiale el nombre para indicar «Altura (cm)».

## Añadir datos numéricos
Cuando añadas o edites un elemento utilizando la plantilla que has creado anteriormente, las propiedades que hayas definido como numéricas aparecerán de la siguiente manera:

### Marca de tiempo
La propiedad «Marca de tiempo» se carga automáticamente con los campos «Año», «Mes» y «Día». El campo «Mes» es un menú desplegable en el que puedes seleccionar uno de los nombres de los meses. 

Si introduces un día sin mes, la información del día no se guardará. 

![Campos de marca de tiempo vacíos, para la propiedad «Fecha»](../modules/modulesfiles/ndt-timestamp1.png)

Al hacer clic en el botón «hora» situado a la derecha del campo de entrada del día, se cargarán campos desplegables adicionales para la hora, los minutos y los segundos. Ten en cuenta que no hay opción AM/PM; utiliza el formato de 24 horas (14 para las 2 p. m., etc.).

![Campos de marca de tiempo vacíos, para la propiedad «Fecha», con una fila de opciones de introducción de la hora debajo de las opciones de introducción de la fecha](../modules/modulesfiles/ndt-timestamp2.png)

Las entradas deben ser números enteros, sin decimales.

### Número
Una propiedad de número es un pequeño campo de texto que permite introducir un número, ya sea entero o con decimales (es decir, este campo admite caracteres numéricos, un signo negativo [-] delante del número y un punto). 

El valor introducido debe ser un número entero o decimal. El número no debe ser inferior a -9007199254740991 ni superior a 9007199254740991. El número de dígitos a la izquierda o a la derecha del punto decimal no puede superar los 16.

![Campo de la propiedad «Cobertura espacial» con el número 1 en el campo de introducción de números y un botón de selección hacia arriba o hacia abajo a la derecha del campo](../modules/modulesfiles/ndt-number.png)

### Duración
La propiedad «Duración» cuenta con una serie de campos en los que introducir la duración del recurso. Hay campos para Años, Meses y Días. Al hacer clic en el botón «hora» situado a la derecha del campo de introducción de días, se cargarán campos desplegables adicionales para horas, minutos y segundos. Ten en cuenta que no hay opción de AM/PM; utiliza el formato de 24 horas (14 para las 2 de la tarde, etc.).

![Una propiedad denominada «duración», que utiliza el término «extent» del vocabulario DCTerms. Los campos descritos se encuentran en una pila, con el año en la parte superior.](../modules/modulesfiles/ndt-duration.png)

No es necesario rellenar todos los campos. Por ejemplo, puedes introducir una duración de 1 año y 5 días, dejando en blanco el campo del mes.

### Intervalo
Una propiedad «Intervalo» te permite introducir las fechas y horas de inicio y fin de un recurso. Hay dos conjuntos de campos de marca de tiempo: uno para la fecha de inicio y otro para la de fin. 

![Propiedad «Intervalo» sin horas introducidas](../modules/modulesfiles/ndt-interval.png)

## Edición masiva de datos numéricos

El módulo añade opciones adicionales al menú desplegable de la [opción «Convertir tipo de datos» en las páginas de edición masiva](../content/items.md#batch-editing) para los recursos (elementos, medios y conjuntos de elementos).

La opción «Convertir tipo de datos» te permite convertir una propiedad de texto existente a otros tipos de datos, incluidos los numéricos. No funcionará en propiedades cuyos datos sean actualmente un recurso de Omeka o un URI. 

Este método te permite añadir tipos de datos numéricos a los recursos sin necesidad de utilizar plantillas de recursos para ello. 

En el primer campo, selecciona una propiedad del menú desplegable. Puedes escribir para buscar entre las propiedades. Ten en cuenta que este menú desplegable carga los nombres de las propiedades del vocabulario y no incluirá las etiquetas adicionales de tu plantilla de recursos, así que asegúrate de saber qué término del vocabulario estás buscando.

En el segundo campo, selecciona una de las siguientes opciones para la conversión:

- Marca de tiempo
- Número
- Duración
- Intervalo.

![Las opciones de edición por lotes para «Convertir a numérico».](modulesfiles/ndt-batchedit.png)

Cuando los datos textuales se convierten en datos numéricos, el módulo identificará números o fechas y horas con formato [ISO 8601](https://en.wikipedia.org/wiki/ISO_8601){target=_blank}. No reconocerá ni reformateará fechas con, por ejemplo, el formato `MM/DD/AAAA`. Tendrás que editar manualmente o importar de forma masiva los formatos correctos mediante la [importación CSV](../modules/csvimport.md).

Utiliza los siguientes formatos para las [fechas](https://en.wikipedia.org/wiki/ISO_8601#Dates){target=_blank}, incluyendo guiones entre los valores:

- `2022`
- `2022-08` (año y mes, sin fecha)
- `2022-08-18`.

Utiliza los siguientes formatos para añadir [horas](https://en.wikipedia.org/wiki/ISO_8601#Times){target=_blank} a tus valores de fecha:

- `2022-08-18T17:26:49+00:00` ([diferencia horaria respecto al UTC](https://en.wikipedia.org/wiki/ISO_8601#Time_offsets_from_UTC){target=_blank})
- `2022-08-18T17:26:49Z` ([tiempo universal coordinado](https://en.wikipedia.org/wiki/ISO_8601#Coordinated_Universal_Time_(UTC)){target=_blank}). 

No se puede omitir el año al indicar un mes y/o un día. No se pueden indicar fechas ordinales (como, por ejemplo, `2000-175` para el día 175 del año 2000). 

Utiliza el siguiente formato para [intervalos](https://en.wikipedia.org/wiki/ISO_8601#Time_intervals){target=_blank} con puntos de inicio y fin:

- `2007-03-01T13:00:00Z/2008-05-11T15:30:00Z` (Inicio y fin).

Utiliza los siguientes formatos para [duraciones](https://en.wikipedia.org/wiki/ISO_8601#Durations){target=_blank}, expresadas en número de años, número de meses, número de días, etc.:

- `P23DT23H` (23 días y 23 horas)
- `P3Y6M4DT12H30M5S` (3 años, 6 meses, 4 días, 12 horas, 30 minutos y 5 segundos).

## Ordenar por datos numéricos

Una vez que dispongas de recursos que utilicen tipos de datos numéricos, estos aparecerán como opciones ordenables en las vistas de exploración de los recursos correspondientes. Por ejemplo, si al menos un elemento tiene un valor de «Marca de tiempo» en un campo, puedes ordenar la tabla de exploración de elementos según ese campo. 

Haz clic en el primer menú desplegable situado en la esquina superior derecha de la tabla de recursos, cuyo valor por defecto es «Creado».

Al hacer clic en este menú desplegable, aparecerán varias opciones, incluidas todas las propiedades que utilizan tipos de datos numéricos. Estas opciones se muestran como la propiedad con el tipo de datos entre paréntesis, por ejemplo, «Fecha (numérico:marca de tiempo)». 

![El contenido del menú desplegable, con las opciones habituales además de ocho propiedades que utilizan tipos de datos numéricos.](../modules/modulesfiles/ndt-browsesort.png)

Ten en cuenta que, en ocasiones, en la interfaz —incluido aquí—, es posible que veas aparecer «entero» cuando se hace referencia a «número». Se seguirá tratando de números que pueden incluir decimales. 

## Búsqueda de datos numéricos

Cuando el módulo está activo, añade opciones de búsqueda adicionales a la «Búsqueda avanzada» de recursos. 

![Opciones de búsqueda por tipo de datos numéricos, sin datos introducidos](../modules/modulesfiles/ndt-search.png)

Para cada opción de búsqueda, debes seleccionar una propiedad específica del menú desplegable. Por ejemplo, si utilizas «Duración» de dos vocabularios distintos, uno para películas (`time:hasDuration`) y otro para eventos (`dcterms:extent`), deberás seleccionar la propiedad correcta de la plantilla de recurso que desees buscar. El menú desplegable mostrará las etiquetas originales de las propiedades (`Extent` o `hasDuration` en los ejemplos anteriores). Si pasas el cursor por encima de las propiedades del menú desplegable, se mostrarán las plantillas de recursos que utilizan esa propiedad y a las que se aplicará la búsqueda.

![La búsqueda «Fecha anterior a», mostrando el menú desplegable de la propiedad «Fecha»](../modules/modulesfiles/ndt-searchhelper.png)

Los datos de **marca de tiempo** tienen dos opciones de búsqueda: «Fecha anterior a» y «Fecha posterior a». Selecciona la propiedad de marca de tiempo en el menú desplegable; en él solo aparecerán las propiedades que se utilizan para la marca de tiempo. 

Los datos de **Duración**, al igual que los de marca de tiempo, tienen dos opciones: «La duración es mayor que» y «La duración es menor que». Tras seleccionar la propiedad en la que desea realizar la búsqueda, introduzca valores para años, meses, días, horas, minutos o segundos.

La búsqueda **«Fecha en un intervalo»** busca una fecha dentro de un intervalo. Al realizar una búsqueda por intervalo, sea lo más preciso posible. Debido a la forma en que el módulo almacena las marcas de tiempo, la fecha que se busca debe estar *dentro* del intervalo. Por lo tanto, una búsqueda del año 1814 no mostraría un evento con el intervalo del 12 al 15 de septiembre de 1814, debido a la forma en que los datos interpretan ambas fechas. 

Los datos **numéricos** se pueden buscar con «Valor menor que» y «Valor mayor que». Al igual que con los datos de marca de tiempo, solo se cargarán en el menú desplegable las propiedades que contengan datos numéricos. 

## Integración con otros módulos

Las funciones de los tipos de datos numéricos son compatibles con [Collecting](../modules/collecting.md), [CSV Import](../modules/csvimport.md), [Navegación por facetas](../modules/facetedbrowse.md) y [Asignación](../modules/mapping.md).