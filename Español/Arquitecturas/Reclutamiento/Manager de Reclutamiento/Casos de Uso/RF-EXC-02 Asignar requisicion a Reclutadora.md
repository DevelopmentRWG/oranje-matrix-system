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
**Excepción al modelo Self-Pick colaborativo (RR-01).** El Manager asigna manualmente una requisición a una Reclutadora específica saltándose el Self-Pick. Aplica solo en escenarios excepcionales: requisición de hotel VIP que debe ir a la Reclutadora más senior, balanceo de carga cuando una Reclutadora está saturada y nadie toma la requisición, ausencia del Líder de Grupo de la zona. Bajo el modelo colaborativo (RR-15), esta asignación distingue dos modos: **agregar como participante** —la Reclutadora se suma a los reclutadores que ya trabajan la requisición sin desplazar a nadie— o **transferir** —se reasigna como dueña principal (ver RF-EXC-03). El caso habitual del Manager es **agregar como participante**.

**Criterios de aceptación:**
La acción es excepcional y requiere justificación obligatoria. Queda en log auditable (regla RR-12). La Reclutadora seleccionada recibe notificación inmediata. El semáforo de la requisición cambia a Amarillo (o se mantiene si ya estaba En proceso). La requisición aparece marcada como "Asignada por Manager" en la bandeja de la Reclutadora. Cuando el Manager la **agrega como participante**, la Reclutadora se une a los reclutadores activos sin desplazar a los existentes y comparte el avance de cobertura (RR-15). El evento queda registrado en el Historial de la requisición (RR-16) con autor y fecha.

**Documentación:**
- PRD: PRD-RECL-03 Manager
- Flow: Asignación manual excepcional
- Prototipo: (link de Figma)

**Flujo:**
`Bandeja de Autorizadas` → MANUAL → `Selecciona requisición` → `Click "Asignar manual a Reclutadora"` → `Selecciona Reclutadora destino + modo (Agregar como participante / Transferir) + justificación obligatoria (VIP / balanceo / ausencia Líder)` → `Confirmar` → AUTOMATICO → `Reclutadora recibe la requisición en su bandeja + Marca como "Asignada por Manager" + Se une como reclutador participante sin desplazar a los existentes (modo Agregar) + Semáforo Amarillo + Notificación + Registra evento en el Historial de la requisición + Registro de excepción en log`
