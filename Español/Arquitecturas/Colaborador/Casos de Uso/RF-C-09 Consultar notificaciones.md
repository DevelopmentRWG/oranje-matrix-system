---
tags:
  - arquitectura
  - rol/colaborador
  - caso-de-uso
aliases:
  - CU RF-C-09
---

# 🪪 ID: RF-C-09
🏷️ **Nombre:** Consultar notificaciones

**Historia:**
El Colaborador recibe notificaciones del sistema sobre eventos relevantes a su perfil y operación: validación de alta aprobada o rechazada, nueva asignación, cambios de estado en el [[Semáforo del Colaborador]], recordatorios de ponche, resultado de reporte de accidente. Desde la app accede a la sección "Notificaciones" y ve la lista ordenada por fecha, distinguiendo leídas de no leídas. Al abrir la pantalla de notificaciones, el badge de notificaciones no leídas desaparece. La vista es de **solo lectura**.

**Criterios de aceptación:**
Lista de notificaciones propias ordenadas por fecha descendente (más recientes primero). Diferenciación visual entre notificaciones leídas y no leídas. Al abrir la sección, el badge (contador) de no leídas desaparece. Tipos de notificación incluidos: validación de alta aprobada, validación de alta rechazada o con correcciones, nueva asignación (hotel, posición, fechas), cambio de estado del semáforo, fin de asignación temporal, resultado de tarjeta de accidente cerrada, recordatorios de ponche (si aplica). Solo se muestran notificaciones propias (RR-C-01). Las notificaciones push (RNF-C-06) redirigen al colaborador a esta sección al tocarlas.

**Documentación:**
- PRD: PRD-COLAB-01
- Flow: Sistema de notificaciones — Colaborador
- Prototipo: (link de Figma)

**Flujo:**
`App → Sección Notificaciones (badge visible si hay no leídas)` → AUTOMATICO → `Badge desaparece al abrir la sección` → MANUAL → `Desplaza la lista de notificaciones (ordenada por fecha, más recientes primero)` → `Toca una notificación para verla en detalle` → AUTOMATICO → `Notificación marcada como leída · Muestra contenido completo de la notificación`
