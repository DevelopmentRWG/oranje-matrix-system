---
tags:
  - arquitectura
  - rol/manager-reclutamiento
  - caso-de-uso
  - excepcion
aliases:
  - CU RF-EXC-01
---

# 🪪 ID: RF-EXC-01
🏷️ **Nombre:** Tomar requisición personal (caso especial Manager)

**Historia:**
**Excepción al modelo Self-Pick (RR-01).** En situaciones extraordinarias —cobertura urgente sin Reclutadora disponible, requisición VIP que requiere atención directa, falta de personal por ausencia masiva— el Manager toma personalmente una requisición y la trabaja como si fuera Reclutadora. Es una intervención excepcional, no su tarea diaria.

**Criterios de aceptación:**
La acción rompe el Self-Pick y por eso requiere justificación obligatoria. Queda en log auditable (regla RR-12). La requisición pasa a una bandeja "Mis Tomadas (Manager)" diferenciada visualmente. El semáforo cambia a Amarillo automáticamente. Reportes y métricas distinguen las requisiciones tomadas por Manager vs por Reclutadora.

**Documentación:**
- PRD: PRD-RECL-03 Manager
- Flow: Self-Pick excepcional Manager
- Prototipo: (link de Figma)

**Flujo:**
`Bandeja de Autorizadas` → MANUAL → `Click "Tomar como Manager"` → `Justificación obligatoria (motivo de la intervención)` → `Confirmar` → AUTOMATICO → `Mueve a "Mis Tomadas (Manager)" + Semáforo Amarillo + Bloquea para otros + Registra excepción en log auditable + Notifica al Líder de zona`
