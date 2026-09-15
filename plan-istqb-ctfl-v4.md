# Plan de preparación — ISTQB CTFL v4.0

Documento de seguimiento. Marca cada tarea al completarla.

---

## Datos del examen

| Concepto | Valor |
|---|---|
| Preguntas | 40, opción múltiple, una respuesta correcta |
| Puntuación mínima | 26 aciertos (65%) |
| Idioma elegido | **Inglés** |
| Duración | **75 minutos** (60 + 25% adicional por no ser lengua materna) |
| Penalización por fallo | Ninguna |
| Libro abierto | No |
| Vigencia del certificado | Permanente |
| Base documental | Syllabus v4.0.1 + Glosario ISTQB |

### Reparto de preguntas

| Capítulo | Preguntas | K1 | K2 | K3 |
|---|---|---|---|---|
| 1. Fundamentos del testing | 8 | 2 | 6 | 0 |
| 2. Testing en el ciclo de vida | 6 | 2 | 4 | 0 |
| 3. Pruebas estáticas | 4 | 2 | 2 | 0 |
| 4. Análisis y diseño de pruebas | 11 | 0 | 6 | 5 |
| 5. Gestión de las actividades de prueba | 9 | 1 | 5 | 3 |
| 6. Herramientas de prueba | 2 | 1 | 1 | 0 |
| **Total** | **40** | **8** | **24** | **8** |

### Estrategia de tiempo

ISTQB presupuesta 1 minuto por pregunta K1/K2 y 3 minutos por pregunta K3: 56 minutos de base. Con 75 minutos disponibles, el margen es de 19.

- Preguntas teóricas (32): unos 75 segundos cada una.
- Preguntas K3 (8): hasta 4 minutos cada una.
- **El tiempo extra es para leer, no para pensar.** Compensa el idioma, no la duda.
- Si una teórica pasa de 2 minutos, se marca y se sigue.
- Sin penalización por fallo: no se deja ninguna en blanco.

---

## Reglas del método

1. **Recuperación activa, no relectura.** Responder antes de sentirse listo, fallar y volver al texto.
2. **Registro de errores por sección.** Cada objetivo de aprendizaje de la v4.0 mapea uno a uno con una sección del syllabus. Cada fallo se anota con su número de sección y se relee solo esa parte.
3. **La definición del syllabus manda sobre la experiencia práctica.** Los distractores están construidos sobre lo que suena razonable en el trabajo diario.
4. **Los exámenes de muestra no se tocan hasta la fase 5.** Son cuatro y son agotables: una vez vista una pregunta, deja de medir nada.
5. **Régimen de idioma.** El examen se presenta en inglés, así que:
   - **Términos: siempre en inglés.** La terminología ISTQB es jerga, no idioma; traducirla obliga a aprenderla dos veces.
   - **Preguntas de práctica: íntegramente en inglés**, con el formato real (mayúsculas de énfasis BEST / NOT / CAN, opciones combinadas i-ii-iii, "Select TWO options").
   - **Explicaciones: en castellano.** No influye en el examen y acelera la asimilación.
   - **Registro de errores: en inglés**, porque lo que hay que reconocer el día del examen es el término.

---

## Fase 0 — Calibración ✅

- [x] **0.1** Prueba en frío: 8 preguntas trampa sin material previo. → Resultado: 2/8
- [x] **0.2** Lectura del mapa del examen: reparto por capítulo, niveles K y estrategia de tiempo
- [x] **0.3** Diagnóstico: razonamiento conceptual correcto, terminología y mecánica de técnicas a cero

---

## Fase 1 — Fundamentos y vocabulario
*Capítulos 1 y 3 → 12 preguntas del examen*

- [x] **1.1** Cap. 1 bloque A — Terminology and principles ✅ **7/8 (88%)**
  - Testing vs debugging · Testing, QA and quality control · Error, defect, failure, root cause · Verification vs validation · The seven testing principles
  - Fallo: defect alojado en documentación (ver registro de errores)
- [ ] **1.2** Cap. 1 bloque B — Proceso y productos
  - Las siete actividades de prueba · Análisis (qué probar) vs diseño (cómo probar) · Testware de cada actividad · Trazabilidad y su valor · Roles de gestión y de prueba
- [ ] **1.3** Cap. 1 bloque C — Personas
  - Habilidades esenciales · Enfoque de equipo completo · Niveles de independencia: ventajas e inconvenientes · Sesgos cognitivos
- [ ] **1.4** Consolidación cap. 1 — Ronda mixta de 10 preguntas
  - *Criterio de avance: ≥8/10*
- [ ] **1.5** Cap. 3 bloque A — Fundamentos de pruebas estáticas
  - Qué puede examinarse · Qué detecta la estática que no detecta la dinámica · Valor del feedback temprano · Estática vs dinámica
- [ ] **1.6** Cap. 3 bloque B — El proceso de revisión
  - Las cinco actividades · Roles y responsabilidades · Tipos de revisión: informal, walkthrough, revisión técnica, inspección · Factores de éxito
- [ ] **1.7** Consolidación cap. 3 — Ronda de 8 preguntas
  - *Criterio de avance: ≥6/8*

---

## Fase 2 — Ciclo de vida
*Capítulo 2 → 6 preguntas del examen*

- [ ] **2.1** Modelos de desarrollo y su impacto en la prueba
  - Secuenciales vs iterativos e incrementales · Enfoques test-first: TDD, ATDD, BDD · DevOps · Shift-left · Retrospectivas y mejora continua
- [ ] **2.2** Niveles de prueba
  - Componente · Integración de componentes · Sistema · Integración de sistemas · Aceptación (UAT, operativa, contractual, alfa y beta)
- [ ] **2.3** Tipos de prueba y mantenimiento
  - Funcional, no funcional, caja blanca, relacionada con cambios · Características de calidad ISO 25010 · Confirmación vs regresión · Detonantes del mantenimiento
  - *Trampa habitual: nivel y tipo son ejes independientes; cualquier tipo puede aplicarse en cualquier nivel*
- [ ] **2.4** Consolidación cap. 2 — Ronda de 10 preguntas
  - *Criterio de avance: ≥8/10*

---

## Fase 3 — Técnicas de prueba
*Capítulo 4 → 11 preguntas, 5 de ellas K3. El capítulo que decide el examen.*

- [ ] **3.1** Panorama de técnicas — Caja negra, caja blanca y basadas en experiencia: en qué se basa cada familia y cuándo puede diseñarse
- [ ] **3.2** Drill K3 — Particiones de equivalencia
  - Identificar particiones · Válidas e inválidas · Coverage items y cálculo de cobertura · Each Choice
- [ ] **3.3** Drill K3 — Valores límite
  - BVA de 2 valores vs 3 valores · Conteo de coverage items · Solo sobre particiones ordenadas
- [ ] **3.4** Drill K3 — Tablas de decisión
  - Condiciones, acciones y reglas · Tablas de entrada limitada y extendida · Colapso de reglas · Cobertura
- [ ] **3.5** Drill K3 — Transición de estados
  - Diagrama y tabla de estados · Cobertura de todos los estados, de transiciones válidas (0-switch) y de todas las transiciones · Jerarquía de fortaleza entre las tres
- [ ] **3.6** Caja blanca — Sentencias y ramas
  - Cobertura de sentencias · Cobertura de ramas · Subsunción · Valor y límites de la caja blanca
- [ ] **3.7** Basadas en experiencia — Predicción de errores y ataques de fallo · Pruebas exploratorias y basadas en sesión · Basadas en checklist
- [ ] **3.8** Drill K3 — Enfoques colaborativos
  - Escritura colaborativa de historias de usuario · INVEST · Las tres C · Criterios de aceptación: estilo escenario y estilo lista · ATDD para derivar casos de prueba
- [ ] **3.9** Consolidación cap. 4 — 15 preguntas cronometradas con reparto K2/K3 realista
  - *Criterio de avance: ≥12/15 y las 5 de técnica resueltas dentro de 3 minutos cada una*

---

## Fase 4 — Gestión y herramientas
*Capítulos 5 y 6 → 11 preguntas, 3 de ellas K3*

- [ ] **4.1** Planificación de pruebas
  - Propósito y contenido del plan · Aportación del tester a la planificación de iteración y entrega · Criterios de entrada vs criterios de salida · Pirámide de pruebas · Cuadrantes de prueba
- [ ] **4.2** Drill K3 — Estimación del esfuerzo
  - Basada en ratios · Extrapolación · Wideband Delphi y planning poker · Estimación de tres puntos (aplicar la fórmula)
- [ ] **4.3** Drill K3 — Priorización de casos de prueba
  - Basada en riesgo · Basada en cobertura · Basada en requisitos · Dependencias entre casos
- [ ] **4.4** Gestión de riesgos
  - Nivel de riesgo = probabilidad × impacto · Riesgo de proyecto vs riesgo de producto · Análisis, evaluación y control · Pruebas basadas en riesgo
- [ ] **4.5** Monitorización, control y finalización
  - Métricas de prueba · Informe de progreso vs informe de finalización · Comunicación del estado de la prueba
- [ ] **4.6** Gestión de configuración — Elementos de configuración, líneas base y soporte a la prueba
- [ ] **4.7** Drill K3 — Informe de defectos
  - Contenido obligatorio · Redactar uno completo desde un escenario · Qué información falta en un informe defectuoso
- [ ] **4.8** Cap. 6 — Herramientas
  - Clasificación por actividad soportada · Beneficios y riesgos de la automatización
- [ ] **4.9** Consolidación caps. 5 y 6 — Ronda de 12 preguntas
  - *Criterio de avance: ≥9/12*

---

## Fase 5 — Simulacros
*Aquí, y solo aquí, se usan los cuatro exámenes oficiales de muestra*

- [ ] **5.1** Simulacro A cronometrado — 60 min, sin material, de una sentada
- [ ] **5.2** Corrección y registro de errores — Cada fallo a su sección del syllabus; relectura dirigida
- [ ] **5.3** Simulacro B cronometrado + corrección y remediación
- [ ] **5.4** Repaso en frío de las 8 técnicas K3 — Un ejercicio de cada una, sin consultar nada
- [ ] **5.5** Simulacro C cronometrado + corrección y remediación
- [ ] **5.6** Simulacro D cronometrado — el que decide
  - *Criterio de listo: ≥33/40. El margen sobre los 26 del aprobado absorbe los nervios y las preguntas desafortunadas del día.*
- [ ] **5.7** Repaso final — Solo el registro de errores acumulado y los términos del glosario que sigan fallando

---

## Fase 6 — Logística previa

- [x] **6.1** Decidir idioma del examen → **inglés**
  - Confirmado en las reglas oficiales: 25% de tiempo adicional por no ser lengua materna (75 min). Todo el material del proyecto ya está en inglés y los distractores se juegan a nivel de palabra.
- [ ] **6.2** Elegir proveedor y modalidad — Presencial o en línea con supervisión remota
- [ ] **6.3** Reservar plaza y confirmar requisitos técnicos e identificación
- [ ] **6.4** Repaso ligero la víspera — Sin simulacros nuevos: solo registro de errores

---

## Registro de errores

Se va rellenando desde la fase 1. Es el documento que más valor acumula.

| Fecha | Term / topic (EN) | Sección | Por qué fallé | Repasado |
|---|---|---|---|---|
| Sesión 1 | **Defect vs error** — un *defect* puede estar en documentación (especificación, test script), no solo en código. El *error* es el acto mental; el *defect* es lo que queda escrito en el work product. | 1.2.3 | Definición | Sí |

Categorías de fallo útiles para distinguir:
- **Definición** — no sabía el término exacto
- **Matiz** — sabía el concepto pero no la excepción que pregunta el syllabus
- **Mecánica** — técnica mal aplicada o mal conteo de coverage items
- **Intuición** — respondí lo que funciona en la práctica, no lo que dice el syllabus
- **Lectura** — no leí bien el enunciado o me comí un "NO"

---

## Estado actual

**Fase 1, tarea 1.2** — siguiente: bloque B del capítulo 1 (actividades del proceso, testware, trazabilidad, roles).

Progreso: **5 de 43 tareas** completadas.

### Historial de resultados

| Tarea | Resultado | Nota |
|---|---|---|
| 0.1 Prueba en frío | 2/8 (25%) | Sin material previo, con preguntas trampa deliberadas |
| 1.1 Ch.1 Block A | **7/8 (88%)** | Primer cuestionario en inglés |

### Ritmo previsto

A una tarea al día: **38 tareas pendientes**, unas 28 horas de estudio. Realista en calendario: 7-8 semanas, contando repeticiones de consolidación y la fase 5 sin comprimir.

**Rutina de sesión:** 5 minutos releyendo el registro de errores antes de la tarea del día. Es lo que convierte la secuencia en repaso espaciado.

### Decisiones tomadas

| Fecha | Decisión | Motivo |
|---|---|---|
| Sesión 1 | Examen en **inglés** | Terminología ISTQB como jerga propia; material oficial en inglés; +25% de tiempo |
| Sesión 1 | Exámenes de muestra reservados a la fase 5 | Recurso agotable: solo miden una vez |
| Sesión 1 | Criterio de listo en 33/40, no 26/40 | Margen para nervios y preguntas desafortunadas |
