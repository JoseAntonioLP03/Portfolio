# Especificación funcional inicial

Esta propuesta se basa únicamente en el contexto disponible: repositorio vacío, portfolio profesional de un desarrollador y prioridades definidas en [AGENTS.md](../AGENTS.md). No presupone todavía ningún framework ni proveedor de despliegue.

## 1. Requisitos funcionales

### RF-01. Página principal

El sistema debe proporcionar una página principal que comunique rápidamente:

- quién es el desarrollador;
- qué tipo de software desarrolla;
- qué valor aporta;
- cómo contactar con él.

La información principal debe ser visible sin depender de JavaScript.

### RF-02. Navegación

La página debe incluir navegación hacia las secciones principales del portfolio.

La navegación debe:

- permitir acceder mediante teclado;
- funcionar correctamente en móvil;
- indicar visualmente el foco;
- permitir volver a la página inicial desde cualquier página adicional.

### RF-03. Presentación personal

Debe existir una sección de presentación con:

- nombre;
- rol profesional;
- descripción breve;
- tecnologías o áreas principales;
- llamada a la acción relevante.

La llamada a la acción podrá dirigir a proyectos, contacto o currículum, según la decisión de producto.

### RF-04. Proyectos

El portfolio debe mostrar una selección de proyectos profesionales o personales.

Cada proyecto debe poder incluir:

- nombre;
- descripción;
- problema que resuelve;
- contribución del desarrollador;
- tecnologías utilizadas;
- enlace al código fuente, demostración o documentación cuando exista.

Los enlaces externos deben indicar claramente su destino y abrirse de forma coherente.

### RF-05. Experiencia y capacidades

Debe existir una forma clara de comunicar la experiencia profesional o las capacidades técnicas.

La primera versión podrá resolverlo mediante una sección breve de experiencia, habilidades o ambas. No debe convertirse en un inventario exhaustivo de tecnologías sin contexto.

### RF-06. Contacto

El usuario debe poder encontrar al menos un medio de contacto profesional.

La primera versión puede utilizar:

- correo electrónico;
- perfil profesional;
- repositorio público;
- otra red profesional relevante.

No se incluirá un formulario propio salvo que exista una necesidad concreta de backend, almacenamiento o gestión de spam.

### RF-07. Información legal y enlaces externos

Los enlaces externos deben ser funcionales y no contener valores ficticios en producción.

Si se utilizan imágenes, tipografías, iconos o contenidos de terceros, debe conocerse su procedencia y licencia.

### RF-08. Metadatos compartibles

La página debe definir información adecuada para:

- título del documento;
- descripción;
- vista previa al compartir en redes;
- URL canónica;
- favicon o identidad equivalente.

### RF-09. Evolución del contenido

La estructura debe permitir añadir posteriormente:

- páginas individuales de proyectos;
- artículos técnicos;
- versión en otro idioma;
- currículum descargable.

Estas posibilidades no forman parte obligatoria de la primera versión.

## 2. Requisitos no funcionales

### RNF-01. Rendimiento

- El contenido principal debe aparecer rápidamente en una conexión móvil normal.
- No debe enviarse JavaScript global si no es necesario.
- Las imágenes deben estar optimizadas y tener dimensiones explícitas.
- Las fuentes externas deben limitarse y no bloquear la presentación.
- La página debe aspirar a una puntuación alta en Lighthouse para rendimiento, SEO y buenas prácticas, sin convertir la puntuación en el único criterio de calidad.

### RNF-02. Accesibilidad

La primera versión debe orientarse a WCAG 2.2 nivel AA:

- HTML semántico;
- jerarquía correcta de encabezados;
- navegación completa con teclado;
- foco visible;
- contraste suficiente;
- textos alternativos útiles;
- formularios correctamente etiquetados si se incorporan;
- compatibilidad con `prefers-reduced-motion`;
- ausencia de información esencial transmitida solo mediante color o animación.

### RNF-03. SEO

- Una única descripción principal y un único `h1`.
- Metadatos completos y coherentes.
- URLs legibles.
- Sitemap cuando exista más de una ruta o sea útil para el despliegue.
- Contenido indexable sin ejecutar JavaScript.
- Datos estructurados solo cuando representen información real.

### RNF-04. Responsive design

La experiencia debe ser usable en:

- móvil;
- tablet;
- escritorio;
- orientación vertical y horizontal cuando sea relevante.

No debe existir desplazamiento horizontal accidental ni contenido solapado.

### RNF-05. Compatibilidad

Debe definirse una matriz mínima de navegadores soportados antes de implementar. Como criterio inicial, se puede cubrir la última versión estable y una versión anterior de los navegadores principales.

### RNF-06. Mantenibilidad

- Componentes o módulos con responsabilidades pequeñas.
- Contenido separado de la presentación cuando aporte valor.
- Nombres descriptivos.
- Tipos explícitos en datos estructurados.
- Sin duplicación innecesaria.
- Sin dependencias añadidas sin una justificación concreta.
- Configuración y comandos documentados.

### RNF-07. Seguridad

- No se almacenarán secretos en el repositorio.
- No se incorporará un backend sin una necesidad definida.
- Los recursos externos se limitarán a fuentes confiables.
- Los datos introducidos por usuarios se validarán si posteriormente se añade interacción con servidor.

### RNF-08. Privacidad

La primera versión debe evitar analítica, cookies y seguimiento salvo que exista una decisión explícita de producto y una política adecuada.

### RNF-09. Verificabilidad

Debe ser posible comprobar como mínimo:

- compilación o generación del sitio;
- ausencia de errores de tipo o lint, si se incorporan esas herramientas;
- enlaces principales;
- accesibilidad básica;
- comportamiento responsive;
- metadatos SEO;
- estado limpio de cambios no relacionados.

## 3. Restricciones

- El repositorio está prácticamente vacío.
- No existe todavía una decisión tecnológica.
- No existe contenido final proporcionado.
- No se deben introducir dependencias sin justificar su coste y necesidad.
- El portfolio debe seguir siendo comprensible para su propietario y servir como laboratorio de ingeniería profesional.
- Las funcionalidades innecesarias deben quedar fuera de la primera versión.
- No se deben incluir secretos, credenciales ni datos privados.
- No se debe asumir la existencia de backend, base de datos, CMS o autenticación.
- La solución debe poder desplegarse con una infraestructura sencilla.
- La primera versión debe priorizar contenido público y navegación, no funcionalidades de aplicación.

## 4. Supuestos

Estos puntos no están confirmados y deben tratarse como hipótesis:

- El público principal serán reclutadores, clientes potenciales, colaboradores y otros desarrolladores.
- El idioma principal podría ser español, aunque una versión bilingüe es posible.
- El contenido se actualizará ocasionalmente, no diariamente.
- La primera versión será principalmente estática.
- Los proyectos dispondrán de enlaces públicos o información que pueda publicarse.
- El contacto podrá realizarse sin almacenar datos en el propio portfolio.
- La identidad personal y profesional tendrá más importancia que una demostración técnica compleja.
- El sitio debe funcionar correctamente sin requerir una cuenta de usuario.

## 5. Decisiones que requieren información

Antes de cerrar la especificación conviene definir:

### Identidad y posicionamiento

- Nombre que aparecerá públicamente.
- Rol profesional exacto.
- Tipo de oportunidades buscadas.
- Especialidades que deben destacar.
- Tono: técnico, cercano, editorial, minimalista u otro.

### Contenido

- Secciones definitivas de la primera versión.
- Proyectos que se publicarán.
- Información profesional que puede hacerse pública.
- Si se incluirán experiencia, estudios, certificaciones o currículum.
- Si habrá artículos desde el inicio.

### Audiencia e idioma

- Público prioritario.
- Idioma inicial.
- Necesidad real de inglés o internacionalización.
- País o mercado profesional principal.

### Contacto y privacidad

- Medio de contacto preferido.
- Inclusión o no de redes sociales.
- Uso de analítica.
- Necesidad de aviso legal o política de privacidad según el despliegue y la jurisdicción.

### Diseño y recursos

- Preferencias visuales.
- Uso de fotografía, avatar o ilustración.
- Tipografía y paleta.
- Disponibilidad de logotipo o recursos propios.
- Presupuesto para dominio, correo y servicios externos.

### Operación

- Proveedor de despliegue.
- Dominio.
- Proceso de actualización.
- Necesidad de edición desde un CMS.
- Navegadores mínimos soportados.

## 6. Criterios de aceptación de la primera versión

La primera versión se considerará aceptable cuando:

1. Una persona que no conozca al autor pueda identificar quién es, qué hace y cómo contactarlo desde la página principal.
2. La página incluya presentación, proyectos, capacidades o experiencia y contacto.
3. Cada proyecto publicado tenga una descripción comprensible y, cuando proceda, enlaces funcionales.
4. La navegación funcione con teclado y muestre un foco visible.
5. La estructura de encabezados sea coherente y exista un único `h1`.
6. No haya contenido esencial oculto para usuarios sin JavaScript.
7. La página sea usable en móvil, tablet y escritorio sin desplazamiento horizontal accidental.
8. Las imágenes incluidas tengan texto alternativo adecuado y no provoquen cambios bruscos de layout.
9. Los enlaces externos funcionen y no existan enlaces ficticios o rotos en el contenido final.
10. El título, la descripción y la vista previa social estén definidos correctamente.
11. No se almacenen secretos ni datos personales innecesarios en el repositorio.
12. El sitio pueda generarse o ejecutarse mediante un proceso documentado y reproducible.
13. Las comprobaciones de calidad definidas para el proyecto se ejecuten sin errores relacionados con la primera versión.
14. El despliegue produzca una página accesible mediante una URL pública y HTTPS.
15. No existan funcionalidades no justificadas, como autenticación, base de datos, panel de administración o formulario propio.

## Alcance excluido inicialmente

Quedarían fuera de la primera versión, salvo necesidad explícita:

- blog completo;
- CMS;
- autenticación;
- panel privado;
- comentarios;
- buscador;
- sistema de analítica;
- newsletter;
- formulario con backend;
- animaciones complejas;
- internacionalización completa;
- API propia.

Esta especificación permite evaluar primero el valor profesional del portfolio y posponer decisiones tecnológicas hasta que estén claros el contenido, el público y el alcance real.
