---
tags:
  - modulo/onboarding-hotel
aliases:
  - Onboarding Hotel
  - Módulo de Onboarding Hotel
---

# Onboarding Hotel

Módulo que representa la fase comercial previa a que un hotel se convierta en cliente operativo de Oranje. Cubre el ciclo desde que el [[Business Developer]] identifica un hotel en su territorio hasta que el [[Business Developer Coordinator]] aprueba la conversión y el hotel queda habilitado para generar [[Requisición|requisiciones]].

> [!info]
> El hotel **solo habilita requisiciones** cuando alcanza el status [[Status - Naranja|Naranja]]. Antes de eso permanece como prospecto comercial gestionado por [[Ventas/Ventas|Ventas]].

## Contenido del módulo

### Roles

- [[Business Developer]] — Responsable del ciclo comercial con el hotel: contacta, propone y da seguimiento.
- [[Business Developer Coordinator]] — Supervisa rutas y zonas, valida términos y da el sí final a la conversión.

### Procesos

- [[Flujo de Onboarding]] — Proceso paso a paso desde la identificación hasta la activación.
- [[Semáforo Onboarding]] — Estados de seguimiento de la negociación con el hotel.

## Estados del onboarding

- [[Status - Gris]] — Hotel identificado.
- [[Status - Azul Claro]] — Contacto y recopilación de datos.
- [[Status - Verde]] — Propuesta enviada.
- [[Status - Amarillo]] — En seguimiento tras propuesta.
- [[Status - Rosa]] — Negociación de términos.
- [[Status - Naranja]] — Acuerdo firmado, hotel cliente activo.
- [[Status - Café]] — Renegociación / desbloqueo.
- [[Status - Rojo]] — Rechazo o no interés.
- [[Status - Negro]] — Cliente pausado o inactivo.

## Conceptos clave

- [[Propuesta Personalizada]]
- [[Documento de Términos y Condiciones]]
- [[Trigger Automático de Conversión]]
- [[Usuario del Hotel]]

## Relación con otros módulos

- [[Hotel/Hotel|Hotel]] — Destino final del onboarding; el hotel convertido comienza su ciclo operativo.
- [[Ventas/Ventas|Ventas]] — Área comercial dueña del proceso de onboarding.
- [[Requisición]] — Solo disponible a partir del status Naranja.
- [[Reclutamiento/Reclutamiento|Reclutamiento]] — Recibe al hotel una vez activo para iniciar cobertura.
