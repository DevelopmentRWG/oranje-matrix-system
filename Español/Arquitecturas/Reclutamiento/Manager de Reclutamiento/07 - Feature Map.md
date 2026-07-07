---
tags:
  - arquitectura
  - rol/manager-reclutamiento
aliases:
  - Feature Map Manager
---

# FEATURE MAP — MANAGER DE RECLUTAMIENTO

---

## Mapa de funcionalidades por módulo

```
MANAGER DE RECLUTAMIENTO
├── 📊 Dashboard
│   ├── KPIs globales del depto
│   ├── Requisiciones críticas (varadas)
│   ├── Casos escalados pendientes
│   └── Indicador de Calidad
│
├── 📋 Requisición (vista global + intervención excepcional + semáforos)
│   ├── Lista global con filtros
│   ├── Tomar requisición personal (caso especial)
│   ├── Asignar manual con justificación (caso VIP)
│   ├── Forzar cambio de semáforo (con log)
│   ├── Semáforo de Urgencia (lectura)
│   └── Semáforo de Posiciones (lectura)
│
├── 🧑‍🤝‍🧑 Reclutamiento (Pool + apoyo operativo)
│   ├── Pool completo
│   ├── Crear colaborador (backup)
│   ├── Editar colaborador
│   └── Asignar a hotel (excepcional)
│
├── ⚫ Blacklist (consulta + agregar)
│   ├── Consulta global
│   └── Agregar (igual que cualquier rol de Reclutamiento)
│
├── 👥 Mi Equipo (EXCLUSIVO del Manager)
│   ├── Vista de Líderes con métricas
│   ├── Vista de Reclutadoras anidada
│   ├── Dar de alta Líder / Reclutadora
│   ├── Editar usuario
│   ├── Mover Reclutadora a otro Líder
│   └── Marcar inactivo / vacaciones / baja
│
├── ⚠️ Incidencias (EXCLUSIVO del Manager)
│   ├── Casos abiertos
│   ├── Investigar
│   ├── Resolver con decisión final
│   └── Escalar a Dirección o a comercial (BD/BDC)
│
└── 📈 Reportes (recibe + genera)
    ├── Reportes recibidos de Líderes
    ├── Generar reporte global
    ├── Comparativa entre Líderes / zonas
    ├── Exportar (CSV / PDF / Excel)
    └── Programar envío recurrente
```

---

## Funcionalidades — comparativa con otros roles

| Feature | Reclutadora | Líder | Manager |
|---|---|---|---|
| Tomar requisición (Self-Pick) | ✅ | ✅ | ⚠️ excepcional |
| Agregar a Blacklist | ✅ | ✅ | ✅ |
| Mi Equipo (gestión completa) | ❌ | ❌ | ✅ exclusivo |
| Incidencias (decisión final) | ❌ | ❌ | ✅ exclusivo |
| Forzar cambio semáforo | ❌ | ❌ | ✅ con justificación |
| Reportes del departamento (seguimiento propio) | ❌ | ❌ | ✅ exclusivo |
| Escalar a Dirección | ❌ | ❌ | ✅ exclusivo |
