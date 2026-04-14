---
tags:
  - modulo/onboarding-hotel
aliases:
  - Semáforo Onboarding
  - Semáforo de Onboarding Hotel
---

# Semáforo Onboarding

Sistema de estados que representa el seguimiento de la negociación comercial con un hotel, desde su identificación como prospecto hasta su activación como cliente (o su pausa/rechazo).

> [!info]
> Este semáforo aplica únicamente al módulo de [[Onboarding-Hotel|Onboarding Hotel]]. Una vez el hotel alcanza [[Status - Naranja|Naranja]], su operación se rige por los semáforos del módulo [[Hotel/Hotel|Hotel]] ([[Semáforo de Requisición]], [[Semáforo del Colaborador]], etc.).

## Estados

| Color      | Estado                                     | Responsable                            |
| ---------- | ------------------------------------------ | -------------------------------------- |
| Gris       | [[Status - Gris\|Hotel identificado]]      | [[Business Developer\|BD]]             |
| Azul claro | [[Status - Azul Claro\|Contacto y recopilación de datos]] | [[Business Developer\|BD]] |
| Café       | [[Status - Café\|Renegociación / desbloqueo]] | [[Business Developer Coordinator\|BDC]] |
| Verde      | [[Status - Verde\|Propuesta enviada]]      | [[Business Developer\|BD]]             |
| Amarillo   | [[Status - Amarillo\|En seguimiento tras propuesta]] | [[Business Developer\|BD]]   |
| Rosa       | [[Status - Rosa\|Negociación de términos]] | [[Business Developer\|BD]] + [[Business Developer Coordinator\|BDC]] |
| Naranja    | [[Status - Naranja\|Acuerdo firmado, hotel cliente activo]] | [[Business Developer Coordinator\|BDC]] |
| Rojo       | [[Status - Rojo\|Rechazo o no interés]]    | [[Business Developer\|BD]]             |
| Negro      | [[Status - Negro\|Cliente pausado o inactivo]] | [[Business Developer Coordinator\|BDC]] |

## Relacionado

- [[Onboarding-Hotel]]
- [[Flujo de Onboarding]]
- [[Business Developer]]
- [[Business Developer Coordinator]]
