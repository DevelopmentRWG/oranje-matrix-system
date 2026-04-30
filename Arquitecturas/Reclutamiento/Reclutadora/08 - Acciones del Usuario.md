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
| Tomar requisición de la bandeja           | La requisición pasa de Autorizadas a Mis Requisiciones; semáforo cambia a Amarillo (En proceso) |
| Liberar requisición tomada                | La requisición vuelve a la bandeja de Autorizadas para que otro la tome                         |
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
