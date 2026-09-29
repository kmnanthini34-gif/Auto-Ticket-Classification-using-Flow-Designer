# Phase 7 – Project Documentation

## 7.1 Project Overview

The **Auto Ticket Classification Using Flow Designer** project provides an automated solution for classifying school IT helpdesk tickets.

The system uses ServiceNow Flow Designer to analyze ticket descriptions and automatically assign Category and Subcategory values.

---

## 7.2 Problem Statement

The school IT helpdesk receives multiple support requests every day.

Manual ticket classification requires IT staff to review each request and select the correct category and subcategory.

This process increases manual effort and can lead to inconsistent classification.

---

## 7.3 Proposed Solution

The project implements a no-code automation using ServiceNow Flow Designer.

The flow is triggered when a new ticket is created and the Category field is empty.

It evaluates the Short Description and assigns the appropriate classification.

---

## 7.4 Key Features

### Automatic Classification

Tickets are automatically classified based on predefined keywords.

### Dependent Subcategory

Subcategory values are associated with the corresponding Category.

### Automated Notification

An email notification is sent to the caller after ticket creation.

### Structured Data

Ticket details are stored using defined fields and data types.

### Update Set Support

The configuration is maintained using a ServiceNow Update Set.

---

## 7.5 Classification Mapping

| Issue            | Category    | Subcategory     |
| ---------------- | ----------- | --------------- |
| WiFi / Network   | Network     | Wi-Fi           |
| Projector        | Hardware    | Projector       |
| Password / Login | Access      | Forgot Password |
| Slow / Hanging   | Performance | Slow Computer   |

---

## 7.6 Benefits

The solution helps:

* Reduce manual classification effort.
* Improve consistency.
* Improve ticket handling efficiency.
* Standardize ticket information.
* Provide automated caller communication.
* Simplify maintenance through no-code configuration.

---

## 7.7 Deployment

The project configuration is maintained in the **Project Update Set**.

After development and testing, the Update Set can be changed to Complete and exported as XML for transfer to another environment.

---

## 7.8 Limitations

The current implementation uses predefined keywords for classification.

Therefore, classification depends on the keywords and conditions configured within the Flow Designer.

The project document does not describe machine-learning-based classification as part of the current implementation.

---

## 7.9 Future Enhancements

The project can be extended with:

* Assignment automation.
* SLA tracking.
* Additional classification conditions.
* More ticket categories.
* Predictive intelligence.
* Additional automation workflows.

---

## 7.10 Conclusion

The project successfully demonstrates the use of ServiceNow Flow Designer for automating IT ticket classification.

The system analyzes predefined keywords, assigns the appropriate Category and Subcategory, and sends an automated email notification to the caller.

The implementation provides a structured, maintainable, and no-code approach to improving IT helpdesk ticket management.
