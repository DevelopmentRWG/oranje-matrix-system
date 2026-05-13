---
tags:
  - arquitectura
  - departamento/ventas
aliases:
  - Criterios de Aceptación Ventas
---

# ✅ CRITERIOS DE ACEPTACIÓN — DEPARTAMENTO DE VENTAS

---

| #           | Criterio                                                                                                                                                                                 |
| ----------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **AC-V-01** | Solo el BDC puede aprobar la conversión de prospecto a cliente (RR-V-01).                                                                                                                |
| **AC-V-02** | El sistema bloquea el botón "Aprobar conversión" si no existe el Usuario del Hotel previamente creado (RR-V-02).                                                                         |
| **AC-V-03** | Al aprobar la conversión, el sistema ejecuta automáticamente y en paralelo: email de bienvenida + notificación al BD + remoción del prospecto del Pipeline, en menos de 1 min (RR-V-03). |
| **AC-V-04** | El status del prospecto pasa automáticamente a Naranja tras la conversión exitosa (RR-V-08).                                                                                             |
| **AC-V-05** | El hotel solo puede generar requisiciones cuando alcanza Naranja en el Semáforo Onboarding (RR-V-08).                                                                                    |
| **AC-V-06** | Solo el BDC puede desbloquear estancamiento (Café) y reactivar al prospecto (RR-V-04).                                                                                                   |
| **AC-V-07** | Solo el BDC puede gestionar clientes pausados (Negro) (RR-V-05).                                                                                                                         |
| **AC-V-08** | El BD gestiona los rechazos (Rojo) y puede reactivar el prospecto.                                                                                                                       |
| **AC-V-09** | Toda reactivación (desde Rojo, Negro o Café) regresa al prospecto a Azul Claro, nunca a Gris (RR-V-07).                                                                                  |
| **AC-V-10** | El Documento de T&C debe contener: Pay rate, Bill rate, Overtime, Festivos, Calendario. Sin estos campos, no se puede iniciar Rosa (RR-V-10).                                            |
| **AC-V-11** | La Propuesta Personalizada se elabora y envía exclusivamente en status Verde (RR-V-09).                                                                                                  |
| **AC-V-12** | Todo cambio de status queda registrado con fecha, responsable y comentario (RR-V-11). No hay cambios silenciosos.                                                                        |
| **AC-V-13** | Post-Naranja, BD y BDC pueden ver el cliente activo pero NO modificar el hotel ni sus requisiciones (RR-V-12).                                                                           |
| **AC-V-14** | El email de bienvenida usa la plantilla configurada y llega al hotel en menos de 1 min (RI-V-05).                                                                                        |
| **AC-V-15** | El BD asignado recibe notificación push en menos de 1 min tras la conversión.                                                                                                            |
| **AC-V-16** | El sistema notifica al rol correspondiente en menos de 1 min tras un evento relevante (cambios de status, etc.).                                                                         |
| **AC-V-17** | La interfaz es responsive: BDC desde 7" (Desktop / Tablet); BD desde 5" (mobile prioritario, RNF-V-04).                                                                                  |
| **AC-V-18** | La disponibilidad mensual del módulo es del 99.5% (RNF-V-02).                                                                                                                            |
| **AC-V-19** | Cada cambio de status incluye un selector de motivo + comentario obligatorio.                                                                                                            |
| **AC-V-20** | El Contrato se genera automáticamente al cierre exitoso en Rosa, usando el T&C validado por el BDC como insumo (RR-V-15).                                                                |
| **AC-V-21** | El BDC puede ver TODOS los prospectos de su zona / rutas; el BD solo ve los de su territorio asignado.                                                                                   |
