# Teoría — Cap. 3 · Static Testing

[← Índice](00-indice.md) · 4 preguntas del examen · Tareas 1.5 y 1.6

---

## 3.1 Static testing basics

En **static testing** (prueba estática) el software **no se ejecuta**. Los work products (productos de trabajo) se evalúan de dos maneras:

- **Reviews** (revisiones): examen manual, hecho por personas.
- **Static analysis** (análisis estático): examen con herramientas.

Objetivos: mejorar la calidad, detectar defects (defectos) y evaluar características como legibilidad, completitud, corrección, testability (capacidad de ser probado) y consistencia. Sirve tanto para **verification** (verificación) como para **validation** (validación).

En la práctica ágil aparece en example mapping, escritura colaborativa de user stories (historias de usuario) y backlog refinement, donde testers, business representatives (representantes de negocio) y developers comprueban que las user stories cumplen los criterios acordados (p. ej. Definition of Ready).

**Static analysis** detecta problemas antes del dynamic testing (prueba dinámica) y suele costar menos, porque no requiere test cases (casos de prueba). Se integra a menudo en CI. Además de defects de código evalúa maintainability (mantenibilidad) y security. Un corrector ortográfico también es static analysis.

### 3.1.1 Qué se puede examinar

Casi cualquier work product: requirements (requisitos), código, test plans (planes de prueba), test cases, product backlog items, test charters (contratos de prueba), documentación de proyecto, contratos, modelos.

- **Reviews**: cualquier work product que se pueda **leer y entender**.
- **Static analysis**: necesita una **estructura** contra la que comprobar (código, modelos, texto con sintaxis formal).

No son apropiados los work products difíciles de interpretar por personas y que no deban analizarse con herramientas, como ejecutables de terceros, por motivos legales.

### 3.1.2 Valor del static testing

- Detecta defects en las **fases más tempranas** (shift-left).
- Detecta defects que el dynamic testing **no puede** encontrar: código inalcanzable, patrones de diseño mal implementados, defects en work products no ejecutables.
- Permite evaluar la calidad de los work products y generar confianza en ellos.
- Revisando los requirements, los stakeholders (partes interesadas) comprueban que describen sus necesidades reales.
- Crea un entendimiento compartido y mejora la comunicación; conviene implicar a stakeholders variados.

Las reviews cuestan, pero el coste total del proyecto suele bajar: se gasta menos en corregir defects más tarde.

### 3.1.3 Static testing vs dynamic testing

Se complementan. Los dos apoyan la detección de defects, pero:

| | Static | Dynamic |
|---|---|---|
| Qué encuentra | **Defects directamente** | **Failures** (fallos), de los que luego se deduce el defect analizando |
| Sobre qué | Work products ejecutables **y no ejecutables** | Solo ejecutables |
| Caminos raros | Llega con más facilidad a caminos que casi nunca se ejecutan | Le cuesta alcanzarlos |
| Qué mide | Características que no dependen de ejecutar (maintainability) | Características que dependen de ejecutar (performance efficiency) |

Defects más fáciles o baratos de encontrar con static testing:

- **Requirements**: inconsistencias, ambigüedades, contradicciones, omisiones, imprecisiones, duplicaciones.
- **Diseño**: estructuras de base de datos ineficientes, mala modularización.
- **Código**: variables sin valor definido o sin declarar, código inalcanzable o duplicado, complejidad excesiva.
- **Desviaciones de estándares**: convenciones de nombres.
- **Interfaces mal especificadas**: número, tipo u orden de parámetros que no coinciden.
- **Vulnerabilidades de seguridad** concretas: buffer overflows.
- **Huecos en la coverage (cobertura) de la test basis** (base de prueba): un acceptance criterion (criterio de aceptación) sin tests.

**Trampa:** todo lo que solo se ve con el sistema en marcha (tiempos de respuesta, un cálculo que sale mal, un crash con cierta entrada) es dynamic.

---

## 3.2 Feedback and review process

### 3.2.1 Early and frequent stakeholder feedback

El feedback temprano y frecuente comunica pronto los problemas de calidad. Sin él, el producto puede no ser lo que el stakeholder (parte interesada) tenía en mente, y eso acaba en retrabajo caro, plazos incumplidos, reproches o el fracaso del proyecto.

Con feedback frecuente:

- Se evitan malentendidos sobre los requirements (requisitos).
- Los cambios de requirements se entienden e implementan antes.
- El equipo entiende mejor lo que está construyendo.
- El esfuerzo se centra en lo que aporta más valor y en lo que más reduce los riesgos identificados.

### 3.2.2 Review process activities

*(Tarea 1.6, en curso)*

Proceso genérico: la formalidad con que se aplica depende del tipo de review.

| Activity | Qué pasa | Trampa |
|---|---|---|
| **Planning** (planificación) | Se define el alcance: propósito, work product (producto de trabajo), quality characteristics (características de calidad) a evaluar, **exit criteria** (criterios de salida), esfuerzo y plazos | Los exit criteria se fijan aquí, no al final |
| **Review initiation** (inicio de la revisión) | Que todos y todo estén listos: acceso al work product, cada uno conoce su rol, tiene el material | Es logística de arranque; todavía nadie revisa |
| **Individual review** (revisión individual) | Cada reviewer (revisor) evalúa por su cuenta y anota **anomalies** (anomalías), recomendaciones y preguntas | Aquí se encuentra el grueso, no en la reunión |
| **Communication and analysis** (comunicación y análisis) | Se analiza cada anomaly: status, ownership, acciones. Normalmente en un review meeting (reunión de revisión), donde también se decide el nivel de calidad y si hace falta follow-up (seguimiento) | Una **anomaly no es necesariamente un defect** (defecto): por eso hay que analizarla |
| **Fixing and reporting** (corrección e informe) | Un **defect report** (informe de defecto) por cada defect, se corrige, se comprueban los exit criteria, se acepta el work product y se informa de los resultados | Los defect reports nacen aquí, no en individual review |

### 3.2.3 Roles and responsibilities

| Role | Qué hace |
|---|---|
| **Manager** (responsable, dirección) | Decide **qué** se revisa y pone **recursos** (gente, tiempo) |
| **Author** (autor) | Crea **y corrige** el work product |
| **Moderator** o facilitator (moderador) | Hace que la **reunión** funcione: mediación, gestión del tiempo, ambiente seguro para hablar |
| **Scribe** o recorder (escriba) | **Recopila** las anomalies de los reviewers y registra decisiones y anomalies nuevas de la reunión |
| **Reviewer** (revisor) | Revisa. Puede ser alguien del proyecto, un experto en la materia o cualquier otro stakeholder |
| **Review leader** (líder de la revisión) | Responsabilidad global de la review: **quién** participa, **cuándo** y **dónde** |

Los pares que se confunden:

- **Manager vs review leader**: qué y con qué recursos, frente a quién, cuándo y dónde.
- **Review leader vs moderator**: organizar la review, frente a conducir la reunión.
- **Scribe vs reviewer**: recopilar y registrar, frente a encontrar.

Una persona puede tener varios roles, salvo la restricción de la inspection (inspección).

### 3.2.4 Review types

De menos a más formal:

| Tipo | Lo que lo identifica | Objetivo principal |
|---|---|---|
| **Informal review** (revisión informal) | Sin proceso definido ni salida documentada formal | Detectar anomalies |
| **Walkthrough** (revisión guiada) | **Lo dirige el author**. La individual review previa es opcional | Muchos: educar a los reviewers, consenso, generar ideas, confianza, detectar anomalies |
| **Technical review** (revisión técnica) | Reviewers técnicamente cualificados, **lo dirige un moderator** | **Consenso y decisiones** sobre un problema técnico |
| **Inspection** (inspección) | El más formal, sigue el proceso completo. Se recogen **metrics** (métricas) para mejorar el SDLC y la propia inspection. **El author no puede ser review leader ni scribe** | Encontrar el **máximo número de anomalies** |

Pistas del enunciado: "led by the author" → walkthrough; "technical decision / consensus" → technical review; "metrics", "most formal", "maximum anomalies" → inspection.

### 3.2.5 Success factors

- Objetivos claros y exit criteria medibles.
- **Evaluar a los participantes nunca es un objetivo.**
- Elegir el tipo de review adecuado.
- Revisar en **trozos pequeños**, para no perder concentración.
- Dar feedback a stakeholders y authors.
- Tiempo suficiente para prepararse.
- Apoyo de management.
- Reviews (revisiones) como parte de la cultura de la organización.
- Formación de los participantes.
- Reuniones bien facilitadas.

**Trampa:** "use the review results to assess the author's performance" siempre es falso.
