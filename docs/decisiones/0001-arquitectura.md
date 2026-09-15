# ADR-0001: Arquitectura del portfolio

## Contexto

El proyecto es un portfolio profesional de un desarrollador de software y también un laboratorio para aplicar prácticas de ingeniería y trabajar con agentes de IA de forma profesional.

La primera versión debe ser principalmente estática y centrarse en contenido público: presentación personal, proyectos, experiencia o capacidades, contacto y metadatos compartibles. No se requiere inicialmente backend, base de datos, CMS, autenticación ni un formulario propio.

Los requisitos priorizan simplicidad, rendimiento, accesibilidad, SEO, mantenibilidad, seguridad y verificabilidad. La información principal debe ser indexable y visible sin depender de JavaScript. La estructura debe permitir evolucionar posteriormente hacia páginas individuales de proyectos, artículos técnicos, una versión en otro idioma y un currículum descargable.

Se han evaluado tres alternativas: HTML, CSS y JavaScript sin framework; Astro + TypeScript; y Next.js + TypeScript.

## Decisión

Adoptar **Astro + TypeScript** para la primera versión del portfolio.

La solución utilizará generación de contenido estático como base, HTML semántico y JavaScript únicamente cuando una interacción concreta lo justifique. TypeScript se utilizará para mejorar la claridad y detectar errores en datos y configuración.

Esta alternativa ofrece el mejor equilibrio entre los requisitos actuales y la evolución prevista: mantiene un buen rendimiento y contenido indexable, proporciona estructura para páginas, layouts, componentes y contenido reutilizable, y evita adoptar inicialmente la complejidad de una aplicación dinámica completa.

La adopción de Astro no sustituye las decisiones de implementación necesarias sobre accesibilidad, SEO, optimización de recursos, validación, pruebas y despliegue.

## Alternativas consideradas

### HTML, CSS y JavaScript sin framework

Es la opción con menor dependencia y menor complejidad inicial. Permite controlar directamente el HTML, el CSS, el JavaScript y el rendimiento.

Es adecuada para una única landing pequeña y estable. Sin embargo, al añadir páginas de proyectos, artículos, contenido estructurado o elementos repetidos, sería necesario gestionar manualmente componentes, layouts, metadatos, sitemap y generación de contenido.

### Next.js + TypeScript

Ofrece un ecosistema amplio y una evolución sencilla hacia una aplicación con React, backend, autenticación, APIs, contenido dinámico o funcionalidades personalizadas.

Puede proporcionar un rendimiento y un SEO excelentes, pero introduce más decisiones y complejidad de la necesaria para una primera versión principalmente estática. Sus capacidades de servidor y aplicación no están justificadas por los requisitos actuales.

### Astro + TypeScript

Permite construir un sitio estático con componentes, layouts, contenido estructurado y TypeScript, enviando JavaScript solo cuando sea necesario.

Proporciona más estructura y capacidad de evolución que una implementación manual, sin asumir la complejidad operativa de Next.js para una landing orientada a contenido.

## Trade-offs

- Se acepta una dependencia adicional frente a HTML, CSS y JavaScript sin framework para obtener mejor organización, reutilización y evolución del contenido.
- Se renuncia inicialmente a parte de la infraestructura y capacidades dinámicas de Next.js para mantener el proyecto simple y alineado con el alcance real.
- Astro no garantiza por sí mismo rendimiento, SEO ni accesibilidad; estos objetivos seguirán dependiendo de la implementación y de las comprobaciones del proyecto.
- La solución requiere aprender las convenciones de Astro y TypeScript, aunque el alcance conceptual es menor que el de una aplicación dinámica completa.
- Si el portfolio permaneciera como una única página muy pequeña y estable, una implementación sin framework tendría menos coste tecnológico.

## Consecuencias

- La primera versión se podrá orientar a generación estática y despliegue sencillo.
- La información principal podrá estar disponible sin depender de JavaScript en el navegador.
- Será posible organizar el proyecto mediante páginas, layouts, componentes y contenido separado de la presentación cuando aporte valor.
- Se podrá añadir interactividad puntual sin convertir toda la página en una aplicación cliente.
- TypeScript permitirá validar datos estructurados y reducir errores en la evolución del proyecto.
- Se deberán establecer comprobaciones de rendimiento, accesibilidad, SEO, responsive design, enlaces y generación del sitio.
- No se incorporarán backend, base de datos, CMS, autenticación ni formulario propio salvo que aparezca una necesidad de producto explícita.

## Criterios para reconsiderar la decisión

Se reconsiderará esta decisión si el alcance cambia de forma sustancial.

Se evaluará una implementación sin framework si:

- el portfolio se limita de forma estable a una única página;
- no se necesitan páginas repetibles ni contenido estructurado;
- la mínima dependencia tecnológica pasa a ser el objetivo principal.

Se evaluará Next.js + TypeScript si:

- se necesita autenticación o un área privada;
- aparecen datos personalizados por usuario;
- se incorpora una API o lógica de servidor relevante;
- se integra un CMS o flujo de contenido dinámico que requiera capacidades de aplicación;
- el proyecto evoluciona hacia una aplicación React completa.

También se reconsiderará Astro si su complejidad real, el coste de mantenimiento o las necesidades operativas dejan de ser proporcionales al valor que aporta al portfolio.
