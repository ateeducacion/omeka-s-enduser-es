# Configuración

Los usuarios administradores pueden modificar la configuración del panel de administración y los ajustes generales de todos los sitios a través de la sección **Configuración**, situada en la parte izquierda del panel de administración (con el icono de un engranaje). 

Los ajustes globales solo están disponibles para los usuarios con privilegios de administrador global.

La configuración se divide en cinco secciones: **General**, **Visualización**, **Edición**, **Búsqueda** y **Seguridad**.

## General

![Configuración general con los campos que se describen a continuación](adminfiles/settings_general.png)

**Correo electrónico del administrador**: Establece la dirección de correo electrónico del administrador de la instalación. 

!!! nota
  Algunas configuraciones de alojamiento pueden requerir que el nombre de dominio del correo electrónico del administrador coincida con el nombre de dominio de la instalación (si su dominio es `yourinstall.org`, el correo electrónico del administrador debe ser `user@yourinstall.org`). Omeka S utiliza la utilidad `sendmail` subyacente del servidor para enviar correo electrónico.

**Título de la instalación**: te permite cambiar el título general de la instalación de Omeka S. Es lo que aparece en la esquina superior izquierda del panel de administración.

**Zona horaria**: establece la zona horaria predeterminada de la instalación, que se utilizará para los mensajes de registro de errores y para determinar las fechas de creación de los elementos, conjuntos de elementos y otros materiales de la instalación. Se trata de un menú desplegable. 

**Configuración regional**: Un menú desplegable que le permite seleccionar entre los [idiomas disponibles](https://www.transifex.com/omeka/omeka-s/){target=_blank} para el núcleo de Omeka S, con el fin de cambiar el idioma en el que se muestra el panel de administración de su instalación.

**Habilitar notificaciones de versión**: Marque esta casilla para habilitar los banners de advertencia sobre nuevas versiones de Omeka S, temas y módulos. Si no está marcada, ningún usuario (de ningún rol) verá las advertencias de actualización, ni siquiera el Administrador global. Si está marcada, todos los usuarios pertinentes podrán verlas (es decir, los usuarios Supervisores que pueden ver la página de Módulos, los Administradores del sitio que pueden ver las páginas de Temas y todos los usuarios de la página de inicio `/admin`).

**Desactivar JSON-LD @reverse**: Desactiva las [propiedades inversas de JSON-LD](https://www.w3.org/TR/json-ld11/#reverse-properties){target=_blank} en la salida de la API para los recursos. 

**Favicon**: Elige entre tus recursos o sube un archivo para que aparezca en el pequeño espacio del icono de la ventana o pestaña del navegador. Un [favicon](https://www.w3schools.com/html/html_favicon.asp){target=_blank} debe ser una imagen pequeña de unos 32x32 píxeles de tamaño subida específicamente para este fin. Los favicons se pueden [configurar a nivel de instalación](../sites/site_settings.md#general-settings) así como en cada sitio individual.

## Visualización

**Resultados por página**: Cambia el número de resultados (elementos, conjuntos de elementos, medios) que se muestran por página al navegar tanto en la parte pública como en la de administración de la instalación.

**Información de la etiqueta de la propiedad**: Determina qué se muestra junto a cada propiedad cuando los usuarios editan elementos y conjuntos de elementos. 

- Por defecto, está configurado en «ninguno», lo que significa que solo se muestra la etiqueta de la propiedad.
- Si se selecciona **Mostrar vocabulario**, la indicación entre paréntesis junto al nombre de la propiedad muestra el vocabulario utilizado (por ejemplo, Dublin Core) 
- Si se selecciona **Mostrar término**, la indicación entre paréntesis junto al nombre de la propiedad muestra el vocabulario:término (por ejemplo, `dc:title`). 

**Sitio predeterminado**: Este menú desplegable le permite controlar a qué página llegan los usuarios cuando acceden a la URL base de su instalación. Puede mostrar una lista de todos los sitios de la instalación (opción predeterminada) o seleccionar un sitio específico del menú desplegable, al que se redirigirá a los usuarios.

**Desactivar la incrustación de JSON-LD**: Por defecto, Omeka incrusta JSON-LD en las páginas de exploración y visualización de recursos con el fin de permitir el descubrimiento de metadatos legibles por máquina. Marque esta casilla para desactivar la incrustación.

![Configuración de visualización con los campos tal y como se describen](adminfiles/settings_display.png)

## Edición

**Establecer la visibilidad predeterminada de los elementos en privada**: Cuando esta casilla está marcada, todos los nuevos elementos creados por todos los usuarios tendrán su visibilidad establecida en privada. Si esta casilla no está marcada, todos los nuevos elementos son públicos por defecto, a menos que se establezca lo contrario en el momento de su creación.

**Establecer la visibilidad predeterminada de los conjuntos de elementos en privada**: Cuando esta casilla está marcada, todos los nuevos conjuntos de elementos creados por todos los usuarios tendrán su visibilidad establecida en privada.

**Establecer la visibilidad predeterminada del sitio en privada**: Cuando esta casilla está marcada, todos los nuevos sitios creados por todos los usuarios tendrán su visibilidad establecida en privada.

**Establecer la visibilidad predeterminada de las páginas del sitio en privada**: Cuando esta casilla está marcada, todas las nuevas páginas del sitio creadas por todos los usuarios tendrán su visibilidad establecida en privada.

**Idiomas sugeridos para los valores**: Aquí puede enumerar idiomas para proporcionar un cómodo menú desplegable de selección de idiomas al rellenar los metadatos descriptivos de los recursos en toda la instalación. Proporcione etiquetas de idioma de dos o cuatro letras [ISO 639-1](https://en.wikipedia.org/wiki/List_of_ISO_639-1_codes){target+_blank} para una compatibilidad máxima. Los usuarios podrán seguir introduciendo sus propios valores al editar los recursos. 

**Propiedad de texto alternativo de los medios**: Seleccione un campo (por ejemplo, `dc:title` o `dc:description`) de la descripción del medio para utilizarlo como texto alternativo si no se ha establecido explícitamente ningún texto alternativo. El [texto alternativo](https://webaim.org/techniques/alttext/){target=_blank} se utiliza en lugar de las imágenes (incluidas las miniaturas en las páginas de navegación y de resultados de búsqueda) cuando un usuario utiliza un lector de pantalla, y es una parte importante para cumplir con las expectativas de accesibilidad.

**Tamaño del bloque por lotes**: Al editar por lotes o procesar cambios, Omeka procesará un «bloque» del total de recursos cada vez. Es posible que desee aumentar o reducir este valor en función de la capacidad de su servidor. 

![Configuración de edición y búsqueda con los campos descritos](adminfiles/settings_editing.png)

## Búsqueda

**Búsqueda de texto completo en el índice**: Marque esta casilla y haga clic en «Guardar» para ejecutar un índice de los recursos y sitios de su instalación. Solo debería ejecutar este proceso si tiene problemas con la búsqueda.

## Seguridad

![Configuración de seguridad con los campos descritos a continuación](adminfiles/settings_security.png)

**Usar HTMLPurifier**: una casilla de verificación. Si está marcada, el servicio [HTMLPurifier](http://htmlpurifier.org/){target=_blank} limpiará cualquier código HTML introducido por el usuario. 

**Desactivar validación de archivos**: una casilla de verificación, desmarcada por defecto. Cuando está desmarcada, las subidas de archivos están limitadas por los dos campos siguientes. Cuando esta casilla está marcada, se puede subir cualquier tipo de medio o tipo MIME.

**Tipos de medios permitidos**: La lista predeterminada contiene los tipos de medios más comunes. Solo se pueden subir a la instalación archivos con tipos de medios incluidos en esta lista.
  - Separe las adiciones a la lista con una coma.
  - Para volver a los valores predeterminados, haga clic en el botón «Restaurar tipos de medios predeterminados».

**Extensiones de archivo permitidas**: La lista predeterminada contiene extensiones de archivo comunes. Solo se pueden cargar en la instalación archivos con extensiones incluidas en esta lista.
  - Separe las adiciones a la lista con una coma.
  - Para volver a los valores predeterminados, haga clic en el botón «Restaurar extensiones predeterminadas».

Los dos últimos campos se refieren a la configuración de [Google reCAPTCHA](https://www.google.com/recaptcha/intro/index.html){target=_blank} para su sitio. Necesitará tanto una clave de sitio como una clave secreta. Introdúzcalas en los campos correspondientes después de registrarse en reCAPTCHA:

**La clave de sitio de reCAPTCHA** permite mostrar el widget en los sitios de su instalación.

**La clave secreta de reCAPTCHA** permite la comunicación entre su instalación y el servidor de reCAPTCHA. 
