# Mapa de Capacidades — Extraído de ChMS existentes (Planning Center y Breeze/Tithely)

**Versión:** 0.1
**Fecha:** Julio 2026
**Propósito:** Servir de insumo empírico para el Modelo de Capacidades de Ministry OS, evitando construir la lista de capacidades ministeriales desde cero.
**Fuentes:** Planning Center (planningcenter.com, worshipresources.church) y Breeze ChMS / Tithely Church Management (breezechms.com).
**Método:** Se extrajeron los módulos/apps oficiales de cada plataforma, se tradujeron a capacidades estables (verbo + sustantivo, independientes de la herramienta, siguiendo el estilo de Business Capability Map de TOGAF) y se compararon entre sí.

---

## Tabla comparativa de capacidades

| Capacidad (nombre estable) | Planning Center | Breeze / Tithely | Notas |
|---|---|---|---|
| Administrar directorio de miembros | People (app central, hub de todo lo demás) | People (base de datos central) | Ambas plataformas organizan todo alrededor de un único registro de personas. Es el patrón más consistente entre ambas. |
| Registrar y conciliar donaciones | Giving | Giving | Cubren efectivo, cheque, online y "text-to-give"; generan reportes/estados de cuenta para donantes. |
| Planificar y coordinar servicios de adoración | Services (+ complemento Music Stand) | Service Planning (+ Song Library, integración SongSelect) | Incluye setlists, orden de servicio y biblioteca de canciones. |
| Programar y asignar voluntarios | Integrado dentro de Services (evita doble reserva de un voluntario) | Integrado dentro de Service Planning | No es un módulo aparte en ninguna de las dos: siempre vive dentro de la planificación de servicios. |
| Registrar asistencia y seguridad de niños | Check-Ins (con impresión de etiquetas y códigos de coincidencia padre-hijo) | Check-in dentro de Events (impresión de etiquetas) | Planning Center tiene un enfoque más fuerte en seguridad infantil (matching de códigos); Breeze lo trata como check-in general de eventos. |
| Gestionar grupos pequeños | Groups | Groups | Ambas permiten crear grupos, controlar membresía y asistencia. |
| Organizar eventos y registros con pago | Registrations | Events + Forms | Registro gratuito o pagado, reportes de asistencia por evento. |
| Crear formularios públicos | Embebido en Registrations/Check-Ins (no es app propia) | Forms (app independiente, vincula respuestas al perfil del miembro) | Breeze lo trata como capacidad de primera clase; Planning Center no. |
| Comunicar con la congregación (email/SMS masivo) | Distribuido entre apps vía Church Center, sin módulo unificado | Communication (mensajes individuales o masivos, programables) | Breeze centraliza esta capacidad; Planning Center la reparte. |
| Publicar contenido y sermones | Publishing (contenido de Church Center, enlace de sermones a YouTube) | Sites / Church Apps (constructor de sitio web y app) | Enfoques distintos: PC enlaza y organiza contenido ya existente; Tithely construye el sitio/app en sí. |
| Gestionar calendario y reservar espacios | Calendar (reserva de salas incluida) | Sin módulo dedicado; se resuelve dentro de Events | Planning Center trata la reserva de espacios como capacidad explícita. |
| Portal de autoservicio para miembros | Church Center (app para feligreses: dar, inscribirse, ver grupos, check-in) | Tithely App | Ambas ofrecen una cara "cliente" de la misma base de datos central. |

---

## Hallazgos clave

**1. El "hub" de personas confirma una intuición de Ministry OS, pero con un matiz importante.**
Ambas plataformas validan la idea de tener un registro central de personas del que cuelga todo lo demás. Sin embargo, ninguna de las dos modela **Roles** como Ministry OS los propone (Pastor, Secretaría, Tesorería como entidades de primer nivel con capacidades heredadas). Lo que existe en su lugar son permisos de administrador *por módulo* (ej. "Administrador de Giving", "Editor de Check-Ins"). Esto sugiere que el modelo de Roles de Ministry OS no está resuelto por el mercado actual — es una posible diferenciación real, no solo una preferencia interna.

**2. Ninguna herramienta trata la IA (ni ninguna tecnología) como un "recurso" formal.**
Confirma que ahí Ministry OS estaría aportando algo que hoy no existe en los ChMS líderes: tratar la inteligencia artificial (o cualquier tecnología) como un recurso intercambiable dentro del modelo de capacidades, en vez de dejarla fuera del sistema o integrarla de forma ad-hoc.

**3. Existe una división clara entre capacidades "operativas" (bien cubiertas) y "creativas/de contenido" (prácticamente ausentes).**
Planning Center y Breeze cubren muy bien lo administrativo: personas, dinero, asistencia, eventos, comunicación. Pero ninguna cubre capacidades como "Preparar sermón", "Diseñar contenido", "Enseñar niños" (currículo/pedagogía) o "Administrar documentos" en el sentido de producción de contenido — esas tareas hoy se resuelven fuera del ChMS, en herramientas sueltas (Word, Canva, ProPresenter, editoriales de currículo). Esto es relevante: es justo el espacio donde las Skills de IA (y por tanto Ministry OS) tendrían más que aportar, sin competir directamente con lo que Planning Center o Breeze ya resuelven bien.

**4. Ninguna de las dos es "modular" en el sentido que propone Ministry OS.**
Planning Center se acerca más (apps separadas, activables por separado), pero sigue siendo una suite cerrada de un solo proveedor. La idea de Ministry OS de que cualquier pieza (incluida la IA) sea reemplazable sin romper el resto del sistema no tiene equivalente directo en el mercado actual.

---

## Recomendación de uso

Este mapa debería tratarse como el **piso mínimo de capacidades operativas** que cualquier iglesia ya espera resolver de una forma u otra (aunque sea con hojas de cálculo). El Modelo de Capacidades de Ministry OS podría dividirse en dos bloques:

- **Capacidades operativas/administrativas** — ya validadas por el mercado (esta tabla). No requieren reinventarse, solo decidir si Ministry OS las absorbe, se integra con un ChMS existente, o las deja fuera de alcance.
- **Capacidades creativas y de conocimiento** — el hueco real detectado (preparación de contenido, enseñanza, diseño, documentación). Aquí es donde Ministry OS tiene espacio genuino para diferenciarse y donde las Skills de IA encajan de forma natural.
