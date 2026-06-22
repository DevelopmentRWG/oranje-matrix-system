---
tags:
  - arquitectura
  - rol/bdc
aliases:
  - BDC System Responses
---

# 7. SYSTEM RESPONSES — BUSINESS DEVELOPER COORDINATOR

---

| Event                                     | System Response                                                                                                                                                                                       |
| ----------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| BDC validates T&C                         | T&C approved · Notifies the BD: *"Your T&C was validated"* · Allows advancing to Pink · Auditable log                                                                                                  |
| BDC rejects T&C with observations         | T&C returns to editable by the BD · Notifies the BD with observations                                                                                                                                 |
| BDC creates Hotel User                    | User created · Enables the "Approve conversion" button · Email is NOT sent yet (waits for approval)                                                                                                    |
| BDC approves conversion                   | Status moves to Orange · **Automatic Trigger runs in parallel:** (1) welcome email to the hotel, (2) notification to the assigned BD, (3) hotel disappears from the Pipeline · Appears in Active Clients |
| Trigger runs successfully                 | The 3 actions are recorded in log · Notifies the BDC of the success                                                                                                                                   |
| BDC marks Brown                           | Status moves to Brown · Notifies the BD                                                                                                                                                               |
| BDC unblocks Brown                        | Decision made · Notifies the BD: *"Your prospect was unblocked"* · Allows reactivating                                                                                                                |
| BDC reactivates from Brown                | Status returns to Light Blue · BD regains control · Timeline updated                                                                                                                                  |
| BDC marks client Black                    | Active client moves to Black · Notifies the assigned BD · Leaves the active clients view                                                                                                              |
| BDC reactivates from Black                | Client returns to Light Blue as a prospect · Notifies the BD                                                                                                                                          |
| BDC reassigns prospect to another BD      | Prospect changes BD · Notifies both BDs · Timeline updated                                                                                                                                            |
| BDC comments on the file                  | Comment appears in the timeline · Notifies the assigned BD                                                                                                                                            |
| BDC generates report                      | Preview with consolidated data · Export / send / save buttons                                                                                                                                         |
| BDC exports report                        | Downloadable file                                                                                                                                                                                     |
| BDC sends report to management            | Email / link sent · History updated · Notifies the BDC when it is read                                                                                                                                |
| BDC schedules recurring sending           | Configuration saved · System will send automatically according to frequency                                                                                                                          |
| BDC requests report from a BD             | Notifies the BD with the request                                                                                                                                                                      |
| Department Quality Indicator drops to Red | Notifies the BDC and the QA Manager                                                                                                                                                                   |
| Session started                           | Redirects to Dashboard · Loads funnel, critical cases, alerts                                                                                                                                         |
| Expired session                           | Redirects to login                                                                                                                                                                                    |
| BDC tries an action without permission    | Button does not appear · If forced via URL: *"You do not have permission for this action"*                                                                                                            |
