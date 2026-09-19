# CLAUDE.md

Preparación de Dani (DaniLoBerr) para la certificación **ISTQB CTFL v4.0** (syllabus v4.0.1). **Este repositorio es la fuente única**: plan, estado, registro de errores y apuntes. Nada vive solo en una conversación.

## Repo público — antes que nada

**El repo es público** (`DaniLoBerr/istqb-ctfl-v4`). Lo que hay aquí es obra propia; el material oficial del ISTQB (syllabus, glosario, exámenes de muestra) tiene copyright y **no se sube**: `*.pdf` está en `.gitignore` y `istqb-ctfl-materials/` es solo local. Tampoco se pegan aquí enunciados literales de los exámenes de muestra ni del syllabus más allá de una cita corta: los apuntes son la idea con palabras propias. Nada de datos personales.

## Economía de contexto

Los documentos están partidos para no abrirlos enteros. **Abre el archivo concreto que responde la pregunta, nunca todos "por contexto".** Al editar, **haz parches sobre las líneas que cambian**; no reescribas un archivo entero para tocar tres líneas.

## Qué hay y qué abrir

| Archivo | Qué es | Cuándo abrirlo |
|---|---|---|
| `ESTADO.md` | Estado actual (qué tarea toca), historial de resultados, **registro de errores**, patrón de fallos y protocolo de cada conversación | **Siempre al empezar una tarea** |
| `plan-istqb-ctfl-v4.md` | Datos del examen, criterio de listo, reglas del método y las 43 tareas de las fases 0-6. Referencia estable | Al entrar en una fase, para el detalle de una tarea o para marcarla |
| `apuntes-conceptos-clave.md` | Conceptos que costaron, condensados a la idea que los desbloqueó. Su índice está arriba | Para repasar o añadir una entrada; usa el índice para ir a la sección |
| `docs/instrucciones-proyecto-claude.md` | Texto para pegar en el proyecto de la app de Claude y hábitos que ahorran tokens | Solo si se cambian esas instrucciones |
| `istqb-ctfl-materials/` | PDFs oficiales (solo locales, ignorados por git) | Solo si hace falta el texto literal del syllabus |

**Syllabus:** en el proyecto de la app está subido como conocimiento del proyecto (es lo único que se sube); en local, en `istqb-ctfl-materials/`. Los exámenes de muestra **no** están en el proyecto a propósito: no se tocan hasta la fase 5.

## Cómo se trabaja aquí

1. **Cada tarea del plan (`1.4`, `1.5`…) es una conversación propia.** Protocolo completo en `ESTADO.md`: leer estado → mini-test de recuperación → teoría → cuestionario → actualizar el repo antes de cerrar.
2. **Al cerrar una tarea se actualiza:** `ESTADO.md` (estado actual, historial de resultados y, si hubo fallos, una fila en el registro de errores con su sección del syllabus y su categoría), la tarea marcada en `plan-istqb-ctfl-v4.md`, y `apuntes-conceptos-clave.md` solo si surgió un concepto nuevo que costó.
3. **Se trabaja directamente en `main`**: commit y `git push` al terminar cada cambio, sin pedir permiso. Un commit por cambio con sentido propio, mensaje en imperativo describiendo el cambio, no el archivo. Rama + PR solo para reestructuraciones grandes.
4. Nunca: cambiar la visibilidad del repo, borrarlo, ni `push --force` (bloqueado en `.claude/settings.json`).
5. Si un archivo que se consulta mucho crece demasiado (`apuntes-conceptos-clave.md`, ~20 KB, es el candidato; también el registro de errores de `ESTADO.md`), se parte por capítulo del syllabus con un `00-indice.md`, y se actualiza esta tabla.

## Cómo quiere Dani las respuestas

- **Términos ISTQB siempre en inglés; explicaciones en castellano.** El examen es en inglés (75 min); la terminología es jerga, no idioma.
- **Preguntas de práctica íntegramente en inglés**, con el formato real: mayúsculas de énfasis (BEST / NOT / CAN), opciones combinadas i-ii-iii, "Select TWO options".
- **La definición del syllabus manda sobre la experiencia práctica.** Los distractores se construyen sobre lo que suena razonable en el trabajo diario.
- **Los exámenes de muestra no se tocan hasta la fase 5.** Son agotables.
- Recuperación activa: preguntar y corregir, no volver a explicar lo que ya se sabe.
- Al grano; sin resumir al final lo que ya se ha dicho.
