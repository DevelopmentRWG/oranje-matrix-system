---
tags:
  - arquitectura
  - rol/manager-de-area
aliases:
  - Area Manager Feature Map
---

# FEATURE MAP — AREA MANAGER

---

## Feature map (Primary / Secondary)

```
HOTEL — MANAGER DE ÁREA / GERENTE DE DEPARTAMENTO
│
├── PRIMARIAS
│   │
│   ├── Requisiciones
│   │   ├── Pendientes de autorización (Verde manzana)
│   │   ├── Autorizadas (Reclutamiento las tiene)
│   │   ├── En proceso (asignando colaboradores)
│   │   ├── Cubiertas (100%)
│   │   ├── Rechazadas (devueltas al Supervisor)
│   │   ├── Autorizar requisición
│   │   ├── Rechazar con observaciones
│   │   ├── Eliminar con posiciones (journal)
│   │   └── Ver historial / journal
│   │
│   ├── Schedule
│   │   ├── Calendario semanal del depto
│   │   ├── Editar asignaciones (reordenar turnos, mover entre días)
│   │   ├── Marcar día de descanso
│   │   └── Solicitar refuerzo a Reclutamiento
│   │
│   ├── Timesheet
│   │   ├── Tabla semanal × colaborador con 6 ponches
│   │   ├── Indicador de Cumplimiento (Verde / Amarillo / Rojo)
│   │   ├── Generar / Renovar QR (exclusivo)
│   │   └── Corregir ponche con justificación
│   │
│   └── Mi Personal
│       ├── Lista de colaboradores asignados
│       ├── Semáforo del Colaborador visible
│       ├── Poner en Stand-by (Rosa) — compartido con Supervisor
│       ├── Reportar colaborador (Rojo) — exclusivo
│       └── Ver historial de incidencias
│
└── SECUNDARIAS
    │
    ├── Análisis
    │   ├── Dashboard — KPIs del depto (cobertura, requisiciones pendientes, accidentes, cumplimiento)
    │   ├── Dashboard — Bandeja de requisiciones pendientes (CTA "Revisar")
    │   ├── Dashboard — Schedule de la semana (resumen)
    │   └── Dashboard — Posiciones críticas (sin colaborador asignado)
    │
    └── Utilidades
        ├── Dashboard — Acciones rápidas
        ├── Schedule — Exportar Schedule semanal
        └── Timesheet — Exportar Timesheet semanal
```

---

## Area Manager features

| Feature | Allowed |
|---|---|
| Authorize requisitions | ✅ exclusive (security layer) |
| Reject requisition with observations | ✅ |
| Generate / Renew Timesheet QR | ✅ exclusive |
| Edit weekly Schedule | ✅ |
| Correct punch with justification | ✅ |
| Put collaborator on Stand-by (Pink) | ✅ shared with Supervisor |
| Report collaborator (Red) | ✅ exclusive |
| Delete requisition with positions | ✅ (individual journal per position) |
| Create requisition | ❌ (that is the Supervisor's) |
| View Extended Lunch Indicator | ❌ (RR-H-15) |
| View global hotel Schedule | ❌ (that is the General Manager's) |
| Report work accident | ❌ (that is the Supervisor's) |
