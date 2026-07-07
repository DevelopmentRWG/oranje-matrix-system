---
tags:
  - arquitectura
  - rol/manager-reclutamiento
aliases:
  - Manager Feature Map
---

# FEATURE MAP — RECRUITMENT MANAGER

---

## Map of functionalities by module

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
├── ⚫ Blacklist (consult + add)
│   ├── Global consult
│   └── Add (same as any Recruitment role)
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

## Functionalities — comparison with other roles

| Feature | Recruiter | Leader | Manager |
|---|---|---|---|
| Take requisition (Self-Pick) | ✅ | ✅ | ⚠️ exceptional |
| Add to Blacklist | ✅ | ✅ | ✅ |
| My Team (full management) | ❌ | ❌ | ✅ exclusive |
| Incidents (final decision) | ❌ | ❌ | ✅ exclusive |
| Force status light change | ❌ | ❌ | ✅ with justification |
| Department reports (Manager's own tracking and supervision) | ❌ | ❌ | ✅ exclusive |
| Escalate to Management | ❌ | ❌ | ✅ exclusive |
