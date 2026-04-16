---
tags:
  - modulo/onboarding-hotel
  - concepto
aliases:
  - Trigger Automático
  - Trigger Automático de Conversión
---

# Trigger Automático de Conversión

Conjunto de acciones automáticas que el sistema ejecuta **en paralelo** cuando el [[Business Developer Coordinator]] aprueba la conversión en [[Semáforo Onboarding|Status Onboarding Rosa]] y se crea el [[Usuario del Hotel]].

## Acciones automáticas

- Sistema envía **email de bienvenida** al hotel.
- Sistema **notifica al [[Business Developer|BD]] asignado**.
- El hotel **desaparece de la lista de prospectos**.

## Disparador

- **Evento:** aprobación de la conversión en [[Semáforo Onboarding|Status Onboarding Rosa]].
- **Precondición:** creación del [[Usuario del Hotel]] en el sistema.
- **Resultado:** el hotel pasa a [[Semáforo Onboarding|Status Onboarding Naranja]] y queda habilitado para generar [[Requisición|requisiciones]].

## Relacionado

- [[Flujo de Onboarding]]
- [[Usuario del Hotel]]
- [[Semáforo Onboarding|Status Onboarding Rosa]]
- [[Semáforo Onboarding|Status Onboarding Naranja]]
