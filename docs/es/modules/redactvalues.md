# Ocultar valores

El [módulo «Ocultar valores»](https://omeka.org/s/modules/RedactValues/){target=_blank} permite a los administradores ocultar determinados metadatos. 

Los visitantes del sitio (que no hayan iniciado sesión) nunca podrán ver los valores ocultos. 

Los usuarios que hayan iniciado sesión con permisos de Editor, Supervisor o Administrador global siempre podrán ver lo que se ha ocultado. El módulo permite al administrador de la instalación configurar la visibilidad para los usuarios con permisos de Autor o Investigador.

!!! nota
  El módulo no aplica la ocultación a los usuarios que tienen permiso para actualizar el recurso. Esto significa que los valores nunca se ocultarán para los administradores globales, supervisores y editores. También significa que los usuarios de niveles inferiores tendrán visibilidad completa sobre los elementos que les pertenecen.

Los administradores podrán elegir un tipo de recurso, crear una consulta para filtrar los recursos, seleccionar la propiedad de la que se va a ocultar el texto, seleccionar el patrón que se utilizará para la ocultación e introducir el texto de sustitución.

## Añadir una ocultación

Seleccione «Ocultar valores» en la lista de módulos del panel de navegación de la izquierda. En la página «Examinar censuraciones», haz clic en el botón «Añadir censuración» situado en la esquina superior derecha.

![Botón Añadir valores de censura.](../modules/modulesfiles/redactValues_add-redact.png)

Al añadir una censura, debes proporcionar:

1. Una **etiqueta** para tu censura
2. El **tipo de recurso** que desea censurar (elemento, conjunto de elementos o medio)
3. La **propiedad** de la que se va a censurar el texto
4. El **patrón** que se va a utilizar al censurar el texto.

![Formulario «Añadir valores de censura» que incluye etiqueta, tipo de recurso, propiedad y patrón.](../modules/modulesfiles/redactValues_add.png)

También puede añadir una consulta para filtrar los recursos de los que se va a ocultar texto. Puede añadir una consulta mediante el botón «Editar», que abrirá un panel a la derecha con opciones para acotar la búsqueda. Como alternativa, puede utilizar «Edición avanzada» para añadir su consulta directamente desde la página de resultados de búsqueda copiando todo lo que aparece en la barra de direcciones del navegador, desde el signo de interrogación hasta el final de la URL de búsqueda (a la derecha). 

En cualquiera de los dos casos, asegúrese de hacer clic en el botón «Aplicar» para añadir su consulta al formulario. Si no se introduce ninguna consulta, se incluirán en la ocultación todos los recursos del tipo especificado. 

![Bandeja de edición de consultas en el formulario «Añadir valores de ocultación».](../modules/modulesfiles/redactValues_query.png)

Hay un campo para incluir el texto de sustitución que aparecerá en lugar de los valores censurados. Si lo deja en blanco, se ocultará todo el campo censurado.

Cada censura tiene opciones de visualización individuales. Tiene la opción de otorgar permisos a determinados tipos de roles para ver las censuras. Tenga en cuenta que cualquier usuario con permiso para actualizar un recurso puede ver automáticamente su texto censurado. Puede autorizar a autores o investigadores marcando sus respectivas casillas. Normalmente, los valores se censurarán para los autores, excepto en los recursos de su propiedad, y para los investigadores, a menos que les conceda permisos en censuras individuales.

![Casillas de verificación de permisos de autor e investigador en el formulario «Añadir valores de censura».](../modules/modulesfiles/redactValues_roles.png)

Haga clic en «Enviar» en la esquina superior derecha para guardar los cambios.

## Gestionar censuras

Puede gestionar las censuras ya creadas desde la pantalla principal del módulo. Para editar una censura añadida anteriormente, haga clic en el icono «Editar» junto a la censura que desee modificar. 

![Botón «Editar» para censuras existentes.](../modules/modulesfiles/redactValues_edit.png)

Asegúrese de enviar el formulario de nuevo después de realizar cualquier cambio. 

También puede ordenar sus redacciones existentes por fecha o etiqueta en orden ascendente o descendente mediante la función «Ordenar» en la esquina superior derecha.

![Función de ordenar para la lista de redacciones existentes.](../modules/modulesfiles/redactValues_sort.png)

## Añadir patrones

Puede personalizar los patrones disponibles para las redacciones seleccionando «Patrones» en Redactar valores, dentro de la pestaña Módulos del panel de navegación de la izquierda. Para crear un nuevo patrón, seleccione el botón «Añadir patrón» situado en la esquina superior derecha. Se le pedirá que introduzca tanto una **Etiqueta** como un **Patrón**.

![Formulario «Añadir patrón» del módulo «Valores de censura», que incluye los campos «Etiqueta» y «Patrón». La etiqueta introducida es «Fecha» y el patrón se rellena con una expresión regular.](../modules/modulesfiles/redactValues_add-pattern.png)

Para el patrón, debe introducir la expresión regular que identifica la secuencia de caracteres que se censurarán. Debe encerrar el patrón entre [delimitadores](https://www.php.net/manual/en/regexp.reference.delimiters.php){target=_blank}. Puede utilizar [modificadores](https://www.php.net/manual/en/reference.pcre.pattern.modifiers.php){target=_blank}. 

Para obtener más información sobre expresiones regulares, consulte [Regular-Expressions.info](https://www.regular-expressions.info/){target=_blank} y [PCRE Patterns](https://www.php.net/manual/en/pcre.pattern.php). 

Para validar su patrón, pruebe [RegExr](https://regexr.com/){target=_blank}.

Una vez que haya añadido esta información, haga clic en «Enviar» en la esquina superior derecha. El patrón que ha añadido debería aparecer ahora en el menú desplegable Patrón al añadir una redacción.

![Ejemplo de un nuevo patrón añadido al campo Patrón en el formulario Añadir valores de censura. Una flecha azul señala la entrada recién añadida «Fecha» en el menú desplegable Patrón.](../modules/modulesfiles/redactValues_pattern-dropdown.png)