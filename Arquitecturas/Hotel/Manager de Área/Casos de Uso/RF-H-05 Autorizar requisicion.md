---
tags:
  - arquitectura
  - rol/manager-de-area
  - caso-de-uso
aliases:
  - CU RF-H-05
---

# 🪪 ID: RF-H-05
🏷️ **Nombre:** Autorizar requisición

**Historia:**
El Supervisor crea una requisición y la envía al Manager de Área para autorización. El Manager revisa que la requisición esté completa, justificada y correcta. Al autorizarla, la requisición se envía automáticamente a la bandeja de Reclutamiento (modelo Self-Pick), donde Reclutadoras y Líderes de Grupo pueden tomarla libremente. La autorización es la **capa de seguridad** del sistema (regla RR-H-02): garantiza que Oranje solo recibe requisiciones validadas por el hotel.

**Criterios de aceptación:**
Solo el Manager de Área puede autorizar (RR-H-02). La requisición debe tener al menos 1 posición registrada (RR-H-03). Al autorizar, el sistema calcula automáticamente la urgencia por posición (>120h Verde, 72-120h Amarillo, <72h Rojo), asigna el Inspector según zona, refleja las posiciones en el Schedule semanal y envía la requisición a la bandeja de Reclutamiento — todo en menos de 30s. Notifica al Supervisor del cambio de estado.

**Documentación:**
- PRD: PRD-HOTEL-03 Manager de Área
- Flow: Autorización de requisición
- Prototipo: (link de Figma)

**Flujo:**
`Bandeja "Pendientes de autorización"` → MANUAL → `Click en requisición` → `Revisa cabecera + posiciones + notas + Supervisor que la creó` → MANUAL → `Click "Autorizar"` → AUTOMATICO → `Valida que tenga ≥1 posición` → Si OK → `Cambia estado a Autorizada + Calcula urgencia (RF-H-08) + Asigna Inspector por zona (RF-H-09) + Refleja en Schedule (RF-H-10) + Envía a bandeja de Reclutamiento (RI-H-01) + Notifica al Supervisor` / Si no tiene posiciones → `Bloquea con mensaje "No tiene posiciones registradas..."`
