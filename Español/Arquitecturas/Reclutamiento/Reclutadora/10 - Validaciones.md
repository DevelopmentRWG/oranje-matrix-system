---
tags:
  - arquitectura
  - rol/reclutadora
aliases:
  - Validaciones Reclutadora
---

# 4. VALIDACIONES — RECLUTADORA

---

| Caso                                            | Comportamiento del Sistema                                                  |
| ----------------------------------------------- | --------------------------------------------------------------------------- |
| Campos obligatorios vacíos al enviar formulario | Bloquea envío y muestra mensaje de error junto a cada campo inválido        |
| Documento de identidad ya existe en el sistema  | Bloquea creación; muestra mensaje "Este documento ya está registrado"       |
| Teléfono con formato inválido                   | Bloquea envío; muestra "Formato de teléfono inválido (10 dígitos)"          |
| Cédula con tamaño mayor a 5 MB                  | Rechaza el archivo; muestra "Tamaño máximo: 5 MB"                           |
| Candidato figura en Blacklist                   | Bloquea creación/asignación; muestra alerta visible con motivo del veto     |
| Edad fuera del rango permitido (<18 o >65)      | Bloquea envío; muestra "La edad debe estar entre 18 y 65 años"              |
| Asignar colaborador no validado                 | Bloquea asignación; muestra "El colaborador debe estar validado primero"    |
| Asignar colaborador ya activo en otro hotel     | Bloquea asignación; muestra "El colaborador ya está asignado a otro hotel"  |
| Marcar requisición como cubierta sin 100%       | Bloquea acción; muestra "Cobertura debe ser 100% para cerrar como cubierta" |
| Tomar requisición ya tomada por otro            | Flujo colaborativo (no bloquea); muestra "Ya hay N reclutador(es); te unirás como participante" y te agrega como reclutador adicional (RR-15) |
| Unirse a una requisición en la que ya participas | Bloquea acción; muestra "Ya eres reclutador participante de esta requisición" |
| Asignar el mismo colaborador a la misma posición que otro reclutador ya cubrió | Bloquea a nivel de slot; gana la primera asignación y muestra "Posición ya cubierta" a la segunda |
| Unirse a una requisición cerrada (cubierta/parcial) | Bloquea acción; muestra "La requisición está cerrada; no es posible unirse" |
| Salir de la requisición sin justificación       | Solicita motivo obligatorio antes de salir                                  |
