---
tags:
  - arquitectura
  - rol/business-developer
aliases:
  - Feature Map Business Developer
---

# FEATURE MAP — BUSINESS DEVELOPER

---

## Mapa de funcionalidades por módulo

```
BUSINESS DEVELOPER (BD)
├── 📊 Dashboard
│   ├── KPIs personales (prospectos por status, conversiones)
│   ├── Próximos seguimientos
│   ├── Alertas (sin actividad >X días)
│   └── Acciones rápidas
│
├── 📋 Pipeline (Mis prospectos por status del Semáforo Onboarding)
│   ├── ⚪ Gris · 🔵 Azul Claro · 🟢 Verde · 🟡 Amarillo · 🩷 Rosa
│   ├── 🟠 Naranja · 🔴 Rojo · ⚫ Negro · 🟤 Café · 📂 Toda
│   ├── ➕ Identificar prospecto
│   ├── ✏️ Crear / Editar perfil del hotel
│   ├── ➕ Registrar visita en frío
│   ├── ➕ Registrar intento de contacto
│   ├── ✏️ Avanzar status (Gris → Azul Claro → Verde → Amarillo → Rosa)
│   ├── 🔴 Marcar Rojo
│   ├── ↩️ Reactivar desde Rojo (a Azul Claro)
│   └── ☕ Marcar Café (BDC desbloquea)
│
├── 🗺️ Mi Territorio
│   ├── Mapa con rutas y zonas asignadas
│   ├── Pines por status del prospecto
│   ├── Filtros por ruta / zona / status
│   ├── Lista lateral de prospectos
│   └── Planeador de ruta del día
│
├── 📝 Propuestas
│   ├── Borradores
│   ├── Enviadas
│   ├── Aceptadas / Rechazadas
│   ├── Histórico
│   ├── ➕ Elaborar Propuesta Personalizada (Verde)
│   ├── 📤 Enviar al hotel
│   ├── ✏️ Editar borrador
│   ├── 📥 Exportar PDF
│   └── 📋 Duplicar como plantilla
│
├── 📄 Documentos T&C
│   ├── Borradores
│   ├── Pendientes de validación BDC
│   ├── Validados
│   ├── ➕ Crear Documento de T&C (Amarillo)
│   ├── ✏️ Editar borrador
│   └── 📤 Enviar al BDC
│
└── 🏨 Clientes Activos
    ├── Lista de clientes (post-Naranja)
    ├── Datos comerciales (no operativos)
    ├── Histórico del onboarding
    └── 📞 Registrar contacto comercial
```

---

## Funcionalidades del Business Developer

| Feature | Permitido |
|---|---|
| Identificar prospecto (Gris) | ✅ |
| Crear perfil (Azul Claro) | ✅ |
| Registrar visita en frío | ✅ |
| Elaborar Propuesta Personalizada | ✅ exclusivo |
| Enviar propuesta | ✅ |
| Crear Documento de T&C | ✅ (compartido con BDC) |
| Negociar (Rosa) | ✅ (junto al BDC) |
| Marcar Rojo | ✅ |
| Reactivar desde Rojo | ✅ |
| Marcar Café | ✅ |
| Validar T&C | ❌ (BDC) |
| Crear Usuario del Hotel | ❌ (BDC) |
| Aprobar conversión | ❌ (RR-V-01) |
| Desbloquear Café | ❌ (RR-V-04) |
| Marcar/Reactivar Negro | ❌ (RR-V-05) |
| Mi Equipo (BDs a cargo) | ❌ (BDC) |
| Generar reportes ejecutivos | ❌ (BDC) |
| Visibilidad global del depto | ❌ (solo mi territorio) |
