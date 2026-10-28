# Lab 5 - Exercise 3: Integration Notes (Working Draft)

Project: Laboratory Equipment Loan and Return System
Status: WORKING DRAFT — observations and proposed actions, not finalized team decisions.

## Inputs reviewed

- Hassan: candidate classes (Student, Equipment, LoanRequest, LabStaff, User) and editable UML diagram.
- Mohammad: candidate classes (Equipment, EquipmentCatalog, LabStaff, User) and UML image.
- Saud: candidate classes (User, Student, LabStaff, Admin, Loan, Report) and UML image.
- Rachad: confirmed Exercise 1 candidate classes (User, LabStaff, LoanRecord, ReturnTransaction, Notification, Equipment) and UML diagram covering UC-13, UC-15, UC-16, UC-17, and UC-18.
- Labs 3 and 4: existing use-case requirements and data-flow models.

## Duplicate classes identified

### User (Hassan, Mohammad, Saud, Rachad)
All model a common account/user entity.
Proposed action: Use ONE User class, reconciling attributes and authentication methods; Student, LabStaff and Admin inherit from it if the team accepts this specialization.

### Student (Hassan, Saud)
Hassan covers request submission/tracking; Saud covers loan history.
Proposed action: Merge their distinct operations into ONE Student class.

### LabStaff (Hassan, Mohammad, Saud, Rachad)
Hassan covers reviewing requests; Mohammad covers managing equipment; Saud covers loan records/reports.
Proposed action: Merge their non-conflicting responsibilities into ONE LabStaff class.

### Equipment (Hassan, Mohammad, Rachad)
Hassan models availability; Mohammad models descriptive details, condition and status.
Proposed action: Merge them into ONE Equipment class; check consistent types/status representation.

## Potential conceptual conflict: Loan vs LoanRecord

Saud's Loan and Rachad's LoanRecord appear to represent a checked-out borrowing transaction.
Resolution: CONFIRMED. Rachad's LoanRecord and Saud's Loan represent the exact same borrowing transaction. They are merged into ONE class named Loan (CC08), retaining borrower tracking, return dates, and overdue status checks.

LoanRequest is NOT a duplicate of Loan: a request can be pending/rejected before any equipment has been loaned.

## Relationships to reconcile

- Student (1) — submits — LoanRequest (0..*).
- Equipment (1) — is requested in — LoanRequest (0..*).
- LabStaff (0..1) — reviews — LoanRequest (0..*) if one reviewer is assigned per request.
- EquipmentCatalog (1) — lists — Equipment (0..*) as proposed by Mohammad.
- Student (1) — borrows — Loan (0..*) as proposed by Saud.
- Equipment (1) — loaned as — Loan (0..*).
- LabStaff (1) — issues/records — Loan (0..*).
- Loan (1) — returned via — ReturnTransaction (0..1) to record return date and equipment condition.
- LoanRequest (0..1) — triggers — Notification (0..*) for approval and rejection notices.
- Loan (1) — triggers — Notification (0..*) for overdue alerts.

All multiplicities are provisional until the merged diagram is reviewed.

## Missing integration points to verify

- UC-11 / UC-12: Approve / Reject Loan Request (staff action and request-status changes).
- UC-19 / UC-20: History and Reports.
- Lab 4: consistency with P1–P5 and the User, Equipment, and Loan data stores.

## Next steps

1. Agree on a single set of classes, class names, attribute types, and method ownership.
2. Build ONE editable consolidated UML diagram under `Object_Modeling/Class_Diagram/`.
3. Verify inheritance, association labels and multiplicities against actual requirements.
4. Complete `Class_Model_Consistency_Check.md` using the final diagram and Labs 3–4.
5. Mark decisions as confirmed only after actual team agreement; preserve individual contributions in `Individual_Models/`.
6. Include an accurate declaration and justification of AI assistance in the final lab submission.
