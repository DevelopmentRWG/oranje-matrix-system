---
tags:
  - arquitectura
  - rol/business-developer
  - caso-de-uso
aliases:
  - CU RF-V-04
---

# 🪪 ID: RF-V-04
🏷️ **Name:** Draft Personalized Proposal

**Story:**
After having the complete hotel profile (Light Blue), the BD drafts the **Personalized Proposal** with the services Oranje offers, the prices and the commercial terms. The proposal is built in the Proposals module as a draft, then sent to the hotel (RF-V-05), which moves the prospect to **Green** status.

**Acceptance criteria:**
The proposal can only be drafted for prospects in Green status or earlier. Mandatory fields: target hotel, proposed services, prices, general terms (min. 100 characters), validity. Optional attachments (PDF/DOCX, max. 10 MB). Allows duplicating previous proposals as a template.

**Documentation:**
- PRD: PRD-VENTAS-02 Business Developer
- Flow: Draft Personalized Proposal
- Prototype: (Figma link)

**Flow:**
`Sidebar → Proposals → Click "New Proposal"` → MANUAL → `Select target hotel (list of my prospects in Light Blue)` → `Select proposed services (catalog)` → `Fill in prices per service + general terms (min. 100 characters) + validity` → `Attach documents optional` → `Save draft` → AUTOMATICO → `Draft saved` → MANUAL (later) → `Click "Send to hotel"` (triggers RF-V-05)
