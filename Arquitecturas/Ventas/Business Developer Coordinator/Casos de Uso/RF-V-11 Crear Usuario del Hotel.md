---
tags:
  - arquitectura
  - rol/bdc
  - caso-de-uso
aliases:
  - CU RF-V-11
---
H
# 🪪 ID: RF-V-11
🏷️ **Nombre:** Crear Usuario del Hotel

**Historia:**
Antes de aprobar la conversión de un prospecto a cliente, el BDC debe crear el **Usuario del Hotel** en el sistema. Este usuario será el responsable principal del hotel en la plataforma (Manager de Área o Manager General) y recibirá las credenciales tras la aprobación. Es la **precondición obligatoria** de la conversión (RR-V-02): sin Usuario del Hotel, el botón "Aprobar conversión" queda bloqueado.

**Criterios de aceptación:**
Solo el BDC puede crear el Usuario del Hotel (acción exclusiva). Email único en el sistema. Rol obligatorio: Manager de Área o Manager General (jerarquía simple o extendida). Al crear, el sistema guarda el usuario pero NO envía credenciales aún — espera la aprobación de conversión. El botón "Aprobar conversión" se habilita en cuanto existe el Usuario del Hotel.

**Documentación:**
- PRD: PRD-VENTAS-03 BDC
- Flow: Crear Usuario del Hotel
- Prototipo: (link de Figma)

**Flujo:**
`Detalle de prospecto en Rosa con T&C validado → Sidebar Conversión` → MANUAL → `Click "Crear Usuario del Hotel"` → `Llena email (único), nombre completo, rol asignado (Manager de Área / Manager General), teléfono opcional, notas opcional` → `Confirmar` → AUTOMATICO → Si email único → `Usuario creado + Habilita botón "Aprobar conversión" + Log auditable` / Si email duplicado → `Bloquea con "Este email ya está registrado en el sistema"`

> [!info]
> El email de bienvenida al usuario del hotel NO se envía en este momento. Se envía cuando el BDC aprueba la conversión (RF-V-12) como parte del Trigger Automático.
