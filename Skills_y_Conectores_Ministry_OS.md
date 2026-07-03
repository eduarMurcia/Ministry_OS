# Skills y Conectores Necesarios — Ministry OS (v1)

**Fecha:** Julio 2026 · última actualización 2026-07-03 (primera revisión mensual automática)
**Metodología:** cada recomendación está mapeada contra una capacidad ya cerrada en `Alcance_v1_Ministry_OS.md`. No se incluye nada que no resuelva una necesidad ya validada, siguiendo el principio de simplicidad del propio proyecto.

---

## 1. Skills a usar desde ya (disponibles en este entorno)

| Skill | Para qué capacidad | Por qué |
|---|---|---|
| **docx** | Orden de servicio editable, manuscrito de sermón, comunicaciones pastorales | Ya existen plantillas reales de la iglesia; solo hay que digitalizarlas como documentos editables. |
| **pptx** | Presentación de la predicación | Ya decidido como una de las tres salidas del sermón. |
| **xlsx** | Directorio de personas (miembros/nuevos/visitantes), informes contables, control de asistencia y grupos | Es la forma más simple de tener una "base de datos" sin construir software todavía. |
| **pdf** | Exportar boletines y documentos listos para imprimir o compartir | El orden de servicio y los tratados terminan siempre en PDF. |
| **canvas-design** | Panfletos, tratados, material gráfico por ministerio (niños, jóvenes, damas, evangelismo) | Permite diseño original sin depender de una cuenta externa de pago. |
| **schedule** | Recordatorios recurrentes (preparar boletín cada sábado, revisar asistencia cada domingo) | Automatiza lo repetitivo sin necesitar un motor propio todavía. |
| **skill-creator** | Construir a futuro skills propias (ej. "Sermon Builder", "Bulletin Generator") | Solo tiene sentido una vez el flujo esté validado manualmente al menos una vez — no antes. |
| **productivity:task-management / memory-management / update** | Seguimiento del proyecto mismo | Ya en uso desde hoy (TASKS.md, CLAUDE.md, memory/). |

---

## 2. Conectores necesarios para la v1

| Conector | Para qué | Estado |
|---|---|---|
| **Google Calendar** | Integración del calendario de eventos, pedida explícitamente | Conectado y verificado (2026-07-03). Falta crear el calendario dedicado a la iglesia (el conector no permite crear calendarios, solo eventos en uno existente). |
| **Google Drive** | Respaldo/colaboración adicional al repo de GitHub | Conectado y verificado (2026-07-03) — funcionando. |
| **GitHub** | Que yo pueda operar el repo directamente (historial, archivos) sin depender de comandos de terminal manuales | Aún no conectado como MCP; se sigue usando git manual por terminal, que funciona bien. Conectar solo si empieza a ser fricción real. |

---

## 3. Gap real detectado: WhatsApp

Elegiste WhatsApp como único canal de comunicación con la congregación. **No existe un conector de WhatsApp en el registro oficial de MCP de Anthropic** (verificado directamente, y reconfirmado en la revisión mensual de 2026-07-03). Sin embargo, la revisión externa de julio 2026 encontró que ya existen proveedores de terceros que ofrecen servidores MCP de WhatsApp Business: **Wassenger, EZContact, AnythingMCP**, y el repositorio abierto **`whatsapp-mcp`** en GitHub. Esto cambia el diagnóstico: el gap ya no es "la tecnología no existe", sino "hay que integrar un servicio de terceros con tus propias credenciales de WhatsApp Business" — es trabajo de integración, no un conector que se pueda simplemente activar desde este entorno.

Dos caminos:

- Mantenerlo manual en la v1 (tú u otra persona sigue enviando los mensajes a los grupos existentes) — recomendado por ahora, no hay urgencia.
- Si más adelante se vuelve un cuello de botella real, evaluar con calma uno de esos proveedores de terceros (Wassenger, EZContact, AnythingMCP o el repo `whatsapp-mcp`) e integrarlo — ya no es un callejón sin salida técnico, solo requiere decidir cuándo se justifica el esfuerzo.

---

## 4. Descartados a propósito (para no sobre-dimensionar el proyecto)

| Conector | Por qué se descarta |
|---|---|
| HubSpot / cualquier CRM | No hay autoservicio ni pipeline de ventas; el directorio de personas es interno y manual. |
| PayPal / Stripe / Square / QuickBooks | Las donaciones se registran manualmente; no se procesan pagos en la v1. |
| Notion / Asana / Linear / Monday / ClickUp | Ya existe Todoist + TASKS.md; sumar otra herramienta de gestión sería duplicar sin necesidad. |
| Figma | Es para diseño de interfaces de software; no aplica porque todavía no hay plataforma web en construcción. |

---

## 5. Recomendación como director de proyecto

Estado al 2026-07-03: Google Calendar y Google Drive ya están conectados y verificados. Sigue así el orden recomendado:

1. ~~Autorizar Google Calendar~~ — hecho. Pendiente: crear manualmente el calendario dedicado a la iglesia (el conector no crea calendarios).
2. Dejar **GitHub** en pausa mientras el flujo manual (terminal) siga siendo suficiente; conectar solo si empieza a ser fricción real.
3. No integrar **WhatsApp** todavía, aunque ya se identificaron proveedores viables (Wassenger, EZContact, AnythingMCP, `whatsapp-mcp`) — es trabajo de integración con credenciales propias, solo se justifica si el canal manual se vuelve un cuello de botella real.
4. No crear ninguna skill nueva (vía skill-creator) hasta producir al menos un caso real de punta a punta con las skills genéricas ya disponibles (docx/pptx/xlsx/canvas-design) — esto es exactamente el "walking skeleton" que ya habíamos acordado como siguiente paso natural antes de ARC-001.
5. Video, transcripción y el "Ministry Platform AI" de ACST (ChMS con IA nativa sobre MCP) quedan como referencia de estado del arte a futuro — no ameritan evaluación todavía; son capacidades de largo plazo, no de la v1.

Esta sección se revisa automáticamente el 1° de cada mes (auditoría interna + búsqueda externa).
