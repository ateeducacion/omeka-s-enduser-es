# Configuración

Los usuarios con permisos de administrador pueden modificar la configuración del panel de administración y los ajustes generales de todos los sitios a través de la sección **Configuración**, situada en la parte izquierda del panel de administración (con el icono de engranaje). 

La configuración global solo está disponible para los usuarios con permisos de administrador global.

La configuración se divide en cinco secciones: **General**, **Visualización**, **Edición**, **Búsqueda** y **Seguridad**.

## General

![Configuración general con los campos que se describen a continuación](adminfiles/settings_general.png)

**Correo electrónico del administrador**: Establece la dirección de correo electrónico del administrador de la instalación. 

!!! nota
  Algunas configuraciones de alojamiento pueden requerir que el nombre de dominio del correo electrónico del administrador coincida con el nombre de dominio de la instalación (si tu dominio es `yourinstall.org`, el correo electrónico del administrador debe ser `user@yourinstall.org`). Omeka S utiliza la utilidad `sendmail` del servidor para enviar correos electrónicos.

**Título de la instalación**: te permite cambiar el título general de la instalación de Omeka S. Es lo que aparece en la esquina superior izquierda del panel de administración.

**Zona horaria**: Establece la zona horaria predeterminada de la instalación, que se utilizará para los mensajes de registro de errores y para determinar las fechas de creación de los elementos, conjuntos de elementos y otros materiales de la instalación. Se trata de un menú desplegable. 

**Configuración regional**: Un menú desplegable que te permite seleccionar uno de los [idiomas disponibles](https://www.transifex.com/omeka/omeka-s/){target=_blank} para el núcleo de Omeka S, con el fin de cambiar el idioma en el que se muestra el panel de administración de tu instalación.

**Habilitar notificaciones de versión**: Marca esta casilla para habilitar los banners de aviso sobre nuevas versiones de Omeka S, temas y módulos. Si no está marcada, ningún usuario (independientemente de su rol) verá las advertencias de actualización, ni siquiera el administrador global. Si está marcada, todos los usuarios a los que les corresponda podrán verlas (es decir, los usuarios con rol de «Supervisor» que puedan ver la página «Módulos», los «Administradores del sitio» que puedan ver las páginas de «Temas» y todos los usuarios que accedan a la página de inicio de `/admin`).

**Desactivar JSON-LD @reverse**: Desactiva las [propiedades inversas de JSON-LD](https://www.w3.org/TR/json-ld11/#reverse-properties){target=_blank} en la salida de la API para los recursos. 

**Favicon**: Elige entre tus recursos o sube un archivo para que aparezca en el pequeño icono de la ventana o pestaña del navegador. Un [favicon](https://www.w3schools.com/html/html_favicon.asp){target=_blank} debe ser una imagen pequeña, de unos 32x32 píxeles, subida específicamente para este fin. Los favicons se pueden [configurar a nivel de instalación](../sites/site_settings.md#general-settings) así como en cada sitio individual.

## Visualización

**Resultados por página**: Cambia el número de resultados (elementos, conjuntos de elementos, archivos multimedia) que se muestran por página al navegar tanto en la parte pública como en la de administración de la instalación.

**Información de la etiqueta de la propiedad**: Determina qué se muestra junto a cada propiedad cuando los usuarios editan elementos y conjuntos de elementos. 

- Por defecto, está configurado en «ninguno», lo que significa que solo se muestra la etiqueta de la propiedad.
- Si se selecciona **Mostrar vocabulario**, la indicación entre paréntesis junto al nombre de la propiedad muestra el vocabulario utilizado (por ejemplo, Dublin Core) 
- Si se selecciona **Mostrar término**, la indicación entre paréntesis junto al nombre de la propiedad muestra el vocabulario:término (por ejemplo, `dc:title`). 

**Sitio predeterminado**: Este menú desplegable te permite controlar a qué página llegan los usuarios cuando acceden a la URL base de tu instalación. Puedes mostrar una lista de todos los sitios de la instalación (opción predeterminada) o seleccionar un sitio específico del menú desplegable, al que se redirigirá a los usuarios.

**Desactivar la incrustación de JSON-LD**: Por defecto, Omeka incrusta JSON-LD en las páginas de exploración y visualización de recursos con el fin de facilitar la detección de metadatos legibles por máquina. Marca esta casilla para desactivar la incrustación.

![Configuración de visualización con los campos tal y como se describen](adminfiles/settings_display.png)

## Edición

**Establecer la visibilidad predeterminada de los elementos en «privada»**: Cuando esta casilla está marcada, todos los nuevos elementos creados por cualquier usuario tendrán su visibilidad establecida en «privada». Si esta casilla no está marcada, todos los nuevos elementos serán públicos por defecto, a menos que se especifique lo contrario en el momento de su creación.

**Establecer la visibilidad predeterminada de los conjuntos de elementos como privada**: cuando esta casilla está marcada, todos los nuevos conjuntos de elementos creados por todos los usuarios tendrán la visibilidad establecida como privada.

**Establecer la visibilidad predeterminada de los sitios como privada**: cuando esta casilla está marcada, todos los nuevos sitios creados por todos los usuarios tendrán la visibilidad establecida como privada.

**Establecer la visibilidad predeterminada de las páginas del sitio en privada**: Cuando esta casilla está marcada, todas las nuevas páginas del sitio creadas por todos los usuarios tendrán su visibilidad establecida en privada.

**Idiomas sugeridos para los valores**: Aquí puedes enumerar idiomas para ofrecer un cómodo menú desplegable de selección de idiomas a la hora de rellenar los metadatos descriptivos de los recursos en toda la instalación. Proporcione etiquetas de idioma de dos o cuatro letras [ISO 639-1](https://en.wikipedia.org/wiki/List_of_ISO_639-1_codes){target+_blank} para garantizar la máxima compatibilidad. Los usuarios podrán seguir introduciendo sus propios valores al editar los recursos. 

**Propiedad de texto alternativo de los medios**: Selecciona un campo (por ejemplo, `dc:title` o `dc:description`) de la descripción del medio para utilizarlo como texto alternativo si no se ha establecido explícitamente ningún texto alternativo. El [texto alternativo](https://webaim.org/techniques/alttext/){target=_blank} se utiliza en lugar de las imágenes (incluidas las miniaturas en las páginas de navegación y de resultados de búsqueda) cuando un usuario utiliza un lector de pantalla, y es un elemento importante para cumplir con los requisitos de accesibilidad.

**Tamaño del bloque por lotes**: Al editar por lotes o procesar cambios, Omeka procesará un «bloque» del total de recursos cada vez. Es posible que desees aumentar o reducir este valor en función de la capacidad de tu servidor. 

![Configuración de edición y búsqueda con los campos tal y como se describen](adminfiles/settings_editing.png)

## Búsqueda

**Búsqueda de texto completo en el índice**: Marca esta casilla y haz clic en «Guardar» para generar un índice de los recursos y sitios de tu instalación. Solo deberías necesitar ejecutar este proceso si tienes problemas con la búsqueda.

## Seguridad

![Configuración de seguridad con los campos tal y como se describen a continuación](adminfiles/settings_security.png)

**Usar HTMLPurifier**: una casilla de selección. Si se marca, el servicio [HTMLPurifier](http://htmlpurifier.org/){target=_blank} depurará cualquier código HTML introducido por el usuario. 

**Desactivar la validación de archivos**: una casilla de selección, desmarcada por defecto. Cuando está desmarcada, las subidas de archivos se limitan a los dos campos siguientes. Cuando esta casilla está marcada, se puede subir cualquier tipo de archivo multimedia o tipo MIME.

**Tipos de archivos multimedia permitidos**: la lista predeterminada contiene los tipos de archivos multimedia más comunes. Solo se podrán subir a la instalación los archivos con tipos de archivos multimedia incluidos en esta lista.
  - Separa las entradas de la lista con una coma.
  - Para volver a los valores predeterminados, haz clic en el botón «Restaurar tipos de archivos multimedia predeterminados».

**Extensiones de archivo permitidas**: La lista predeterminada contiene las extensiones de archivo más comunes. Solo se pueden subir a la instalación los archivos con extensiones incluidas en esta lista.
  - Separa las entradas de la lista con una coma.
  - Para volver a los valores predeterminados, haz clic en el botón «Restaurar extensiones predeterminadas».

Los dos últimos campos se refieren a la configuración de [Google reCAPTCHA](https://www.google.com/recaptcha/intro/index.html){target=_blank} para tu sitio web. Necesitarás tanto una clave de sitio como una clave secreta. Introdúcelas en los campos correspondientes tras registrarte en reCAPTCHA:

**La clave de sitio de reCAPTCHA** permite mostrar el widget en los sitios de tu instalación.

**La clave secreta de reCAPTCHA** permite la comunicación entre tu instalación y el servidor de reCAPTCHA. 
