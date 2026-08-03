# Ocultar valores

El [módulo «Ocultar valores»](https://omeka.org/s/modules/RedactValues/){target=_blank} permite a los administradores ocultar determinados metadatos. 

Los visitantes del sitio (que no hayan iniciado sesión) nunca podrán ver los valores que estén ocultos. 

Los usuarios que hayan iniciado sesión y tengan los niveles de Editor, Supervisor o Administrador global siempre podrán ver lo que se haya ocultado. El módulo permite al administrador de la instalación configurar la visibilidad para los usuarios con los niveles de Autor o Investigador.

!!! Nota
  El módulo no aplica la ocultación a los usuarios que tienen permiso para actualizar el recurso. Esto significa que los valores nunca se ocultarán para los administradores globales, supervisores y editores. También significa que los usuarios de niveles inferiores tendrán visibilidad completa sobre los elementos de los que son propietarios.

Los administradores podrán elegir un tipo de recurso, crear una consulta para filtrar los recursos, seleccionar la propiedad de la que se va a ocultar texto, seleccionar el patrón que se utilizará para la ocultación e introducir el texto de sustitución.

## Añadir una ocultación

Selecciona «Ocultar valores» en la lista de módulos del panel de navegación de la izquierda. En la página «Examinar censuras», haz clic en el botón «Añadir censura» situado en la esquina superior derecha.

![Botón «Añadir valores de censura».](../modules/modulesfiles/redactValues_add-redact.png)

Al añadir una ocultación, debes proporcionar:

1. Una **etiqueta** para tu ocultación
2. El **tipo de recurso** que deseas ocultar (elemento, conjunto de elementos o medio)
3. La **propiedad** de la que se va a ocultar el texto
4. El **patrón** que se va a utilizar al ocultar el texto.

![Formulario «Añadir valores de ocultación» que incluye etiqueta, tipo de recurso, propiedad y patrón.](../modules/modulesfiles/redactValues_add.png)

También puedes añadir una consulta para filtrar los recursos de los que se va a ocultar texto. Puedes añadir una consulta mediante el botón «Editar», que abrirá un panel a la derecha con opciones para acotar la búsqueda. Como alternativa, puede utilizar «Edición avanzada» para añadir su consulta directamente desde la página de resultados de búsqueda copiando todo lo que aparece en la barra de direcciones de su navegador, desde el signo de interrogación hasta el final de la URL de búsqueda (a la derecha). 

En cualquiera de los dos casos, asegúrate de hacer clic en el botón «Aplicar» para añadir tu consulta al formulario. Si no se introduce ninguna consulta, se incluirán en la ocultación todos los recursos del tipo especificado. 

![Bandeja de edición de consultas en el formulario «Añadir valores de censura».](../modules/modulesfiles/redactValues_query.png)

Hay un campo para incluir el texto de sustitución que aparecerá en lugar de los valores censurados. Si lo dejas en blanco, se ocultará todo el campo censurado.

Cada ocultación tiene opciones de visualización individuales. Tienes la opción de conceder permisos a determinados tipos de roles para visualizar las ocultaciones. Ten en cuenta que cualquier usuario con permiso para actualizar un recurso puede ver automáticamente su texto ocultado. Puedes autorizar a los autores o investigadores marcando sus respectivas casillas. Normalmente, los valores se ocultarán a los autores, salvo en el caso de los recursos de su propiedad, y a los investigadores, a menos que les concedas permisos en cada ocultación concreta.

![Casillas de verificación de permisos para autores e investigadores en el formulario «Añadir valores ocultos».](../modules/modulesfiles/redactValues_roles.png)

Haz clic en «Enviar» en la esquina superior derecha para guardar los cambios.

## Gestionar censuras

Puedes gestionar las censuras que ya hayas creado desde la pantalla principal del módulo. Para editar una censura añadida anteriormente, haz clic en el icono «Editar» situado junto a la censura que desees modificar. 

![Botón «Editar» para las censuras existentes.](../modules/modulesfiles/redactValues_edit.png)

Asegúrate de volver a enviar el formulario después de haber realizado cualquier cambio. 

También puedes ordenar tus censuras existentes por fecha o etiqueta, en orden ascendente o descendente, mediante la función «Ordenar» situada en la esquina superior derecha.

![Función de ordenar para la lista de censuras existentes.](../modules/modulesfiles/redactValues_sort.png)

## Añadir patrones

Puedes personalizar los patrones disponibles para las censuras seleccionando «Patrones» en «Redact Values», dentro de la pestaña «Módulos» del menú de navegación de la izquierda. Para crear un nuevo patrón, selecciona el botón «Añadir patrón» situado en la esquina superior derecha. Se te pedirá que introduzcas tanto una **Etiqueta** como un **Patrón**.

![Formulario «Añadir patrón» del módulo «Valores de censura», que incluye los campos «Etiqueta» y «Patrón». La etiqueta introducida es «Fecha» y el patrón se ha rellenado con una expresión regular.](../modules/modulesfiles/redactValues_add-pattern.png)

Para el patrón, debe introducir la expresión regular que identifique la secuencia de caracteres que se ocultarán. Debe encerrar el patrón entre [delimitadores](https://www.php.net/manual/en/regexp.reference.delimiters.php){target=_blank}. Puede utilizar [modificadores](https://www.php.net/manual/en/reference.pcre.pattern.modifiers.php){target=_blank}. 

Para obtener más información sobre expresiones regulares, consulta [Regular-Expressions.info](https://www.regular-expressions.info/){target=_blank} y [PCRE Patterns](https://www.php.net/manual/en/pcre.pattern.php). 

Para validar su patrón, pruebe [RegExr](https://regexr.com/){target=_blank}.

Una vez que haya añadido esta información, haga clic en «Enviar» en la esquina superior derecha. El patrón que ha añadido debería aparecer ahora en el menú desplegable «Patrón» al añadir una ocultación.

![Ejemplo de un nuevo patrón añadido al campo «Patrón» en el formulario «Añadir valores de censura». Una flecha azul señala la entrada «Fecha», recién añadida, en el menú desplegable «Patrón».](../modules/modulesfiles/redactValues_pattern-dropdown.png)