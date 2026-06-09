---
tags:
  - arquitectura
  - rol/reclutadora
aliases:
  - Acciones Reclutadora
---

# 6. ACCIONES DEL USUARIO — RECLUTADORA

---

| Acción                                    | Resultado                                                                                       |
| ----------------------------------------- | ----------------------------------------------------------------------------------------------- |
| Tomar requisición de la bandeja           | Me uno como reclutador participante; la requisición aparece en Mis Requisiciones; semáforo a Amarillo (En proceso). No bloquea a las demás (Self-Pick colaborativo) |
| Unirse a requisición ya tomada            | Me agrego como reclutador participante adicional sin desplazar a los existentes ni retroceder el semáforo; el avance de cobertura es compartido. Se registra en el Historial |
| Ver reclutadores activos                  | Muestra la lista de reclutadores participantes que trabajan la requisición ahora mismo (rol + nombre) |
| Ver historial de la requisición           | Muestra el timeline cronológico inmutable con actor: quién tomó/salió y quién asignó/desasignó cada colaborador, con fecha y autor |
| Salir de la requisición                   | Me retira solo a mí; la requisición sigue En proceso si quedan otros reclutadores; no resetea lo asignado; vuelve a Autorizada solo cuando sale el último reclutador |
| Buscar candidato en Pool                  | Resulta lista filtrada de colaboradores disponibles                                             |
| Completar formulario de nuevo colaborador | Los datos del candidato quedan cargados en el sistema con estado 'Pendiente de validación'      |
| Guardar borrador del colaborador          | El registro se guarda con estado 'Borrador'                                                     |
| Enviar candidato a validación             | El registro cambia a estado 'Pendiente de validación'                                           |
| Validar alta en App                       | El colaborador queda aprobado e ingresa al Pool con estado Blanco                               |
| Habilitar accesos del colaborador         | Sistema propaga accesos a los paneles del colaborador                                           |
| Registrar entrevista                      | El resultado queda ligado al perfil del candidato                                               |
| Consultar Blacklist                       | Sistema muestra si el candidato está vetado                                                     |
| Asignar colaborador a posición            | Se actualiza el % de cobertura de la requisición                                                |
| Asignar al Schedule                       | Se genera entrada en el Schedule semanal del hotel                                              |
| Reasignar colaborador a otro hotel        | Historial de asignaciones se actualiza                                                          |
| Desasignar colaborador                    | Libera la posición; notifica al hotel                                                           |
| Marcar requisición como cubierta          | Solicita cierre al Manager (solo si cobertura = 100%)                                           |
| Marcar requisición como parcial           | Cierra la requisición con faltantes                                                             |
| Cancelar acción                           | Los cambios no se guardan; se regresa a la vista anterior                                       |
