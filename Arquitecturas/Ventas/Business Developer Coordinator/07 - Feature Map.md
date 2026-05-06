---
tags:
  - arquitectura
  - rol/bdc
aliases:
  - Feature Map BDC
---

# FEATURE MAP — BUSINESS DEVELOPER COORDINATOR

---

## Mapa de funcionalidades por módulo

```
BUSINESS DEVELOPER COORDINATOR (BDC)
├── 📊 Dashboard
│   ├── Embudo de conversión
│   ├── Heatmap por zona
│   ├── Ranking de BDs
│   ├── Casos críticos (T&C pendientes, Café, alertas calidad)
│   └── Acciones rápidas
│
├── 📋 Pipeline (vista global del territorio)
│   ├── Todos los status (Gris → Naranja + Rojo / Negro / Café)
│   ├── Filtros por BD / ruta / zona / status / días en status
│   ├── 💬 Comentar al expediente
│   ├── 📤 Reasignar prospecto a otro BD
│   └── Bandeja Café (sub-vista dedicada)
│
├── 📄 Documentos T&C
│   ├── Pendientes de validación (badge >24h)
│   ├── Validados / Rechazados
│   ├── ✓ Validar T&C (sí final)
│   ├── ✗ Rechazar con observaciones
│   └── 💬 Comentar al BD
│
├── ✅ Conversión
│   ├── Listos para conversión (Rosa + T&C validado)
│   ├── ➕ Crear Usuario del Hotel (precondición)
│   ├── ✓ Aprobar conversión (sí final)
│   └── Convertidos (últimos 30 días)
│
├── 👥 Mi Equipo
│   ├── BDs a cargo con métricas
│   ├── Detalle individual (cobertura, tiempos, casos)
│   ├── 💬 Comunicar
│   └── 📊 Solicitar reporte específico
│
├── 🏨 Clientes Activos
│   ├── Activos (Naranja)
│   ├── ⚫ Negro (pausados)
│   ├── Marcar Negro (exclusivo)
│   └── Reactivar desde Negro
│
└── 📈 Reportes
    ├── Pipeline · Conversión · Desempeño · Café · Negro · Calidad · Ejecutivo
    ├── 📥 Exportar (CSV / PDF / Excel)
    ├── 📤 Enviar a dirección
    ├── 📅 Programar envío recurrente
    └── Histórico de envíos
```

---

## Funcionalidades del BDC

| Feature | Permitido |
|---|---|
| Validar T&C | ✅ exclusivo |
| Crear Usuario del Hotel | ✅ exclusivo |
| Aprobar conversión | ✅ exclusivo (RR-V-01) |
| Desbloquear Café | ✅ exclusivo (RR-V-04) |
| Reactivar desde Café | ✅ exclusivo |
| Marcar Negro | ✅ exclusivo (RR-V-05) |
| Reactivar desde Negro | ✅ exclusivo |
| Negociar (Rosa) | ✅ junto al BD |
| Crear Documento de T&C | ✅ compartido |
| Comentar al expediente | ✅ |
| Reasignar prospecto a otro BD | ✅ |
| Mi Equipo (BDs a cargo) | ✅ exclusivo |
| Generar reportes ejecutivos | ✅ exclusivo |
| Enviar a dirección | ✅ exclusivo |
| Identificar prospecto | ❌ (rol del BD) |
| Elaborar Propuesta | ❌ (rol del BD) |
| Marcar Rojo | ❌ (RR-V-06 — BD exclusivo) |
| Operación post-Naranja | ❌ (RR-V-12 — depto Hotel y Reclutamiento) |
