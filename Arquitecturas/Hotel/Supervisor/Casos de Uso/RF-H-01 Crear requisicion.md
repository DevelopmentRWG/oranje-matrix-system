---
tags:
  - arquitectura
  - rol/supervisor-hotel
  - caso-de-uso
aliases:
  - CU RF-H-01
---

# 🪪 ID: RF-H-01
🏷️ **Nombre:** Crear requisición

**Historia:**
Cuando el hotel detecta una necesidad de personal (cobertura de turnos, refuerzo en temporada, reemplazo por baja), el Supervisor crea una nueva requisición desde la app. Captura las posiciones, cantidad, modalidad, nivel de inglés, horarios, fecha de inicio y notas adicionales. La requisición queda como **borrador** (Verde manzana — En elaboración) hasta que el Supervisor la envía a autorización del Manager del Hotel.

**Criterios de aceptación:**
El sistema asigna automáticamente el número de requisición con formato `AAAAMMDDHHMM + Homoclave` (RR-H-04). Una requisición puede tener múltiples posiciones. La fecha de inicio debe ser futura. Si la requisición no tiene posiciones al salir del editor, se elimina físicamente (RR-H-07). El Supervisor puede crear desde mobile (RNF-H-04) o desktop.

**Documentación:**
- PRD: PRD-HOTEL-02 Supervisor
- Flow: Creación de requisición
- Prototipo: (link de Figma)

**Flujo:**
`Sidebar → Requisiciones → Click "Nueva Requisición"` → MANUAL → `Llena cabecera (notas adicionales)` → `Agrega posiciones (Posición + Cantidad + Modalidad + Inglés + Horario + Fecha de inicio)` → `Guardar borrador` → AUTOMATICO → `Sistema asigna número auto + Estado borrador (Verde manzana — En elaboración)` → MANUAL (más tarde) → `Click "Enviar a autorización"` (dispara RF-H-03)
