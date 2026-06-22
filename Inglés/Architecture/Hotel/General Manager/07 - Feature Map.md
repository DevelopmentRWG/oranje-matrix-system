---
tags:
  - arquitectura
  - rol/manager-general
aliases:
  - Feature Map General Manager
---

# FEATURE MAP — GENERAL MANAGER

---

## Functionality map (Primary / Secondary)

```
HOTEL — MANAGER GENERAL (GM, solo jerarquía extendida)
│
├── PRIMARIAS
│   │
│   ├── Schedule Global (consulta)
│   │   ├── Calendario consolidado del hotel
│   │   ├── Vista por depto + agregada
│   │   ├── Drill-down a posiciones / colaboradores
│   │   └── Filtros por depto / posición / cobertura / semana
│   │
│   ├── Timesheet Global (consulta)
│   │   ├── Tabla consolidada del hotel
│   │   ├── Indicador de Cumplimiento por colaborador y depto
│   │   ├── Resumen por depto (horas pagables, brutas, deducciones)
│   │   └── Drill-down a jornadas individuales
│   │
│   ├── Requisiciones (vista global, supervisión)
│   │   ├── Todos los estados (pendientes, autorizadas, en proceso, cubiertas, rechazadas)
│   │   ├── Filtros por depto / Gerente / urgencia / posición
│   │   ├── Comentar al expediente (visible para Gerente)
│   │   └── Escalar requisición demorada a Reclutamiento
│   │
│   └── Mi Equipo del Hotel
│       ├── Gerentes de Departamento
│       ├── Supervisores
│       ├── Métricas individuales
│       └── Comunicar (chat / nota)
│
└── SECUNDARIAS
    │
    ├── Análisis
    │   ├── Dashboard — KPIs globales del hotel (cobertura, cumplimiento, calidad)
    │   ├── Dashboard — Heatmap por depto y día
    │   ├── Dashboard — Ranking de Gerentes (autorización, cobertura)
    │   ├── Dashboard — Alertas críticas (cobertura <70%, accidentes, calidad Rojo)
    │   ├── Reportes — Plantillas: Cobertura · Desempeño · Cumplimiento · Calidad · Accidentes · Indicadores
    │   └── Reportes — Vista previa
    │
    └── Utilidades
        ├── Dashboard — Acciones rápidas
        ├── Schedule Global — Exportar Schedule consolidado
        ├── Timesheet Global — Exportar Timesheet consolidado
        ├── Requisiciones — Generar reporte de tiempos de autorización por Gerente
        ├── Mi Equipo del Hotel — Solicitar reporte específico
        ├── Reportes — Filtros (rango fechas / depto / tipo)
        ├── Reportes — Exportar (CSV / PDF / Excel)
        ├── Reportes — Enviar a dirección
        ├── Reportes — Programar envío recurrente
        └── Reportes — Histórico de reportes enviados
```

---

## General Manager functionalities

| Feature | Allowed |
|---|---|
| View global hotel Schedule | ✅ exclusive (in extended hierarchy) |
| View global hotel Timesheet | ✅ exclusive |
| Comment on requisition file | ✅ |
| Escalate delayed requisition | ✅ |
| Request report from Department Manager | ✅ |
| Generate executive report | ✅ exclusive |
| Send to direction | ✅ exclusive |
| Schedule recurring send | ✅ |
| Create / Authorize requisition | ❌ (RR-H-14) |
| Generate QR / Correct punch | ❌ |
| Edit Schedule | ❌ |
| Stand-by / Report (Red) | ❌ |
| Report workplace accident | ❌ |
| Add / remove Managers or Supervisors | ❌ (Administrator) |
| View Extended Lunch Indicator | ❌ (RR-H-15) |
