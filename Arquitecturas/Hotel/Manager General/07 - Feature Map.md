---
tags:
  - arquitectura
  - rol/manager-general
aliases:
  - Feature Map Manager General
---

# FEATURE MAP — MANAGER GENERAL

---

## Mapa de funcionalidades por módulo

```
MANAGER GENERAL (GM) — solo jerarquía extendida
├── 📊 Dashboard
│   ├── KPIs globales del hotel (cobertura, cumplimiento, calidad)
│   ├── Heatmap por depto y día
│   ├── Ranking de Gerentes (autorización, cobertura)
│   ├── Alertas críticas (cobertura <70%, accidentes, calidad Rojo)
│   └── Acciones rápidas
│
├── 📅 Schedule Global (consulta)
│   ├── Calendario consolidado del hotel
│   ├── Vista por depto + agregada
│   ├── Drill-down a posiciones / colaboradores
│   ├── Filtros por depto / posición / cobertura / semana
│   └── Exportar Schedule consolidado
│
├── ⏱️ Timesheet Global (consulta)
│   ├── Tabla consolidada del hotel
│   ├── Indicador de Cumplimiento por colaborador y depto
│   ├── Resumen por depto (horas pagables, brutas, deducciones)
│   ├── Drill-down a jornadas individuales
│   └── Exportar Timesheet consolidado
│
├── 📋 Requisiciones (vista global, supervisión)
│   ├── Todos los estados (pendientes, autorizadas, en proceso, cubiertas, rechazadas)
│   ├── Filtros por depto / Gerente / urgencia / posición
│   ├── 💬 Comentar al expediente (visible para Gerente)
│   ├── 🚨 Escalar requisición demorada a Reclutamiento
│   └── 📊 Generar reporte de tiempos de autorización por Gerente
│
├── 👥 Mi Equipo del Hotel
│   ├── 🧑‍💼 Gerentes de Departamento
│   ├── 🦺 Supervisores
│   ├── Métricas individuales
│   ├── 💬 Comunicar (chat / nota)
│   └── 📊 Solicitar reporte específico
│
├── 📈 Reportes
│   ├── Plantillas: Cobertura · Desempeño · Cumplimiento · Calidad · Accidentes · Indicadores
│   ├── Filtros (rango fechas / depto / tipo)
│   ├── Vista previa
│   ├── 📤 Exportar (CSV / PDF / Excel)
│   ├── 📤 Enviar a dirección
│   ├── 📅 Programar envío recurrente
│   └── Histórico de reportes enviados
│
└── ⚫ Blacklist (consulta)
    └── Consulta global con filtros
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
| Consultar Blacklist | ✅ (solo lectura) |
| Crear / Autorizar requisición | ❌ (RR-H-14) |
| Generar QR / Corregir ponche | ❌ |
| Editar Schedule | ❌ |
| Stand-by / Reportar (Rojo) | ❌ |
| Reportar accidente laboral | ❌ |
| Dar de alta / baja Gerentes o Supervisores | ❌ (Administrador) |
| Ver Indicador de Lunch Extendido | ❌ (RR-H-15) |
