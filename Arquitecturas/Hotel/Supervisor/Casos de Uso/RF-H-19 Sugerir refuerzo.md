---
tags:
  - arquitectura
  - rol/supervisor-hotel
  - caso-de-uso
aliases:
  - CU RF-H-19
---

# 🪪 ID: RF-H-19
🏷️ **Nombre:** Sugerir refuerzo de personal

**Historia:**
Cuando el Supervisor consulta el Schedule semanal y detecta una posición vacante o con cobertura parcial, puede iniciar rápidamente una nueva requisición desde esa misma vista. El sistema **prefilla** los datos de la posición (posición, días vacantes, depto) en el formulario de Nueva Requisición — el Supervisor solo completa los campos faltantes y envía a autorización.

**Criterios de aceptación:**
La sugerencia se activa desde el módulo Schedule. El sistema pre-llena: posición, días vacantes, modalidad estándar. El Supervisor debe agregar la justificación (mín. 20 caracteres) y completar los demás campos. Al continuar, el flujo sigue como una nueva requisición regular (RF-H-01 → RF-H-03).

**Documentación:**
- PRD: PRD-HOTEL-02 Supervisor
- Flow: Sugerir refuerzo
- Prototipo: (link de Figma)

**Flujo:**
`Módulo Schedule` → MANUAL → `Detecta posición vacante / parcial` → `Click "Sugerir refuerzo"` → AUTOMATICO → `Pre-llena formulario de Nueva Requisición con posición, días vacantes, modalidad estándar` → MANUAL → `Agrega justificación (mín. 20 caracteres)` → `Completa campos restantes (cantidad / inglés / horario / fecha de inicio)` → `Click "Continuar a Nueva Requisición"` → Sigue flujo de RF-H-01 → RF-H-03
