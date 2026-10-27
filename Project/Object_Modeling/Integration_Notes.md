# Lab 5 - Exercise 3: Integration Notes (Working Draft)

Project: Laboratory Equipment Loan and Return System
Status: WORKING DRAFT — observations and proposed actions, not finalized team decisions.

## Inputs reviewed

- Hassan: candidate classes (Student, Equipment, LoanRequest, LabStaff, User) and editable UML diagram.
- Mohammad: candidate classes (Equipment, EquipmentCatalog, LabStaff, User) and UML image.
- Saud: candidate classes (User, Student, LabStaff, Admin, Loan, Report) and UML image.
- Rachad: preliminary UML screenshot (Notification, ReturnTransaction, LoanRecord); final Exercise 1 inventory pending.
- Labs 3 and 4: existing use-case requirements and data-flow models.

## Duplicate classes identified

### User (Hassan, Mohammad, Saud)
All model a common account/user entity.
Proposed action: Use ONE User class, reconciling attributes and authentication methods; Student, LabStaff and Admin inherit from it if the team accepts this specialization.

### Student (Hassan, Saud)
Hassan covers request submission/tracking; Saud covers loan history.
Proposed action: Merge their distinct operations into ONE Student class.

### LabStaff (Hassan, Mohammad, Saud)
Hassan covers reviewing requests; Mohammad covers managing equipment; Saud covers loan records/reports.
Proposed action: Merge their non-conflicting responsibilities into ONE LabStaff class.

### Equipment (Hassan, Mohammad)
Hassan models availability; Mohammad models descriptive details, condition and status.
Proposed action: Merge them into ONE Equipment class; check consistent types/status representation.

## Potential conceptual conflict: Loan vs LoanRecord

Saud's Loan and Rachad's LoanRecord appear to represent a checked-out borrowing transaction.
Proposed action: Review their attributes and methods and likely consolidate them, but do NOT mark this decision resolved before team review.

LoanRequest is NOT a duplicate of Loan: a request can be pending/rejected before any equipment has been loaned.

## Relationships to reconcile

- Student (1) — submits — LoanRequest (0..*).
- Equipment (1) — is requested in — LoanRequest (0..*).
- LabStaff (0..1) — reviews — LoanRequest (0..*) if one reviewer is assigned per request.
- EquipmentCatalog (1) — lists — Equipment (0..*) as proposed by Mohammad.
- Student (1) — borrows — Loan (0..*) as proposed by Saud.
- Loan and ReturnTransaction: proposed Loan (1) — ReturnTransaction (0..1) for loans that have not yet been returned.
- Notification must be linked to appropriate triggering requests/loans and a recipient; Rachad's draft currently connects it to LoanRecord only. Review because approval/rejection notifications may happen before checkout.
- LabStaff to Equipment: review whether the association represents managing many items, rather than implying a particular staff member owns all equipment.

All multiplicities are provisional until the merged diagram is reviewed.

## Missing integration points to verify

- UC-11 / UC-12: Approve / Reject Loan Request (staff action and request-status changes).
- UC-13 / UC-14: Record Equipment Checkout / Expected Return Date.
- UC-15 / UC-16: Record Equipment Return / Equipment Condition.
- UC-17 / UC-18: Monitor Overdue Equipment / Send Notifications.
- UC-19 / UC-20: History and Reports.
- Lab 4: consistency with P1–P5 and the User, Equipment, and Loan data stores.

## Next steps

1. Receive Rachad's candidate-class inventory and any updated model.
2. Agree on a single set of classes, class names, attribute types, and method ownership.
3. Build ONE editable consolidated UML diagram under `Object_Modeling/Class_Diagram/`.
4. Verify inheritance, association labels and multiplicities against actual requirements.
5. Complete `Class_Model_Consistency_Check.md` using the final diagram and Labs 3–4.
6. Mark decisions as confirmed only after actual team agreement; preserve individual contributions in `Individual_Models/`.
7. Include an accurate declaration and justification of AI assistance in the final lab submission.
