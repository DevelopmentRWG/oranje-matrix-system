---
tags:
  - modulo/onboarding-hotel
  - flujo
aliases:
  - Flujo de Onboarding Hotel
---

# Flujo de Onboarding

Proceso comercial paso a paso para incorporar un hotel como cliente activo de Oranje. Cada etapa corresponde a un status del [[Semáforo Onboarding]].

## Etapa 1 — [[Status - Gris]] Hotel identificado

**Responsable:** [[Business Developer]]
**Acción única:** el BD identifica el hotel dentro de su territorio como posible cliente.

**Avance →** cuando inicia contacto y recopilación de datos, mueve el status a [[Status - Azul Claro|Azul Claro]].

## Etapa 2 — [[Status - Azul Claro]] Contacto y recopilación de datos

**Responsable:** [[Business Developer]]
**Acciones durante este status:**

- Crea el perfil del hotel en el sistema.
- Recopila datos: nombre del hotel, email, teléfono, nombre y cargo del contacto, necesidad del negocio.
- Realiza visita en frío al hotel.

**Avance →** al enviar la propuesta, el status cambia a [[Status - Verde|Verde]].

## Etapa 3 — [[Status - Verde]] Propuesta enviada

**Responsable:** [[Business Developer]]
**Acciones:**

- Elabora [[Propuesta Personalizada|propuesta personalizada]] (servicios, precios, condiciones).
- Adjunta y envía la propuesta al hotel.
- Registra intentos de contacto y respuestas.
- Hace seguimiento al hotel.

**Decisión: ¿El hotel responde con interés?**

- **SÍ →** pasa a [[Status - Amarillo|Amarillo]].
- **NO →** pasa a [[Status - Rojo|Rojo]].

**Rama alterna:** si hay estancamiento, se activa [[Status - Café|Café]] y el [[Business Developer Coordinator]] investiga y da solución para retomar la propuesta → regresa a [[Status - Azul Claro|Azul Claro]].

## Etapa 4 — [[Status - Amarillo]] En seguimiento tras propuesta

**Responsable:** [[Business Developer]] (con apoyo del [[Business Developer Coordinator]])
**Acciones durante este status:**

- BD o BDC crea el [[Documento de Términos y Condiciones]], que establece:
  - Pay rate
  - Bill rate
  - Overtime
  - Festivos
  - Calendario

**Avance →** al iniciar negociación formal, pasa a [[Status - Rosa|Rosa]].

## Etapa 5 — [[Status - Rosa]] Negociación de términos

**Responsable:** [[Business Developer]] + [[Business Developer Coordinator]]

**Decisión: ¿Se cierra el acuerdo?**

- **NO →** vuelve al flujo (renegociación / [[Status - Café|Café]] / Fin).
- **SÍ →** el BDC aprueba la conversión y se crea el [[Usuario del Hotel]] en el sistema.

**Al crearse el usuario** se dispara el [[Trigger Automático de Conversión]] (en paralelo):

- Sistema envía email de bienvenida al hotel.
- Sistema notifica al BD asignado.
- Hotel desaparece de la lista de prospectos.

**Avance →** pasa a [[Status - Naranja|Naranja]].

## Etapa 6 — [[Status - Naranja]] Hotel cliente activo

**Responsable operativo:** [[QA Inspector|Inspector]] + [[Reclutadora|Reclutadores]]
**Estado:** el hotel ya tiene [[Usuario del Hotel|usuario creado]] y está trabajando con Oranje.

- Pasa a responsabilidad de [[Reclutadora|Reclutadores]].
- Inicia ciclo operativo: [[Requisición|requisiciones]] → cobertura → [[Core/Módulos/Schedule|Schedule]] → [[Timesheet]].
- BD y BDC quedan como referentes comerciales.

**Decisión: ¿El hotel deja de operar?**

- **NO →** Fin (continúa activo).
- **SÍ →** pasa a [[Status - Negro|Negro]].

## Etapa 7 — [[Status - Rojo]] Hotel rechazó la propuesta / no interesado

**Responsable:** [[Business Developer]]

**Decisión: ¿Reactivar?**

- **NO →** Fin.
- **SÍ →** regresa a [[Status - Azul Claro|Azul Claro]].

## Etapa 8 — [[Status - Negro]] Cliente dejó de operar / relación pausada

**Responsable:** [[Business Developer Coordinator]]
**Motivos:** cierre del hotel, cambio de administración, pausa, disputa.

**Decisión: ¿Reactivar?**

- **NO →** Fin.
- **SÍ →** regresa a [[Status - Azul Claro|Azul Claro]].

## Puntos clave

- Todo cambio de status queda registrado con fecha, responsable y comentario.
- [[Status - Naranja|Naranja]] es el único status que habilita al hotel para generar [[Requisición|requisiciones]].
- El [[Usuario del Hotel]] se crea al aprobar la conversión en [[Status - Rosa|Rosa]], justo antes del [[Trigger Automático de Conversión|trigger automático]].
- [[Status - Rojo|Rojo]], [[Status - Negro|Negro]] y [[Status - Café|Café]] siempre reactivan hacia [[Status - Azul Claro|Azul Claro]].
- La aprobación final de conversión la da únicamente el [[Business Developer Coordinator]].
