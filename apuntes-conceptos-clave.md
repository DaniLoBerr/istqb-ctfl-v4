# Apuntes — conceptos que costaron

Complemento del plan de estudio. Aquí van los conceptos que pedí aclarar aparte, condensados a la idea que los desbloqueó.

**No es una transcripción de las explicaciones**: es la versión corta para repasar en cinco minutos. Cada entrada tiene la duda original, la clave y, cuando aplica, la trampa de examen asociada.

**Cómo usarlo:** leer al empezar cada sesión, junto con el registro de errores del plan. Cuando una entrada ya resulte obvia dos sesiones seguidas, marcarla como asentada y dejar de leerla.

---

## Índice

1. [Coverage item](#1-coverage-item)
2. [BVA — Boundary Value Analysis](#2-bva--boundary-value-analysis)
3. [La cadena de términos](#3-la-cadena-de-términos)
4. [Error, defect, failure, root cause](#4-error-defect-failure-root-cause)
5. [Defect clusters y risk-based testing](#5-defect-clusters-y-risk-based-testing)
6. [Tests wear out vs regresión automatizada](#6-tests-wear-out-vs-regresión-automatizada)
7. [Los dos principios que se confunden](#7-los-dos-principios-que-se-confunden)
8. [La frontera analysis / design / implementation](#8-la-frontera-analysis--design--implementation)

---

## 1. Coverage item

**Duda:** qué es exactamente y en qué se diferencia de un test case.

**La clave:** es **cada casilla que hay que tocar** para poder decir que has probado algo del todo. Sin esa lista no hay porcentaje posible.

```
Cobertura = casillas tocadas ÷ casillas totales × 100
```

**La lista no la inventas tú, te la da la técnica.** Eso es lo que hace el resultado comprobable en vez de opinable: otra persona con la misma técnica llega a la misma lista.

Campo de edad 18-65:

| Técnica | Coverage items | Cuántos |
|---|---|---|
| Equivalence partitioning | <18 · 18-65 · >65 | 3 |
| 2-value BVA | 17 · 18 · 65 · 66 | 4 |
| 3-value BVA | 17 · 18 · 19 · 64 · 65 · 66 | 6 |

**Coverage item vs test case:** el coverage item es *lo que hay que tocar*; el test case es *cómo lo tocas*. Un test case puede cubrir varios coverage items a la vez.

**Trampa:** no existe "la cobertura" a secas. Siempre es cobertura **respecto a una técnica concreta**. Y los coverage items se producen en **test design**, no en analysis ni en implementation.

*Imagen útil: examen de 6 preguntas. Las preguntas son los coverage items, tus respuestas son los test cases, tu nota es la cobertura.*

Secciones 1.4.3, 4.2

---

## 2. BVA — Boundary Value Analysis

**Duda:** qué significa la sigla y en qué se diferencian las dos variantes.

**La clave:** los defects se concentran en los **bordes** de un rango, no en el medio. El 40 en un campo de 18-65 no descubre nada; los problemas están en el 17, 18, 65 y 66, donde alguien escribió `>` en lugar de `>=`.

| Variante | Regla | Para 18-65 | Items |
|---|---|---|---|
| **2-value** | Cada frontera + su vecino de la partición de al lado | 17, 18, 65, 66 | 4 |
| **3-value** | Cada frontera + **ambos** vecinos | 17, 18, 19, 64, 65, 66 | 6 |

**Fórmula mental:** contar fronteras × 2 o × 3 según la variante.

**Restricción importante:** solo se aplica sobre **particiones ordenadas** (números, fechas, horas). Si el conjunto no tiene orden (métodos de pago, países), no hay fronteras y la técnica no aplica: ahí se usa equivalence partitioning a secas.

Sección 4.2.2 · Se trabaja a fondo en la tarea 3.3 (es K3)

---

## 3. La cadena de términos

**Duda:** test object, test basis, test condition, coverage item, test case y test procedure se confunden entre sí. *(Ha vuelto tres veces: si sigue sin agarrar, usar la analogía de abajo en vez de las definiciones.)*

### La analogía: un plano y un edificio

**Test basis = el plano. Test object = el edificio.** Probar es **comparar el edificio contra el plano**.

| Término | En la obra |
|---|---|
| Test object | El edificio. Lo que inspeccionas. |
| Test basis | El plano. De donde sacas qué comprobar. |
| Test condition | "La resistencia de la viga del segundo piso" |
| Coverage item | Los puntos concretos donde vas a medir |
| Expected result | Lo que dice el plano que debería medir |
| Actual result | Lo que marca tu instrumento en el edificio |

Los dos que se confunden juegan papeles **opuestos**: el plano dice lo que *debería* pasar, el edificio es lo que *pasa*.

**Las dos preguntas que los separan:**
- "¿De dónde saco qué comprobar?" → **test basis**
- "¿A qué le doy?" → **test object**

**Testability con la misma imagen:** un plano que dice "la viga debe ser resistente" no es testeable (no hay número que comparar); una viga tapiada a la que no puedes acceder tampoco, aunque el plano sea perfecto.

**Y el static testing:** un plano contradictorio se detecta **leyéndolo, sin pisar la obra**. Si la página 4 dice 500 kg y la 12 dice 300, ahí hay un defect.

### La cadena

**La clave:** no son una lista suelta, son una **cadena de producción**, y cada eslabón cae en una actividad distinta.

```
test condition  → qué probar       (test analysis)
coverage item   → qué contar       (test design)
test case       → cómo probar      (test design)
test procedure  → en qué orden     (test implementation)
```

Los dos que más se cruzan:

- **Test object** = lo que pruebas.
- **Test basis** = de dónde sacas *qué* probar (requisitos, especificaciones, código, riesgos).

**Work product** es el paraguas: cualquier artefacto del desarrollo. **Testware** son los work products que produce la prueba.

Ejemplo completo — formulario de registro con campo de edad 18-65:

| Término | En el ejemplo |
|---|---|
| Work product | El documento de requisitos |
| Test basis | Ese mismo documento |
| Test object | El formulario de registro |
| Test condition | "La validación del campo edad" |
| Coverage item | 17, 18, 19, 64, 65, 66 |
| Test case | Entrada 17 → esperado: rechazo |
| Test procedure | La secuencia ordenada de esos casos |

Secciones 1.4.1, 1.4.3

---

## 4. Error, defect, failure, root cause

**Duda:** por qué una especificación mal escrita es un *defect* y no un *error*.

**La clave:** **el error es el acto mental; el defect es lo que queda escrito.**

La malinterpretación ocurrió dentro de la cabeza y duró un instante: no se puede abrir, revisar ni corregir. El documento que salió de ahí sí existe y tiene número de página. Ese documento es el defect.

**Los defects no viven solo en el código.** El syllabus lo dice expresamente: también en documentación, en una especificación de requisitos o en un test script. Si el modelo mental es "defect = bug en el código", esta pregunta se falla.

**La cadena se lee en dos direcciones:**

```
Producción:    root cause → error → defect → failure
Descubrimiento: failure → [debugging] → defect → [root cause analysis] → error
```

**Nunca encuentras un error probando.** Encuentras un failure y caminas hacia atrás.

Escenario de referencia: el analista trabaja con prisa *(root cause)*, malinterpreta el requisito *(error)*, escribe la especificación mal *(defect)*, el desarrollador la implementa fielmente *(defect heredado)*, en producción el importe sale mal *(failure)*.

**Detalle que lo hace caro:** el defect nació al escribir la especificación; el failure se vio meses después. En ese hueco se propagó al código, a las pruebas y a la documentación de usuario. Eso es literalmente *early testing saves time and money*. Y solo lo habría cazado una **revisión de la especificación** (static testing): ningún test dinámico podía, porque el código hacía exactamente lo que el documento pedía.

Sección 1.2.3 · **Fallado en el test del bloque A**

---

## 5. Defect clusters y risk-based testing

**Duda:** cómo conectan los clusters con el risk-based testing.

**La clave:** los clusters alimentan el lado de la **probabilidad** del riesgo.

```
Risk level = risk likelihood × risk impact
```

Si un componente históricamente acumula defects, su *likelihood* es alta → sube su risk level → sube en prioridad de prueba.

**Precisión que el examen aprovecha:** los clusters informan de la **probabilidad, no del impacto**. Son factores **independientes**. Un componente puede acumular muchísimos defects y tener impacto bajo si es cosmético; otro puede tener un solo defect potencial e impacto catastrófico si maneja pagos.

**Los dos tipos, por el momento en que aparecen:**

- **Predichos** (antes de probar): complejidad alta, tecnología nueva para el equipo, código muy modificado, historial de problemas, desarrollo con prisas, muchas manos.
- **Observados** (durante el testing o en operación): dónde salen los defects de verdad.

**No es una entrada de una sola vez, es un bucle:** predices → pruebas → observas → **reasignas esfuerzo**. Ese último paso es la consecuencia práctica: el principio justifica cambiar el plan a mitad de proyecto cuando los datos contradicen la predicción.

**Trampa por cruce de principios:** si reaccionas a un cluster ejecutando **las mismas** pruebas más veces, chocas con *tests wear out* y no encontrarás nada. La reacción correcta es diseñar pruebas **nuevas** y más profundas sobre esa zona.

Secciones 1.3, 5.2

---

## 6. Tests wear out vs regresión automatizada

**Duda:** parece una contradicción dentro del propio principio.

**La clave está en una palabra del enunciado:** las pruebas repetidas son menos eficaces para detectar defects **nuevos**. No dice que sean inútiles: dice que pierden capacidad de *descubrimiento*.

**Por qué la regresión es distinta:** un regression test no se ejecuta dos veces sobre el mismo código, **se ejecuta sobre código que ha cambiado**. El test es el mismo, el objeto bajo prueba no.

| | Buscar defects nuevos | Detectar regresiones |
|---|---|---|
| Qué pregunta | ¿Hay algo que no sabíamos? | ¿Sigue funcionando lo que funcionaba? |
| Sobre qué corre | El mismo código | Código modificado |
| Efecto de repetir | Se agota | Es su función |

Un regression test es un **centinela**: su valor no está en cuántos defects encuentra, sino en la confianza que da cuando no encuentra ninguno. Un centinela que nunca da la alarma está haciendo bien su trabajo.

**Por qué el syllabus dice "automated":** es economía. El rendimiento por ejecución es bajo (casi siempre pasa). Si repite una persona, gastas horas caras en algo de rendimiento bajo. Si repite una máquina, el coste marginal es casi cero, y entonces rendimiento bajo sigue mereciendo la pena porque el coste de **no** detectar la regresión es alto.

**Síntesis:** una suite madura tiene dos poblaciones conviviendo.

- **Conjunto estable automatizado** → detectar cambios no deseados. La repetición *es* el valor.
- **Conjunto rotatorio** → descubrir defects nuevos. Aquí sí aplica el desgaste, y la respuesta es modificar pruebas y datos, y escribir nuevas.

El principio habla del segundo grupo; el matiz protege al primero.

**Otra repetición legítima:** *confirmation testing*. Tras corregir un defect se vuelve a ejecutar exactamente la prueba que falló. Repetición con propósito, y nadie diría que está desgastada.

**Distractores típicos:** que la regresión automatizada no aporta valor a largo plazo, que ninguna prueba debería ejecutarse más de una vez, que hay que reescribir la suite entera cada iteración. Las tres exageran el principio e ignoran el matiz.

Sección 1.3

---

## 7. Los dos principios que se confunden

**Duda:** el primero y el séptimo suenan casi igual.

**La clave:** hablan de límites distintos.

| Principio | Qué dice | Sobre qué habla |
|---|---|---|
| **1. Testing shows the presence, not the absence of defects** | El testing no puede demostrar que no queden defects | Los límites del **testing** |
| **7. Absence-of-defects fallacy** | Ausencia de defects ≠ éxito del sistema | Los límites de la **calidad técnica** |

El séptimo, completo: puedes probar a fondo todos los requisitos especificados y corregir todos los defects encontrados, y aun así entregar un sistema que no cubre las necesidades ni expectativas de los usuarios, que no ayuda a los objetivos de negocio del cliente, o que es inferior a la competencia.

**Cómo distinguirlos en una pregunta:** si el escenario habla de *no haber encontrado defects* → principio 1. Si habla de un sistema *correcto pero inútil o rechazado* → principio 7 (y suele venir acompañado de la distinción verification/validation).

Sección 1.3

---

## 8. La frontera analysis / design / implementation

**Duda:** los conceptos del párrafo sobre los dos matices de test analysis y test design.

**La clave que unifica todo:** **analysis y design producen descripciones; implementation produce las cosas.** Donde veas *"X requirements"* → design. Donde veas *"X"* a secas → implementation.

### Test analysis tiene dos trabajos

1. **Decidir qué probar** → leer el test basis y sacar las *test conditions*, priorizadas con sus riesgos.
2. **Examinar críticamente lo que lee** → buscar defects en el **test basis** y valorar la **testability** del test object.

El segundo es el que se pregunta y el que se olvida. Por eso el test analysis produce **dos** salidas: test conditions priorizadas **y defect reports sobre el test basis**.

### Testability

Es lo fácil que resulta probar algo. Funciona en dos planos:

- **Del test basis:** "el sistema debe ser rápido" no es testeable, no hay nada que comparar. "El 95% de las peticiones responde en menos de 2 s" sí lo es.
- **Del test object:** ¿puedes controlar las entradas? ¿observar el estado interno? ¿hay interfaces por donde entrar? Un componente sellado tiene testability baja aunque el requisito sea perfecto.

### Por qué el análisis es static testing

**Static testing** = examinar work products **sin ejecutar el software** (capítulo 3). Si analizando el test basis descubres que el requisito 4.2 contradice el 7.1, has encontrado un defect sin ejecutar nada. Eso es static testing.

Defects típicos del test basis: **ambigüedades, contradicciones, omisiones, inexactitudes, duplicaciones, inconsistencias**.

### La frontera, en tabla

| Concepto | Actividad | Qué es en realidad |
|---|---|---|
| Coverage items | **Design** | La lista de casillas que tocar |
| Test data **requirements** | **Design** | "Necesito un usuario con saldo negativo" |
| Test data | **Implementation** | El registro creado en la base de datos |
| Test environment **requirements** | **Design** | "Servidor versión X, BD Y, mock de la pasarela" |
| Test environment | **Implementation** | El entorno montado, con stubs y drivers, y verificado |

**En design escribes la lista de la compra. En implementation vas al supermercado.**

**Trampa:** "preparar datos de prueba" suena a una sola cosa y son dos, repartidas en dos actividades distintas.

Secciones 1.4.1, 1.4.3

---

## Asentados

*Mover aquí las entradas que resulten obvias dos sesiones seguidas, para dejar de leerlas sin perderlas.*

(vacío)
