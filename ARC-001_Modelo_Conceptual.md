# ARC-001 — Modelo Conceptual de Ministry OS

| Campo | Valor |
|---|---|
| ID | ARC-001 |
| Título | Modelo Conceptual de Ministry OS |
| Versión | 0.1 |
| Estado | Borrador |
| Autor | Eduard (con asistencia de Claude) |
| Última revisión | 2026-07-03 |
| Dominio | Arquitectura (ARC) |
| Dependencias | `Alcance_v1_Ministry_OS.md`, `Mapa_Capacidades_ChMS.md` |
| Relacionado con | DOC-001 (pendiente), GOV-001 (pendiente) |

---

## 1. Propósito

Este documento define los conceptos fundamentales de Ministry OS: qué existe en el dominio y cómo se relaciona. No describe software, plataforma ni inteligencia artificial — describe el ministerio mismo, de forma que cualquier tecnología futura pueda implementarse sin tener que rehacer este modelo.

## 2. Principios rectores

- **Knowledge First** — el conocimiento es el activo permanente; las tecnologías son implementaciones reemplazables.
- **Domain Driven** — el modelo parte de cómo funciona una iglesia real, no de las herramientas disponibles.
- **Capability Driven** — el sistema se organiza alrededor de lo que el ministerio necesita poder hacer, no alrededor de apps.
- **Technology Neutral** — ninguna tecnología es indispensable; toda pieza debe poder reemplazarse.
- **Modular** — cada componente puede añadirse, actualizarse o retirarse sin romper el resto.

## 3. Entidades del modelo

### 3.1 Ministerio
Contexto raíz del modelo. En la v1 existe una sola instancia: la Primera Iglesia Bíblica Bautista de Montenegro (Quindío).

### 3.2 Rol
Una función estable dentro del ministerio, independiente de qué persona la ocupe en un momento dado. Una persona puede ocupar varios roles; un rol puede tener varias personas.

Roles confirmados a partir de las plantillas reales de la iglesia:
- Pastor (enseñanza y predicación)
- Encargado de diezmos
- Maestro de Escuela Dominical (uno por grupo)

Roles pendientes de formalizar (identificados pero sin proceso definido todavía): Tesorería, Multimedia/Publicaciones, Secretaría.

### 3.3 Capacidad
Lo que el ministerio necesita poder hacer, con nombre estable (verbo + sustantivo), independiente de cómo se implemente. Ya cerradas en `Alcance_v1_Ministry_OS.md`, agrupadas en dos tipos:

- **Operativas** — administrar personas, informes contables, planificar servicios, asignar responsables, check-in de niños, grupos pequeños, eventos, comunicación, publicaciones, calendario y tareas.
- **Creativas / de conocimiento** — preparar sermones, diseñar contenido gráfico (y, a futuro, currículo, gestión de conocimiento, automatización, transcripción, reportes, comunicaciones pastorales, video/audio).

### 3.4 Proceso
La secuencia concreta y repetible mediante la cual se realiza una capacidad. Tiene entradas, pasos, salidas y un rol responsable.

Los dos procesos reales que ya tenemos documentados (con plantilla propia de la iglesia):
- **Armar el orden de servicio dominical** → realiza la capacidad "Planificar y coordinar servicios de adoración".
- **Elaborar el manuscrito de predicación** → realiza la capacidad "Preparar sermones".

El resto de capacidades de la v1 todavía no tienen su proceso específico documentado — queda como trabajo pendiente (ver sección 8).

### 3.5 Recurso
Reemplaza el término "herramienta". Se clasifica en cinco categorías: humano, documental, digital, tecnológico, inteligente. Un proceso consume y/o produce recursos.

Ejemplo: el proceso "elaborar el manuscrito de predicación" consume un recurso documental (la plantilla de manuscrito) y puede consumir un recurso inteligente (asistencia de IA para investigación); produce un recurso documental (el sermón escrito) y un recurso digital (la presentación).

### 3.6 Conocimiento (Knowledge Object)
Todo proceso genera o consume conocimiento: un documento, una decisión, un registro. En la v1 el conocimiento vive como archivos (plantillas, documentos, este mismo repositorio). La clasificación formal en áreas de conocimiento queda para DOC-001 — este documento no la anticipa para no repetir el error de gobernar antes de tener contenido que gobernar.

### 3.7 Dominio
Agrupación temática de capacidades relacionadas. Identificados hasta ahora: Administración, Adoración, Comunicación, Formación.

## 4. Relaciones del modelo

```
Rol ──tiene──> Capacidad ──se realiza mediante──> Proceso
                   │                                 │
                   └──pertenece a──> Dominio          ├──es responsabilidad de──> Rol
                                                       ├──consume/produce──> Recurso
                                                       └──genera──> Conocimiento
```

## 5. Aplicación al caso real

Dos instancias completas del modelo, usando lo que ya existe hoy en la iglesia:

**Caso 1 — Orden de servicio**
Rol: Pastor (+ responsables asignados por servicio) → Capacidad: *Planificar y coordinar servicios de adoración* → Proceso: *armar el orden de servicio dominical* → Recursos: plantilla de bulletin (documental) → Conocimiento generado: el boletín de cada domingo, acumulable como historial.

**Caso 2 — Sermón**
Rol: Pastor → Capacidad: *Preparar sermones* → Proceso: *elaborar el manuscrito de predicación* → Recursos: plantilla de manuscrito (documental), asistencia de IA (inteligente) → Conocimiento generado: el manuscrito y su presentación asociada.

Estos dos casos validan el modelo contra la realidad antes de extenderlo a las demás capacidades.

## 6. Qué NO es este documento

No define tecnología, base de datos, plataforma ni motores. Eso corresponde a los niveles Lógico e Implementación (Skills, conectores, workflows) ya tratados en `Skills_y_Conectores_Ministry_OS.md`, y a documentos de arquitectura técnica futuros.

## 7. Preguntas abiertas

- Los roles de Tesorería, Multimedia/Publicaciones y Secretaría existen como intención pero no tienen todavía un proceso ni capacidades formalmente asignadas.
- Falta definir el proceso para el resto de capacidades operativas (directorio de personas, informes contables, check-in de niños, grupos pequeños, eventos, calendario).
- Falta el proceso del servicio de miércoles (hoy solo existe la plantilla del domingo).

## 8. Próximos documentos derivados

- **DOC-001** — Arquitectura del Conocimiento (cómo se almacena, clasifica y versiona el conocimiento del proyecto).
- **GOV-001** — Metodología de Ingeniería.
- **Modelo de Capacidades detallado** — una ficha por capacidad con su proceso, recursos y rol responsable, expandiendo la sección 3.4 conforme se vayan definiendo.
