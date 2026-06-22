---
tags:
  - modulo/core
aliases:
  - System Architecture
  - Blueprint Oranje
---
# Organizational Architecture of the Oranje Matrix System Vault
## Blueprint to replicate in a new system

The **oranje-matrix-system** vault documents a staffing system for hotels. This is the architecture extracted as a replicable pattern for any new organizational system.

---

## 1. Design principle: Departmental Hub-and-Spoke

```
                    Home.md (hub central)
                         │
        ┌────────┬───────┼───────┬────────┐
        │        │       │       │        │
   Departamento Departamento  Core/   Entidad   Simulaciones/
       A/          B/      │    Central/
                       ┌───┼───┐
                  Catálogos/ Módulos/ Semáforos/
```

**Rule:** Everything is accessed from `Home.md`. Each top-level folder is autonomous but interconnected via wikilinks.

---

## 2. Folder structure (replicable pattern)

```
nuevo-sistema/
│
├── Home.md                          ← Índice maestro (hub central)
│
├── Core/                            ← Módulos transversales compartidos
│   ├── Catálogos/                   ← Datos de referencia (enums, listas)
│   │   ├── Catalogo-A.md
│   │   └── Catalogo-B.md
│   └── Módulos/                     ← Entidades y procesos del sistema
│       ├── Semáforos/               ← State-machines visuales (indicadores)
│       │   ├── Semáforo de X.md
│       │   └── Indicador de Y.md
│       ├── [Submodulo-Complejo]/    ← Carpeta propia si tiene flujo + entidad
│       │   ├── Entidad.md
│       │   └── Flujo de Entidad.md
│       ├── Modulo-Simple.md         ← Archivo único si no necesita flujo
│       └── Reglas de Negocio.md     ← Fuente de verdad centralizada
│
├── [Departamento-A]/                ← Un folder por departamento
│   ├── Departamento-A.md           ← Hub/índice del departamento
│   ├── Rol-1.md                    ← Un archivo por rol
│   ├── Rol-2.md
│   ├── Reglas de Departamento-A.md ← Reglas locales del departamento
│   └── Flujo de Proceso-A.md      ← Procesos propios del departamento
│
├── [Departamento-B]/
│   ├── ...mismo patrón...
│   └── Subfolder/                   ← Sub-áreas si el departamento es complejo
│       ├── Subfolder.md            ← Hub del sub-área
│       ├── Flujo de Sub-Proceso.md
│       └── Conceptos/             ← Definiciones propias del sub-área
│
├── [Entidad-Central]/               ← La entidad principal del negocio
│   ├── Entidad-Central.md
│   └── Reglas de Entidad.md
│
├── [Capa-de-Control]/               ← QA, auditoría, supervisión
│   ├── Control.md
│   ├── Reglas de Control.md
│   ├── Métricas y KPIs.md
│   └── Dashboard.md
│
├── Simulaciones/                    ← Documentación narrativa
│   ├── Simulación - Vista de Dept-A.md
│   └── Simulación - Vista de Dept-B.md
│
└── .claude/                         ← Agentes IA (opcional)
    └── agents/
        ├── consultor.md             ← Agente de lectura/consulta
        └── editor.md               ← Agente de escritura
```

---

## 3. File type taxonomy

Each file in the vault has a **type** that determines its internal structure:

| Type | Naming convention | Purpose | Example |
|------|---------------------|-----------|---------|
| **Hub/Index** | `[Nombre-Departamento].md` | Entry point to a folder | `Hotel.md`, `QA.md` |
| **Role** | `[Título del Rol].md` | Defines an actor's responsibilities | `Reclutadora.md`, `Inspector.md` |
| **Rules** | `Reglas de [Área].md` | Constraints and policies | `Reglas del Hotel.md` |
| **Flow** | `Flujo de [Proceso].md` | Step-by-step workflow | `Flujo de Nómina.md` |
| **Status Light** | `Semáforo de [Entidad].md` | Visual state-machine | `Semáforo del Colaborador.md` |
| **Indicator** | `Indicador de [Métrica].md` | KPI with thresholds | `Indicador de Calidad.md` |
| **Catalog** | `[Nombre descriptivo].md` | Reference data (enums) | `Posiciones.md`, `Zonas.md` |
| **Module** | `[Nombre del módulo].md` | System entity | `Schedule.md`, `Contrato.md` |
| **Simulation** | `Simulación - [Perspectiva].md` | Narrative walkthrough | `Simulación - Vista de QA.md` |
| **Concept** | `[Nombre del concepto].md` | Definition of a sub-element | `Propuesta Personalizada.md` |

---

## 4. Template for each file type

### Departmental Hub/Index
```markdown
---
tags:
  - department/[name]
aliases:
  - [Alternative alias]
---
# [Department Name]

> One-line description of the department's purpose.

## Roles
- [[Role-1]]
- [[Role-2]]

## Processes
- [[Flow of X]]

## Rules
- [[Department Rules]]

## Relationship with other modules
- [[Related-Core-Module]]
- [[Other-Department]]
```

### Role
```markdown
---
tags:
  - role/[department]
aliases:
  - [Alternative role name]
---
# [Role Name]

> Short description.

## Responsibilities
- Responsibility 1
- Responsibility 2

## Interactions
- With [[Other Role]]: description of the interaction
- With [[Module]]: how it uses it
```

### Flow
```markdown
---
tags:
  - flow/[area]
aliases:
  - [Alias]
---
# Flow of [Process]

## Actors involved
| Actor | Role in the flow |
|-------|----------------|
| [[Role-1]] | Description |

## Steps
1. **[Actor]** does X
2. Condition? → YES: step 3 / NO: step 4
3. ...

## Key rules
- Applicable rule 1
- Applicable rule 2

## Related
- [[Status Light of X]]
- [[Module Y]]
```

### Status Light (State-Machine)
```markdown
---
tags:
  - status-light/[entity]
aliases:
  - Status [Entity] [Color1]
  - Status [Entity] [Color2]
---
# Status Light of [Entity]

| Color | State | Responsible | Description |
|-------|--------|-------------|-------------|
| Green | Active | System | ... |
| Yellow | At risk | [[Role]] | ... |
| Red | Critical | [[Role]] | ... |

## Detail by state

### Green — Active
- Entry condition: ...
- Allowed actions: ...
- Possible transitions: → Yellow (if...), → Red (if...)

## Key rules
- ...

## Related
- [[Flow of X]]
- [[Business Rules]]
```

### Business Rules (centralized)
```markdown
---
tags:
  - modulo/core
---
# Business Rules

## [Domain 1: Central Entity]
- Rule 1
- Rule 2

> [!important] Highlighted critical rule

## [Domain 2: Process X]
- ...

> [!warning] Security restriction
```

### Catalog
```markdown
---
tags:
  - catalog/[name]
---
# [Catalog name]

- Value 1
- Value 2
- Value 3

> [!info] This list is not exhaustive / is exhaustive.

## Related
- [[Module that consumes it]]
```

---

## 5. Connection system (wikilinks)

### Reference hierarchy
```
Home.md
  └─→ [Dept].md (hub)
        ├─→ Roles (hacia abajo)
        ├─→ Flujos (hacia abajo)
        ├─→ Reglas locales (lateral)
        └─→ Core/Módulos (hacia el centro)
              ├─→ Semáforos (lateral)
              ├─→ Catálogos (datos)
              └─→ Reglas de Negocio (fuente de verdad)
```

### Connection rule
- **Vertical:** Hub → Roles → Flows (from general to specific)
- **Horizontal:** Department ↔ Department (when they interact)
- **Central:** Everything points to `Core/Módulos/` for shared entities
- **Aliases:** Allow multiple ways to reference the same concept

---

## 6. Tag system (frontmatter)

```
Patrón: [tipo]/[área]

Tipos usados:
  - modulo/[nombre]        → Módulos core y departamentales
  - departamento/[nombre]  → Archivos departamentales
  - rol/[departamento]     → Roles de cada área
  - flujo/[area]           → Flujos de proceso
  - semaforo/[entidad]     → Indicadores de estado
  - catalogo/[nombre]      → Catálogos de referencia
```

---

## 7. System layers (bottom-up)

```
┌─────────────────────────────────────────────┐
│  CAPA 5: Simulaciones (documentación narrativa) │
├─────────────────────────────────────────────┤
│  CAPA 4: QA / Control (transversal)            │
├─────────────────────────────────────────────┤
│  CAPA 3: Departamentos operativos              │
│  (Reclutamiento, Ventas, Inspección, etc.)     │
├─────────────────────────────────────────────┤
│  CAPA 2: Módulos Core + Semáforos              │
│  (Schedule, Pool, Timesheet, Contrato, etc.)   │
├─────────────────────────────────────────────┤
│  CAPA 1: Fundamentos                          │
│  (Catálogos + Reglas de Negocio + Entidad Central) │
└─────────────────────────────────────────────┘
```

- **Layer 1** depends on no one. Defines the base data and the rules.
- **Layer 2** implements the rules as operational modules and state-machines.
- **Layer 3** consumes the core modules for its departmental processes.
- **Layer 4** observes all lower layers and measures their performance.
- **Layer 5** documents complete walkthroughs across all layers.

---

## 8. Numbers of the current system (reference)

| Concept | Quantity |
|----------|----------|
| Departments | 8 (+ Core + Central Entity) |
| Roles | 14 |
| Flows | 6 |
| Status Lights/Indicators | 7 |
| Catalogs | 5 |
| Core Modules | ~10 |
| Simulations | 7 |
| Total .md files | ~89 |

---

## 9. Checklist to replicate this architecture in a new system

1. [ ] Define the **central entity** of the business (equivalent to "Collaborator")
2. [ ] Identify the **departments** that operate over that entity
3. [ ] Create `Home.md` as the central hub
4. [ ] Create `Core/` with:
   - [ ] `Catálogos/` — system reference data
   - [ ] `Módulos/` — entities shared across departments
   - [ ] `Módulos/Semáforos/` — state indicators per key entity
   - [ ] `Reglas de Negocio.md` — centralized source of truth
5. [ ] For each department create a folder with:
   - [ ] `[Dept].md` — hub/index
   - [ ] One file per role
   - [ ] `Reglas de [Dept].md`
   - [ ] `Flujo de [Proceso].md` if it has its own processes
6. [ ] Create `Simulaciones/` with a walkthrough per department perspective
7. [ ] Connect everything with bidirectional wikilinks
8. [ ] Apply tags with the `[tipo]/[área]` pattern
9. [ ] (Optional) Create Claude agents in `.claude/agents/`

---

## 10. Anti-patterns avoided in this vault

- **No orphan files** — everything is linked from at least one hub
- **No duplicated rules** — rules live in a single place (central [[Business Rules|Business Rules]] or local `Reglas de [Dept].md`) and are referenced, not copied
- **No deep hierarchy** — maximum 4 nesting levels
- **No language mixing** — everything in one language consistently
- **Status lights don't define rules** — they implement them. The definition lives in [[Business Rules|Business Rules]]
