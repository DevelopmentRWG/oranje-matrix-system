---
tags:
  - arquitectura
  - rol/supervisor-hotel
aliases:
  - Supervisor Feature Map
---

# FEATURE MAP — SUPERVISOR

---

## Feature map (Primary / Secondary)

```
HOTEL — SUPERVISOR (SUP)
│
├── PRIMARIAS
│   │
│   ├── Requisiciones
│   │   ├── Borradores
│   │   ├── Pendientes de autorización (Verde manzana)
│   │   ├── Rechazadas (con observaciones del Manager de Área)
│   │   ├── Autorizadas (en Reclutamiento)
│   │   ├── En proceso (Reclutamiento asignando)
│   │   ├── Cubiertas (100%)
│   │   ├── Crear nueva requisición
│   │   ├── Editar borrador / requisición rechazada
│   │   ├── Enviar a autorización
│   │   └── Eliminar borrador
│   │
│   ├── Schedule (consulta)
│   │   ├── Calendario semanal del depto
│   │   ├── Filtros por posición / cobertura / semana
│   │   └── Sugerir refuerzo (prefill nueva requisición)
│   │
│   ├── Timesheet (consulta)
│   │   ├── Tabla semanal × colaborador
│   │   └── Indicador de Cumplimiento (Verde / Amarillo / Rojo)
│   │
│   ├── Mi Personal
│   │   ├── Lista de colaboradores asignados
│   │   ├── Semáforo del Colaborador visible
│   │   ├── Poner en Stand-by (Rosa) — compartido con Manager de Área
│   │   ├── Contactar al colaborador
│   │   └── Ver historial
│   │
│   └── Accidentes Laborales
│       ├── Casos activos (en investigación por Inspector)
│       ├── Casos cerrados (último mes)
│       ├── Histórico
│       ├── Reportar accidente — Escenario A (acudir tras notificación)
│       ├── Reportar accidente — Escenario B (detectar primero)
│       └── Captura presencial (foto, evidencia, testigos)
│
└── SECUNDARIAS
    │
    ├── Análisis
    │   ├── Dashboard — KPIs personales (mis requisiciones, accidentes activos)
    │   ├── Dashboard — Requisiciones rechazadas (necesitan corrección)
    │   └── Dashboard — Posiciones críticas del Schedule
    │
    └── Utilidades
        ├── Dashboard — Acciones rápidas
        ├── Schedule — Exportar Schedule semanal
        └── Timesheet — Exportar Timesheet
```

---

## Supervisor Functionalities

| Feature | Allowed |
|---|---|
| Create requisitions | ✅ main action |
| Edit draft / rejected requisition | ✅ |
| Send for authorization | ✅ |
| Delete draft | ✅ |
| Report accidents (Scenarios A and B) | ✅ main action |
| Put on Stand-by (Pink) | ✅ shared with Area Manager |
| Suggest staffing reinforcement | ✅ |
| Consult Schedule / Timesheet | ✅ (read-only) |
| Authorize requisition | ❌ (security layer RR-H-02) |
| Generate Timesheet QR | ❌ (RR-H-09) |
| Correct clock-in | ❌ (RR-H-09 → only Area Manager) |
| Report collaborator (Red) | ❌ (RR-H-10) |
| Edit Schedule | ❌ (only Area Manager) |
| View Extended Lunch Indicator | ❌ (RR-H-15) |
| Global hotel visibility | ❌ (only General Manager) |
