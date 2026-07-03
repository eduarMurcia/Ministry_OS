# DOC-001 — Arquitectura del Conocimiento

| Campo | Valor |
|---|---|
| ID | DOC-001 |
| Título | Arquitectura del Conocimiento |
| Versión | 0.1 |
| Estado | Borrador |
| Autor | Eduard (con asistencia de Claude) |
| Última revisión | 2026-07-03 |
| Dominio | Arquitectura (ARC) |
| Dependencias | ARC-001 |
| Relacionado con | GOV-001 (pendiente) |

---

## 1. Propósito

Definir cómo se identifica, clasifica y versiona el conocimiento de Ministry OS, para que documentos, investigaciones y decisiones se puedan encontrar y relacionar entre sí sin depender de la memoria de una conversación.

## 2. Principio rector: proporcionalidad

Antes de listar reglas, una advertencia que aplica a todo este documento: la arquitectura documental debe ser tan simple como el proyecto lo permita hoy, y crecer solo cuando un documento real lo justifique. Ya identificamos como riesgo propio de este proyecto tener más gobernanza que contenido gobernado. Este documento define **lo mínimo necesario para los 5 documentos que existen ahora mismo**, no una taxonomía especulativa para cientos de documentos que todavía no existen.

## 3. Identificador de documentos

Formato: `PREFIJO-NNN_Título.md`, ya en uso (`ARC-001_Modelo_Conceptual.md`).

Prefijos activos hoy — se abre uno nuevo solo cuando un documento no encaje en ninguno de estos:

| Prefijo | Área | Ejemplo actual |
|---|---|---|
| **ARC** | Arquitectura / modelo | ARC-001 |
| **DOC** | Arquitectura del conocimiento / documentación del propio sistema | DOC-001 (este documento) |
| **RES** | Investigación empírica (estado del arte, comparativas) | Mapa_Capacidades_ChMS |
| **OPS** | Decisiones operativas y de alcance | Alcance_v1, Skills_y_Conectores |
| **GOV** | Metodología y gobernanza | GOV-001 (pendiente) |

No se crean los prefijos DOM, TEC, IMP, REF, HIS previstos en la conversación original hasta que un documento real los necesite — evita clasificar en el vacío.

## 4. Metadata mínima obligatoria

Todo documento nuevo lleva la misma tabla usada en ARC-001: **ID, Título, Versión, Estado, Autor, Última revisión, Dominio, Dependencias, Relacionado con**. No se añaden más campos (Categoría, Etiquetas, etc.) hasta que la falta de alguno cause un problema real de búsqueda.

## 5. Ciclo de vida (simplificado)

```
Borrador → Vigente → Reemplazado / Archivado
```

Se descarta deliberadamente el ciclo de nueve estados (idea → research → experimento → propuesta → revisión → aprobado → publicado → deprecado → archivado) propuesto al inicio del proyecto: con un equipo pequeño y cinco documentos, esa granularidad no aporta información, solo fricción. Se puede volver a un ciclo más detallado si el equipo crece o el volumen de documentos lo justifica.

- **Borrador**: en discusión, puede cambiar de fondo.
- **Vigente**: es la versión que se usa para tomar decisiones.
- **Reemplazado / Archivado**: ya no aplica, pero se conserva por historial (nunca se borra un documento vigente, se marca y se referencia el que lo reemplaza).

## 6. Ubicación física

Todos los documentos viven en la raíz del repositorio, sin carpetas. Con cinco documentos, una carpeta por área añadiría navegación sin beneficio — `git` y la búsqueda de texto ya resuelven encontrar cualquier archivo por nombre o contenido.

**Regla de crecimiento:** se introduce una carpeta por prefijo únicamente cuando ese prefijo acumule más de 8–10 documentos. Hasta entonces, el nombre del archivo (con su prefijo) es suficiente organización.

## 7. Inventario actual de Knowledge Objects

| ID | Documento | Estado |
|---|---|---|
| OPS-001 (informal) | `Alcance_v1_Ministry_OS.md` | Vigente |
| RES-001 (informal) | `Mapa_Capacidades_ChMS.md` | Vigente |
| ARC-001 | `ARC-001_Modelo_Conceptual.md` | Vigente |
| OPS-002 (informal) | `Skills_y_Conectores_Ministry_OS.md` | Vigente |
| DOC-001 | `DOC-001_Arquitectura_del_Conocimiento.md` | Borrador (este documento) |

Los dos primeros documentos se crearon antes de que existiera esta numeración; se les asigna número informal aquí sin necesidad de renombrarlos — no vale la pena el churn de renombrar archivos ya enlazados en commits anteriores.

## 8. Qué NO resuelve este documento todavía

No define motores de búsqueda, base de datos de conocimiento, ni una plataforma de consulta. Con cinco archivos de texto en un repositorio git, ninguna de esas cosas resuelve un problema real todavía. Se revisita cuando el volumen de documentos haga que buscar a mano deje de ser suficiente.

## 9. Próximo documento derivado

- **GOV-001** — Metodología de Ingeniería (cómo se toman decisiones, cómo se revisa un documento antes de pasar de Borrador a Vigente).
