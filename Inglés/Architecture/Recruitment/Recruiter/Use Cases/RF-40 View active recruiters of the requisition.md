---
tags:
  - arquitectura
  - rol/reclutadora
  - caso-de-uso
aliases:
  - UC RF-40 (Recruiter)
---

# 🪪 ID: RF-40
🏷️ **Name:** View active recruiters of the requisition

**Story:**
Since the requisitions model is **collaborative (RR-15)**, the same requisition can have **several participating recruiters** at once. From the requisition detail, the Recruiter views the **list of active recruiters**: who is working it right now, with their role and since when they joined. This way they know who they share the work with before assigning collaborators or joining.

**Acceptance criteria:**
Visible in the detail of any In process requisition. Lists each participating recruiter with: role (Recruiter / Group Leader), name and the moment they joined. It updates when a recruiter joins (RF-39) or leaves (RF-03). There is no single owner: all participants are shown equally. From here the full History is accessed (RF-41).

**Documentation:**
- PRD: PRD-RECL-02 Recruiter
- Flow: Active recruiters of the requisition
- Prototype: (Figma link)

**Flow:**
`Requisitions → Open requisition (detail)` → AUTOMATIC → `System lists the active participating recruiters (role + name + "joined X ago")` → MANUAL → `(optional) Join (RF-39)` · `View the requisition's History (RF-41)`
