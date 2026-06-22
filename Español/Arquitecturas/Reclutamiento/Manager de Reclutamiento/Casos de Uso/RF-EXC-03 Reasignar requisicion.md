---
tags:
  - arquitectura
  - rol/manager-reclutamiento
  - caso-de-uso
  - excepcion
aliases:
  - CU RF-EXC-03
---

# 🪪 ID: RF-EXC-03
🏷️ **Nombre:** Reasignar requisición entre Reclutadoras

**Historia:**
**Excepción al modelo Self-Pick colaborativo (RR-01).** Cuando una Reclutadora ya tomó una requisición pero no puede continuarla (ausencia inesperada, sobrecarga, escalamiento del Líder), el Manager mueve la requisición a otra Reclutadora. En el modo **transferencia**, la Reclutadora original pierde acceso y la nueva la recibe con todo el contexto previo (notas, candidatos preseleccionados, historial). Como **alternativa colaborativa (RR-15)** —cuando se trata de apoyo o sobrecarga y no de un reemplazo total— el Manager suma a la nueva Reclutadora como participante y la **original permanece como reclutador participante**; ambas trabajan la requisición en paralelo con avance de cobertura compartido.

**Criterios de aceptación:**
La acción es excepcional y requiere motivo obligatorio. Queda en log auditable (regla RR-12). En modo transferencia, la Reclutadora original recibe notificación de pérdida de acceso; en modo apoyo/colaborativo, la original conserva el acceso como participante y solo se le notifica el refuerzo. La nueva Reclutadora recibe la requisición con todo el contexto. Si la requisición tenía colaboradores preseleccionados, esos quedan visibles para la nueva Reclutadora y no se retrocede lo ya asignado por otros. El semáforo no se resetea. El evento (transferencia o incorporación de apoyo) queda registrado en el Historial de la requisición (RR-16) con autor y fecha. *(No afecta a RR-05, que rige la exclusividad del colaborador/trabajador entre hoteles.)*

**Documentación:**
- PRD: PRD-RECL-03 Manager
- Flow: Reasignación excepcional
- Prototipo: (link de Figma)

**Flujo:**
`Detalle de requisición tomada` → MANUAL → `Click "Reasignar"` → `Selecciona nueva Reclutadora + modo (Transferir / Agregar como apoyo) + motivo obligatorio (ausencia / sobrecarga / escalamiento)` → `Confirmar` → AUTOMATICO → `[Modo Transferir] Reclutadora original pierde acceso + Notificación a Reclutadora original / [Modo Apoyo] Reclutadora original permanece como participante + Notificación de refuerzo + Nueva Reclutadora recibe la requisición con contexto completo (notas + candidatos preseleccionados + historial) + Notificación a nueva Reclutadora + Notificación a ambos Líderes (si distintos) + Registra evento en el Historial de la requisición + Registro de excepción en log auditable`
