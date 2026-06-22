---
tags:
  - arquitectura
  - departamento/ventas
aliases:
  - Reglas de Negocio Ventas
---

# 8. REGLAS DE NEGOCIO — DEPARTAMENTO DE VENTAS

---

| ID          | Regla                                                | Descripción                                                                                                                                                                                                                                           |
| ----------- | ---------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **RR-V-01** | Conversión exclusiva del BDC                         | Solo el [[Ventas/Roles/Business Developer Coordinator\|BDC]] puede aprobar la conversión de prospecto a cliente (status Rosa → Naranja). El BD nunca puede aprobar.                                                                                   |
| **RR-V-02** | Precondición de conversión — Usuario del Hotel       | Antes de aprobar la conversión, el BDC debe crear el [[Ventas/Onboarding-Hotel/Conceptos/Usuario del Hotel\|Usuario del Hotel]] en el sistema. Sin este paso, el sistema bloquea el botón de "Aprobar conversión".                                    |
| **RR-V-03** | Trigger Automático de Conversión                     | Al aprobar la conversión, el sistema ejecuta **automáticamente y en paralelo** 3 acciones: (1) email de bienvenida al hotel, (2) notificación al BD asignado, (3) hotel desaparece de la lista de prospectos.                                         |
| **RR-V-04** | Desbloqueo de estancamiento (Café) exclusivo del BDC | El status **Café** es un puente de desbloqueo. Solo el BDC investiga la causa del estancamiento, da solución y reactiva.                                                                                                                              |
| **RR-V-05** | Gestión de cliente pausado (Negro) exclusiva del BDC | Cuando un cliente activo deja de operar (cierre, cambio de administración, pausa, disputa), pasa a **Negro**. La gestión y posible reactivación son exclusivas del BDC.                                                                               |
| **RR-V-06** | Gestión de rechazo (Rojo) por el BD                  | Cuando un prospecto rechaza la propuesta, pasa a **Rojo**. El BD gestiona la reactivación si aplica.                                                                                                                                                  |
| **RR-V-07** | Reactivaciones siempre regresan a Azul Claro         | Reactivar desde **Rojo, Negro o Café** siempre regresa el hotel a **Azul Claro** (datos ya capturados, contacto activo) — nunca a Gris.                                                                                                               |
| **RR-V-08** | Naranja habilita generación de requisiciones         | El status **Naranja** es el **único** que habilita al hotel a generar requisiciones en el módulo Hotel. Antes de Naranja, el hotel es solo prospecto.                                                                                                 |
| **RR-V-09** | Propuesta Personalizada en Verde                     | La [[Ventas/Onboarding-Hotel/Conceptos/Propuesta Personalizada\|Propuesta Personalizada]] se elabora y envía exclusivamente en status **Verde**. Se ajusta o retoma desde **Café** (con desbloqueo del BDC).                                          |
| **RR-V-10** | T&C — contenido obligatorio                          | El [[Ventas/Onboarding-Hotel/Conceptos/Documento de Términos y Condiciones\|Documento de Términos y Condiciones]] debe contener: **Pay rate, Bill rate, Overtime, Festivos, Calendario**. Sin estos campos, no se puede iniciar Rosa.                 |
| **RR-V-11** | Trazabilidad de cambios de status                    | Todo cambio de status en el [[Core/Módulos/Semáforos/Semáforo Onboarding\|Semáforo Onboarding]] queda registrado con: **fecha, responsable y comentario**. No hay cambios silenciosos.                                                                |
| **RR-V-12** | Post-Naranja: BD y BDC como referentes comerciales   | Cuando el hotel alcanza Naranja, BD y BDC dejan de operar y quedan como **referentes comerciales** (no editan el hotel ni sus requisiciones). El hotel pasa a [[Reclutamiento/Reclutamiento\|Reclutamiento]] e [[Inspección/Inspección\|Inspección]]. |
| **RR-V-13** | QA observa pero no opera                             | Un [[QA/Operador de QA\|Operador de QA]] está asignado al depto Ventas para medir e informar. NO ejecuta operación.                                                                                                                                   |
| **RR-V-14** | Escalamiento de Calidad a dirección                  | Si el [[Core/Módulos/Semáforos/Indicador de Calidad\|Indicador de Calidad]] del depto entra a **Rojo** sin mejora tras notificación, el Manager de QA escala a dirección.                                                                             |
| **RR-V-15** | Contrato resulta del cierre exitoso en Rosa          | El [[Core/Módulos/Contrato\|Contrato]] se genera al aprobarse la conversión. Insumo obligatorio: el Documento de T&C validado por BDC.                                                                                                                |

---

## Referencias cruzadas

- [[Ventas/Reglas de Ventas|Reglas de Ventas]] — fuente de verdad operativa
- [[Reglas de Negocio]] — concentrado general del sistema
- [[Ventas/Onboarding-Hotel/Onboarding-Hotel|Onboarding-Hotel]]
- [[Ventas/Onboarding-Hotel/Flujo de Onboarding|Flujo de Onboarding]]
- [[Core/Módulos/Semáforos/Semáforo Onboarding|Semáforo Onboarding]]
- [[Core/Módulos/Contrato|Contrato]]
