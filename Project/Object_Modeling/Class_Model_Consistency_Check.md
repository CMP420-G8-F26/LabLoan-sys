Lab 5 - Class Model Consistency and Traceability Check

Project: Laboratory Equipment Loan and Return System
Team: Mohammad Ibrahim, Saud Alzaabi, Hassan Almarri, Rachad Bouida
Exercise: 3 - Team Integration
Review date: October 28, 2026
Status: Reviewed; some minor corrections are still recommended before final submission.


1. Purpose of the Check

This document checks whether the consolidated UML Class Diagram is consistent with the team's Lab 3 requirements and use cases, Lab 4 Data Flow Diagrams and core processes, and the individual class models prepared for Lab 5.

The review is based on the updated Consolidated_UML.drawio file and the previous project reports. It identifies the functionality represented by the classes, checks relationships and multiplicities, and records items that still require correction or clarification.


2. Consolidated Classes

The consolidated diagram contains these 11 classes:

User
Student
LabStaff
Admin
EquipmentCatalog
Equipment
LoanRequest
Loan
Report
Notification
ReturnTransaction

The individual models contained overlapping definitions of User, Student, LabStaff, and Equipment. These have been consolidated so that only one copy of each appears in the team diagram.

Saud's Loan and Rachad's LoanRecord refer to the same actual borrowing record. The combined model uses Loan. LoanRequest remains separate because requesting an item is different from actually checking it out.


3. Consistency with Lab 3 Use Cases

UC-01 - Login
User includes a login method. Status: Covered.

UC-02 - Logout
User includes a logout method. Status: Covered.

UC-03 - Manage Users
Admin includes methods for creating, updating, and deactivating users. Status: Covered.

UC-04 - Manage Equipment
LabStaff includes equipment-management methods, and Equipment represents the managed item. Status: Covered.

UC-05 - View Equipment Details
Equipment provides item details, and EquipmentCatalog supports finding items. Status: Covered.

UC-06 - Search Equipment
EquipmentCatalog includes equipment-search functionality. Status: Covered.

UC-07 - Check Equipment Availability
Equipment includes availability information and an availability-check method. Status: Covered.

UC-08 - Submit Loan Request
Student includes a submission method and is associated with LoanRequest. Status: Covered.

UC-09 - View Loan Request Status
LoanRequest stores its status and provides a status-retrieval method; Student can view the request status. Status: Covered.

UC-10 - Review Loan Requests
LabStaff includes methods for viewing and reviewing pending LoanRequest objects. Status: Covered.

UC-11 - Approve Loan Request
LoanRequest includes an approval method. The exact status change and equipment reservation behavior should be confirmed. Status: Covered conceptually; details to verify.

UC-12 - Reject Loan Request
LoanRequest includes a rejection method with a reason. Related notification behavior should be checked. Status: Covered conceptually; details to verify.

UC-13 - Record Equipment Checkout
Loan represents checkout details, and LabStaff includes a record-checkout method. The method currently has no parameters, so its link to the created loan could be clearer. Status: Partially specified.

UC-14 - Record Expected Return Date
Loan stores expectedReturnDate. A separate method for entering or setting the date is not explicitly shown, but the date may be recorded during checkout. Status: Partially specified.

UC-15 - Record Equipment Return
ReturnTransaction is associated with Loan and includes return-processing functionality. Status: Covered.

UC-16 - Record Equipment Condition
ReturnTransaction records conditionAtReturn, and Equipment includes an update-condition method. Status: Covered.

UC-17 - Monitor Overdue Equipment
Loan stores the expected and actual return dates and includes an overdue-check method. Notifications support overdue alerts. Status: Covered.

UC-18 - Send Notifications
Notification includes message details and sending functionality. It is linked to loan requests and loans. Status: Covered; verify event and recipient handling.

UC-19 - View Loan and Return History
Student includes a loan-history method, and Loan stores historical borrowing data. One LabStaff method still refers to LoanRecord, which was merged into Loan. Status: Covered, with a type-name correction needed.

UC-20 - Generate Reports
Report includes methods for usage, overdue, and loan-history reports. Admin is associated with Report; access for other authorized staff should be clarified if required. Status: Covered conceptually.

Overall Lab 3 result: The consolidated diagram represents the major functionality of UC-01 through UC-20. Some operations and relationships need minor refinement, rather than additional unrelated classes.


4. Consistency with Lab 4 Data Flow Modeling

P1 - Manage Users and Authentication
Corresponding classes: User, Student, LabStaff, Admin.
Result: Consistent. The user classes cover shared account information and role-specific responsibilities.

P2 - Manage Equipment
Corresponding classes: Equipment, EquipmentCatalog, LabStaff.
Result: Consistent. Equipment data, catalog lookup, and staff management are represented.

P3 - Process Loan Request
Corresponding classes: LoanRequest, Student, LabStaff, Equipment.
Result: Consistent. Request submission, availability checking, status, and review are represented.

P4 - Record Checkout and Return
Corresponding classes: Loan, ReturnTransaction, Equipment, LabStaff.
Result: Mostly consistent. Checkout and return data are represented, but the checkout operation could be made more explicit.

P5 - Monitor Overdue Equipment and Send Notifications
Corresponding classes: Loan, Notification, Report.
Result: Consistent. Overdue checks, alert information, and related reporting are represented.

D1 - UserDB
The information in this data store corresponds to User and its specialized user classes.

D2 - EquipmentDB
The information corresponds to Equipment and catalog retrieval functions.

D3 - LoanDB
The information corresponds to LoanRequest, Loan, and ReturnTransaction.

The DFD describes processes and data movement, while the UML Class Diagram describes objects and relationships. A separate UML class is not required for every process or data store, provided the responsibilities and stored information are represented consistently.


5. Relationships and Multiplicities

Student submits LoanRequest
One student may submit zero or many requests. Each request belongs to one student. Multiplicities: Student 1, LoanRequest 0..*.

Equipment is requested in LoanRequest
One equipment item may appear in zero or many requests over time. Each request refers to one item in the current design. Multiplicities: Equipment 1, LoanRequest 0..*.

LabStaff reviews LoanRequest
One staff member may review many requests. A request may have no assigned reviewer until it is reviewed. The diagram assumes at most one assigned reviewer per request. Multiplicities: LabStaff 0..1, LoanRequest 0..*.

EquipmentCatalog lists Equipment
One catalog may list multiple equipment items, while each item is associated with one catalog under the proposed system design. Multiplicities: EquipmentCatalog 1, Equipment 0..*.

Student borrows Loan
A student may have zero or many loans. Each loan belongs to one student. Multiplicities: Student 1, Loan 0..*.

Equipment is loaned through Loan
One item may have many historical loans. Each loan is for one equipment item. Multiplicities: Equipment 1, Loan 0..*.

Loan is returned through ReturnTransaction
A loan may have no return transaction before the item is returned, and one return transaction afterward. Each return transaction belongs to one loan. Multiplicities: Loan 1, ReturnTransaction 0..1. This assumes one completed return per loan.

LoanRequest and Loan trigger Notification
A request or loan may generate multiple notifications. The notification's trigger and recipient should be clearly defined, particularly for approval/rejection versus overdue notices.

The diagram also includes staff relationships for managing equipment, reviewing requests, and recording loans or returns. Their labels and multiplicities should be checked against the intended responsibility of each staff member.


6. Inheritance and Class Definition Check

Student, LabStaff, and Admin inherit from the common User class. This is a meaningful generalization because all three represent system users with shared account information.

The inheritance arrows point toward User. Duplicate definitions of User, Student, LabStaff, and Equipment have been removed from the consolidated model.

LoanRequest is separate from Loan, and LoanRecord has been merged into Loan. These decisions avoid representing the same borrowing transaction with duplicate classes.

The main classes include attributes, methods, visibility symbols, data types, parameter types, and return types. Some referenced types, such as EquipmentStatus, EquipmentCondition, LoanStatus, and NotificationType, should be identified as enumerations or otherwise clearly defined.


7. Issues to Correct or Confirm

1. LabStaff currently includes viewOverdueLoans(): List<LoanRecord>. Since LoanRecord was merged into Loan, the return type should be changed to List<Loan>.

2. The reviews connector should be attached to the overall LabStaff class rather than only to its methods compartment, if that attachment remains in the current editable diagram.

3. Any stray or unfinished diagram objects or connectors, including objects labelled Issues or Processes if they are unintended, should be removed.

4. The approval and rejection methods should reflect the intended request-status changes. The corresponding notification behavior should also be consistent.

5. The expected return date is stored in Loan. The team should confirm whether it is entered during checkout or whether an explicit operation is needed to record it.

6. ReturnTransaction should remain linked to the correct Loan, and condition-at-return information should be consistent with Equipment condition updates.

7. Association labels and multiplicities should be legible and reflect the team's actual assumptions, especially the assigned reviewer, return transaction, and notification relationships.

8. Class_Inventory.md should show LoanRecord as a merged duplicate rather than an additional active class. Integration_Notes.md should reflect the final decisions without outdated draft or provisional wording.

9. The team should ensure that all four members' contributions are identifiable and that the final report includes an accurate declaration and justification of AI assistance.


8. Conclusion

The consolidated UML Class Diagram contains the 11 main classes and broadly matches the functionality identified in Lab 3 and the core processes and data stores identified in Lab 4.

The main class structure, inheritance, and major relationships are appropriate for the Laboratory Equipment Loan and Return System. A few references, method details, connector placements, and documentation items still require review before claiming full consistency.

Final review result: MOSTLY CONSISTENT - MINOR CORRECTIONS RECOMMENDED.

This check records the current review findings. Final approval of the integrated design and submission remains the responsibility of the team.
