---
tags:
  - architecture
  - role/collaborator
  - use-case
aliases:
  - CU RF-C-09
---

# 🪪 ID: RF-C-09
🏷️ **Name:** View notifications

**Story:**
The Collaborator receives system notifications about events relevant to their profile and operation: sign-up validation approved or rejected, new assignment, status changes in the [[Collaborator Status Light]], clock-in reminders, and accident report results. From the app they access the "Notifications" section and see the list ordered by date, distinguishing read from unread notifications. When opening the notifications screen, the unread notifications badge disappears. The view is **read-only**.

**Acceptance criteria:**
List of own notifications ordered by descending date (most recent first). Visual differentiation between read and unread notifications. When opening the section, the unread badge (counter) disappears. Types of notifications included: sign-up validation approved, sign-up validation rejected or requiring corrections, new assignment (hotel, position, dates), status light change, end of temporary assignment, result of closed accident card, clock-in reminders (if applicable). Only own notifications are shown (RR-C-01). Push notifications (RNF-C-06) redirect the collaborator to this section when tapped.

**Documentation:**
- PRD: [[03 - PRD]]
- Flow: Notification system — Collaborator
- Prototype: (Figma link)

**Flow:**
`App → Notifications Section (badge visible if there are unread ones)` → AUTOMATIC → `Badge disappears upon opening the section` → MANUAL → `Scroll through notification list (ordered by date, most recent first)` → `Tap a notification to see it in detail` → AUTOMATIC → `Notification marked as read · Shows full notification content`
