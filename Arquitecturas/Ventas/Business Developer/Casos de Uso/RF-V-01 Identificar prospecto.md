---
tags:
  - arquitectura
  - rol/business-developer
  - caso-de-uso
aliases:
  - CU RF-V-01
---

# 🪪 ID: RF-V-01
🏷️ **Nombre:** Identificar prospecto (Gris)

**Historia:**
El BD detecta un hotel en su territorio que podría ser cliente. Crea un registro inicial en el sistema en status **Gris** capturando datos mínimos (nombre, ciudad, zona, geolocalización opcional). El prospecto queda visible en su Pipeline esperando el primer contacto.

**Criterios de aceptación:**
El BD solo puede identificar prospectos en su territorio asignado. Datos obligatorios: nombre, ciudad, zona. Geolocalización automática si se hace desde mobile. Se asigna automáticamente al BD que lo crea. Aparece en el Pipeline en menos de 2s.

**Documentación:**
- PRD: PRD-VENTAS-02 Business Developer
- Flow: Identificación de prospecto
- Prototipo: (link de Figma)

**Flujo:**
`Sidebar → Mi Territorio o Pipeline → Click "Identificar prospecto"` → MANUAL → `Llena nombre, ciudad, zona` → AUTOMATICO desde mobile → `Captura geolocalización` → MANUAL → `Origen del lead opcional + notas iniciales` → `Confirmar` → AUTOMATICO → `Crea registro en Gris + Asigna al BD + Aparece en Pipeline + Línea de tiempo iniciada`
