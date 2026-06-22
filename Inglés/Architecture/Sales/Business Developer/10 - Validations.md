---
tags:
  - arquitectura
  - rol/business-developer
aliases:
  - Business Developer Validations
---

# 4. VALIDATIONS — BUSINESS DEVELOPER

---

| Case                                                | System Behavior                                                                                                |
| --------------------------------------------------- | -------------------------------------------------------------------------------------------------------------- |
| Identify prospect without name or city              | Blocks submission; shows: *"Complete the mandatory fields (name, city)"*                                       |
| Create profile without email or phone               | Blocks submission; shows: *"Email and phone are mandatory"*                                                    |
| Email with invalid format                           | Blocks submission; shows: *"Invalid email format"*                                                             |
| Business need <30 characters                        | Blocks submission; shows: *"Describe the business need (min. 30 characters)"*                                  |
| Advance to Green without proposal sent              | Blocks action; shows: *"You must send a Personalized Proposal before advancing to Green"*                      |
| Create proposal for prospect in non-Green status    | Allows creating a draft, but on sending shows: *"The proposal can only be sent in Green status"* (RR-V-09)     |
| Send proposal without services or prices            | Blocks submission; shows: *"Complete services and prices before sending"*                                      |
| Create T&C without Pay/Bill/Overtime/Holidays/Calendar | Blocks submission; shows: *"Complete the 5 mandatory T&C fields (RR-V-10)"*                                  |
| Initiate negotiation (Pink) without complete T&C    | Blocks action; shows: *"You must have a complete T&C Document before initiating negotiation"*                  |
| Attempt to approve conversion                       | Action not available; the button does not appear (RR-V-01)                                                     |
| Attempt to create Hotel User                        | Action not available (BDC exclusive)                                                                           |
| Attempt to unblock Brown                            | Action not available; shows: *"Only the BDC can unblock stagnations"* (RR-V-04)                               |
| Attempt to mark / reactivate Black                  | Action not available (BDC exclusive — RR-V-05)                                                                 |
| Mark Red without reason                             | Blocks submission; shows: *"Select the rejection reason"*                                                      |
| Mark Red with comment <30 characters                | Blocks submission; shows: *"The comment must be at least 30 characters"*                                       |
| Reactivate from Red                                 | Status automatically returns to Light Blue (RR-V-07)                                                           |
| Mark Brown without notes for the BDC                | Blocks submission; shows: *"The notes for the BDC are mandatory"*                                              |
| Edit prospect outside my territory                  | No access; shows: *"You do not have permission to manage this prospect"*                                       |
| Edit active client (post-Orange)                    | No access to operational fields; read-only view (RR-V-12)                                                      |
| Attachment >10 MB                                   | Rejects file; shows: *"Maximum size: 10 MB"*                                                                   |
| Session expired                                     | Redirects to login                                                                                            |
