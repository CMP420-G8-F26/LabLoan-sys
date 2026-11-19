Goal ID DG-01

Design Goal
Security and Authorization

Description
The system should protect user accounts and loan information by requiring users to log in and by controlling access based on their assigned roles. Students, laboratory staff, and administrators should only be able to perform actions that they are authorized to perform.

Related Requirements
Saud's functional requirements 1 and 4 cover login and role-based access. Saud's non-functional requirement 3 requires authentication. Rachad's non-functional requirement 1 requires role-based authorization. Mohammad's non-functional requirement 2 addresses privacy.

Priority is high

Justification
The system handles personal information, equipment records, and loan approvals. Proper access control is needed to prevent unauthorized users from viewing private information or changing important records.


DG-02

Data Integrity and Reliability

Description
The system should keep equipment availability, loan requests, active loans, and return records accurate and consistent. It should also prevent incomplete or invalid loan and return transactions from being recorded as completed.

Related Requirements
Hassan's non-functional requirement 5 requires equipment status and availability to remain synchronized. Rachad's non-functional requirements 2 and 3 cover data integrity and reliability. Rachad's functional requirements 2 and 3 cover recording returns and updating equipment status.

Priority is high

Justification
Incorrect equipment or loan information could allow students to request unavailable equipment or cause staff to see the wrong loan status. Accurate and consistent records help the system work correctly.


DG-03

Design Goal
Maintainability and Modularity

Description
The system should be organized into components with clear responsibilities. Each component should be easy to update and test without unnecessarily affecting unrelated parts of the system.

Related Requirements
Saud's non-functional requirement 5 requires a modular and maintainable structure. Mohammad's non-functional requirement 4 requires major modules to be testable independently and together. Mohammad's non-functional requirement 5 addresses maintainability through version control.

Priority is high

Justification
LabLoan-sys includes user management, equipment management, loan requests, returns, and notifications. Separating these functions into components will make the project easier to manage, test, and improve.
