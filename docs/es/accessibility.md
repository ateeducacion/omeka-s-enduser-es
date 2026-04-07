# Declaración de accesibilidad

El equipo de Omeka se compromete a hacer de Omeka S una opción accesible para crear colecciones y exposiciones en línea. Estamos trabajando para que el código base sea accesible y seguiremos dando prioridad a la accesibilidad para las personas con discapacidad a medida que desarrollamos el código. Omeka se esfuerza por cumplir con los [estándares de diseño web del W3C](http://www.w3.org/standards/){target=_blank} y por ajustarse a la [Sección 508](http://www.section508.gov/){target=_blank} de la Ley de Estadounidenses con Discapacidades.

Para obtener más información, consulte los siguientes informes:

- Omeka S versión 4.x, diciembre de 2025.
	- [Informe de conformidad de accesibilidad, utilizando las normas internacionales VPAT 2.5 revisadas (PDF)](files/OmekaS4x_ACR.pdf){target=_blank}
  - [Informe de conformidad de accesibilidad, utilizando las normas internacionales VPAT 2.5 revisadas (DOCX)](files/OmekaS4x_ACR.docx){target=_blank} 
- Omeka S versión 3.x [Informe de conformidad con la accesibilidad, utilizando las normas internacionales VPAT 2.4 revisadas (PDF)](files/OmekaS3x_ACR.pdf){target=_blank}, octubre de 2020.
- Omeka S versión 2.x [Informe de conformidad con la accesibilidad, utilizando VPAT 2.0 (PDF)](files/VPAT_OmekaS2-0-1.pdf){target=_blank}, agosto de 2019.
- Omeka S versión 1.x [Informe de conformidad de accesibilidad, utilizando VPAT 2.0 (PDF)](files/VPAT2.0-OmekaS1-1.pdf){target=_blank}, abril de 2018.

## Hoja de ruta
Según el actual Informe de conformidad con la accesibilidad, durante 2026 el equipo de Omeka está trabajando en los siguientes elementos:

-   Alternativas navegables mediante teclado a las interfaces de arrastrar y soltar
-   Información sobre herramientas compatible con lectores de pantalla y navegable mediante teclado
-   Anuncios de estado compatibles con lectores de pantalla para las interacciones
-   Orden de enfoque mejorado a través de la interfaz de administración
-   Roles y atributos de relación mejorados en toda la interfaz de administración

Consulte la [lista actual de incidencias](https://github.com/omeka/omeka-s/issues?q=is%3Aissue%20state%3Aopen%20label%3Aa11y){target=_blank} en el repositorio de GitHub del software principal.

## Características

Las siguientes afirmaciones se aplican a Omeka S versión 1.0.1 y superiores:

### Interfaz de usuario (vista pública)

Los temas de Omeka S creados por el equipo de Omeka cuentan con las siguientes características para mejorar la accesibilidad:

-   Puntos de referencia [ARIA](http://www.w3.org/WAI/intro/aria){target=_blank} (Aplicaciones de Internet enriquecidas accesibles) para desplazarse por el contenido de la página con el teclado, cuando no se utiliza el ratón o se emplea un lector de pantalla.
-   Marcado HTML5 semántico.

Tenga en cuenta que, aunque el código central de Omeka S cumple con los estándares anteriores, las instalaciones de Omeka S que hayan sido personalizadas o que utilicen módulos y temas que no sean de RRCHNM pueden carecer de algunas o de todas estas opciones. Aunque animamos a los desarrolladores a tener en cuenta la accesibilidad, no podemos garantizar que su código incluya puntos de referencia ARIA, SkipNav u otras consideraciones de accesibilidad.

### Back-end (vista administrativa)

El panel de control administrativo de Omeka S cuenta con las siguientes características de accesibilidad:

-   Puntos de referencia ARIA para lectores de pantalla en el panel de control administrativo, que designan el encabezado, la navegación, el contenido principal y los pies de página.
-   Marcado HTML5 semántico.

## Problemas de accesibilidad

Si detecta algún problema de accesibilidad en el software principal de Omeka S o en los complementos desarrollados por el equipo de Omeka, por favor, comuníquelo mediante una [publicación en el foro](https://forum.omeka.org/c/omeka-s/accessibility/36){target=_blank} o creando una incidencia en el repositorio de GitHub correspondiente.
