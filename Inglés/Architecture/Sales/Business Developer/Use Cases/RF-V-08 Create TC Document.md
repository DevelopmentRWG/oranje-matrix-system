---
tags:
  - arquitectura
  - rol/business-developer
  - caso-de-uso
aliases:
  - CU RF-V-08 (BD)
---

# 🪪 ID: RF-V-08
🏷️ **Name:** Create T&C Document

**Story:**
When the hotel responds with interest to the Proposal (Yellow status), the BD creates the **Terms and Conditions Document** with the 5 mandatory fields defined by RR-V-10: Pay rate, Bill rate, Overtime, Holidays, Calendar. Once complete, they send it to the BDC for validation. Without this document, formal negotiation (Pink) cannot start.

**Acceptance criteria:**
Only applies in Yellow status. The 5 mandatory fields are required (RR-V-10). Optional attachments. On save, it remains an editable draft. When sent to the BDC, it locks for editing and stays pending validation. The BDC can reject with observations (returns to editable) or approve (RF-V-10).

**Documentation:**
- PRD: PRD-VENTAS-02 Business Developer
- Flow: Create T&C Document
- Prototype: (Figma link)

**Flow:**
`Prospect detail in Yellow → Sidebar T&C Documents → Click "Create T&C Document"` → MANUAL → `Fill in Pay rate (>0), Bill rate (>0), Overtime, Holidays (catalog), Calendar (range)` → `Validity and renewal optional` → `Attach documents optional` → `Save draft` → AUTOMATICO → `Draft saved` → MANUAL → `Click "Send to BDC for validation"` → AUTOMATICO → If the 5 fields OK → `Document stays pending validation + Notifies the BDC + Locks editing` / If any field is missing → `Blocks with "Complete the 5 mandatory T&C fields"`
