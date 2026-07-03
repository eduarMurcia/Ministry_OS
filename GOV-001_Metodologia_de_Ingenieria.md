# GOV-001 — Metodología de Ingeniería

| Campo | Valor |
|---|---|
| ID | GOV-001 |
| Título | Metodología de Ingeniería |
| Versión | 0.1 |
| Estado | Borrador |
| Autor | Eduard (con asistencia de Claude) |
| Última revisión | 2026-07-03 |
| Dominio | Gobernanza (GOV) |
| Dependencias | ARC-001, DOC-001 |
| Relacionado con | — |

---

## 1. Propósito

Definir cómo se toman, documentan y revisan las decisiones de Ministry OS, y qué debe cumplirse antes de marcar un documento o desarrollo como terminado.

Aplica el mismo principio de proporcionalidad de DOC-001 §2: esta metodología es la mínima necesaria para un equipo pequeño con cinco documentos, no un proceso de comité para una organización grande.

## 2. Flujo de decisión

1. **Definir el problema real** — no hipotético. (Ejemplo real: no "¿qué capacidades podría tener una iglesia?" sino "¿qué necesita la Primera Iglesia Bíblica Bautista de Montenegro hoy?").
2. **Investigar estado del arte** antes de diseñar desde cero — ya se hizo con Planning Center/Breeze en `Mapa_Capacidades_ChMS.md`, y aplica a cualquier decisión futura (tecnológica, metodológica, de contenido).
3. **Comparar alternativas y decidir.**
4. **Documentar la decisión** — como entrada en el registro de decisiones (sección 4) si es de fondo/arquitectónica, o directamente en el documento correspondiente si es de alcance operativo.
5. **Validar con un caso real** antes de generalizar — el mismo criterio ya aplicado en ARC-001 (dos procesos reales antes de expandir a los demás).
6. **Marcar como Vigente** una vez validada (ver criterios en sección 5).

## 3. Quién decide

Eduard tiene la decisión final. Cualquier colaborador puede proponer, pero ninguna propuesta se acepta si no se puede ubicar en el Modelo Conceptual (ARC-001): qué rol la usa, qué capacidad satisface, qué proceso mejora, qué recurso consume. Esta regla ya se estableció informalmente durante el diseño de ARC-001; aquí queda formalizada.

## 4. Registro de decisiones (ADR)

Formato mínimo por decisión: **Contexto → Decisión → Consecuencias**. No se crea un archivo por decisión mientras quepan en esta tabla; si el registro crece más allá de ~10 entradas, se promueven a archivos individuales (`ADR-NNN_Título.md`), igual que la regla de carpetas de DOC-001 §6.

| # | Contexto | Decisión | Consecuencias |
|---|---|---|---|
| 1 | Público inicial hispanohablante; documentar en dos idiomas duplica tiempo y tokens | Idioma oficial del proyecto: español | Internacionalización se evalúa solo tras una versión estable |
| 2 | Riesgo de sobre-diseñar una plataforma para "cualquier iglesia" sin validar con una real | Ministry OS se construye primero para la Primera Iglesia Bíblica Bautista de Montenegro, con ambición de plataforma completa a futuro | El modelo conceptual se ancla en casos reales antes de generalizarse a otros contextos |
| 3 | Ya existen ChMS maduros (Planning Center, Breeze) que cubren lo operativo | No reinventar capacidades ya validadas por el mercado; enfocar la diferenciación en la capa creativa/de conocimiento que ningún ChMS cubre | El Alcance v1 y ARC-001 se apoyan en `Mapa_Capacidades_ChMS.md` en vez de partir de cero |
| 4 | Riesgo detectado de tener más gobernanza que contenido | La arquitectura documental (DOC-001) y esta metodología se mantienen deliberadamente simples, y crecen solo cuando un documento real lo justifique | Se descartó el ciclo de vida de 9 estados y las 10 áreas de conocimiento originalmente imaginadas |

## 5. Criterios antes de marcar algo como Vigente / Terminado

- ¿Resuelve una necesidad real, no hipotética?
- ¿Está documentado?
- ¿Se validó con al menos un caso concreto?
- ¿Es la solución más simple que resuelve el problema?

Si alguna respuesta es negativa, el documento o desarrollo permanece en **Borrador**.

## 6. Qué NO define este documento todavía

No define un proceso de aprobación por comité, ni SLAs de revisión, ni estándares detallados por tipo de Skill/GPT/MCP — eso se crea cuando exista el primer desarrollo real de ese tipo (probablemente al construir la primera Skill propia de Ministry OS), no antes.

## 7. Estado de los documentos fundacionales

Con este documento, los tres pilares iniciales quedan cerrados: **ARC-001** (qué existe y cómo se relaciona), **DOC-001** (cómo se organiza el conocimiento), **GOV-001** (cómo se decide). El siguiente trabajo no es generar más documentos fundacionales, sino cerrar los procesos operativos que ARC-001 §7 dejó pendientes.
