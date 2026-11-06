# Automatización de Reclutamiento

Proyectos para automatizar el proceso de **atracción de talento** de un área de Recursos Humanos: un **tablero Kanban en Google Sheets** que gestiona el flujo de candidatos de punta a punta y **Claude (Anthropic)** como asistente para las tareas que requieren criterio.

> Este repositorio describe los proyectos a grandes rasgos. No contiene datos de candidatos, URLs internas ni información confidencial de la organización.

## Objetivo

Automatizar lo mecánico del proceso (registro, seguimiento, recordatorios, invitaciones y correos) para no depender de un asistente de IA en el día a día, y reservar a Claude para lo que aporta más valor: **búsqueda de perfiles, filtrado y mensajes personalizados**.

---

## 1. Tablero de Reclutamiento (Kanban en Google Sheets)

Tablero Kanban construido sobre **Google Sheets + Google Apps Script** que concentra todas las vacantes y candidatos.

**Etapas del flujo (ejemplo):** Contactado → Entrevista agendada → Entrevistado → Terna → Oferta → Contratado / Descartado

**Funcionalidades principales**

- **App web para celular** (Apps Script) para consultar y actualizar el tablero desde el teléfono, con acceso restringido a usuarios del dominio.
- **Panel / dashboard** con el estado de cada vacante y candidato.
- **Alta rápida de candidatos** como «Contactado» desde la app, en el momento en que se envía el primer mensaje.
- **Invitación automática a entrevista** (Google Calendar, videollamada) al capturar la fecha.
- **Resumen diario por correo** a las 8:00 con pendientes y vacantes en riesgo.
- **Menú «Reclutamiento»** dentro de Sheets que prepara los correos del proceso (documentos para contratación, nuevo ingreso, equipo de cómputo, altas y bajas) como **borradores en Gmail**.
- **Tiempos objetivo por tipo de puesto** (Operativo, Administrativo, Especializado, Gerencial) contados desde la fecha de requisición, alineados al proceso documentado bajo ISO.
- **Acceso de solo lectura** para colaboradores que dan seguimiento, y flujo de aprobación del jefe directo (en desarrollo).

**Stack:** Google Sheets · Google Apps Script · Gmail · Google Calendar

---

## 2. Flujo de reclutamiento asistido con Claude

Claude se usa como asistente en las etapas que requieren juicio y redacción:

1. **Búsqueda de candidatos** en bolsas de trabajo (p. ej. OCC) a partir del perfil de la vacante.
2. **Filtrado y evaluación** de CVs contra los requisitos del puesto.
3. **Mensajes personalizados** de primer contacto y seguimiento por WhatsApp y correo, con una plantilla y firma consistentes.
4. **Propuesta y agendado de entrevistas** respetando reglas de agenda (franjas horarias definidas, sin viernes, siempre por videollamada y con confirmación previa del reclutador).
5. **Convenciones estandarizadas**: claves de vacante (`REC-AAAA-NNN`), títulos de eventos (`CLAVE // NOMBRE DEL CANDIDATO`) y nomenclatura de contactos.

**Herramientas:** Claude (Cowork / Claude in Chrome) · Gmail · Google Calendar · Google Drive · WhatsApp

---

## Cómo se conectan

```
Vacante (requisición)
      │
      ▼
Claude: búsqueda y filtro ──► Mensaje personalizado (WhatsApp / correo)
      │
      ▼
Tablero Kanban (Sheets): alta como «Contactado»
      │
      ├─► Invitación automática a entrevista (Calendar)
      ├─► Resumen diario por correo
      └─► Borradores de correos del proceso (Gmail)
```

## Estado

En operación y mejora continua. Próximo paso: aprobación de procesos por el jefe directo desde la app del tablero.

## Autor

**Edgar Rojas** — Líder de Atracción de Talento · Lic. en Psicología (UNAM)
