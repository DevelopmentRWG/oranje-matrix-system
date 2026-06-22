---
tags:
  - arquitectura
  - rol/colaborador
  - caso-de-uso
aliases:
  - CU RF-C-04
---

# 🪪 ID: RF-C-04
🏷️ **Nombre:** Activar disponibilidad voluntaria (Amarillo)

**Historia:**
El Colaborador que se encuentra libre (Verde fuerte, Naranja o Rosa) desea declarar que está disponible para recibir una asignación temporal. Desde la app activa el toggle de disponibilidad voluntaria. El sistema solicita confirmación explícita antes de ejecutar el cambio. Al confirmar, el estado del colaborador transita a **Amarillo (Disponible voluntario)** de forma inmediata, sin aprobación de ningún otro rol (RR-C-02). Esta es la **única transición de estado que el Colaborador activa de forma autónoma**. Amarillo es una declaración de disponibilidad, no una asignación; el colaborador queda visible en el Pool como disponible voluntario pero sigue sin [[Core/Módulos/Schedule|Schedule]] ni [[Timesheet]] activos hasta que la [[Reclutadora]] lo asigne (→ Café). El colaborador también puede desactivar Amarillo para regresar a Verde fuerte cuando ya no desea estar disponible.

**Criterios de aceptación:**
El toggle solo está disponible si el colaborador está en estado Verde fuerte, Naranja o Rosa; en cualquier otro estado el sistema lo bloquea con el mensaje correspondiente. El sistema requiere confirmación modal con botón "Confirmar disponibilidad" antes de ejecutar el cambio (RR-C-02). Al confirmar, el estado transita inmediatamente a Amarillo. Confirmación al colaborador: *"Quedaste registrado como disponible. Reclutamiento puede asignarte"*. En Amarillo, el colaborador no tiene asignación activa, no puede ponchar. Si el colaborador desactiva el toggle, el estado regresa a Verde fuerte y aparece la confirmación: *"Ya no apareces como disponible voluntario"*.

**Documentación:**
- PRD: PRD-COLAB-01
- Flow: [[Semáforo del Colaborador]] — Transición Amarillo
- Prototipo: (link de Figma)

**Flujo:**
`App → Sección Disponibilidad` → MANUAL → `Activa toggle "Estoy disponible"` → `Sistema muestra modal de confirmación: "¿Confirmas que estás disponible para una asignación temporal?"` → `Colaborador toca "Confirmar disponibilidad"` → AUTOMATICO → Si estado válido (Verde fuerte / Naranja / Rosa) → `Estado → Amarillo · Colaborador aparece en Pool como disponible voluntario · Confirmación: "Quedaste registrado como disponible. Reclutamiento puede asignarte"` / Si estado no válido (Café / Morado / Rojo / Gris / Negro) → `Bloquea · Muestra: "No puedes modificar tu disponibilidad en tu estado actual. Contacta a Reclutamiento"` / Si ya está en Café (asignación activa) → `Bloquea · Muestra: "No puedes declararte disponible mientras tienes una asignación activa"`
