---
tags:
  - arquitectura
  - rol/lider-de-grupo
  - caso-de-uso
aliases:
  - CU RF-40
---

# 🪪 ID: RF-40
🏷️ **Name:** View active recruiters of the requisition

**Story:**
Since the requisition model is **collaborative (RR-15)**, the same requisition can have **several participating recruiters** working it at once. From the requisition detail, any participant (and the Leader/Manager) sees the **list of active recruiters**: who is working it right now, with their role and since when they joined. It is the visual foundation of the collaborative model: knowing who you share the work with before assigning or joining.

**Acceptance criteria:**
Visible in the detail of any In progress requisition. Lists each participating recruiter with: role (Recruiter / Group Leader), name and the moment they joined. It updates automatically when someone joins (RF-39) or leaves (RF-03). The first who took it and those who joined later are shown equally (there is no single owner). Visible to all participants, the group Leader and the Manager. From here the full History can be accessed (RF-41).

**Documentation:**
- PRD: PRD-RECL-03 Group Leader
- Flow: Active recruiters of the requisition
- Prototype: (Figma link)

**Flow:**
`Requisitions → Open requisition (detail)` → AUTOMATICO → `System lists the active participating recruiters (role + name + "joined X ago")` → MANUAL → `(optional) Join (RF-39)` · `View requisition History (RF-41)`
