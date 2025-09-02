# ✅ Day 5 — AI for Requirements Gathering (Sample Output for Students)

> This sample demonstrates how to transform a vague stakeholder note into structured, testable requirements.  
> - User Stories numbered (US-#), ≤25 words.  
> - Acceptance Criteria traceable to stories (AC-#.#) in Given/When/Then format.  
> - 10 Open Questions grouped by theme.  
> - Self-Critique with ≥3 bullets.  

---

## 1. User Stories

- **US-1**: As a customer, I want push notifications so that I know when my order status changes.  
- **US-2**: As an iOS user, I want notifications compatible with iOS devices so that I stay informed.  
- **US-3**: As an Android user, I want notifications supported on Android devices so that I remain updated.  
- **US-4**: As an operations manager, I want visibility into notification logs so that I can troubleshoot delivery failures.  
- **US-5**: As a developer, I want integration with existing order systems so that notifications are accurate.  
- **US-6**: As a customer, I want customizable notification settings so that I control how I receive updates.  

---

## 2. Acceptance Criteria

- **AC-1.1**: Given a confirmed order, when status changes, then a notification is sent within 5 seconds.  
- **AC-1.2**: Given a failed delivery, when a notification is undelivered, then system retries once within 60 seconds.  

- **AC-2.1**: Given an iOS device, when status changes, then a push notification displays on lock screen.  
- **AC-2.2**: Given an iOS device, when app is closed, then notification still appears in Notification Center.  

- **AC-3.1**: Given an Android device, when status changes, then a push notification appears on the device.  
- **AC-3.2**: Given an Android device, when app is closed, then notification persists until opened.  

- **AC-4.1**: Given access to logs, when a notification fails, then logs display error details.  
- **AC-4.2**: Given admin access, when reviewing logs, then system shows timestamp, device type, and error code.  

- **AC-5.1**: Given an integrated order system, when order is canceled, then notification updates status to “Canceled.”  
- **AC-5.2**: Given an integrated order system, when item ships, then notification updates status to “Shipped.”  

- **AC-6.1**: Given notification settings, when customer disables them, then no push notifications are sent.  
- **AC-6.2**: Given notification settings, when customer selects preferences, then notifications follow chosen settings.  

---

## 3. Open Questions

**Technical**  
- Q1: How will notifications integrate with existing backend systems?  
- Q2: What retry logic is required for failed notifications?  
- Q3: Are there limits on notification frequency?  

**UX**  
- Q4: Can users customize which order events trigger notifications?  
- Q5: Should notifications include order details or only status?  
- Q6: How will preferences be managed across devices?  

**Business**  
- Q7: Is this feature part of the premium plan or standard offering?  
- Q8: What KPIs measure success (e.g., fewer support calls)?  

**Compliance**  
- Q9: Do notifications need GDPR/CCPA consent handling?  
- Q10: What retention policy applies to notification logs?  

---

## 4. Self-Critique

- Missing: Performance benchmarks for notification delivery under load.  
- Risky: No defined escalation if all retries fail.  
- Assumption: Customers want real-time updates rather than daily summaries.  

---

## ✅ Submission Checklist
- [x] 6 user stories, ≤25 words, correct template.  
- [x] ≥2 acceptance criteria per story, Given/When/Then format.  
- [x] Exactly 10 open questions, grouped by theme.  
- [x] ≥3 critique bullets, covering missing info, risks, assumptions.  
- [x] Clear markdown headings and numbering.  
