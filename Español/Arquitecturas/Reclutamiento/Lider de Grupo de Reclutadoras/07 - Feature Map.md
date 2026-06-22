---
tags:
  - arquitectura
  - rol/lider-de-grupo
aliases:
  - Feature Map Líder de Grupo
---

# FEATURE MAP — LÍDER DE GRUPO DE RECLUTADORAS

---

## Mapa de funcionalidades (Primarias / Secundarias)

```
RECLUTAMIENTO — LÍDER DE GRUPO DE RECLUTADORAS
│
├── PRIMARIAS
│   │
│   ├── Requisición (Self-Pick + Semáforos)
│   │   ├── Cola de Autorizadas
│   │   ├── Mis Requisiciones (tomadas)
│   │   ├── Tomar requisición
│   │   ├── Marcar cubierta / parcial
│   │   ├── Liberar requisición
│   │   ├── Semáforo de Urgencia (lectura)
│   │   └── Semáforo de Posiciones (lectura)
│   │
│   ├── Reclutamiento (Pool + Crear + Asignación)
│   │   ├── Pool de Colaboradores (lista, filtros, detalle)
│   │   ├── Crear colaborador (Fase 1)
│   │   ├── Validar alta en App (Fase 2)
│   │   ├── Habilitar accesos
│   │   ├── Registrar entrevista
│   │   ├── Asignar colaborador a hotel
│   │   ├── Asignar al Schedule
│   │   ├── Reasignar / Desasignar
│   │   └── Atender incidencia 1er nivel (escala al Manager si excede)
│   │
│   ├── Blacklist
│   │   ├── Consulta de vetados
│   │   └── Agregar a Blacklist (con motivo y evidencia)
│   │
│   └── Mi Grupo (EXCLUSIVO del Líder)
│       ├── Lista de Reclutadoras del grupo
│       ├── Detalle por Reclutadora
│       ├── Métricas individuales
│       ├── Carga actual por persona
│       ├── Reasignar requisición a otra Reclutadora
│       └── Marcar disponibilidad (vacaciones / vuelta)
│
└── SECUNDARIAS
    │
    ├── Análisis
    │   ├── Dashboard — KPIs personales (como Reclutadora)
    │   ├── Dashboard — KPIs del grupo (extra del Líder)
    │   ├── Dashboard — Pool por posición
    │   ├── Dashboard — Mis Requisiciones
    │   ├── Dashboard — Cola de Autorizadas (vista corta)
    │   └── Reportes — Vista previa con métricas (cobertura, desempeño, casos escalados)
    │
    └── Utilidades
        ├── Dashboard — Acciones rápidas
        ├── Reportes — Generar reporte del grupo (EXCLUSIVO del Líder)
        ├── Reportes — Filtros (zona, fecha, posición)
        ├── Reportes — Enviar al Manager
        └── Reportes — Exportar (CSV / PDF)
```

---

## Funcionalidades — comparativa con otros roles

| Feature | Reclutadora | Líder | Manager |
|---|---|---|---|
| Tomar requisiciones (Self-Pick) | ✅ | ✅ | ⚠️ excepcional |
| Crear colaboradores | ✅ | ✅ | ✅ |
| Agregar a Blacklist | ✅ | ✅ | ✅ |
| Resolver disputa / Remover Blacklist | ❌ | ❌ | ✅ exclusivo |
| Mi Grupo | ❌ | ✅ exclusivo | ❌ |
| Reportes formales | ❌ | ✅ envía al Manager | ✅ recibe + genera |
| Mi Equipo (gestión usuarios) | ❌ | ❌ | ✅ exclusivo |
