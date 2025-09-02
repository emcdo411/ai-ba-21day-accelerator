# ✅ Day 7 — MiniProject1: AI-Assisted BRD Draft (Sample Output for Students)

This sample demonstrates the **four required files** for Day 7.  
Your deliverables should be saved separately in the folder:  
`Projects/MiniProject1_BRD_Draft/`

---

## 1. BRD_v1.md

```markdown
# Business Requirements Document (v1)

## Problem Statement
Our e-commerce platform currently suffers from delays in order notifications, causing customer dissatisfaction and increased support tickets.  
Without automated push notifications, customers often call support for order status, raising costs and reducing efficiency.  

## Scope
- **In Scope**
  - Push notifications for order status changes
  - iOS and Android device support
- **Out of Scope**
  - Email/SMS notifications
  - Non-mobile platforms

## Actors / Stakeholders
- Customer
- Mobile App User
- Support Team
- IT Operations

### RACI Table
| Role           | Responsible | Accountable | Consulted | Informed |
|----------------|-------------|-------------|-----------|----------|
| Product Owner  |             | X           |           |          |
| Dev Team Lead  | X           |             |           |          |
| QA Lead        |             |             | X         |          |
| Support Manager|             |             |           | X        |

## User Stories & Acceptance Criteria

- **US-1:** As a customer, I want push notifications so that I know when my order status changes.  
  - **AC-1.1**: Given an order status change, when it occurs, then a notification is sent within 5 seconds.  
  - **AC-1.2**: Given device offline, when status changes, then notification queues and delivers when online.  

- **US-2:** As a support agent, I want customers notified automatically so that support tickets decrease.  
  - **AC-2.1**: Given notification sent, when customer confirms receipt, then support system logs reduced inquiries.  
  - **AC-2.2**: Given failure to notify, when retries exceed 3, then system flags support.  

*(Repeat until 6–12 stories are covered, each ≤25 words, each with ≥2 ACs in Given/When/Then format.)*

## Risks & Assumptions
- Risk: Notification delivery failures on Android.  
- Risk: Push service outages increase delays.  
- Assumption: Customers opt-in to receive notifications.  
- Assumption: Device tokens remain valid for 90 days.  
- Risk: Integration with backend introduces latency.

## SMART KPI Targets
- Reduce order-related support calls by **20% within 6 months**.  
- Deliver notifications with **95% success rate within 3 seconds**.


