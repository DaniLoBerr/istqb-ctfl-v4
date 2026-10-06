# Teoría — Cap. 1 · Fundamentals of Testing

[← Índice](00-indice.md) · 8 preguntas del examen · Tareas 1.1, 1.2 y 1.3

---

## 1.1 What is testing

**Testing** (prueba) es un conjunto de actividades para **descubrir defects** (defectos) y **evaluar la calidad** de work products (productos de trabajo). Lo que se prueba se llama **test object** (objeto de prueba).

Tres ideas que el examen ataca:

- Testing **no es solo ejecutar** software. Hay **dynamic testing** (prueba dinámica; se ejecuta) y **static testing** (prueba estática; no se ejecuta: reviews —revisiones— y static analysis —análisis estático—).
- Testing **no es solo verification** (verificación: ¿cumple lo especificado?). También es **validation** (validación: ¿cubre lo que el usuario necesita en su entorno real?).
- Testing no es solo técnico: hay que planificarlo, estimarlo, monitorizarlo y controlarlo.

### 1.1.1 Test objectives

Los objetivos típicos, que cambian según el contexto (work product, test level, riesgos, SDLC):

- Evaluar work products (requirements, user stories, diseños, código).
- Provocar failures (fallos) y encontrar defects.
- Asegurar la coverage (cobertura) requerida del test object.
- Reducir el nivel de riesgo de una calidad insuficiente.
- Verificar que se cumplen los requisitos especificados.
- Verificar que se cumplen requisitos contractuales, legales y regulatorios.
- Dar información a los stakeholders (partes interesadas) para que decidan con criterio.
- Generar confianza en la calidad del test object.
- Validar que el test object está completo y funciona como esperan los stakeholders.

### 1.1.2 Testing vs debugging

| | Testing | Debugging (depuración) |
|---|---|---|
| Qué hace | Provoca failures (dynamic) o encuentra defects directamente (static) | Busca la causa del failure, la analiza y la elimina |

El proceso de debugging tras un failure en dynamic testing: **reproducir** el failure → **diagnosticar** (encontrar el defect) → **corregir**.

Después vienen dos tipos de testing, que son testing y no debugging:

- **Confirmation testing** (prueba de confirmación): comprueba que la corrección resolvió el problema. Mejor si lo hace quien hizo el test original.
- **Regression testing** (prueba de regresión): comprueba que la corrección no ha roto otra cosa.

Si el defect lo encontró static testing, no hay nada que reproducir ni diagnosticar: el defect ya está localizado y debugging se reduce a eliminarlo.

---

## 1.2 Why is testing necessary

### 1.2.1 Contribución al éxito

- Es una forma rentable de detectar defects (defectos).
- Permite evaluar la calidad en distintas fases del SDLC, y eso alimenta decisiones (por ejemplo, si se libera).
- Da a los usuarios una representación indirecta en el proyecto: el tester vela por sus necesidades.
- Puede ser obligatorio por contrato, ley o regulación.

### 1.2.2 Testing, QA y QC

| | Quality control, QC (control de calidad) | Quality assurance, QA (aseguramiento de la calidad) |
|---|---|---|
| Orientado a | **Producto** | **Proceso** |
| Enfoque | **Correctivo** | **Preventivo** |
| Idea | Actividades para alcanzar el nivel de calidad adecuado | Si se sigue bien un buen proceso, sale un buen producto |
| Responsable | — | Todos los del proyecto |

**Testing (prueba) es una forma de QC**, no de QA. QA se aplica tanto al proceso de desarrollo como al de testing.

Los test results (resultados de prueba) sirven a los dos: en QC, para corregir defects; en QA, como feedback sobre cómo están funcionando los procesos.

**Trampa:** "testing y QA son lo mismo". No lo son.

### 1.2.3 Errors, defects, failures y root causes

→ [apuntes 4](../apuntes/cap1-fundamentals-of-testing.md#4-error-defect-failure-root-cause)

La cadena: una persona comete un **error** (mistake; equivocación) → queda un **defect** (fault, bug; defecto) en un work product (producto de trabajo) → al ejecutarse puede producir un **failure** (fallo).

- **Error**: el acto humano. Causas típicas: presión de tiempo, complejidad, cansancio, falta de formación.
- **Defect**: lo que queda escrito. Puede estar en **documentación** (una especificación, un test script), en código o en artefactos de soporte (un build file). Un defect en un work product temprano se propaga a los que derivan de él.
- **Failure**: el comportamiento incorrecto observable en ejecución. Un defect **no siempre** causa un failure: algunos solo en circunstancias concretas, otros nunca.
- Un failure también puede venir del **entorno** (radiación, campos electromagnéticos), sin defect de por medio.
- **Root cause** (causa raíz): la razón de fondo por la que ocurrió el problema, normalmente la situación que llevó al error. Se identifica con root cause analysis (análisis de causa raíz); atacarla evita o reduce defects similares en el futuro.

---

## 1.3 The seven testing principles

| # | Principio | Idea |
|---|---|---|
| 1 | **Testing shows the presence, not the absence of defects** (la prueba muestra la presencia de defectos, no su ausencia) | Probar reduce la probabilidad de que queden defects (defectos), pero no demuestra que no haya |
| 2 | **Exhaustive testing is impossible** (la prueba exhaustiva es imposible) | Salvo casos triviales, no se puede probar todo. Se usan test techniques (técnicas de prueba), priorización y risk-based testing (prueba basada en el riesgo) |
| 3 | **Early testing saves time and money** (probar pronto ahorra tiempo y dinero) | Un defect eliminado pronto no genera defects en lo que deriva de él. Vale para static y dynamic |
| 4 | **Defects cluster together** (los defectos se agrupan) | Unos pocos componentes concentran la mayoría de defects (Pareto). Los clusters previstos y reales alimentan el risk-based testing |
| 5 | **Tests wear out** (las pruebas se desgastan) | Repetir los mismos tests deja de encontrar defects nuevos. Hay que modificar tests y test data (datos de prueba) y escribir nuevos |
| 6 | **Testing is context dependent** (la prueba depende del contexto) | No hay un enfoque único válido para todo |
| 7 | **Absence-of-defects fallacy** (falacia de la ausencia de defectos) | Verificar todo y corregir todo no garantiza un sistema que cubra las necesidades del usuario. Hace falta validation (validación) |

Matices:

- **5 no contradice la regresión automatizada**: repetir los mismos tests es útil precisamente para regression testing (prueba de regresión). → [apuntes 6](../apuntes/cap1-fundamentals-of-testing.md#6-tests-wear-out-vs-regresión-automatizada)
- **1 vs 7** se confunden: el 1 habla de lo que el testing (prueba) puede demostrar; el 7, de que un producto sin defects puede seguir siendo el producto equivocado. → [apuntes 7](../apuntes/cap1-fundamentals-of-testing.md#7-los-dos-principios-que-se-confunden)
- **4** → [apuntes 5](../apuntes/cap1-fundamentals-of-testing.md#5-defect-clusters-y-risk-based-testing)

---

## 1.4 Test activities, testware and test roles

### 1.4.1 Las siete actividades

No son estrictamente secuenciales: se solapan, se iteran y se adaptan al contexto.

| Activity | Qué se hace | Pregunta |
|---|---|---|
| **Test planning** (planificación de la prueba) | Definir los test objectives (objetivos de prueba) y elegir el enfoque que mejor los logra dentro de las restricciones | — |
| **Test monitoring and control** (monitorización y control de la prueba) | **Monitoring**: comparar el progreso real con el plan. **Control**: tomar las acciones necesarias para cumplir los objetivos | — |
| **Test analysis** (análisis de prueba) | Analizar la test basis (base de prueba) para identificar testable features (características que se pueden probar); definir y priorizar **test conditions** (condiciones de prueba); evaluar la test basis y el test object (objeto de prueba) en busca de defects (defectos) y testability (capacidad de ser probado) | **What to test?** |
| **Test design** (diseño de prueba) | Convertir test conditions en **test cases** (casos de prueba) y otro testware (productos de prueba), como los test charters; identificar **coverage items** (elementos de cobertura); definir test data requirements (requisitos de datos de prueba), diseñar el test environment (entorno de prueba) | **How to test?** |
| **Test implementation** (implementación de la prueba) | Crear o conseguir el testware para ejecutar: test data (datos de prueba), **test procedures** (procedimientos de prueba) agrupados en **test suites** (juegos de pruebas), test scripts (guiones de prueba); ordenar los procedures en un test execution schedule (calendario de ejecución de pruebas); **montar** el test environment y verificarlo | — |
| **Test execution** (ejecución de la prueba) | Ejecutar según el schedule; comparar actual vs expected results; registrar test results (resultados de prueba); analizar anomalies (anomalías) y reportarlas | — |
| **Test completion** (finalización de la prueba) | En hitos (release, fin de iteración, fin de test level): change requests (solicitudes de cambio) para defects sin resolver, archivar o entregar testware útil, dejar el entorno en el estado acordado, lessons learned (lecciones aprendidas), test completion report (informe de finalización de la prueba) | — |

La frontera fina: **diseñar** el entorno y **definir** qué datos hacen falta es design; **construir** el entorno y **crear** los datos es implementation. → [apuntes 8](../apuntes/cap1-fundamentals-of-testing.md#8-la-frontera-analysis--design--implementation)

### 1.4.2 El test process depende del contexto

Factores que lo condicionan: stakeholders (partes interesadas), miembros del equipo, dominio de negocio, factores técnicos, restricciones del proyecto, factores organizativos, SDLC y herramientas.

Afectan a: test strategy (estrategia de prueba), test techniques (técnicas de prueba), grado de automatización, coverage (cobertura) requerida, nivel de detalle de la documentación e informes.

### 1.4.3 Testware

→ [apuntes 3](../apuntes/cap1-fundamentals-of-testing.md#3-la-cadena-de-términos)

**Testware** = los work products (productos de trabajo) que salen de las test activities (actividades de prueba).

| Activity | Testware |
|---|---|
| Planning | Test plan (plan de prueba), test schedule (calendario de prueba), risk register (registro de riesgos), entry and exit criteria (criterios de entrada y de salida) |
| Monitoring and control | Test progress reports (informes de avance de la prueba), control directives (directivas de control), información de riesgos |
| Analysis | Test conditions priorizadas (p. ej. acceptance criteria), defect reports (informes de defecto) sobre la test basis |
| Design | Test cases, test charters (contratos de prueba), coverage items, test data requirements, test environment requirements (requisitos del entorno de prueba) |
| Implementation | Test procedures, automated test scripts, test suites, test data, test execution schedule, elementos del entorno (stubs, drivers, simulators) |
| Execution | Test logs (registros de prueba), defect reports |
| Completion | Test completion report, acciones de mejora, lessons learned, change requests |

**Trampa:** test **conditions** → analysis; test **cases** y coverage items → design; test **procedures** y test data → implementation.

### 1.4.4 Traceability

→ [apuntes 9](../apuntes/cap1-fundamentals-of-testing.md#9-traceability)

Vínculo entre la test basis y el testware (requirements ↔ test conditions ↔ test cases ↔ test results ↔ defects). Sirve para:

- Evaluar **coverage** (¿todos los requirements tienen test cases?) y **residual risk** (riesgo residual: test results ↔ risks).
- Analizar el impacto de un cambio.
- Facilitar auditorías y cumplir criterios de IT governance.
- Hacer los informes más comprensibles para los stakeholders.

### 1.4.5 Roles

→ [apuntes 10](../apuntes/cap1-fundamentals-of-testing.md#10-los-dos-roles)

| Role | Responsabilidad | Actividades |
|---|---|---|
| **Test management role** (rol de gestión de la prueba) | El test process, el equipo y el liderazgo de las test activities | Planning, monitoring and control, completion |
| **Testing role** (rol de prueba) | La parte de ingeniería (técnica) | Analysis, design, implementation, execution |

Son roles, no puestos: una misma persona puede tener los dos, y cambian según el contexto (en Agile, parte de la gestión la asume el propio equipo).

**Regla:** de la tarea a la activity, y de la activity al rol. Nunca del verbo al rol.

---

## 1.5 Essential skills and good practices

### 1.5.1 Skills genéricas

- Testing knowledge (conocimiento de pruebas; para ser eficaz, p. ej. con test techniques).
- Minuciosidad, cuidado, curiosidad, atención al detalle, método.
- Comunicación, escucha activa, trabajo en equipo.
- Pensamiento analítico y crítico, creatividad.
- Technical knowledge (para ser eficiente, p. ej. con herramientas).
- Domain knowledge (para entender a usuarios y negocio).

El tester suele traer malas noticias. El **confirmation bias** (sesgo de confirmación) hace difícil aceptar información que contradice lo que uno cree, y el testing puede percibirse como destructivo. Por eso los defects (defectos) y failures (fallos) se comunican de forma constructiva.

### 1.5.2 Whole-team approach

→ [apuntes 11](../apuntes/cap1-fundamentals-of-testing.md#11-whole-team-approach)

Cualquier miembro con los conocimientos necesarios puede hacer cualquier tarea, y **todos son responsables de la calidad**. El equipo comparte espacio (físico o virtual), lo que mejora comunicación y colaboración y aprovecha las skills de cada uno.

Los testers trabajan con los business representatives (representantes de negocio), para crear acceptance tests (pruebas de aceptación) adecuados, y con los developers (para acordar la test strategy y la automatización), y así transfieren conocimiento de testing al equipo.

**Trampa:** no elimina la necesidad de testers ni de independencia. Y no siempre es apropiado: en sistemas safety-critical (críticos para la seguridad) puede hacer falta un alto nivel de independencia.

### 1.5.3 Independence of testing

Niveles, de menos a más:

1. Sin independencia: el propio author (autor).
2. Algo: compañeros del author, del mismo equipo.
3. Alta: testers de fuera del equipo, dentro de la organización.
4. Muy alta: testers de fuera de la organización.

Lo habitual es combinar varios niveles (developers en component testing, test team en system testing, business representatives en acceptance testing).

| Ventajas | Inconvenientes |
|---|---|
| Detectan otros tipos de failures y defects por tener otra formación, perspectiva y sesgos | Aislamiento del equipo de desarrollo: falta de colaboración, problemas de comunicación, relación de enfrentamiento |
| Pueden verificar, cuestionar o refutar las suposiciones de los stakeholders (partes interesadas) | Los developers pueden perder el sentido de responsabilidad sobre la calidad |
| | Se les ve como cuello de botella o se les culpa de los retrasos |

**Trampa:** la independencia no sustituye a la familiaridad. Un developer encuentra muchos defects en su propio código de forma eficiente.
