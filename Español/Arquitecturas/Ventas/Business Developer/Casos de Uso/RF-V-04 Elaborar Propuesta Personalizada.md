---
tags:
  - arquitectura
  - rol/business-developer
  - caso-de-uso
aliases:
  - CU RF-V-04
---

# 🪪 ID: RF-V-04
🏷️ **Nombre:** Elaborar Propuesta Personalizada

**Historia:**
Tras tener el perfil del hotel completo (Azul Claro), el BD elabora la **Propuesta Personalizada** con los servicios que Oranje ofrece, los precios y las condiciones comerciales. La propuesta se construye en el módulo Propuestas como borrador, luego se envía al hotel (RF-V-05), lo que hace que el prospecto pase a status **Verde**.

**Criterios de aceptación:**
La propuesta solo puede elaborarse para prospectos en status Verde o anteriores. Campos obligatorios: hotel destino, servicios propuestos, precios, condiciones generales (mín. 100 caracteres), vigencia. Adjuntos opcionales (PDF/DOCX, máx. 10 MB). Permite duplicar propuestas previas como plantilla.

**Documentación:**
- PRD: PRD-VENTAS-02 Business Developer
- Flow: Elaborar Propuesta Personalizada
- Prototipo: (link de Figma)

**Flujo:**
`Sidebar → Propuestas → Click "Nueva Propuesta"` → MANUAL → `Selecciona hotel destino (lista de mis prospectos en Azul Claro)` → `Selecciona servicios propuestos (catálogo)` → `Llena precios por servicio + condiciones generales (mín. 100 caracteres) + vigencia` → `Adjunta documentos opcional` → `Guardar borrador` → AUTOMATICO → `Borrador guardado` → MANUAL (más tarde) → `Click "Enviar al hotel"` (dispara RF-V-05)
