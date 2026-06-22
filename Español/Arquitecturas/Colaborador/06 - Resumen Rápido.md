---
tags:
  - arquitectura
  - rol/colaborador
aliases:
  - Resumen Rápido Colaborador
---

# RESUMEN RÁPIDO — COLABORADOR

---

| Campo                    | Contenido                                                                                                    |
| ------------------------ | ------------------------------------------------------------------------------------------------------------ |
| **Rol**                  | 👷 Colaborador (COL)                                                                                         |
| **Objetivo**             | Autoservicio personal: alta, ponche QR, disponibilidad, reporte de accidente y consulta de datos propios    |
| **Modelo**               | Pasivo — sujeto del sistema. La única acción de cambio de estado que ejecuta es activar Amarillo             |
| **Permisos Clave**       | Ver (solo propio) · Crear (alta, ponches, accidente, Amarillo) · Editar limitado (datos de perfil/emergencia) |
| **Dispositivo**          | Mobile + Web (responsive) — ponche por QR exclusivo de móvil                                                 |
| **Acciones Principales** | Completar alta (Fase 2 + 3) · Ponchar QR · Activar Amarillo · Reportar accidente · Consultar schedule, timesheet y pago |
| **Nivel**                | 🟢 Bajo (solo datos propios)                                                                                 |
| **Reglas clave**         | RR-C-01 (solo propio) · RR-C-02 (solo Amarillo autónomo) · RR-C-03 (ponche requiere Timesheet activo) · RR-C-04 (móvil + web; ponche QR exclusivo de móvil) |

---

## Lo que el Colaborador SÍ hace

- Completa su propio alta en la app (Fase 2 y Fase 3).
- Poncha sus entradas y salidas diarias vía QR (6 ponches).
- Activa su disponibilidad voluntaria (Amarillo) — su única acción autónoma de cambio de estado.
- Reporta accidentes laborales cuando es él quien los detecta primero (Escenario A).
- Consulta su schedule, timesheet, pago, notificaciones y perfil (todos en modo lectura).

## Lo que el Colaborador NO hace

- No acepta ni rechaza asignaciones.
- No edita el Schedule ni corrige ponches.
- No ve datos de ningún otro colaborador.
- No autoriza, no asigna, no gestiona.
- No puede ponchar por web (el ponche QR requiere la cámara del teléfono).

---

## Fuentes de dominio

- [[Colaborador]] — entidad y datos en 3 fases
- [[Reglas del Colaborador]] — ponchado, lunch, pago, inasistencias, accidente, pool
- [[Semáforo del Colaborador]] — 12 estados y transiciones
