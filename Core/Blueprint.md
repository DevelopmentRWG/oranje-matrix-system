---
tags:
  - module/core
aliases:
  - System Architecture
  - Oranje Blueprint
---
# Organizational Architecture of the Oranje Matrix System Vault
## Blueprint for replicating in a new system

The **oranje-matrix-system** vault documents a hotel staffing system. This is the architecture extracted as a replicable pattern for any new organizational system.

---

## 1. Design Principle: Departmental Hub-and-Spoke

```
                    Home.md (central hub)
                         │
        ┌────────┬───────┼───────┬────────┐
        │        │       │       │        │
   Department  Department  Core/  Central   Simulations/
       A/          B/      │    Entity/
                       ┌───┼───┐
                  Catalogs/ Modules/ Status Indicators/
```

**Rule:** Everything is accessed from `Home.md`. Each top-level folder is autonomous but interconnected via wikilinks.

---

## 2. Folder Structure (replicable pattern)

```
new-system/
│
├── Home.md                          ← Master index (central hub)
│
├── Core/                            ← Shared cross-cutting modules
│   ├── Catalogs/                    ← Reference data (enums, lists)
│   │   ├── Catalog-A.md
│   │   └── Catalog-B.md
│   └── Modules/                     ← System entities and processes
│       ├── Status Indicators/       ← Visual state-machines (indicators)
│       │   ├── Status Indicator of X.md
│       │   └── Indicator of Y.md
│       ├── [Complex-Submodule]/     ← Own folder if it has flow + entity
│       │   ├── Entity.md
│       │   └── Entity Flow.md
│       ├── Simple-Module.md         ← Single file if no flow needed
│       └── Business Rules.md        ← Centralized source of truth
│
├── [Department-A]/                  ← One folder per department
│   ├── Department-A.md             ← Department hub/index
│   ├── Role-1.md                   ← One file per role
│   ├── Role-2.md
│   ├── Department-A Rules.md       ← Local department rules
│   └── Process-A Flow.md           ← Department-specific processes
│
├── [Department-B]/
│   ├── ...same pattern...
│   └── Subfolder/                   ← Sub-areas if department is complex
│       ├── Subfolder.md            ← Sub-area hub
│       ├── Sub-Process Flow.md
│       └── Concepts/               ← Sub-area-specific definitions
│
├── [Central-Entity]/                ← The main business entity
│   ├── Central-Entity.md
│   └── Entity Rules.md
│
├── [Control-Layer]/                 ← QA, auditing, supervision
│   ├── Control.md
│   ├── Control Rules.md
│   ├── Metrics and KPIs.md
│   └── Dashboard.md
│
├── Simulations/                     ← Narrative documentation
│   ├── Simulation - Dept-A Perspective.md
│   └── Simulation - Dept-B Perspective.md
│
└── .claude/                         ← AI agents (optional)
    └── agents/
        ├── consultant.md            ← Read/query agent
        └── editor.md               ← Write agent
```

---

## 3. File Type Taxonomy

Each file in the vault has a **type** that determines its internal structure:

| Type | Naming Convention | Purpose | Example |
|------|-------------------|---------|---------|
| **Hub/Index** | `[Department-Name].md` | Entry point for a folder | `Hotel.md`, `QA.md` |
| **Role** | `[Role Title].md` | Defines an actor's responsibilities | `Recruiter.md`, `Inspector.md` |
| **Rules** | `[Area] Rules.md` | Restrictions and policies | `Hotel Rules.md` |
| **Flow** | `[Process] Flow.md` | Step-by-step workflow | `Payroll Flow.md` |
| **Status Indicator** | `[Entity] Status Indicator.md` | Visual state-machine | `Associate Status Indicator.md` |
| **Indicator** | `[Metric] Indicator.md` | KPI with thresholds | `Quality Indicator.md` |
| **Catalog** | `[Descriptive name].md` | Reference data (enums) | `Positions.md`, `Zones.md` |
| **Module** | `[Module name].md` | System entity | `Schedule.md`, `Contract.md` |
| **Simulation** | `Simulation - [Perspective].md` | Narrative walkthrough | `Simulation - QA Perspective.md` |
| **Concept** | `[Concept name].md` | Sub-element definition | `Customized Proposal.md` |

---

## 4. Template for Each File Type

### Department Hub/Index
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
- [[X Flow]]

## Rules
- [[Department Rules]]

## Relationship with Other Modules
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

> Brief description.

## Responsibilities
- Responsibility 1
- Responsibility 2

## Interactions
- With [[Other Role]]: interaction description
- With [[Module]]: how they use it
```

### Flow
```markdown
---
tags:
  - flow/[area]
aliases:
  - [Alias]
---
# [Process] Flow

## Actors Involved
| Actor | Role in the Flow |
|-------|-----------------|
| [[Role-1]] | Description |

## Steps
1. **[Actor]** does X
2. Condition? → YES: step 3 / NO: step 4
3. ...

## Key Rules
- Applicable rule 1
- Applicable rule 2

## Related
- [[Status Indicator of X]]
- [[Module Y]]
```

### Status Indicator (State-Machine)
```markdown
---
tags:
  - status-indicator/[entity]
aliases:
  - [Entity] Status [Color1]
  - [Entity] Status [Color2]
---
# [Entity] Status Indicator

| Color | State | Responsible | Description |
|-------|-------|-------------|-------------|
| Green | Active | System | ... |
| Yellow | At Risk | [[Role]] | ... |
| Red | Critical | [[Role]] | ... |

## Detail by State

### Green — Active
- Entry condition: ...
- Allowed actions: ...
- Possible transitions: → Yellow (if...), → Red (if...)

## Key Rules
- ...

## Related
- [[X Flow]]
- [[Business Rules]]
```

### Business Rules (centralized)
```markdown
---
tags:
  - module/core
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
# [Catalog Name]

- Value 1
- Value 2
- Value 3

> [!info] This list is non-exhaustive / exhaustive.

## Related
- [[Module that consumes it]]
```

---

## 5. Connection System (wikilinks)

### Reference Hierarchy
```
Home.md
  └─→ [Dept].md (hub)
        ├─→ Roles (downward)
        ├─→ Flows (downward)
        ├─→ Local rules (lateral)
        └─→ Core/Modules (toward the center)
              ├─→ Status Indicators (lateral)
              ├─→ Catalogs (data)
              └─→ Business Rules (source of truth)
```

### Connection Rule
- **Vertical:** Hub → Roles → Flows (from general to specific)
- **Horizontal:** Department ↔ Department (when they interact)
- **Central:** Everything points to `Core/Modules/` for shared entities
- **Aliases:** Allow multiple ways to reference the same concept

---

## 6. Tag System (frontmatter)

```
Pattern: [type]/[area]

Types used:
  - module/[name]              → Core and departmental modules
  - department/[name]          → Departmental files
  - role/[department]          → Roles in each area
  - flow/[area]                → Process flows
  - status-indicator/[entity]  → Status indicators
  - catalog/[name]             → Reference catalogs
```

---

## 7. System Layers (bottom-up)

```
┌─────────────────────────────────────────────────┐
│  LAYER 5: Simulations (narrative documentation)     │
├─────────────────────────────────────────────────┤
│  LAYER 4: QA / Control (cross-cutting)              │
├─────────────────────────────────────────────────┤
│  LAYER 3: Operational departments                   │
│  (Recruitment, Sales, Inspection, etc.)             │
├─────────────────────────────────────────────────┤
│  LAYER 2: Core Modules + Status Indicators          │
│  (Schedule, Pool, Timesheet, Contract, etc.)        │
├─────────────────────────────────────────────────┤
│  LAYER 1: Foundations                               │
│  (Catalogs + Business Rules + Central Entity)       │
└─────────────────────────────────────────────────┘
```

- **Layer 1** depends on nothing. Defines base data and rules.
- **Layer 2** implements the rules as operational modules and state-machines.
- **Layer 3** consumes core modules for their departmental processes.
- **Layer 4** observes all lower layers and measures their performance.
- **Layer 5** documents complete walkthroughs across all layers.

---

## 8. Current System Numbers (reference)

| Concept | Count |
|---------|-------|
| Departments | 8 (+ Core + Central Entity) |
| Roles | 14 |
| Flows | 6 |
| Status Indicators | 7 |
| Catalogs | 5 |
| Core Modules | ~10 |
| Simulations | 7 |
| Total .md files | ~89 |

---

## 9. Checklist for Replicating This Architecture in a New System

1. [ ] Define the **central entity** of the business (equivalent to "Associate")
2. [ ] Identify the **departments** that operate on that entity
3. [ ] Create `Home.md` as the central hub
4. [ ] Create `Core/` with:
   - [ ] `Catalogs/` — system reference data
   - [ ] `Modules/` — shared entities across departments
   - [ ] `Modules/Status Indicators/` — status indicators per key entity
   - [ ] `Business Rules.md` — centralized source of truth
5. [ ] For each department create a folder with:
   - [ ] `[Dept].md` — hub/index
   - [ ] One file per role
   - [ ] `[Dept] Rules.md`
   - [ ] `[Process] Flow.md` if it has its own processes
6. [ ] Create `Simulations/` with a walkthrough per department perspective
7. [ ] Connect everything with bidirectional wikilinks
8. [ ] Apply tags with `[type]/[area]` pattern
9. [ ] (Optional) Create Claude agents in `.claude/agents/`

---

## 10. Anti-patterns Avoided in This Vault

- **No orphan files** — everything is linked from at least one hub
- **No duplicated rules** — rules live in a single place ([[Reglas de Negocio]] centralized or `[Dept] Rules.md` local) and are referenced, not copied
- **No deep hierarchy** — maximum 4 levels of nesting
- **No language mixing** — everything consistently in English
- **Status indicators don't define rules** — they implement them. The definition lives in [[Reglas de Negocio]]
