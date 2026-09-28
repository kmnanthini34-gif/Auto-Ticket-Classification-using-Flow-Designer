# Phase 4 – Project Planning

## 4.1 Planning Overview

The project planning phase defines the activities required to implement, test, document, and demonstrate the Auto Ticket Classification system.

The project follows a structured phase-wise development approach.

---

## 4.2 Project Plan

| Phase   | Activity                 | Expected Output                              |
| ------- | ------------------------ | -------------------------------------------- |
| Phase 1 | Brainstorming & Ideation | Problem identification and proposed solution |
| Phase 2 | Requirement Analysis     | Business and functional requirements         |
| Phase 3 | Project Design           | System and data design                       |
| Phase 4 | Project Planning         | Implementation plan                          |
| Phase 5 | Project Development      | Configured ServiceNow solution               |
| Phase 6 | Project Testing          | Validated automation                         |
| Phase 7 | Project Documentation    | Complete project documentation               |
| Phase 8 | Project Demonstration    | Project demonstration video                  |

---

## 4.3 Development Activities

The implementation activities include:

1. Create a ServiceNow Update Set.
2. Create the custom Incident Workflow table.
3. Configure the auto-number functionality.
4. Create required fields.
5. Configure Category choices.
6. Configure Subcategory choices.
7. Configure State choices.
8. Configure Category/Subcategory dependency.
9. Create the Flow Designer flow.
10. Configure the Record Created trigger.
11. Implement classification conditions.
12. Configure Update Record actions.
13. Configure email notification.
14. Activate the flow.
15. Test the automation.
16. Complete the Update Set.
17. Export the Update Set if required.
18. Prepare final documentation and demonstration.

---

## 4.4 Classification Plan

The classification logic is planned around predefined keywords.

| Condition                                    | Result                      |
| -------------------------------------------- | --------------------------- |
| Short Description contains WiFi or Network   | Network → Wi-Fi             |
| Short Description contains Projector         | Hardware → Projector        |
| Short Description contains Password or Login | Access → Forgot Password    |
| Short Description contains Slow or Hanging   | Performance → Slow Computer |

---

## 4.5 Testing Plan

The project will be tested using different ticket descriptions.

Example test scenarios include:

* WiFi not working in library.
* Projector not turning on.
* Password-related issue.
* Slow computer issue.

Testing will verify:

* Correct Category.
* Correct Subcategory.
* Ticket creation.
* Email notification.
* Data consistency.

---

## 4.6 Deployment Planning

The project configuration will be maintained using the **Project Update Set**.

After development and testing:

1. Open the Project Update Set.
2. Change the state from In Progress to Complete.
3. Save the Update Set.
4. Export the Update Set as XML when required.

---

## 4.7 Planning Outcome

The planning phase establishes a clear implementation and validation process for completing the ServiceNow automation project.
