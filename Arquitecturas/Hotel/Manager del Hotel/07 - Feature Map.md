---
tags:
  - arquitectura
  - rol/manager-del-hotel
aliases:
  - Feature Map Manager del Hotel
---

# FEATURE MAP — MANAGER DEL HOTEL

---

## Mapa de funcionalidades por módulo

```
MANAGER DEL HOTEL / GERENTE DE DEPARTAMENTO
├── 📊 Dashboard
│   ├── KPIs del depto (cobertura, requisiciones pendientes, accidentes, cumplimiento)
│   ├── Bandeja de requisiciones pendientes (CTA "Revisar")
│   ├── Schedule de la semana (resumen)
│   ├── Posiciones críticas (sin colaborador asignado)
│   └── Acciones rápidas
│
├── 📋 Requisiciones
│   ├── Pendientes de autorización (Verde manzana)
│   ├── Autorizadas (Reclutamiento las tiene)
│   ├── En proceso (asignando colaboradores)
│   ├── Cubiertas (100%)
│   ├── Rechazadas (devueltas al Supervisor)
│   ├── ✓ Autorizar requisición
│   ├── ✗ Rechazar con observaciones
│   ├── 🗑️ Eliminar con posiciones (journal)
│   └── Ver historial / journal
│
├── 📅 Schedule
│   ├── Calendario semanal del depto
│   ├── Editar asignaciones (reordenar turnos, mover entre días)
│   ├── Marcar día de descanso
│   ├── Solicitar refuerzo a Reclutamiento
│   └── Exportar Schedule semanal
│
├── ⏱️ Timesheet
│   ├── Tabla semanal × colaborador con 6 ponches
│   ├── Indicador de Cumplimiento (Verde / Amarillo / Rojo)
│   ├── 📷 Generar / Renovar QR (exclusivo)
│   ├── Corregir ponche con justificación
│   └── Exportar Timesheet semanal
│
├── 👥 Mi Personal
│   ├── Lista de colaboradores asignados
│   ├── Semáforo del Colaborador visible
│   ├── 🩷 Poner en Stand-by (Rosa) — compartido con Supervisor
│   ├── 🔴 Reportar colaborador (Rojo) — exclusivo
│   └── Ver historial de incidencias
│
└── ⚫ Blacklist
    └── Consulta de vetados (sin acción)
```

---

## Funcionalidades del Manager del Hotel

| Feature | Permitido |
|---|---|
| Autorizar requisiciones | ✅ exclusivo (capa de seguridad) |
| Rechazar requisición con observaciones | ✅ |
| Generar / Renovar QR del Timesheet | ✅ exclusivo |
| Editar Schedule semanal | ✅ |
| Corregir ponche con justificación | ✅ |
| Poner colaborador en Stand-by (Rosa) | ✅ compartido con Supervisor |
| Reportar colaborador (Rojo) | ✅ exclusivo |
| Eliminar requisición con posiciones | ✅ (journal individual por posición) |
| Consultar Blacklist | ✅ (solo lectura) |
| Crear requisición | ❌ (eso es del Supervisor) |
| Ver Indicador de Lunch Extendido | ❌ (RR-H-15) |
| Agregar / Remover Blacklist | ❌ (depto Reclutamiento) |
| Ver Schedule global del hotel | ❌ (eso es del Manager General) |
| Reportar accidente laboral | ❌ (eso es del Supervisor) |
