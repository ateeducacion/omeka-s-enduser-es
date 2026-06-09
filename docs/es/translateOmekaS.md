# Traducir Omeka S

Necesitamos la ayuda de la comunidad para traducir el texto en inglés de Omeka S a nuevos idiomas, de modo que los usuarios puedan disponer de una amplia variedad de opciones. No es necesario saber programar para ayudar a traducir Omeka S; solo tienes que dominar el inglés y otro idioma.

## Primeros pasos

### Regístrate en Transifex.com
Omeka S utiliza [Transifex.com](https://www.transifex.com){target=_blank} para gestionar las traducciones. Para empezar a ayudar a traducir Omeka a otros idiomas, primero tendrás que [registrarte para crear una cuenta](https://www.transifex.com/signup/){target=_blank}. Transifex.net ofrece varios planes, pero como Omeka es un proyecto de código abierto, puedes utilizar el plan gratuito.

### Únete a un equipo de traducción o crea uno
Una vez que te hayas registrado, visita la [página del proyecto Omeka S](https://explore.transifex.com/omeka/omeka-s/){target=_blank} y haz clic en el botón «unirse a este proyecto».

Aquí puedes elegir entre todos los idiomas en los que ya se está trabajando. Si quieres empezar a trabajar en la traducción a un nuevo idioma que no aparece en la lista, primero debes solicitar ese idioma. Haz clic en «Cancelar», desplázate hasta la parte inferior de la página, haz clic en el enlace «Solicitar idioma» y selecciona el idioma en el que deseas trabajar.

Por otro lado, si alguien ya ha creado un equipo para el idioma en el que quieres trabajar, haz clic en el nombre del idioma y, en la siguiente pantalla, haz clic en el botón «Unirse a este equipo». Dependerá del coordinador aprobar tu solicitud para ser miembro del equipo.

Una vez que el coordinador te haya aceptado en el equipo, puedes ir al panel de control de Omeka S y hacer clic en el botón «Traducir» para empezar a traducir.

Si quieres comprobar tu traducción o cualquier otra cosa que necesites para crear un archivo mo a partir de tu archivo po, puedes hacerlo con msgfmt del [paquete GNU gettext](http://www.gnu.org/software/gettext/){target=_blank}.

Para cuestiones específicas de Transifex, consulta su [documentación](http://docs.transifex.com/){target=_blank}.

## Directrices de traducción 

La mayoría de las cadenas que se deben traducir en Omeka son sencillas y se pueden traducir directamente. Sin embargo, hay algunos casos especiales que deben tratarse con cuidado.

### Marcadores de posición
Algunas cadenas contienen texto que se parece a `%s` o `%1$s`. Estos fragmentos de texto de aspecto extraño se denominan **marcadores de posición**. Los marcadores de posición se utilizan para permitir que Omeka inserte información variable, como el número de elementos en un sitio de Omeka, en una cadena traducida.

Si una cadena de origen contiene marcadores de posición, debes incluirlos en tu traducción. Puedes mover los marcadores de posición dentro de la cadena, e incluso cambiar el orden de los marcadores numerados, pero todos los marcadores de posición de la cadena de origen deben aparecer en la traducción.

### HTML y URL
Algunas cadenas contienen código HTML o URL incrustados. Puedes traducir y modificar el texto en inglés sin formato de estas cadenas, pero debes conservar las etiquetas HTML o las URL.
