# Citas de Zotero

El [módulo de citas de Zotero](https://omeka.org/s/modules/ZoteroCitations/){target=_blank} permite a los usuarios acceder a sus bibliotecas de Zotero para añadir citas mediante el editor de texto enriquecido integrado.

Una vez activado, los usuarios configuran su acceso a Zotero desde sus ajustes de usuario. Se podrá acceder a sus bibliotecas de Zotero a través de bloques HTML y de otro tipo en las [páginas del sitio](../sites/site_pages.md). 

## Ajustes de Zotero

El módulo de citas de Zotero añade varias opciones de configuración a la página de configuración del usuario. Estas son las configuraciones predeterminadas del módulo.

- Estilo de cita: selecciona uno de los formatos de cita disponibles en el menú desplegable.
- Configuración regional de la bibliografía: selecciona una configuración regional de idioma para mostrar la cita y la bibliografía.
- Ajustar enlaces de la bibliografía: marca esta opción si deseas que las URL de la bibliografía se ajusten al resto del texto de la entrada.
- Tipo de biblioteca API: selecciona si deseas acceder a una biblioteca de usuario o a una biblioteca de grupo.
- ID de la biblioteca de la API: Introduce el identificador numérico de la biblioteca a la que deseas acceder.
- Clave de la API: Si deseas acceder a una biblioteca que no es pública, deberás generar una clave de la API desde la cuenta de Zotero propietaria de la biblioteca. Introduce esa clave aquí.
- Ordenar búsqueda por: Selecciona un campo de ordenación para los resultados de búsqueda al acceder a tu biblioteca: Título, Autor o Fecha de modificación.

![Opciones de citas de Zotero en la sección de configuración de usuario de la vista «Editar usuario»; el estilo de citas está configurado en «Chicago Manual of Style», la configuración de la bibliografía está establecida en inglés, la opción «Ajustar enlaces en la bibliografía» está marcada, el tipo de biblioteca API está establecido en «Usuario», el ID de la biblioteca API está establecido en 15, la clave API está en blanco y la opción «Ordenar búsqueda por» está establecida en «Título»](../modules/modulesfiles/zoterocitation_usersettings.png)

## Acceso a Zotero para citas y bibliografías

Dentro de las páginas del sitio, se pueden añadir citas y bibliografías a cualquier elemento que cuente con un editor de texto enriquecido, como el [bloque HTML](../sites/site_pages.md#html) o en los pies de foto de los elementos.

Cuando el módulo está activo, añade un icono «Z» rojo al editor de texto enriquecido. 

![Imagen de los comandos del editor WYSIWYG con el icono «Z» rojo](../modules/modulesfiles/zoterocitation_redZ.png)

Coloca el cursor en el lugar deseado de la ventana de edición y haz clic en el icono para abrir el cuadro de diálogo de selección de Zotero, que cuenta con tres pestañas: 

- **Añadir cita**: Busca el elemento concreto utilizando el campo de texto. Haz clic en «Buscar en la biblioteca». Selecciona una entrada de los resultados. Solo se puede añadir una cita cada vez. Haz clic en «Aceptar» para generar la cita en el editor.
- **Añadir bibliografía**: Si has añadido varias citas en el editor, puedes colocar el cursor en el lugar deseado para generar una bibliografía. Marca la casilla de autorización y haz clic en el botón **Aceptar** para generar la bibliografía en el editor.
- **Configuración**: Aunque hayas introducido la configuración predeterminada en tu página de usuario, es posible que desees modificar esas opciones mientras creas contenido. Aquí puedes cambiar el estilo de cita, la configuración regional de la bibliografía, el tipo de biblioteca, el ID de la biblioteca, tu clave API (si utilizas una) y el criterio de ordenación. Al ajustar la configuración, solo se modifican los ajustes para la generación actual de citas o bibliografía. Una vez que hayas ajustado la configuración, vuelve a las pestañas «Añadir cita» o «Añadir bibliografía» para aplicar los ajustes a las acciones que desees.

![Cuadro de diálogo de Zotero Citation con la pestaña «Añadir cita» activa](../modules/modulesfiles/zoterocitation_addcitation.png)
