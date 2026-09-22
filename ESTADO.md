# Estado — ISTQB CTFL v4.0

**Documento de arranque.** Es lo único que hace falta leer al empezar una conversación.
El método, las fases y las 43 tareas están en [`plan-istqb-ctfl-v4.md`](plan-istqb-ctfl-v4.md);
los conceptos que costaron, en [`apuntes-conceptos-clave.md`](apuntes-conceptos-clave.md).

---

## Estado actual

**Capítulo 1 completo y consolidado.** Tarea 1.5 (Cap. 3 bloque A, fundamentos de pruebas estáticas): **8/8 (100%)**. Pleno, sin fallos nuevos.

**Siguiente: tarea 1.6** — Cap. 3 bloque B, el proceso de revisión.

Progreso: **9 de 43 tareas** completadas.

---

### Historial de resultados

| Tarea | Resultado | Nota |
|---|---|---|
| 0.1 Prueba en frío | 2/8 (25%) | Sin material previo, con preguntas trampa deliberadas |
| 1.1 Ch.1 Block A | **7/8 (88%)** | Primer cuestionario en inglés |
| 1.2 Ch.1 Block B | **7/8 (88%)** | Fallo de clasificación (roles) |
| Mini-test Ch.1 A+B | **5/5 (100%)** | Recuperación espaciada. Incluía las dos casillas falladas antes (testware y roles): superadas |
| 1.3 Ch.1 Block C | **8/8 (100%)** | Primer pleno. Capítulo 1 completo |
| 1.4 Consolidación Ch.1 (mixta A+B+C) | **8/10 (80%)** | Dos fallos: clasificación fina (test procedures → implementation, no analysis) y matiz (whole-team approach). El fallo de clasificación management/testing de 1.2 no reincidió |
| 1.5 Ch.3 Block A — Static testing basics | **8/8 (100%)** | Pleno. Mini-test de recuperación previo (4/4) también sin fallos: whole-team approach y test procedures/implementation, ambos corregidos en 1.4, no reincidieron |

---

## Registro de errores

Se va rellenando desde la fase 1. Es el documento que más valor acumula.

| Fecha | Term / topic (EN) | Sección | Por qué fallé | Repasado |
|---|---|---|---|---|
| Sesión 1 | **Defect vs error** — un *defect* puede estar en documentación (especificación, test script), no solo en código. El *error* es el acto mental; el *defect* es lo que queda escrito en el work product. | 1.2.3 | Definición | Sí |
| Sesión 1 | **Test management role vs testing role** — *"take corrective action to meet the objectives of the test plan"* = test control → management. El sonido cotidiano de los verbos está invertido: *organizar* suena a gestión pero es implementation; *acciones correctivas* suena operativo pero es gestión. **Regla: ir de la tarea a la ACTIVIDAD, y de la actividad al rol. Nunca del verbo al rol.** | 1.4.5 | Clasificación | Sí |
| Sesión 3 | **Test procedures vs test conditions** — identificar/priorizar *test conditions* es test analysis; derivar y priorizar *test procedures* es test implementation. Ya estaba en apuntes (entrada "La cadena de términos") pero no se aplicó bajo presión de examen. | 1.4.1 / 1.4.3 | Clasificación | Sí |
| Sesión 3 | **Whole-team approach** — su propósito es integrar la experiencia de testing en el equipo desde el principio (mejor calidad, menos necesidad de una fase de prueba separada), no eliminar la necesidad de testers independientes o especialistas. | 1.5.2 | Matiz | Sí |

Categorías de fallo útiles para distinguir:
- **Definición** — no sabía el término exacto
- **Matiz** — sabía el concepto pero no la excepción que pregunta el syllabus
- **Mecánica** — técnica mal aplicada o mal conteo de coverage items
- **Clasificación** — entendía el concepto pero lo metí en la casilla equivocada
- **Intuición** — respondí lo que funciona en la práctica, no lo que dice el syllabus
- **Lectura** — no leí bien el enunciado o me comí un "NO"

---

### Patrón de fallos detectado

Los dos fallos de la fase 1 (1.1 y 1.2) fueron de **clasificación**, no de comprensión: los conceptos estaban, la casilla no. La clasificación no se entrena leyendo explicaciones más largas, se entrena clasificando bajo evaluación — de ahí el mini-test de recuperación al inicio de cada tarea.

**Confirmado en 1.4:** el mini-test de bloques A+B (5/5) y la consolidación 1.4 (8/10, con separación temporal real) muestran que la frontera **management vs testing role** quedó asentada — cero fallos en ella en 1.3 y 1.4. Lo que sigue costando es un nivel más fino: **dentro** del testing role, la frontera entre sub-actividades (analysis vs implementation) en tareas concretas como test conditions/coverage items (design) vs test procedures/test data (implementation). Mismo patrón de fondo — ir de la tarea a la actividad exacta, no fiarse del sonido de la palabra — aplicado a una frontera más estrecha.

**Confirmado en 1.5:** el mini-test de recuperación previo a la tarea (4/4, incluyendo whole-team approach y test procedures/implementation) confirma que los dos fallos de 1.4 quedaron cerrados, no solo repasados. Capítulo 3 bloque A resuelto sin ningún fallo — primer bloque de contenido nuevo con pleno directo.

**Descartado:** el mini-drill autoadministrado (ítems con las respuestas debajo). Mide reconocimiento, no recuperación: al ver la respuesta no se distingue saberla de reconocerla.

---

## Protocolo de cada conversación

Cada tarea se trabaja en su **propia conversación** dentro del proyecto, para no arrastrar contexto.
La continuidad la dan los documentos del repo, no el historial del chat.

1. Leer **este archivo** (`ESTADO.md`) para saber qué tarea toca. Nada más, salvo que haga falta.
2. **Mini-test de recuperación**: 4-5 preguntas sobre tareas **anteriores**, antes de la teoría.
3. Teoría de la tarea, consultando en el proyecto **solo el syllabus**.
4. **Cuestionario de 8 preguntas** en formato de examen.
5. **Actualizar `ESTADO.md`** (y los apuntes, si surgió alguna duda) antes de cerrar.

**Regla que sostiene el sistema:** lo que no quede escrito en el repo se pierde al cerrar la
conversación. Si surge algo que merece conservarse — una duda recurrente, una decisión, un patrón
de fallo — se escribe antes de cerrar.

Nombrar cada conversación con su tarea (`Tarea 1.4`, `Tarea 1.5`…) y no cerrarla hasta que el
resultado esté escrito aquí.

### Dónde está cada cosa

| Necesito… | Voy a… |
|---|---|
| Saber por dónde vamos | `ESTADO.md` (este archivo) |
| El detalle de una tarea o del método | `plan-istqb-ctfl-v4.md` |
| Lo que ya costó explicar | `apuntes-conceptos-clave.md` |
| Contenido del temario | El **syllabus** en los archivos del proyecto |
| Exámenes de muestra | **Nada hasta la fase 5.** No están en el proyecto a propósito |

---
