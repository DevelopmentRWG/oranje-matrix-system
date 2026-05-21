---
tags:
  - arquitectura
  - rol/manager-general
  - caso-de-uso
aliases:
  - CU RF-H-25
---

# 🪪 ID: RF-H-25
🏷️ **Nombre:** Enviar reporte a dirección

**Historia:**
Tras generar un reporte ejecutivo (RF-H-24), el Manager General lo envía formalmente a dirección por email o link interno. Puede programar envío recurrente (semanal / mensual / trimestral) para que el sistema lo genere y envíe automáticamente. Es el canal oficial por el que dirección recibe la información operativa del hotel.

**Criterios de aceptación:**
El reporte debe estar generado previamente (RF-H-24). Destinatarios obligatorios (mín. 1 directivo o email válido). Asunto obligatorio (mín. 10 caracteres). Si se programa envío recurrente, la frecuencia es obligatoria. Queda en histórico con destinatario, asunto, fecha y estado (enviado / leído).

**Documentación:**
- PRD: PRD-HOTEL-04 Manager General
- Flow: Envío de reporte ejecutivo
- Prototipo: (link de Figma)

**Flujo:**
`Sidebar → Reportes → Vista previa de reporte (post RF-H-24)` → MANUAL → `Click "Enviar a dirección"` → `Selecciona destinatarios (lista de directivos o emails válidos)` → `Llena asunto (mín. 10 caracteres)` → `Mensaje opcional (máx. 1000 caracteres)` → `Marca "Programar envío recurrente" opcional` → Si recurrente → `Selecciona frecuencia (Semanal / Mensual / Trimestral)` → `Confirmar` → AUTOMATICO → `Envía reporte por email/link interno + Registra en histórico (destinatario / asunto / fecha / estado) + Si recurrente, programa próximo envío + Notifica al GM cuando se lee`
