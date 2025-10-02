# Declaración de Accesibilidad

El equipo de Omeka se compromete a hacer de Omeka S una opción accesible para construir colecciones y exposiciones en línea. Estamos trabajando para que el código núcleo sea accesible y continuaremos haciendo de la accesibilidad para personas con discapacidad una prioridad a medida que desarrollamos el código. Omeka se esfuerza por adherirse a los [estándares de diseño web del W3C](http://www.w3.org/standards/){target=_blank} y por cumplir con la [Sección 508](http://www.section508.gov/){target=_blank} de la Ley de Estadounidenses con Discapacidades (Americans with Disabilities Act).

Para más información, por favor revise los siguientes informes:

- Omeka S versión 3.x [Informe de Conformidad de Accesibilidad, usando VPAT 2.4 Estándares Internacionales Revisados](files/OmekaS3x_ACR.pdf){target=_blank} (pdf), octubre de 2020.
- Omeka S versión 2.x [Informe de Conformidad de Accesibilidad usando VPAT versión 2.0](files/VPAT_OmekaS2-0-1.pdf){target=_blank} (pdf), agosto de 2019.
- Omeka S versión 1.x [Informe de Conformidad de Accesibilidad usando VPAT versión 1.1](files/VPAT2.0-OmekaS1-1.pdf){target=_blank} (pdf), abril de 2018.

Las siguientes declaraciones se aplican a Omeka S versión 1.0.1 y superiores:

## Interfaz pública (Front end)

Los temas de Omeka S producidos por el equipo de Omeka tienen las siguientes características para mejorar la accesibilidad:

-   Puntos de referencia [ARIA](http://www.w3.org/WAI/intro/aria){target=_blank} (Accessible Rich Internet Applications) para navegar por el contenido de la página con el tabulador, cuando no se usa un ratón o se utiliza un lector de pantalla.
-   Marcado semántico HTML5.

Tenga en cuenta que, aunque el código núcleo de Omeka S cumple con los estándares anteriores, las instalaciones de Omeka S que han sido personalizadas o que utilizan módulos y temas no desarrollados por el equipo de Omeka (RRCHNM) pueden carecer de algunas o todas estas opciones. Aunque animamos a los desarrolladores a considerar la accesibilidad, no podemos garantizar que su código incluya puntos de referencia ARIA, SkipNav u otras consideraciones de accesibilidad.

## Interfaz de administración (Back end)

El panel de administración de Omeka S tiene las siguientes características de accesibilidad:

-   Puntos de referencia ARIA para lectores de pantalla en el Panel de Administración, designando el encabezado, la navegación, el contenido principal y los pies de página.
-   Marcado semántico HTML5.

## Problemas de Accesibilidad

Si encuentra un problema de accesibilidad con el software núcleo de Omeka S o con los complementos desarrollados por el Equipo Omeka, por favor reporte sus hallazgos ya sea a través de una [publicación en el Foro](https://forum.omeka.org/c/omeka-s/accessibility/36) o creando una incidencia (issue) en el repositorio de Github correspondiente.