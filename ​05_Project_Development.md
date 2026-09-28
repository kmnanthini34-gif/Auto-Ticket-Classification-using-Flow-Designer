# Phase 5 – Project Development

## 5.1 Development Overview

The development phase focuses on implementing the designed solution in ServiceNow.

The project uses ServiceNow configuration and Flow Designer to automate IT ticket classification.

---

## 5.2 Update Set Creation

A new local Update Set is created.

### Configuration

**Name:** Project Update Set

**State:** In Progress

**Application:** Global

The Update Set is then made the current Update Set.

---

## 5.3 Custom Table Creation

A custom table named:

**Incident Workflow**

is created to store the IT support ticket records.

Auto-number functionality is enabled for generating unique ticket numbers.

---

## 5.4 Field Configuration

The following fields are created:

| Field             | Type        |
| ----------------- | ----------- |
| Number            | Auto Number |
| Caller            | Reference   |
| Category          | Choice      |
| Subcategory       | Choice      |
| Short Description | String      |
| Description       | String      |
| State             | Choice      |
| Assigned Group    | Reference   |
| Assigned To       | Reference   |

---

## 5.5 Choice Configuration

### Category

```text
Network
Hardware
Access
Performance
```

### Subcategory

```text
Wi-Fi
Projector
Forgot Password
Slow Computer
```

### State

```text
New
In Progress
On Hold
Resolved
Closed
```

---

## 5.6 Dependent Choice Configuration

The Subcategory field is configured to depend on the Category field.

The dependency mapping is:

```text
Wi-Fi             → Network
Projector         → Hardware
Forgot Password   → Access
Slow Computer     → Performance
```

This allows the system to display the appropriate subcategory according to the selected category.

---

## 5.7 Flow Designer Configuration

### Flow Name

**Auto Classify School IT Tickets**

### Trigger

**Record Created**

### Table

**Incident Workflow**

### Trigger Condition

**Category is Empty**

---

## 5.8 Wi-Fi Classification

The flow checks whether the Short Description contains:

* Wi-Fi
* Network

If the condition is satisfied:

```text
Category    = Network
Subcategory = Wi-Fi
```

---

## 5.9 Projector Classification

The flow checks whether the Short Description contains:

**Projector**

If the condition is satisfied:

```text
Category    = Hardware
Subcategory = Projector
```

---

## 5.10 Password Classification

The flow checks for password-related information.

If the condition is satisfied:

```text
Category    = Access
Subcategory = Forgot Password
```

---

## 5.11 Slow Computer Classification

The flow checks for slow computer-related information.

If the condition is satisfied:

```text
Category    = Performance
Subcategory = Slow Computer
```

---

## 5.12 Email Action

After classification, the flow uses a Send Email action.

**To:** Caller → Email

**Subject:** Your Request for the issue has been submitted.

The email confirms ticket submission to the caller.

---

## 5.13 Flow Activation

After all conditions and actions are configured, the flow is activated.

The completed flow provides automated classification whenever a new ticket meets the trigger condition.

---

## 5.14 Development Outcome

The development phase results in a working ServiceNow solution consisting of:

* Custom ticket table.
* Configured ticket fields.
* Choice fields.
* Dependent fields.
* Flow Designer automation.
* Automated classification.
* Email notification.
* Update Set configuration.
