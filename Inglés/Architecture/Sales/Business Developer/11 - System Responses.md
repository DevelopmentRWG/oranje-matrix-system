---
tags:
  - arquitectura
  - rol/business-developer
aliases:
  - Business Developer System Responses
---

# 7. SYSTEM RESPONSES — BUSINESS DEVELOPER

---

| Event                              | System Response                                                                                    |
| ---------------------------------- | -------------------------------------------------------------------------------------------------- |
| BD identifies prospect             | Creates record in Gray · Appears in my Pipeline · Captures geolocation if from mobile             |
| BD creates hotel profile           | Status moves to Light Blue · Notification to the BDC of the progress                              |
| BD registers cold visit            | Visit logged in history · If "next follow-up" is marked, creates a reminder                       |
| BD prepares Personalized Proposal  | A draft is created · Allows free editing                                                          |
| BD sends proposal to hotel         | Status moves to Green · Notifies the BDC · Email with proposal sent to the hotel                 |
| Hotel responds with interest       | BD advances to Yellow · Notifies the BDC · Allows starting the T&C                                |
| BD creates T&C Document            | Draft with mandatory fields ready to fill in                                                      |
| BD sends T&C to the BDC            | Notifies the BDC · Document remains pending validation                                            |
| BDC validates T&C                  | Notifies the BD: *"Your T&C was validated"* · Allows advancing to Pink                            |
| BDC rejects T&C                    | Notifies the BD with observations · BD corrects and resends                                       |
| BD initiates negotiation (Pink)    | Status moves to Pink · Notifies the BDC · Traceability in the timeline                            |
| BDC approves conversion            | Notifies the BD: *"Your prospect converted into an active client"* · Status moves to Orange      |
| Automatic Trigger executes         | Welcome email to the hotel · Notif to the BD · Hotel leaves the Pipeline · Appears in Active Clients |
| BD marks Red (rejection)           | Status moves to Red · Notifies the BDC · Logged with reason                                       |
| BD reactivates from Red            | Status returns to Light Blue · History keeps the rejection                                        |
| BD marks Brown                     | Status moves to Brown · Notifies the BDC to unblock · BD can no longer modify this prospect       |
| BDC unblocks Brown                 | Notifies the BD: *"Your prospect was unblocked by [BDC]"* · Status returns to Light Blue          |
| BD attempts action without permission | Button does not appear · If attempted via URL, message: *"You do not have permission for this action"* |
| Session started                    | Redirects to Dashboard · Loads personal KPIs · Lists upcoming follow-ups                          |
| Session expired                    | Redirects to login                                                                                |
| Form validation error              | Shows clear error messages next to each invalid field                                             |
