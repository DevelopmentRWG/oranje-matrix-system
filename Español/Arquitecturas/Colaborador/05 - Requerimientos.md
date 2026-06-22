---
tags:
  - arquitectura
  - rol/colaborador
aliases:
  - Requerimientos Colaborador
---

# REQUERIMIENTOS POR ROL

## 👷 ROL-C-01 · Colaborador (COL)

---

## Requerimientos Funcionales

| ID      | Requerimiento                                       | Prioridad |
| ------- | --------------------------------------------------- | --------- |
| RF-C-01 | Completar alta en la app — Fase 2                   | 🔴 Alta   |
| RF-C-02 | Completar datos de emergencia — Fase 3              | 🔴 Alta   |
| RF-C-03 | Ponchar vía QR (6 tipos de ponche)                  | 🔴 Alta   |
| RF-C-04 | Activar disponibilidad voluntaria — Amarillo         | 🔴 Alta   |
| RF-C-05 | Reportar accidente laboral desde la app             | 🔴 Alta   |
| RF-C-06 | Consultar Mi Schedule                               | 🟡 Media  |
| RF-C-07 | Consultar Mi Timesheet                              | 🟡 Media  |
| RF-C-08 | Consultar Mi Pago semanal                           | 🟡 Media  |
| RF-C-09 | Consultar notificaciones                            | 🟡 Media  |
| RF-C-10 | Consultar Mi perfil y estado del semáforo           | 🟡 Media  |

---

## Requerimientos No Funcionales

| ID       | Requerimiento                                                                 | Prioridad |
| -------- | ----------------------------------------------------------------------------- | --------- |
| RNF-C-01 | **Responsive, web y móvil:** la plataforma debe funcionar en móvil (Android e iOS) y en navegador web; diseñada con enfoque mobile-first pero adaptada para escritorio. El ponche por QR (RF-C-03) es una funcionalidad exclusiva de móvil (requiere cámara del dispositivo). | 🔴 Alta |
| RNF-C-02 | **Offline-tolerante para ponche:** el escaneo QR y el registro de ponche deben tolerar pérdida temporal de conectividad, encolando el registro y sincronizando al recuperar señal | 🔴 Alta |
| RNF-C-03 | **Seguridad de datos sensibles:** SSN/ITIN deben almacenarse cifrados; no deben mostrarse en texto plano en la interfaz (enmascarar tras validación de Fase 2) | 🔴 Alta |
| RNF-C-04 | **Disponibilidad 99.5%** especialmente en la franja horaria de entrada/salida de jornada (ponche QR) | 🔴 Alta |
| RNF-C-05 | **UX simplificada:** la app debe ser usable por colaboradores con nivel básico de dominio tecnológico; texto claro, íconos reconocibles, flujos de máximo 3 pasos | 🔴 Alta |
| RNF-C-06 | **Notificaciones push:** el sistema debe enviar notificaciones push al colaborador ante cambios de estado del semáforo, nueva asignación, validación de alta aprobada/rechazada | 🟡 Media |
| RNF-C-07 | **Soporte multilingüe:** español como idioma principal; inglés como secundario para colaboradores que lo prefieran | 🟢 Baja  |
| RNF-C-08 | **Compatibilidad de cámara:** la funcionalidad de escaneo QR debe funcionar con la cámara nativa del dispositivo, sin requerir app externa | 🔴 Alta |

---

## Reglas de Negocio

| ID      | Regla                                                                                                       | Prioridad |
| ------- | ----------------------------------------------------------------------------------------------------------- | --------- |
| RR-C-01 | El Colaborador solo puede ver y editar SUS PROPIOS datos — ningún dato de otro colaborador es visible       | 🔴 Alta   |
| RR-C-02 | Amarillo es la única transición de estado que el Colaborador activa por sí mismo, sin aprobación           | 🔴 Alta   |
| RR-C-03 | El Colaborador no puede ponchar sin un Timesheet activo (requiere Schedule + asignación activa)             | 🔴 Alta   |
| RR-C-04 | El Colaborador accede a la plataforma desde **móvil y web (responsive)**. El onboarding (Fase 2 y 3) y las vistas de consulta (Mi Schedule, Mi Timesheet, Mi Pago, Notificaciones, Mi Perfil) y la activación de disponibilidad (Amarillo) están disponibles en ambos canales. El ponche por QR (RF-C-03) es una acción nativa de móvil (escaneo del QR físico en el hotel con la cámara del teléfono). | 🔴 Alta   |
| RR-C-05 | El Colaborador puede consultar el **historial de sus pagos ya recibidos** (semana, hotel(es), horas, monto pagado y fecha de pago). **No puede ver el monto de su pago en curso o próximo**: el cálculo del pago es exclusivo de Contabilidad y solo se revela al Colaborador una vez que el pago ha sido liberado. El Consolidado Semanal completo (rate interno, deducciones, facturación) permanece de uso exclusivo de Contabilidad. Ver [[RF-C-08 Consultar Mi Pago semanal]]. | 🟡 Media |

> [!info]
> Las reglas sobre deducción de lunch, 3 inasistencias → Blacklist, protección Gris por accidente laboral, y cálculo de pago semanal están definidas en [[Reglas del Colaborador]] y no se redefinen aquí.
