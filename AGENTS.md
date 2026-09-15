# Instrucciones del agente

## 1. Propósito

Este repositorio contiene el desarrollo de un portfolio personal de un desarrollador de software.

El proyecto se utilizará como proyecto real y como laboratorio para aprender a desarrollar software utilizando agentes de IA de forma profesional.

El agente debe priorizar:

- calidad técnica;
- simplicidad;
- mantenibilidad;
- accesibilidad;
- rendimiento;
- seguridad;
- verificabilidad;
- comprensión por parte del desarrollador.

La velocidad de implementación no es un objetivo por sí misma.

---

## 2. Principios de ingeniería

### Simplicidad antes que complejidad

Utilizar la solución más sencilla que satisfaga los requisitos.

No introducir abstracciones, patrones, dependencias o infraestructura innecesarios.

### Cambios pequeños

Cada modificación debe tener un propósito concreto y limitarse al alcance de la tarea.

No modificar código o configuración no relacionados con el objetivo actual.

### Dependencias

No añadir una dependencia sin justificar:

1. qué problema resuelve;
2. por qué no se puede resolver razonablemente con las herramientas existentes;
3. qué coste de mantenimiento introduce.

Preferir las capacidades nativas de la plataforma cuando sean suficientes.

### Comprensión

Antes de implementar una decisión arquitectónica relevante, explicar:

- problema;
- alternativas consideradas;
- decisión;
- trade-offs;
- consecuencias.

No asumir que una solución generada automáticamente es correcta.

---

## 3. Proceso de trabajo

Para cada tarea seguir este flujo:

1. Analizar el contexto existente.
2. Identificar requisitos y restricciones.
3. Inspeccionar los archivos afectados.
4. Proponer la estrategia de implementación.
5. Identificar posibles riesgos.
6. Implementar el cambio.
7. Ejecutar las comprobaciones correspondientes.
8. Revisar los cambios realizados.
9. Resumir qué se ha modificado y cómo se ha verificado.

No comenzar una implementación importante sin comprender primero el contexto.

---

## 4. Código

Escribir código claro, explícito y mantenible.

Preferir:

- composición frente a abstracciones innecesarias;
- funciones pequeñas con responsabilidades claras;
- nombres descriptivos;
- tipos explícitos cuando aporten valor;
- validación en límites del sistema;
- separación clara entre presentación, dominio e infraestructura cuando corresponda.

Evitar:

- `any` salvo justificación explícita;
- duplicación innecesaria;
- funciones excesivamente complejas;
- comentarios que simplemente describan código obvio;
- código muerto;
- soluciones temporales que no estén documentadas.

---

## 5. Calidad

Una tarea no se considera terminada únicamente porque el código compile.

Cuando sea aplicable, verificar:

- compilación;
- TypeScript;
- lint;
- tests;
- comportamiento esperado;
- accesibilidad;
- rendimiento;
- responsive design.

No eliminar ni debilitar una comprobación para hacer que el proyecto pase los checks.

---

## 6. Testing

Los tests deben verificar comportamiento y no detalles internos innecesarios.

Toda funcionalidad no trivial debe incorporar una estrategia de pruebas adecuada a su nivel de riesgo.

Preferir:

- tests unitarios para lógica aislada;
- tests de integración para interacción entre componentes;
- tests E2E para flujos críticos de usuario.

No crear tests cuyo único objetivo sea aumentar artificialmente la cobertura.

---

## 7. Seguridad

No introducir secretos en el repositorio.

Nunca escribir:

- claves API;
- tokens;
- contraseñas;
- credenciales;
- secretos de servicios externos.

Utilizar variables de entorno cuando sea necesario.

Validar y sanitizar datos procedentes de fuentes externas.

---

## 8. Git

Los commits deben representar cambios lógicos y coherentes.

Utilizar mensajes siguiendo Conventional Commits.

Ejemplos:

- `feat: añade sección de proyectos`
- `fix: corrige navegación móvil`
- `refactor: simplifica componente de navegación`
- `test: añade pruebas de formulario`
- `docs: documenta decisión arquitectónica`

No mezclar cambios no relacionados en un mismo commit.

No realizar commits automáticamente sin informar al desarrollador, salvo que se solicite expresamente.

---

## 9. Cambios destructivos

Antes de:

- eliminar archivos;
- modificar configuraciones críticas;
- cambiar dependencias principales;
- realizar migraciones;
- ejecutar comandos potencialmente destructivos;

explicar el impacto y solicitar confirmación.

Nunca utilizar comandos destructivos como mecanismo para solucionar un problema sin comprender su causa.

---

## 10. Uso de IA

La IA es una herramienta de desarrollo y revisión, no una autoridad técnica.

Cuando exista incertidumbre:

- declararla;
- investigar;
- comparar alternativas;
- evitar inventar APIs, documentación o comportamientos.

No afirmar que algo funciona si no se ha verificado.

No inventar resultados de tests, builds o herramientas.

Cuando se utilice información externa relevante, indicar su fuente.

---

## 11. Criterio de finalización

Una tarea está terminada cuando:

1. cumple los requisitos definidos;
2. el código es coherente con la arquitectura;
3. las comprobaciones pertinentes pasan;
4. no existen cambios accidentales relacionados con la tarea;
5. el comportamiento ha sido verificado;
6. cualquier decisión relevante está documentada.

---

## 12. Comunicación

Toda comunicación con el desarrollador debe realizarse en castellano.

Las explicaciones deben distinguir claramente entre:

- hechos verificados;
- decisiones propuestas;
- supuestos;
- incertidumbres.

Cuando existan varias soluciones razonables, presentarlas antes de elegir una.

No ocultar errores ni corregirlos silenciosamente.