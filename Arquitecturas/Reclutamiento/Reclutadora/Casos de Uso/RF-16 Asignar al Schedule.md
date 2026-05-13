---
tags:
  - arquitectura
  - rol/reclutadora
  - caso-de-uso
aliases:
  - CU RF-16
---

# 🪪 ID: RF-16
🏷️ **Nombre:** Asignar al Schedule

**Historia:**
Al asignar un colaborador a una posición, el sistema genera automáticamente la entrada correspondiente en el Schedule semanal del hotel. El colaborador aparece tanto en el Schedule del hotel como en su propio Schedule personal.

**Criterios de aceptación:**
La entrada en Schedule se genera en menos de 10s tras la asignación. Aparece en Schedule del hotel y del colaborador. Refleja horario, posición y modalidad correctos.

**Documentación:**
- PRD: PRD-RECL-02 Reclutadora
- Flow: Schedule automático
- Prototipo: (link de Figma)

**Flujo:**
`Asignación de colaborador (RF-15)` → AUTOMATICO → `Sistema genera entrada en Schedule del hotel` → `Refleja en Schedule personal del colaborador` → `Notifica al Manager de Área`
