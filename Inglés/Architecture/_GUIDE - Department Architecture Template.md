---
tags:
  - arquitectura
  - guia
aliases:
  - Architecture Template Guide
  - Department Architecture Template
---

# 📘 GUIDE — Department Architecture Template

> **Purpose:** document the per-department software architecture methodology used to design, organize and communicate internal products. It applies to any project where **operational roles** work with **software modules** within a defined **business flow**.

---

## 1. Methodology philosophy

Architecture is not just the visual wireframe. It is the **complete set** of documentation that answers:

| Question | Document that answers it |
|---|---|
| Who uses the system? | Role Sheet · Detailed Sheet |
| What exactly do they do? | User Actions · Use Cases |
| What can they see/touch/approve? | Detailed Permissions · Permissions Matrix |
| What screens do they use? | Architecture wireframe |
| What rules govern the system? | Business Rules |
| What requirements does it meet? | Requirements Table · By Module |
| What is considered "done"? | Acceptance Criteria |
| What does it depend on? | Dependencies |
| What information does it capture? | Form Fields |
| What does it block? | Validations |
| What does the system respond? | System Responses |

---

## 2. Folder structure

```
Arquitecturas/
└── [Department Name]/
    │
    ├── _Globales del Depto/         ← 9 files shared by the whole department
    │   ├── 01 - Portada.md
    │   ├── 02 - PRD - [Depto].md
    │   ├── 03 - Tabla de Requerimientos.md
    │   ├── 04 - Por Módulo.md
    │   ├── 05 - Leyenda.md
    │   ├── 06 - Matriz de Permisos.md
    │   ├── 07 - Reglas de Negocio.md
    │   ├── 08 - Criterios de Aceptación.md
    │   └── 09 - Dependencias.md
    │
    └── [Each role]/                 ← one folder per role with 12 files + use cases
        ├── 00 - Arquitectura [Rol].md
        ├── 01 - Ficha de Rol.md
        ├── 02 - Ficha Detallada.md
        ├── 03 - PRD.md
        ├── 04 - Permisos Detallados.md
        ├── 05 - Requerimientos.md
        ├── 06 - Resumen Rápido.md
        ├── 07 - Feature Map.md
        ├── 08 - Acciones del Usuario.md
        ├── 09 - Campos del Formulario.md
        ├── 10 - Validaciones.md
        ├── 11 - Respuestas del Sistema.md
        └── Casos de Uso/
            ├── RF-XX [Name].md
            └── ...
```

---

## 3. Conventions

### 3.1 File numbering

Each file carries a **numeric prefix** (`00 -`, `01 -`, `02 -`, ...) to force a specific reading order. Number 0 is the main wireframe; 1 through 11 are detail files.

### 3.2 Role IDs

Format: `ROL-[X]-[NN]` where:
- `X` = initial letter of the department (R = Recruitment, H = Hotel, V = Sales).
- `NN` = sequential number (01, 02, 03...).

Always reserve:
- An ID for **System** (automation, not a person).
- An ID for **Administrator** (technical management, usually left on pause).

### 3.3 Requirement IDs

Format: `[Type]-[X]-[NN]`

| Prefix | Type | Defines |
|---|---|---|
| **RF** | Functional Requirement | WHAT the system does (actions, flows) |
| **RNF** | Non-Functional Requirement | HOW it does it (performance, security, usability) |
| **RR** | Business Requirement | WHY it exists (rules, policies, constraints) |
| **RI** | Integration Requirement | WHAT it connects WITH (other modules, external systems) |

Examples: `RF-V-01`, `RR-H-05`, `RNF-V-02`, `RI-H-04`.

### 3.4 PRD IDs

Format: `PRD-[DEPT]-[NN]`
- `PRD-[DEPT]-01` = PRD for the whole department.
- `PRD-[DEPT]-02`, `03`, ... = PRD per role.

### 3.5 Acceptance criteria IDs

Format: `AC-[X]-[NN]` (Acceptance). Example: `AC-V-01`.

### 3.6 Frontmatter of each file

```yaml
---
tags:
  - arquitectura
  - departamento/[name]        # only in _Globales del Depto
  - rol/[role-name]            # only in role files
aliases:
  - [Short document alias]
---
```

### 3.7 Wikilinks (if you use Obsidian)

```markdown
[[Path/File|Visible alias]]
```

Connect each document with everything it references (status lights, other roles, modules, rules). The graph builds itself.

---

## 4. Templates per file

### 📂 _Globales del Depto

#### 01 - Portada.md

**Function:** department index. Lists the roles, IDs, hierarchies and names.

**Structure:**
- Header with document data (version, status, related to PRD).
- "ROLES DEFINED IN THIS DOCUMENT" table with: ID, Role, Short description.
- Hierarchies section (if applicable): table with each hierarchy + applicable roles.
- Informative callout with key notes.

---

#### 02 - PRD - [Depto].md

**Function:** Product Requirements Document for the whole department.

**Structure:**
- Header: PRD ID, HU, Department, Feature, Main Actor, Device, Status, Version.
- **Objective** (1 paragraph).
- **Scope:** Includes / Out of scope.
- **General Flow** (1 line + optional diagram).
- **Actors:** table with Actor, Type, Main responsibility.
- **Constraints / Applicable rules:** reference to 07 - Business Rules.
- **Integrations (RI):** table with ID, Integration, Description.
- **Dependencies:** reference to 09 - Dependencies.

---

#### 03 - Tabla de Requerimientos.md

**Function:** all the RFs, RNFs, RRs, RIs of the department in one large table for Sheet/Excel.

**Structure:**
- Document header.
- Requirement Types (RF/RNF/RR/RI legend).
- Priority and Status (🔴/🟡/🟢/⬜/🔵/✅ legend).
- Master table:

| ID | Type | Module | Requirement | Detailed Description | Role(s) | Acceptance Criterion | Priority | Status | Notes |
|---|---|---|---|---|---|---|---|---|---|

---

#### 04 - Por Módulo.md

**Function:** group the RFs by **sidebar module**. Each module has its short description + RF table.

**Structure per module:**
```markdown
## 📋 [Module Name]

Short 1-2 line description explaining what the module does.

| ID | Requirement | Role(s) | Priority |
|---|---|---|---|
| RF-X-NN | ... | ... | 🔴 High |
```

Close with sections for:
- Configuration (Admin on pause)
- Non-Functional (Cross-cutting)
- Business Rules (summary with link to 07)
- Integrations

---

#### 05 - Leyenda.md

**Function:** explain the permissions matrix symbols.

**Structure:**
- Table of Symbols / Meaning / Applies to.
- Table of Roles defined in the document.

Typical symbols:
- ✅ CRUD · ➕ Create · 👁️ View · 📝 C · E · ✓ Approve · ✗ Reject · 🔍 Investigate · 🚨 Report · ⚙️ Auto · — No permission · ⏸️ On pause

---

#### 06 - Matriz de Permisos.md

**Function:** who can do what, module by module, action by action.

**Structure:**

| Module | Feature / Action | ROL-1 | ROL-2 | ROL-3 | ... |
|---|---|---|---|---|---|
| **NAME** | Action 1 | Create | View | — | ... |
| | Action 2 | — | C · E | Auto | ... |

Close with a "Key notes" section with the department's golden rules.

---

#### 07 - Reglas de Negocio.md

**Function:** consolidated RR-X-NN rules with ID, rule, description.

**Structure:**

| ID | Rule | Description |
|---|---|---|
| RR-X-01 | Short name | Detailed description |

Close with a "Cross-references" section linking to related documents.

---

#### 08 - Criterios de Aceptación.md

**Function:** conditions that must be met to consider the system "done".

**Structure:**

| # | Criterion |
|---|---|
| AC-X-01 | The system meets X when Y happens under Z conditions |

Each criterion references the RR/RF rule it covers. They are verifiable (yes/no).

---

#### 09 - Dependencias.md

**Function:** map what the department needs to operate.

**Structure:** 5 sections:
1. **Internal dependencies** (other system modules).
2. **External dependencies** (apps, systems, integrations).
3. **Catalog dependencies** (system configuration).
4. **External role dependencies** (roles from other departments that take part).
5. **Status-light dependencies** (visual states of the flow).

Each section is a table with Dependency / Description.

---

### 📂 Each role's folder

#### 00 - Arquitectura [Rol].md

**Function:** **main role wireframe**. It is the most visual and most referenced document.

**Mandatory structure:**
1. **N0 — Start**: login flow diagram.
2. **HEADER** (present across the whole app):
   - 👤 User profile
   - 🔍 Search
   - 🔔 Notifications
3. **N1 — SIDEBAR**: list of modules the role has access to.
4. **Detail per module** (one by one):
   - Sub-views
   - Filters
   - Detail
   - Actions
   - Informative / important / warning callouts
   - **🔄 How this module is used** (narrative flow of how the role operates it day to day)
5. **Key differences vs [other roles]**: comparison table.
6. **General ASCII diagram** of the complete wireframe.
7. **Related**: list of wikilinks.

---

#### 01 - Ficha de Rol.md

**Function:** role summary card in compact format.

**Structure:** table with: Role ID, Name, Type, Department, Reports to, Supervises.

Short sections:
- Description (1 paragraph)
- Objective in the system
- Main actions (bullets)
- Key permissions
- Access level
- Device
- Usage frequency

---

#### 02 - Ficha Detallada.md

**Function:** extended sheet with all the fields for Sheet/Excel.

**Structure:** one long table with all the fields from 01 + additional:
- Modules it uses
- CRUD permissions
- Pain / Current need
- UX notes / Recommendations

---

#### 03 - PRD.md

**Function:** PRD specific to the role.

**Structure:**
- Header (PRD ID, HU, Feature, Actor, Device, Status, Version).
- Objective
- General Flow
- Use Cases (table with ID, Case, Priority)
- **Applicable Business Rules** (table with ID, Rule, Description, Priority)
- **Constraints / Permissions** (table with #, Action they CANNOT do, Why, Who CAN)

> **Tip:** these last two sections are done as tables so they can be copied to Google Sheets.

---

#### 04 - Permisos Detallados.md

**Function:** granular detail of the role's permissions, module by module.

**Structure:**

| Module | Feature | Permission | Description |
|---|---|---|---|
| **Module X** | Action 1 | ➕ Create | Action detail |

---

#### 05 - Requerimientos.md

**Function:** list of RFs/RRs/RNFs applicable to this role specifically (filtered from 03 - Requirements Table).

**Structure:**

| ID | Requirement | Priority |
|---|---|---|

Group by category if it makes sense (Operational / Executive / etc.).

---

#### 06 - Resumen Rápido.md

**Function:** one-pager with the essentials.

**Structure:** compact table with Role, Objective, Key Permissions, Device, Main Actions, Level.

---

#### 07 - Feature Map.md

**Function:** visual map of all the role's features grouped by module + primary/secondary classification.

**Structure:** tree with 2 main branches:

```
[DEPARTMENT] — [ROLE]
│
├── PRIMARY
│   │
│   ├── Module 1
│   │   └── Core features
│   └── Module 2
│       └── Core features
│
└── SECONDARY
    │
    ├── Analytics
    │   └── Metrics, dashboards
    └── Utilities
        └── Export, download, support
```

**Do not use 🔴🟡 emojis to classify.** The tree structure classifies. What falls under "Primary" are the core sidebar modules; what falls under "Secondary" are cross-cutting features (analytics, utilities, integrations).

---

#### 08 - Acciones del Usuario.md

**Function:** action → result table.

**Structure:**

| Action | Result |
|---|---|
| Click on X | System executes Y · Notifies Z · Changes state to W |

---

#### 09 - Campos del Formulario.md

**Function:** fields of each form the role fills out.

**Structure per form:**

```markdown
## A) Form "Form name" (RF-X-NN)

| Field | Input Type | Required | Validation | Description |
|---|---|---|---|---|
```

Repeat for each form (A, B, C, ...).

---

#### 10 - Validaciones.md

**Function:** validation cases and what the system does.

**Structure:**

| Case | System Behavior |
|---|---|
| Empty field | Blocks submission; shows "..." |
| Invalid email | Blocks submission; shows "..." |

---

#### 11 - Respuestas del Sistema.md

**Function:** what the system responds to events.

**Structure:**

| Event | System Response |
|---|---|
| User X does Y | System changes Z · Notifies W · Records log |

---

### 📂 Casos de Uso/ (subfolder inside the role)

#### RF-X-NN [Case name].md

**Function:** narrative detail of a specific use case, ready to copy to the Sheet.

**Fixed structure:**

```markdown
---
tags:
  - arquitectura
  - rol/[role]
  - caso-de-uso
aliases:
  - CU RF-X-NN
---

# 🪪 ID: RF-X-NN
🏷️ **Name:** [Case name]

**Story:**
[2-4 lines narrating the context and why it matters]

**Acceptance criteria:**
[1 paragraph with the verifiable criteria]

**Documentation:**
- PRD: PRD-[DEPT]-NN [Role]
- Flow: [Flow name]
- Prototype: (Figma link)

**Flow:**
`State/Origin` → MANUAL → `Action` → AUTOMATICO → `Result`
```

---

## 5. Steps to apply the methodology in a new project

### Step 1 — Define the scope
List the **departments** the platform will have (e.g. Sales, Operations, Support, Finance).

### Step 2 — For each department, identify the **roles**
At least 2 operational roles + System + Administrator. For each role define:
- Technical name (short)
- Commercial name / alias
- Hierarchy (who it reports to, who it supervises)
- Whether it is operational, supervisor or executive

### Step 3 — Create `_Globales del Depto/`
ALWAYS start here. These 9 files are the base that everything else references:
1. Cover (roles and IDs)
2. Department PRD (objective + scope)
3. **Requirements Table** (the RFs/RRs/RNFs/RIs)
4. By Module (grouped RFs)
5. Legend
6. Permissions Matrix
7. Business Rules (RRs)
8. Acceptance Criteria
9. Dependencies

### Step 4 — For each role, create its folder with 12 files
Start with:
- **00 - Architecture** (the wireframe — it is the most visible)
- **01 - Role Sheet** (summary)
- **04 - Detailed Permissions** (what it can do)
- **05 - Requirements** (RFs applicable to the role)

Then complete:
- 02 Detailed Sheet
- 03 Role PRD
- 06 Quick Summary
- 07 Feature Map
- 08 User Actions
- 09 Form Fields
- 10 Validations
- 11 System Responses

### Step 5 — Use Cases
For each important RF of the role, create a file in `Casos de Uso/` with the narrative format (Story / Criteria / Flow).

### Step 6 — Iterate
Architecture is alive. When a business rule changes:
1. Update `07 - Reglas de Negocio.md` first.
2. Propagate to the Permissions Matrix.
3. Adjust per-role files (Permissions, Actions, Validations).
4. Update the Use Cases that depend on the rule.

---

## 6. Best practices

### What TO do
- ✅ Use wikilinks intensively to connect everything.
- ✅ Tables for Sheet/Excel: structure thinking about copy-paste.
- ✅ Short descriptions (1-2 lines) under each module heading.
- ✅ Each status change / critical action with an associated RR-X-NN rule.
- ✅ Consistent frontmatter so the graph looks good.
- ✅ Use cases with an RF number for traceability.

### What NOT to do
- ❌ Don't duplicate content between files. Use references.
- ❌ Don't use complex ASCII art if it's not needed (narrative is better).
- ❌ Don't classify features with colors in the tree (the structure classifies).
- ❌ Don't mix business rules (RR) with acceptance criteria (AC).
- ❌ Don't forget the "System" role (automation) and "Administrator" (on pause).
- ❌ Don't start with wireframes without having defined roles + rules + RFs.

---

## 7. Quality checklist

Before considering a department's architecture "done":

- [ ] The 9 files of `_Globales del Depto/` exist.
- [ ] Each role has its 12 files + Use Cases.
- [ ] Each RF in the requirements table has a use case or is covered by the matrix.
- [ ] Each action in the permissions matrix has an RR that justifies it if it is exclusive.
- [ ] The wikilinks are not broken (`[[X]]` that doesn't exist).
- [ ] Consistent frontmatter across all files.
- [ ] The permissions matrix covers ALL the wireframe actions.
- [ ] External dependencies are explicit.
- [ ] The use cases follow the Story + Criteria + Flow format.
- [ ] The Cover lists all the roles correctly with ID and description.

---

## 8. How to export this document to PDF (Obsidian)

1. Open this file in Obsidian.
2. Click the **3 dots** at the top right (More options).
3. Select **"Export to PDF..."**.
4. Choose options:
   - **Paper size:** A4 or Letter
   - **Include footer**: optional
   - **Open after export**: ✅
5. Save wherever you want.

> **Alternative with Pandoc** (if you don't have Obsidian):
> ```
> pandoc "_GUIA - Plantilla de Arquitectura de Departamento.md" -o guia.pdf
> ```

---

## 9. Glossary

| Term | Meaning |
|---|---|
| **PRD** | Product Requirements Document |
| **HU** | User Story |
| **RF** | Functional Requirement |
| **RNF** | Non-Functional Requirement |
| **RR** | Business Requirement (Rule) |
| **RI** | Integration Requirement |
| **AC** | Acceptance Criterion |
| **CU** | Use Case |
| **Wireframe** | Low-fidelity visual mockup of the screens |
| **Sidebar** | Side menu with the role's modules |
| **Self-Pick** | Model where users freely take from the inbox instead of someone assigning to them |
| **Automatic Trigger** | Set of actions the system executes automatically when an event occurs |
| **Status Light** | Visual state indicator (typically Green / Yellow / Red) |

---

> **This guide is a template.** Apply it to any project, adjusting department, role and rule names to the domain. The methodology is the same.
