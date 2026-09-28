# Phase 2 – Requirement Analysis

## 2.1 Requirement Analysis Overview

The requirement analysis phase identifies the functional requirements, data requirements, and expected behavior of the Auto Ticket Classification system.

The project focuses on automating the classification of school IT support tickets.

---

## 2.2 Business Requirements

The system must:

1. Automatically classify IT tickets based on the issue description.
2. Assign both Category and Subcategory without manual intervention.
3. Support dependent choice logic between Category and Subcategory.
4. Send an automated email notification to the caller after ticket creation.
5. Store ticket information in a structured and standardized format.
6. Support easy maintenance and future scalability.

---

## 2.3 Functional Requirements

### Ticket Creation

The system should allow a user to create an IT support ticket by providing the required ticket information.

### Automatic Classification

The system should analyze the Short Description and identify predefined keywords.

### Category Assignment

The system should automatically assign the appropriate category.

### Subcategory Assignment

The system should automatically assign the appropriate subcategory according to the detected issue.

### Email Notification

After ticket creation and classification, the system should send an email notification to the caller.

---

## 2.4 Ticket Classification Requirements

| Issue Keyword | Category    | Subcategory     |
| ------------- | ----------- | --------------- |
| WiFi          | Network     | Wi-Fi           |
| Network       | Network     | Wi-Fi           |
| Projector     | Hardware    | Projector       |
| Password      | Access      | Forgot Password |
| Login         | Access      | Forgot Password |
| Slow          | Performance | Slow Computer   |
| Hanging       | Performance | Slow Computer   |

---

## 2.5 Data Requirements

The custom ticket table contains the following fields:

| Field             | Type                       |
| ----------------- | -------------------------- |
| Number            | Auto Number                |
| Caller            | Reference – sys_user       |
| Category          | Choice                     |
| Subcategory       | Choice                     |
| Short Description | String                     |
| Description       | String                     |
| State             | Choice                     |
| Assigned Group    | Reference – sys_user_group |
| Assigned To       | Reference – sys_user       |

---

## 2.6 Choice Values

### Category

* Network
* Hardware
* Access
* Performance

### Subcategory

* Wi-Fi
* Projector
* Forgot Password
* Slow Computer

### State

* New
* In Progress
* On Hold
* Resolved
* Closed

---

## 2.7 Non-Functional Requirements

The solution should be:

* Easy to maintain.
* Scalable for future enhancements.
* Structured and consistent.
* Based on a no-code implementation.
* Reliable during ticket creation and classification.

---

## 2.8 Requirement Analysis Outcome

The requirement analysis establishes the business and technical requirements needed to implement automated IT ticket classification using ServiceNow Flow Designer.
