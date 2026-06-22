---
tags:
  - arquitectura
  - rol/reclutadora
  - caso-de-uso
aliases:
  - UC RF-06
---

# 🪪 ID: RF-06
🏷️ **Name:** Search candidates in Pool

**Story:**
The Recruiter opens the Collaborator Pool and applies filters (position, zone, modality, English, availability) to find candidates that meet the requirements of the taken requisition.

**Acceptance criteria:**
The search returns results in under 2 seconds. It allows combining at least 4 filters simultaneously. It shows the Collaborator Status Light on each result.

**Documentation:**
- PRD: PRD-RECL-02 Recruiter
- Flow: Pool search
- Prototype: (Figma link)

**Flow:**
`Recruitment Module → Pool` → MANUAL → `Apply filters` → AUTOMATIC → `System filters Pool in <2s` → `List of available candidates` → MANUAL → `Click on candidate` → `Collaborator detail view`
