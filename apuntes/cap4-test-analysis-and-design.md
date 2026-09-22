# Apuntes · Cap. 4 — Test Analysis and Design

Entradas 1-2. Índice general en [`00-indice.md`](00-indice.md).

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
