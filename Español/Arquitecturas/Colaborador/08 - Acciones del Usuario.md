---
tags:
  - arquitectura
  - rol/colaborador
aliases:
  - Acciones Colaborador
---

# 6. ACCIONES DEL USUARIO — COLABORADOR

---

| Acción                                                      | Resultado                                                                                                                                                         |
| ----------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Completar alta — Fase 2 (RF-C-01)                           | Sistema guarda datos laborales del colaborador · Estado del semáforo transita a → Blanco (pre-validación) · Notifica a la Reclutadora que hay un alta pendiente de revisión |
| Completar datos de emergencia — Fase 3 (RF-C-02)            | Sistema guarda contacto de emergencia, tipo de sangre y condiciones médicas · Datos disponibles para uso en caso de accidente laboral                              |
| Escanear QR — Ponchar Entrada (RF-C-03)                     | Sistema registra hora de entrada · Crea o actualiza el Timesheet de esa jornada · Requiere Timesheet activo (Schedule + asignación) (RR-C-03)                    |
| Escanear QR — Ponchar Salida Lunch                          | Sistema registra hora de salida a lunch · Inicia cómputo del tiempo de lunch · Aplicará deducción según [[Reglas del Colaborador]]                               |
| Escanear QR — Ponchar Entrada Lunch                         | Sistema registra regreso de lunch · Cierra cómputo del tiempo de lunch · Si lunch < 30 min, sistema aplica mínimo de 30 min                                      |
| Escanear QR — Ponchar Salida Break                          | Sistema registra hora de salida a break · Pausa cómputo de horas brutas                                                                                           |
| Escanear QR — Ponchar Entrada Break                         | Sistema registra regreso de break · Reanuda cómputo de horas brutas                                                                                               |
| Escanear QR — Ponchar Salida (fin de jornada) (RF-C-03)     | Sistema registra hora de salida · Calcula horas brutas (Salida − Entrada) · Aplica deducción de lunch · Calcula horas netas · Actualiza Timesheet del colaborador |
| Intentar ponchar sin Timesheet activo                        | Sistema bloquea; muestra: *"No tienes un turno activo. Comunícate con tu supervisor"* (RR-C-03)                                                                   |
| Activar disponibilidad voluntaria — Amarillo (RF-C-04)       | Estado del semáforo cambia a Amarillo · Colaborador queda visible en el Pool como disponible voluntario · Sin Schedule ni Timesheet activos hasta asignación      |
| Desactivar disponibilidad — volver a Verde fuerte            | Estado regresa a Verde fuerte · El colaborador ya no aparece como disponible voluntario en el Pool                                                                |
| Reportar accidente laboral (RF-C-05)                         | Sistema crea tarjeta de accidente laboral · Estado del colaborador transita a Gris (Accidentado) · Notifica simultáneamente al Supervisor e Inspector de zona · Colaborador queda protegido de regla de 3 inasistencias → Blacklist |
| Consultar Mi Schedule (RF-C-06)                             | Vista semanal de turnos asignados: hotel, posición, horario, fechas · Solo lectura                                                                                |
| Consultar Mi Timesheet (RF-C-07)                            | Tabla semanal: 6 columnas de ponches, horas brutas por jornada, deducción de lunch, horas netas · Solo lectura                                                   |
| Consultar Mi Pago semanal (RF-C-08)                         | Historial de pagos ya liberados (semana, hotel, horas, monto pagado, fecha); la semana en curso aparece como "En cálculo" sin monto · Solo lectura (RR-C-05)     |
| Consultar notificaciones (RF-C-09)                          | Lista de notificaciones ordenadas por fecha: leídas y no leídas · Badge desaparece al abrir                                                                       |
| Consultar Mi Perfil y estado del semáforo (RF-C-10)         | Vista de todos sus datos (Fase 1, 2, 3) + color y nombre de su estado actual en el semáforo · Puede editar datos de contacto y emergencia con límites            |
| Editar teléfono o datos de emergencia desde Mi Perfil        | Sistema guarda el cambio · No requiere re-validación para datos de emergencia · Cambio registrado en journal del colaborador                                       |
| Cancelar acción en formulario                               | Cambios no se guardan · Colaborador regresa a la pantalla anterior                                                                                                |
