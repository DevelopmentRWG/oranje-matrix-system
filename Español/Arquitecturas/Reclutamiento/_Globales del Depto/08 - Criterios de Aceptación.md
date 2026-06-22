---
tags:
  - arquitectura
  - departamento/reclutamiento
aliases:
  - Criterios de Aceptación Reclutamiento
---

# ✅ CRITERIOS DE ACEPTACIÓN — DEPARTAMENTO DE RECLUTAMIENTO

---

| #         | Criterio                                                                                                          |
| --------- | ----------------------------------------------------------------------------------------------------------------- |
| **AC-01** | El formulario de creación de colaborador no puede enviarse si hay campos obligatorios vacíos.                     |
| **AC-02** | El documento de identidad debe ser único en el sistema.                                                           |
| **AC-03** | El teléfono debe tener formato válido (10 dígitos).                                                               |
| **AC-04** | Al enviar el formulario, el candidato aparece en estado 'Pendiente de validación' en la lista.                    |
| **AC-05** | El sistema bloquea el registro si el candidato figura en Blacklist.                                               |
| **AC-06** | La requisición autorizada aparece en la bandeja de Autorizadas en menos de 30 segundos tras aprobación del hotel. |
| **AC-07** | Cuando el PRIMER reclutador toma una requisición (Self-Pick colaborativo), el semáforo cambia automáticamente a Amarillo; las tomas posteriores no lo vuelven a disparar. |
| **AC-08** | La búsqueda en el Pool entrega resultados en menos de 2 segundos.                                                 |
| **AC-09** | El Pool permite combinar al menos 4 filtros simultáneamente.                                                      |
| **AC-10** | Solo se puede marcar una requisición como "Cubierta" si todas las posiciones están al 100%.                       |
| **AC-11** | El sistema bloquea la asignación si el colaborador está en Blacklist y muestra alerta visible.                    |
| **AC-12** | Al asignar un colaborador, la requisición actualiza su porcentaje de cobertura en tiempo real.                    |
| **AC-13** | Al asignar un colaborador, se genera automáticamente entrada en el Schedule del hotel.                            |
| **AC-14** | Las acciones excepcionales del Manager requieren comentario obligatorio antes de ejecutarse.                      |
| **AC-15** | El sistema notifica al rol correspondiente en menos de 1 minuto tras un evento relevante.                         |
| **AC-16** | El cifrado de datos sensibles cumple con la política de protección de datos vigente.                              |
| **AC-17** | La interfaz es responsive desde 7 pulgadas (tablet/desktop).                                                      |
| **AC-18** | La disponibilidad mensual del módulo es del 99.5%.                                                                |
| **AC-19** | Cada cambio de estado en una requisición o colaborador queda registrado en el journal con fecha, autor y motivo.  |
| **AC-20** | La numeración de requisiciones y tarjetas sigue el formato `AAAAMMDDHHMM + Homoclave`.                            |
| **AC-21** | Una requisición ya tomada puede ser tomada por otro reclutador que se agrega sin desplazar a los existentes ni retroceder el semáforo. |
| **AC-22** | La ficha de la requisición lista a todos los reclutadores activos.                                               |
| **AC-23** | Si dos reclutadores asignan la misma posición, gana la primera y la segunda ve "posición ya cubierta".          |
| **AC-24** | El Historial muestra cronológicamente quién tomó/salió y quién asignó/desasignó cada colaborador, con fecha y autor. |
