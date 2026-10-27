# Lab 5 - Exercise 3: Consolidated Class Inventory (Working Draft)

Project: Laboratory Equipment Loan and Return System
Team: Mohammad Ibrahim, Saud Alzaabi, Hassan Almarri, Rachad Bouida
Status: WORKING DRAFT — awaiting Rachad's completed Exercise 1 inventory and team confirmation of integration decisions.

## Basis of this draft

- Hassan: individual Exercise 1 and UML diagram (UC-07 through UC-10).
- Mohammad: uploaded `Mohammad_Candidate_Classes.md` and UML image.
- Saud: uploaded `Saud_Candidate_Classes.md` and UML image.
- Rachad: preliminary UML screenshot from WhatsApp; his individual class inventory has not yet been received.
- Previous project requirements, use cases and DFDs from Labs 3 and 4.

Class IDs below are NEW consolidated IDs; each member's original C01/C02/etc. remains unchanged in their individual inventory.

## Proposed consolidated candidate classes

### CC01 — User
Responsibility: Represents shared account information and authentication (e.g., user ID, name, email, password hash, login/logout).
Related use cases: UC-01, UC-02.
Origin: Hassan, Mohammad, Saud.
Integration status: Duplicate class identified; propose one shared User superclass.

### CC02 — Student
Responsibility: Represents a student who requests equipment, tracks request status, and views borrowing history.
Related use cases: UC-07, UC-08, UC-09, UC-19.
Origin: Hassan, Saud.
Integration status: Duplicate class identified; propose one combined Student subclass of User.

### CC03 — LabStaff
Responsibility: Represents staff who maintain equipment records, inspect pending requests, and view authorized loan information.
Related use cases: UC-04, UC-07, UC-10, UC-19, UC-20.
Origin: Hassan, Mohammad, Saud.
Integration status: Duplicate class identified; propose one combined LabStaff subclass of User.

### CC04 — Equipment
Responsibility: Holds equipment ID, descriptive details, condition and availability/status; provides availability information.
Related use cases: UC-04, UC-05, UC-07, UC-08.
Origin: Hassan, Mohammad.
Integration status: Duplicate class identified; combine attributes and operations, avoiding parallel Equipment classes.

### CC05 — LoanRequest
Responsibility: Records the student’s request for particular equipment and dates and tracks pending/approved/rejected status for review.
Related use cases: UC-08, UC-09, UC-10.
Origin: Hassan.
Integration status: Keep distinct from an actual checked-out Loan.

### CC06 — EquipmentCatalog
Responsibility: Searches, finds and lists equipment available for borrowing.
Related use cases: UC-05, UC-06, UC-07.
Origin: Mohammad.
Integration status: Keep provisionally; relationship to Equipment will be modeled.

### CC07 — Admin
Responsibility: Manages user accounts, roles and access to system functions.
Related use cases: UC-03.
Origin: Saud.
Integration status: Keep as a User subtype, subject to team review.

### CC08 — Loan
Responsibility: Represents an actual borrowing/checkout record, including checkout date, expected return date, actual return date, and loan status.
Related use cases: UC-19 (Saud); potentially UC-13, UC-14, UC-15 and UC-17 when integrated with other components.
Origin: Saud.
Integration status: Compare with Rachad's LoanRecord; likely overlapping models but merge NOT YET CONFIRMED.

### CC09 — Report
Responsibility: Represents generated loan/return history and equipment usage/overdue reports.
Related use cases: UC-20.
Origin: Saud.
Integration status: Keep provisionally; report-generation operations need review.

### CC10 — Notification
Responsibility: Stores notification details and supports messages for approvals, rejections, reminders and overdue items.
Related use cases: UC-18.
Origin: Rachad (preliminary screenshot; earlier Lab 3 responsibility for UC-18 was assigned to Hassan).
Integration status: Provisional until Rachad confirms his final model and individual inventory.

### CC11 — ReturnTransaction
Responsibility: Represents the processing of an equipment return, including return date, late status and staff member receiving the item.
Related use cases: UC-15 (inferred from functionality; check Rachad's final inventory).
Origin: Rachad (preliminary screenshot).
Integration status: Provisional; confirm relationships to Loan and equipment condition handling (UC-16).

### CC12 — LoanRecord (possible duplicate of CC08)
Responsibility: Holds borrower ID, checkout/return dates and overdue status in Rachad's preliminary model.
Related use cases: UC-13, UC-14, UC-15 and UC-17 (inferred from functionality; Rachad has not supplied a use-case mapping).
Origin: Rachad (preliminary screenshot).
Integration status: UNRESOLVED. Compare with CC08 Loan; if they represent the same actual loan, retain one class rather than both.

## Outstanding class-inventory decisions

1. Confirm that User, Student, LabStaff and Equipment are each represented once after integration.
2. Decide whether LoanRecord is the same domain entity as Loan; if yes, remove CC12 and merge its relevant attributes/operations into CC08.
3. Confirm whether ReturnTransaction remains a separate object recording a return, rather than just a method on Loan.
4. Confirm Rachad's individual candidate classes and official related use cases when received.
5. Confirm agreed final IDs, class definitions and contributors as a team before marking this inventory APPROVED.
6. Ensure the final UML diagram and traceability check match the approved inventory.

This file is a team-integration draft, not a claim that every model decision has already been approved.
