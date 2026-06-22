---
tags:
  - arquitectura
  - rol/business-developer
  - caso-de-uso
aliases:
  - CU RF-V-02
---

# 🪪 ID: RF-V-02
🏷️ **Nombre:** Crear perfil del hotel (Azul Claro)

**Historia:**
Tras la visita en frío al prospecto, el BD recopila los datos del hotel y los carga en el sistema: email, teléfono, nombre y cargo del contacto, necesidad del negocio, tamaño y cantidad estimada de personal. Esta acción mueve el prospecto de Gris a **Azul Claro**.

**Criterios de aceptación:**
Datos obligatorios: email (formato válido), teléfono (formato válido), nombre del contacto, cargo, necesidad del negocio (mín. 30 caracteres). Tamaño y cantidad estimada son opcionales. Al guardar, el status pasa automáticamente a Azul Claro y notifica al BDC del avance.

**Documentación:**
- PRD: PRD-VENTAS-02 Business Developer
- Flow: Crear perfil del hotel
- Prototipo: (link de Figma)

**Flujo:**
`Detalle de prospecto en Gris` → MANUAL → `Click "Crear perfil"` → `Llena email, teléfono, contacto, cargo, necesidad del negocio (mín. 30 caracteres)` → `Tamaño y cantidad estimada opcional` → `Confirmar` → AUTOMATICO → Si validaciones OK → `Guarda perfil + Status pasa a Azul Claro + Notifica al BDC + Línea de tiempo actualizada` / Si error → `Bloquea con mensaje claro`
