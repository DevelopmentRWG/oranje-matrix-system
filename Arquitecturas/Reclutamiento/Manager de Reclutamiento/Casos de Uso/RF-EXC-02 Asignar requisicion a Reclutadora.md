---
tags:
  - arquitectura
  - rol/manager-reclutamiento
  - caso-de-uso
  - excepcion
aliases:
  - CU RF-EXC-02
---

# 🪪 ID: RF-EXC-02
🏷️ **Nombre:** Asignar requisición a Reclutadora (caso VIP / balanceo)

**Historia:**
**Excepción al modelo Self-Pick (RR-01).** El Manager asigna manualmente una requisición a una Reclutadora específica saltándose el Self-Pick. Aplica solo en escenarios excepcionales: requisición de hotel VIP que debe ir a la Reclutadora más senior, balanceo de carga cuando una Reclutadora está saturada y nadie toma la requisición, ausencia del Líder de Grupo de la zona.

**Criterios de aceptación:**
La acción rompe el Self-Pick y requiere justificación obligatoria. Queda en log auditable (regla RR-12). La Reclutadora seleccionada recibe notificación inmediata. El semáforo de la requisición cambia a Amarillo. La requisición aparece marcada como "Asignada por Manager" en la bandeja de la Reclutadora.

**Documentación:**
- PRD: PRD-RECL-03 Manager
- Flow: Asignación manual excepcional
- Prototipo: (link de Figma)

**Flujo:**
`Bandeja de Autorizadas` → MANUAL → `Selecciona requisición` → `Click "Asignar manual a Reclutadora"` → `Selecciona Reclutadora destino + justificación obligatoria (VIP / balanceo / ausencia Líder)` → `Confirmar` → AUTOMATICO → `Reclutadora recibe la requisición en su bandeja + Marca como "Asignada por Manager" + Semáforo Amarillo + Notificación + Registro de excepción en log`
