# Phase 6 – Project Testing

## 6.1 Testing Objective

Testing is performed to verify that the developed ServiceNow solution works according to the defined requirements.

The testing focuses on:

* Ticket creation.
* Automatic classification.
* Category assignment.
* Subcategory assignment.
* Email notification.
* Data validation.

---

## 6.2 Data Validation Checks

The following validation checks are performed:

* Mandatory fields are captured correctly.
* Auto-number is generated without duplication.
* Category values are stored accurately.
* Subcategory values are stored accurately.
* Reference fields resolve correctly.
* Ticket information is stored in the expected structure.

---

## 6.3 Test Case 1 – Wi-Fi Issue


### Test Input

```text
Caller: Test User

Short Description:
WiFi not working in library
```

### Expected Result

```text
Category    → Network
Subcategory → Wi-Fi
```

### Email

An email notification should be sent to the caller's email address.

### Result
<img width="1917" height="851" alt="Screenshot 2026-09-29 172248" src="https://github.com/user-attachments/assets/1fa35151-043c-48e1-88b9-76131bcc948c" />
<img width="1917" height="1035" alt="Screenshot 2026-09-29 170807" src="https://github.com/user-attachments/assets/7bed736d-407b-4624-a302-fda41b81bb70" />

The ticket is classified as a Network / Wi-Fi issue and the notification is generated.

---

## 6.4 Test Case 2 – Projector Issue

### Test Input

```text
Caller: Test User

Short Description:
Projector not turning on
```

### Expected Result

```text
Category    → Hardware
Subcategory → Projector
```

### Email

An email notification should be sent to the caller.

### Result
<img width="1917" height="770" alt="Screenshot 2026-09-29 172223" src="https://github.com/user-attachments/assets/702aca9d-4692-4562-87aa-78fccfdecc38" />
<img width="1917" height="1027" alt="Screenshot 2026-09-29 175032" src="https://github.com/user-attachments/assets/003d56b3-5360-40ef-8f67-30fa02b7eeb9" />

The ticket is classified as a Hardware / Projector issue.

---

## 6.5 Test Case Summary

| Test ID | Test Scenario               | Expected Category | Expected Subcategory |
| ------- | --------------------------- | ----------------- | -------------------- |
| TC-01   | WiFi not working in library | Network           | Wi-Fi                |
| TC-02   | Projector not turning on    | Hardware          | Projector            |
| TC-03   | Password-related issue      | Access            | Forgot Password      |
| TC-04   | Slow computer issue         | Performance       | Slow Computer        |

---

## 6.6 Email Notification Testing

The email notification can be validated through the ServiceNow email records.

### Validation Process

1. Open the ServiceNow All menu.
2. Search for Emails.
3. Open the email records.
4. Search using the configured subject.
5. Open the corresponding email record.
6. Preview the email.
7. Verify the recipient and notification content.

---

## 6.7 Testing Outcome

Testing confirms the expected behavior of the automated ticket classification workflow for the defined scenarios.

The test results demonstrate that the Flow Designer automation can classify supported IT ticket descriptions and generate the corresponding caller notification.
