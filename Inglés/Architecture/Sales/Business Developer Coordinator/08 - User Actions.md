---
tags:
  - arquitectura
  - rol/bdc
aliases:
  - BDC Actions
---

# 6. USER ACTIONS — BUSINESS DEVELOPER COORDINATOR

---

| Action                         | Result                                                                                                                                      |
| ------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------- |
| Validate T&C Document          | T&C approved · Notifies the BD · Allows advancing to Pink · Recorded in log                                                                 |
| Reject T&C with observations   | T&C returns to editable · Notifies the BD with observations                                                                                 |
| Start negotiation (Pink)       | Status moves to Pink · Traceability                                                                                                         |
| Create T&C Document            | Document created with mandatory fields                                                                                                      |
| Create Hotel User              | User created · Enables the "Approve conversion" button                                                                                      |
| Approve conversion to client   | Status moves to Orange · **Automatic Trigger** runs 3 actions in parallel: email + notif to the BD + leaves the Pipeline · Hotel becomes active |
| Mark prospect Brown            | Status moves to Brown · Notifies the BD                                                                                                     |
| Investigate Brown case         | Access to history, contacts, BD notes                                                                                                       |
| Unblock Brown                  | Decision made · Allows reactivating                                                                                                         |
| Reactivate from Brown          | Status returns to Light Blue · Notifies the original BD                                                                                     |
| Mark client Black              | Active client moves to Black · Notifies the assigned BD · Recorded in log                                                                   |
| Reactivate from Black          | Black client returns to Light Blue as a prospect · Notifies the BD                                                                          |
| Reassign prospect to another BD | Change of assigned BD · Notifies both BDs · Recorded in log                                                                                |
| Comment on the file            | Comment appears in the timeline · Notifies the assigned BD                                                                                  |
| Request report from a BD       | Notifies the BD with the request                                                                                                           |
| Generate Sales report          | Preview with consolidated data · Export / send / save buttons                                                                              |
| Export report                  | Download CSV / PDF / Excel                                                                                                                  |
| Send report to management      | Email / link sent · History with recipient and status                                                                                      |
| Schedule recurring sending     | Configuration saved · System will send automatically                                                                                       |
| Communicate with BD            | Message / internal note · Notification to the BD                                                                                           |
| Cancel action                  | Changes are not saved                                                                                                                       |
