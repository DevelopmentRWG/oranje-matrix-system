---
tags:
  - arquitectura
  - rol/manager-general
aliases:
  - Feature Map Manager General
---

# FEATURE MAP — MANAGER GENERAL

---

## Mapa de funcionalidades (Primarias / Secundarias)

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

## Funcionalidades del Manager General

| Feature | Permitido |
|---|---|
| Ver Schedule global del hotel | ✅ exclusivo (en jerarquía extendida) |
| Ver Timesheet global del hotel | ✅ exclusivo |
| Comentar al expediente de requisición | ✅ |
| Escalar requisición demorada | ✅ |
| Solicitar reporte a Gerente de Departamento | ✅ |
| Generar reporte ejecutivo | ✅ exclusivo |
| Enviar a dirección | ✅ exclusivo |
| Programar envío recurrente | ✅ |
| Crear / Autorizar requisición | ❌ (RR-H-14) |
| Generar QR / Corregir ponche | ❌ |
| Editar Schedule | ❌ |
| Stand-by / Reportar (Rojo) | ❌ |
| Reportar accidente laboral | ❌ |
| Dar de alta / baja Gerentes o Supervisores | ❌ (Administrador) |
| Ver Indicador de Lunch Extendido | ❌ (RR-H-15) |
