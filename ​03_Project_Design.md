# Phase 3 – Project Design

## 3.1 Design Overview

The project design defines the structure of the ServiceNow solution and describes how the different components work together.

The system consists of:

* Custom ticket table
* Ticket fields
* Choice fields
* Dependent Category and Subcategory fields
* Flow Designer automation
* Email notification
* Update Set

---

## 3.2 System Architecture

```text
                    ┌──────────────────────┐
                    │       Caller         │
                    │ Student / Teacher    │
                    └──────────┬───────────┘
                               │
                               ▼
                    ┌──────────────────────┐
                    │   Incident Workflow  │
                    │    Ticket Creation   │
                    └──────────┬───────────┘
                               │
                               ▼
                    ┌──────────────────────┐
                    │    Short Description │
                    │   Keyword Evaluation │
                    └──────────┬───────────┘
                               │
                               ▼
                    ┌──────────────────────┐
                    │    Flow Designer     │
                    │ Classification Logic │
                    └──────────┬───────────┘
                               │
              ┌────────────────┼────────────────┐
              │                │                │
              ▼                ▼                ▼
          Network          Hardware          Access
           / Wi-Fi         / Projector    / Password
              │                │                │
              └────────────────┼────────────────┘
                               │
                               ▼
                    ┌──────────────────────┐
                    │ Performance / Slow   │
                    │       Computer       │
                    └──────────┬───────────┘
                               │
                               ▼
                    ┌──────────────────────┐
                    │ Category &           │
                    │ Subcategory Updated  │
                    └──────────┬───────────┘
                               │
                               ▼
                    ┌──────────────────────┐
                    │   Email Notification │
                    └──────────────────────┘
```

---

## 3.3 Custom Table Design

The project uses a custom table named:

**Incident Workflow**

The table is configured with an auto-number field and the required ticket fields.

---

## 3.4 Field Design

| Field             | Data Type   | Purpose                              |
| ----------------- | ----------- | ------------------------------------ |
| Number            | Auto Number | Unique ticket identification         |
| Caller            | Reference   | Identifies the ticket requester      |
| Category          | Choice      | Stores the main issue category       |
| Subcategory       | Choice      | Stores the detailed issue type       |
| Short Description | String      | Stores the primary issue description |
| Description       | String      | Stores additional issue details      |
| State             | Choice      | Tracks ticket status                 |
| Assigned Group    | Reference   | Stores the support group             |
| Assigned To       | Reference   | Stores the assigned user             |

---

## 3.5 Dependent Field Design

The Subcategory field is configured as a dependent field based on Category.

```text
Category
   │
   ├── Network
   │      └── Wi-Fi
   │
   ├── Hardware
   │      └── Projector
   │
   ├── Access
   │      └── Forgot Password
   │
   └── Performance
          └── Slow Computer
```

This ensures that the available subcategory corresponds to the selected category.

---

## 3.6 Flow Design

The Flow Designer automation is named:

**Auto Classify School IT Tickets**

### Trigger

* Trigger: Record Created
* Table: Incident Workflow
* Condition: Category is Empty

### Classification Logic

The flow evaluates the Short Description and uses conditional branches.

```text
Record Created
      │
      ▼
Category Empty?
      │
      ▼
Check Short Description
      │
      ├── WiFi / Network
      │       ↓
      │   Network / Wi-Fi
      │
      ├── Projector
      │       ↓
      │   Hardware / Projector
      │
      ├── Password / Login
      │       ↓
      │   Access / Forgot Password
      │
      └── Slow / Hanging
              ↓
          Performance / Slow Computer
```

---

## 3.7 Email Notification Design

After classification, an email notification is sent to the caller's email address.

**Recipient:** Caller → Email

**Subject:** Your Request for the issue has been submitted.

The notification confirms the submission of the support request.

---

## 3.8 Design Outcome

The project design establishes a complete flow from ticket creation to automatic classification and caller notification.
