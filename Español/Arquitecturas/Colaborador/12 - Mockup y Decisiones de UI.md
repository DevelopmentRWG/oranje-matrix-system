---
tags:
  - arquitectura
  - rol/colaborador
aliases:
  - Mockup Colaborador
  - UI Colaborador
  - Decisiones de UI Colaborador
---

# Mockup y Decisiones de UI — Colaborador

Documenta el mockup web interactivo del rol Colaborador y las decisiones de diseño tomadas durante su implementación.

> [!info]
> El mockup vive en el repo de mockups: `oranje-mockups/Mockups/Colaborador/Colaborador - Oranje.html`. La fuente de verdad visual (tokens y componentes) es `oranje-seed.css` — ver [[Convenciones de Diseño]].

---

## Pantallas implementadas

| Pantalla | Descripción |
|---|---|
| **Onboarding (Fase 2 + Fase 3)** | Wizard a pantalla completa (sin sidebar, no hay acceso aún) para el colaborador nuevo: stepper Datos laborales (Fase 2) → Emergencia (Fase 3) → Revisar → envío. La Fase 2 incluye campos opcionales de SSN/ITIN y el campo de carga de documento (JPG/PNG/PDF, máx. 10 MB, también opcional · recomendado si hay SSN/ITIN); el campo de carga se habilita al ingresar SSN o ITIN. Si el colaborador no proporciona ni SSN ni ITIN, un banner le avisa de la retención del 16% (reembolsable) y puede continuar igual. Termina en pantalla **Pendiente de validación** (estado Blanco): sin acceso a módulos hasta que la Reclutadora valide (RF-08). RF-C-01, RF-C-02. En el mockup se alterna con el **switch de demo** (flotante, abajo a la derecha): "Colaborador nuevo" / "Ya en Oranje". |
| **Inicio** | Dashboard personal: saludo con estado del semáforo ([[Semáforo del Colaborador]]), KPIs de la semana, próximo turno y accesos rápidos. |
| **Mi Schedule** | Calendario semanal de turnos asignados; solo lectura. |
| **Ponche** | Consulta del estado de los 6 ponches del día. El registro real es acción móvil por QR (RR-C-04). |
| **Mi Timesheet** | Tabla de horas de la semana con deducción de lunch por jornada y total de horas netas. |
| **Mi Pago** | Historial de pagos recibidos (semana, hotel, horas, monto, fecha). La semana en curso se muestra como "En cálculo" sin monto; el próximo pago no es visible (RR-C-05). |
| **Disponibilidad** | Toggle para activar el estado Amarillo (disponibilidad voluntaria); incluye stepper visual del flujo (Amarillo → Café → Verde), historial de turnos extra recientes y guía de cuándo activarla. |
| **Reportar accidente** | Formulario de reporte de accidente (Escenario A); al enviarse activa el estado Gris y notifica al Inspector. |

> [!note]
> **Notificaciones** y **Mi Perfil** se acceden desde el header (campana y avatar), no desde el sidebar. No son módulos independientes en la navegación lateral.

---

## Decisiones de UI

- **Gate de acceso por onboarding.** Sin completar Fase 2 + Fase 3 y ser validado por la Reclutadora, el colaborador permanece en estado Blanco (Pre-asignación) **sin acceso a los módulos** ni posibilidad de asignación. El mockup implementa el wizard de alta (Fase 2/3) y la pantalla de "Pendiente de validación". Fundamento: RF-C-01, RF-C-02, RF-08; transición Blanco → Verde fuerte del [[Semáforo del Colaborador]].
- **Modelo pasivo reflejado en la UI.** El Colaborador no tiene controles de asignación ni gestión. La interfaz expone únicamente sus propios datos y sus dos acciones autónomas: activar Amarillo y reportar accidente. Fundamento: RR-C-01, RR-C-02.
- **Ponche QR es acción móvil.** La pantalla de Ponche en web muestra el estado de los 6 ponches pero no permite registrarlos. El registro real requiere cámara del dispositivo. Fundamento: RR-C-04.
- **Historial de pagos, sin próximo pago.** Mi Pago muestra solo pagos ya liberados (semana, hotel, horas, monto, fecha); el monto del pago en curso o próximo no se revela al Colaborador hasta que Contabilidad lo libere. La semana en curso aparece como "En cálculo" sin monto. Fundamento: RR-C-05.
- **Notificaciones y perfil en el header.** Campana (notificaciones) y avatar (menú de perfil) viven en el header, siguiendo la convención global. Ver [[Estructura General App]].
- **Semilla de diseño compartida.** El mockup enlaza `oranje-seed.css` y solo agrega estilos específicos del Colaborador. No reimplementa componentes. Ver [[Convenciones de Diseño]].
- **SSN/ITIN opcionales + retención 16%.** SSN, ITIN y el documento de SSN/ITIN son opcionales en Fase 2. Si el colaborador no proporciona SSN ni ITIN, un banner le avisa de la retención del 16% (reembolsable) y puede continuar igual. El campo de carga del documento se habilita al ingresar un SSN o ITIN. Fundamento: [[Deducciones]] (disparador "sin SSN/TaxID"); cierra también la inconsistencia con RF-08.

---

## Relacionado

- [[Convenciones de Diseño]]
- [[Estructura General App]]
- [[03 - PRD]]
- [[07 - Feature Map]]
- [[08 - Acciones del Usuario]]
- [[Semáforo del Colaborador]]
- [[00 - Arquitectura Colaborador]]
