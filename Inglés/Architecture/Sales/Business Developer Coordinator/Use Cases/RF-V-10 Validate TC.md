---
tags:
  - arquitectura
  - rol/bdc
  - caso-de-uso
aliases:
  - CU RF-V-10
---

# 🪪 ID: RF-V-10
🏷️ **Name:** Validate T&C Document

**Story:**
When the BD finishes assembling the Terms and Conditions Document, they send it to the BDC for validation. The BDC reviews the 5 mandatory fields (Pay rate, Bill rate, Overtime, Holidays, Calendar) and other conditions, and issues a decision: **approve** (allows advancing to Pink) or **reject with observations** (returns to the BD for correction). T&C validation is a **prerequisite** for the final conversion.

**Acceptance criteria:**
Only the BDC can validate (exclusive action). On approval, the T&C is set as "Validated" and the prospect can advance to Pink. On rejection, observations are mandatory (min. 30 characters) and the T&C returns to an editable state for the BD. Notifies the BD in under 1 min in both cases. Recorded in an auditable log with author and date.

**Documentation:**
- PRD: PRD-VENTAS-03 BDC
- Flow: Validate T&C
- Prototype: (Figma link)

**Flow:**
`Inbox "T&C pending validation"` → MANUAL → `Click on T&C` → `Reviews the 5 mandatory fields + general conditions` → HMANUAL → `Decision: Approve or Reject` → If Approves → `Optional comment` → `Confirm` → AUTOMATICO → `T&C set as Validated + Notifies the BD + Allows advancing to Pink + Auditable log` / If Rejects → `Mandatory observations (min. 30 characters)` → `Confirm` → AUTOMATICO → `T&C returns to editable by the BD + Notifies the BD with observations + Auditable log`
