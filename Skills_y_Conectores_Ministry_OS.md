# Skills y Conectores Necesarios — Ministry OS (v1)

**Fecha:** Julio 2026
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
| **Google Calendar** | Integración del calendario de eventos, pedida explícitamente | Requiere autorización tuya en configuración de conectores. |
| **Google Drive** | Respaldo/colaboración adicional si se quiere además del repo de GitHub | Opcional — el repo ya cumple la función de persistencia. |
| **GitHub** | Que yo pueda operar el repo directamente (historial, archivos) sin depender de comandos de terminal manuales | Recomendado para agilizar, no imprescindible (ya funciona por terminal). |

---

## 3. Gap real detectado: WhatsApp

Elegiste WhatsApp como único canal de comunicación con la congregación, pero **no existe hoy un conector de WhatsApp en el registro de MCP disponible** (lo verifiqué directamente). Dos caminos:

- Mantenerlo manual en la v1 (tú u otra persona sigue enviando los mensajes a los grupos existentes) — recomendado por ahora.
- Si más adelante se vuelve un cuello de botella, investigar un proveedor de WhatsApp Business API de terceros e integrarlo como MCP propio — es trabajo de desarrollo, no una skill que se pueda simplemente activar.

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

Antes de conectar todo lo de la sección 2, propongo un orden:

1. Autorizar **Google Calendar** primero — es el único pedido explícito y no reemplaza nada que ya funcione.
2. Dejar **GitHub** y **Drive** en pausa mientras el flujo manual (terminal) siga siendo suficiente; conectar solo si empieza a ser fricción real.
3. No tocar **WhatsApp** todavía — es un problema de integración, no de activar un conector existente.
4. No crear ninguna skill nueva (vía skill-creator) hasta producir al menos un caso real de punta a punta con las skills genéricas ya disponibles (docx/pptx/xlsx/canvas-design) — esto es exactamente el "walking skeleton" que ya habíamos acordado como siguiente paso natural antes de ARC-001.
