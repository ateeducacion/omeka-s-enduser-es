# Exploración de metadatos

El [módulo de exploración de metadatos](https://omeka.org/s/modules/MetadataBrowse){target=_blank} permite explorar todos los recursos que comparten un valor para una propiedad de metadatos concreta.

Para ello, convierte las propiedades seleccionadas en un enlace o añade un enlace debajo de las propiedades con el texto «Ver todos los elementos con este valor». Estos enlaces solo aparecen en las páginas de visualización de elementos. Al hacer clic en el enlace, el módulo muestra los resultados de esa búsqueda (el valor de la propiedad es igual a la entrada). Es similar al complemento de Omeka Classic [Búsqueda por metadatos](http://omeka.org/add-ons/plugins/search-by-metadata/){target=_blank}.

![El elemento «Sentido y sensibilidad». La propiedad de fecha se muestra como un enlace y se indica con una flecha azul.](../modules/modulesfiles/mdbr-directlinkYes.png)

El módulo añade un menú de configuración específico del sitio que permite hacer que las propiedades sean navegables en cada sitio. También permite que propiedades específicas sean navegables en la interfaz de administración. La elección de propiedades enlazadas directamente, o la visualización de un enlace independiente, es una configuración universal y no se puede cambiar de un sitio a otro.

Estas configuraciones solo están disponibles para usuarios con el nivel de Administrador global, Supervisor o Editor. Los administradores de sitio no pueden cambiar las configuraciones específicas del sitio.

## Navegación por metadatos en los sitios
Una vez activado el módulo, aparecerá en el menú contextual de [cada uno de los sitios de su instalación](../sites/index.md). Para configurar la Navegación por metadatos en un sitio, haga clic en la pestaña Navegación por metadatos del menú contextual del sitio.

![Una flecha roja señala la pestaña «Navegación por metadatos»](../modules/modulesfiles/mdbr_sites1.png)

En la página que se muestra, la sección principal muestra todas las propiedades habilitadas actualmente. Seleccione las propiedades haciendo clic en ellas en la barra lateral para habilitar la navegación por metadatos.

![Página de configuración de Metadata Browse del sitio. La barra lateral muestra las propiedades disponibles y la zona principal muestra las propiedades que ya se han configurado: Creador, Fecha, Editor, Es versión de y Título.](../modules/modulesfiles/mdbr_sites2.png)

Elimine cualquier propiedad seleccionada haciendo clic en el icono de la papelera. Si hace clic accidentalmente en el botón de eliminar, simplemente haga clic en el botón de deshacer que lo sustituye para conservar esa propiedad.

![Una propiedad marcada para ser eliminada, resaltada en rojo, mostrando el botón de deshacer.](../modules/modulesfiles/mdbr_sites3.png)

Recuerde hacer clic en el botón «Guardar» para guardar los cambios.

### Vista pública
Una vez que haya seleccionado las propiedades y guardado los cambios, los visitantes de su sitio podrán utilizar las propiedades seleccionadas para explorar todos los elementos del sitio con valores coincidentes.

La vista del elemento se mostrará con la propiedad como un enlace o con un enlace que diga «Ver todos los elementos con este valor», dependiendo de si la [opción Enlaces directos está marcada](#direct-links) en la configuración global del módulo.

En el ejemplo siguiente, la navegación por metadatos está disponible para Título, Fecha de publicación y Editor, y la configuración «Enlaces directos» no está marcada.

![Un elemento con flechas que apuntan a los enlaces para «ver todos los elementos con este valor»](../modules/modulesfiles/mdbr_public1.png)

Al hacer clic en «Ver todos los elementos con este valor» en la sección de creador, el visitante accede a una página con resultados de búsqueda de coincidencia exacta. Por ejemplo, este es el resultado al hacer clic en «Ver todos los elementos con este valor» para la propiedad Editor en la imagen anterior:

![Una pantalla de resultados de búsqueda de elementos que muestra que la búsqueda es «El editor es exactamente: Thomas Egerton» con dos resultados visibles](../modules/modulesfiles/mdbr_public2.png)

## Configuración de administración
La configuración global del sitio y la configuración del lado del administrador se pueden modificar desde la página de configuración del módulo, en la pestaña «Módulos» del menú de navegación de la izquierda. Haga clic en el botón «Configurar», con el icono de la llave inglesa, situado a la derecha de la etiqueta «Metadata Browse».

El módulo tiene dos opciones de configuración con casillas de verificación: «Configuración global» y «Enlaces directos».

![Ajustes de configuración de Metadata Browse, con las dos opciones descritas a continuación. La casilla «Usar configuración global en el lado de administración» está marcada; «Enlaces directos» no está marcada. Se añaden algunas propiedades al área de abajo: Fecha, Derechos, Titular de los derechos.](../modules/modulesfiles/mdbr_config2.png)

### Configuración global
La casilla «Usar configuración global en el lado del administrador» determina cómo se definen las propiedades disponibles para la navegación por metadatos en el **lado administrativo** (en las vistas de elementos y conjuntos de elementos): agregando las propiedades seleccionadas en todos los sitios de la instalación (desmarcada), o limitándolas únicamente a las propiedades elegidas en esta página (marcada).

Esta casilla de verificación modifica el lado administrativo para todos los usuarios. Por ejemplo, un sitio sobre artistas podría tener habilitada la navegación por metadatos para «Creador» (Dublin Core), mientras que un sitio que recopila ponencias de conferencias podría habilitar la navegación por metadatos para «presentado en» (Ontología Bibliográfica). Si la casilla está desmarcada, tanto «Creador» como «presentado en» tendrían la navegación por metadatos habilitada en las vistas de administración de todos los elementos y conjuntos de elementos de toda la instalación.

Marcar la casilla permite limitar el número de propiedades que tienen la navegación por metadatos habilitada en el panel de administración. Si, por ejemplo, el sitio sobre artistas utilizara la navegación por metadatos en todas las propiedades posibles, esos enlaces de navegación por metadatos serían visibles en el sitio público, pero no aparecerían en el lado de administración. En su lugar, los administradores globales podrían decidir qué propiedades habilitar para la navegación en el lado de administración.

### Enlaces directos
La casilla «Enlaces directos» establece cómo se muestran los enlaces de navegación por metadatos tanto en el panel de administración como en todos los sitios.

Si esta casilla no está marcada, las propiedades seleccionadas para la navegación por metadatos se mostrarán con un enlace de texto debajo que dice «Ver todos los elementos con este valor». Al hacer clic en el texto del enlace se abre la página de elementos con metadatos coincidentes.

En este ejemplo, la navegación por metadatos está activa para la propiedad «Fecha de publicación»:

![El elemento «Sentido y sensibilidad». La propiedad de fecha tiene el texto descrito y se indica con una flecha azul.](../modules/modulesfiles/mdbr-directlinkNo.png)

Si esta casilla está marcada, los propios valores de las propiedades se convierten en el enlace, de forma similar a cómo se muestra una propiedad rellenada por un recurso. En este caso, al hacer clic en el valor de la propiedad se abre la página de elementos con metadatos coincidentes.

![El elemento «Sentido y sensibilidad». La propiedad de fecha se muestra como un enlace y se indica con una flecha azul.](../modules/modulesfiles/mdbr-directlinkYes.png)

### Elegir propiedades
La selección de propiedades para la exploración de metadatos en la configuración del módulo solo funcionará si la [casilla «Usar configuración global»](#global-configuration) está marcada.

Seleccione las propiedades en la barra lateral haciendo clic en la propiedad deseada. Se cargará bajo el indicador «Elegir propiedades».

![Configuración de Metadata Browse, algunas propiedades seleccionadas](../modules/modulesfiles/mdbr_config4.png)

Para eliminar una propiedad, simplemente haz clic en el icono de la papelera situado a la derecha de la etiqueta de la propiedad.

## Navegación en el panel de administración

Una vez que hayas seleccionado las propiedades para la Navegación por metadatos, ya sea en la configuración del módulo o en al menos un sitio, podrás buscar coincidencias exactas con las propiedades de los elementos y conjuntos de elementos en el panel de administración.

Al visualizar los metadatos de cualquier elemento (no al editarlos), podrá explorar esas propiedades como coincidencias exactas con cualquier otro elemento de la instalación que tenga ese valor en esa propiedad. Si la [casilla de verificación de enlaces directos](#direct-links) está activa, estas propiedades se mostrarán como enlaces; si no, se mostrarán con el texto «Ver todos los elementos con este valor» justo debajo del valor de la propiedad.

![Vista del panel de administración de un elemento con flechas rojas que señalan los enlaces de exploración de metadatos](../modules/modulesfiles/mdbr_admin1.png)
