---
título: Limpieza de datos
---
# Limpieza de datos

El [módulo de limpieza de datos](https://omeka.org/s/modules/DataCleaning){target=_blank} sirve para la auditoría y limpieza de bajo nivel de los metadatos de los recursos. Está diseñado para preparar los metadatos de los recursos para su uso en visualizaciones.

Los cambios realizados por el módulo de limpieza de datos no se pueden deshacer fácilmente y pueden resultar destructivos. Debido a la gran potencia del módulo, solo pueden utilizarlo los administradores globales. 

!!! nota
  Antes de ejecutar cualquier auditoría, asegúrate de tener una copia de seguridad reciente de tus datos. La copia de seguridad de la base de datos SQL se puede realizar con muchos proveedores de alojamiento, y puedes hacer una copia de seguridad de toda tu instalación de Omeka si la instalaste a través de un gestor de aplicaciones.

Una vez que hayas [instalado](index.md#installing-modules) Data Cleaning, se añadirá a los módulos disponibles en el panel de navegación de la izquierda de tu vista administrativa.

## Realizar una auditoría
En la sección de «Data Cleaning» dentro de «Módulos», haz clic en el botón «Preparar nueva auditoría» situado en la esquina superior derecha de la página. 

### Preparar la auditoría
Esto abrirá el formulario «Preparar auditoría», que te permite centrarte en los datos que deseas revisar y, quizás, corregir. El formulario cuenta con las siguientes opciones básicas: 

- **Tipo de recurso**: selecciona el tipo de recurso que deseas auditar en el menú desplegable. Las opciones son elementos, conjuntos de elementos o medios.

- **Consulta de recursos**: Haz clic en el botón «Editar» para mostrar la interfaz del generador de consultas en la barra lateral derecha. Utiliza el formulario para definir el conjunto de recursos que deseas auditar. Puedes hacer clic en el botón «Edición avanzada» para mostrar y editar la cadena de consulta.

- **Propiedad**: Selecciona la propiedad que se va a auditar. Este menú desplegable cargará todas las propiedades de todos los vocabularios de tu instalación. Cuando está abierto, la parte superior del menú funciona como un campo de búsqueda que te permite localizar una propiedad más rápidamente. 

- **Columna de auditoría**: Establece qué tipo de datos se van a auditar en el conjunto de recursos. Selecciona en el menú desplegable entre `value`, `uri` o `value-resource-id`. En general, los tipos de datos pueden utilizar estas columnas por diferentes motivos. Sin embargo, en concreto, el tipo de datos «literal» utiliza la columna `value` para almacenar el valor; el tipo de datos «uri» utiliza la columna «uri» para almacenar el URI y la columna «_value_» para almacenar la etiqueta del URI; y el tipo de datos «resource» utiliza la columna «value-resource-id» para almacenar el ID del recurso. Los módulos que añaden tipos de datos asignan datos a una o varias de estas tres columnas. 

- **Tipo de datos**: Selecciona en un menú desplegable los tipos de datos que deseas auditar. Esto incluye los tipos de datos estándar de Omeka S, así como cualquier tipo de datos adicional añadido por otros módulos, por ejemplo, los tipos de datos numéricos. 

#### Opciones avanzadas

Si deseas auditar los datos contenidos en una propiedad, pero almacenar los datos corregidos en una ubicación diferente dentro de los recursos, puedes utilizar las opciones «destino» para hacerlo.
 
- **Propiedad de destino**: Selecciona la propiedad en la que deseas que se almacenen las correcciones. No es necesario seleccionar un destino si coincide con la propiedad anterior. Este menú desplegable cargará todas las propiedades de todos los vocabularios de su instalación. Cuando está abierto, la parte superior del menú funciona como un campo de búsqueda que le permite localizar una propiedad más rápidamente. 

- **Columna de auditoría de destino**: Selecciona la columna en la que se almacenarán las correcciones. No es necesario seleccionar un destino si coincide con la columna de auditoría anterior. Las opciones son `value`, `uri` o `value_resource_id`. 

- **Tipo de datos de destino**: Selecciona el tipo de datos en el que se almacenarán las correcciones. No es necesario seleccionar un destino si coincide con el tipo de datos anterior. Este menú desplegable incluye los tipos de datos estándar de Omeka S, así como cualquier tipo de datos adicional añadido por otros módulos, por ejemplo, los tipos de datos numéricos. 

Una vez que haya introducido la información en todos los campos pertinentes, haga clic en el botón «Enviar» situado en la esquina superior derecha. 

Puede salir en cualquier momento haciendo clic en el botón «Cancelar». 

![La pantalla «Preparar auditoría» con «Elementos» establecido como tipo de recurso; una consulta de recursos para eventos relacionados con elementos; la propiedad establecida en «Esquema:ubicación»; la columna de auditoría establecida en «value_resource_id»;  y el tipo de datos establecido en «Recurso»](../modules/modulesfiles/datacleaning_prepareAudit.png)

### Datos de auditoría
Al hacer clic en «Enviar» en la página «Preparar auditoría», se le redirigirá a la página «Datos de auditoría». 

En la parte superior de la página, justo debajo del encabezado, aparecerá un mensaje que le indicará cuántas cadenas únicas está editando y para cuántos recursos. El número de recursos es un enlace a los recursos devueltos por la consulta de búsqueda que introdujo en la página anterior. 

Debajo de este mensaje hay una tabla que muestra los datos que se están auditando. Hay tres columnas: «Columna de auditoría», «Propiedad» y «Tipo de datos». Hay dos filas: «Desde» y «Hasta». Asegúrate de comprobar dos veces la información de esta tabla antes de continuar. 

![Mensaje y tabla de cadenas para una auditoría. Esta auditoría tiene 18 cadenas únicas para 66 recursos, y la información de «Desde» y «Hasta» es idéntica](../modules/modulesfiles/datacleaning_auditTable1.png) 

A continuación verás una fila de botones que te permiten realizar operaciones con todas las cadenas que estás auditando.

- **Copiar todo**: copia los datos de la columna «De» a la columna «A» para todas las cadenas únicas.
- **Borrar todo**: elimina todos los datos de la columna «A».
- **Validar todo**: comprueba todos los cambios propuestos para asegurarse de que son posibles dentro de los límites de la columna y el tipo de datos actuales; es decir, no se puede establecer un `value_resource_id` como una cadena de texto literal, ya que el tipo de datos requiere un número. La validación solo comprueba que la entrada sea estructuralmente posible, no que la modificación introducida exista; es decir, se podría cambiar un `value_resource_id` por un número que no se correspondiera con un ID real de Omeka S.
- **Eliminar todo**: Marca la casilla «Eliminar» para todas las cadenas únicas. Esto establecerá en nulo los datos de la propiedad que se está auditando. Se recomienda actuar con extrema precaución al aplicar esta opción.
- **Deshacer la eliminación de todo**: Desmarca la casilla «Eliminar» para todas las cadenas únicas.

A continuación, verás una tabla con todas las cadenas únicas de tu auditoría. Si el resultado de la auditoría contiene muchas cadenas únicas, puedes utilizar los filtros para centrarte en las cadenas que deseas editar. Además, las columnas con los datos actuales de la auditoría se pueden ordenar haciendo clic en el encabezado de la columna.

La tabla le proporciona el recuento del número de recursos por cadena, la cadena única tal y como existe actualmente (De:), un cuadro de entrada para editar las cadenas actuales (A:) y una casilla de selección de eliminación para establecer los datos en nulo. La celda de edición de cada fila también cuenta con botones que te permiten copiar, borrar y validar los cambios propuestos.

![Tabla de edición de auditoría con una cadena no válida en la primera fila de la columna «A:»; el botón de validación aparece en rojo, lo que indica una discrepancia en el tipo de datos; la segunda fila de la columna «A:» contiene datos enteros válidos y el botón de validación aparece en verde](../modules/modulesfiles/datacleaning_auditTableValidation.png)

Una vez que haya editado cuidadosamente el contenido de la columna _Para_, haga clic en el botón «Enviar» para ejecutar la actualización de sus datos. Dada la potencia del módulo, se le pedirá que confirme sus decisiones. El proceso de limpieza de datos se ejecutará en segundo plano y, aunque la tarea se puede revisar, no se puede deshacer.

## Ejemplo de flujo de trabajo
Este es un ejemplo de flujo de trabajo para un usuario que desea auditar los títulos de los elementos de un conjunto de elementos específico:

- En el menú de navegación de la izquierda, ve al módulo «Limpieza de datos».
- Haz clic en el botón «Preparar nueva auditoría» (arriba a la derecha).
- Selecciona los criterios (expande las flechas para obtener más información):
  - Tipo de recurso: «Elemento»
  - Consulta de recursos: item_set_id[]=1234
  - Propiedad: «Dublin Core: Título»
  - Columna de auditoría: «valor»
  - Tipo de datos: «Texto».
- Ignora la sección «Avanzado».
- Haz clic en «Enviar» (arriba a la derecha).
- Revisa la columna «De: valor» para detectar posibles correcciones o eliminaciones.
- Realiza las correcciones introduciendo el texto correcto en la columna «A: valor».
- Realice eliminaciones marcando la casilla «Eliminar».
- Haga clic en «Enviar» (arriba a la derecha).
- Haga clic para confirmar el envío.
- Actualice la página «Auditorías anteriores» hasta que la tarea aparezca como «Completada».
- Compruebe los elementos para ver si los valores se han corregido y eliminado.