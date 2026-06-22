---
tags:
  - arquitectura
  - rol/colaborador
  - caso-de-uso
aliases:
  - CU RF-C-06
---

# 🪪 ID: RF-C-06
🏷️ **Nombre:** Consultar Mi Schedule

**Historia:**
El Colaborador quiere revisar sus turnos asignados para la semana. Desde la app accede a la sección "Mi Schedule" y ve el calendario semanal con sus asignaciones propias: hotel, posición, horario y fechas. El colaborador puede navegar entre la semana en curso y la siguiente. La vista es de **solo lectura**; el Colaborador no puede editar el Schedule (RR-C-01). Solo se muestran SUS asignaciones, nunca datos de otros colaboradores.

**Criterios de aceptación:**
Vista solo lectura (RR-C-01). Solo muestra asignaciones del propio colaborador. Información visible por turno: hotel, posición, horario (hora de entrada y salida esperada), fechas. El colaborador puede navegar entre la semana en curso y la semana siguiente. Disponible en vista lista y vista calendario. Si no tiene asignaciones en la semana seleccionada, el sistema muestra estado vacío: *"No tienes turnos asignados esta semana"*. No tiene acceso al Schedule de otros colaboradores ni a la herramienta de edición del Schedule.

**Documentación:**
- PRD: PRD-COLAB-01
- Flow: [[Core/Módulos/Schedule|Schedule]] — Vista del Colaborador
- Prototipo: (link de Figma)

**Flujo:**
`App → Sección Mi Schedule` → MANUAL → `Selecciona semana (en curso / siguiente)` → `Selecciona vista (lista / calendario)` → AUTOMATICO → `Sistema carga las asignaciones del colaborador para la semana seleccionada` → `Muestra: hotel, posición, horario, fechas por cada turno` / Si sin asignaciones → `Muestra: "No tienes turnos asignados esta semana"`
