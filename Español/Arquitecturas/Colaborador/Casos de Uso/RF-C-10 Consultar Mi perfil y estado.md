---
tags:
  - arquitectura
  - rol/colaborador
  - caso-de-uso
aliases:
  - CU RF-C-10
---

# 🪪 ID: RF-C-10
🏷️ **Nombre:** Consultar Mi perfil y estado

**Historia:**
El Colaborador quiere revisar sus datos personales y conocer su estado actual en el [[Semáforo del Colaborador]]. Desde "Mi Perfil" ve todos sus datos capturados en las tres fases: datos básicos de la Fase 1 (capturados por la Reclutadora, solo lectura), datos laborales de la Fase 2, y datos de emergencia de la Fase 3. También ve el color y nombre de su estado actual en el semáforo. El Colaborador puede editar de forma limitada: su teléfono propio y sus datos de emergencia (contacto, teléfono, parentesco). Los datos sensibles como SSN/ITIN quedan bloqueados tras la aprobación de Fase 2 y solo pueden modificarse con intervención de la [[Reclutadora]].

**Criterios de aceptación:**
Vista de todos sus datos (Fase 1, 2 y 3) agrupados por sección. Estado del semáforo visible: color y nombre del estado actual (ejemplo: "Naranja — Fijo"). Campos editables por el propio colaborador: teléfono propio, nombre/teléfono/parentesco del contacto de emergencia. El cambio de datos de contacto y emergencia no requiere re-validación; se guarda de inmediato y se registra en el journal del colaborador. Campo SSN/ITIN: bloqueado tras la aprobación de Fase 2; muestra: *"Para modificar este dato, comunícate con tu Reclutadora"*. Teléfono con formato inválido bloquea el guardado con mensaje de error. Guardado de emergencia sin nombre del contacto: bloquea con mensaje de error. Solo ve sus propios datos (RR-C-01).

**Documentación:**
- PRD: PRD-COLAB-01
- Flow: Mi Perfil — Colaborador
- Prototipo: (link de Figma)

**Flujo:**
`App → Sección Mi Perfil` → AUTOMATICO → `Sistema carga datos del colaborador (Fase 1 + 2 + 3) y estado del semáforo` → MANUAL → `Colaborador revisa datos en secciones (datos básicos / datos laborales / datos de emergencia / estado del semáforo)` → `Toca "Editar" en campos permitidos (teléfono propio / datos de emergencia)` → `Modifica el valor` → `Guardar` → AUTOMATICO → Si datos válidos → `Sistema guarda el cambio · Registra en journal del colaborador · Confirmación: "Datos actualizados"` / Si teléfono con formato inválido → `Bloquea · Muestra: "Ingresa un número de teléfono válido"` / Si intenta editar SSN/ITIN → `Campo bloqueado · Muestra: "Para modificar este dato, comunícate con tu Reclutadora"`
