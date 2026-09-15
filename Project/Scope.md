# Project Scope

## Objective

The objective of the Laboratory Equipment Loan and Return System is to develop a centralized system for managing the borrowing and returning of laboratory equipment.

The system aims to improve the current equipment-loan process by providing a clear way to record equipment and check its availability and submit and manage loan requests and record equipment checkout and return, and monitor the condition and status of equipment.

The system should to reduce manual record keeping and improve the accuracy of lab equipment loan information and also provide better visibility of equipment usage for students and lab staff.


## Target Users

1. Students: the students will use the system to:
- View available lab equipment
- Check equipment information and availability
- Submit equipment loan requests
- View the status of their requests
- View their active and previous loans
- Return borrowed equipment through the lab's return process

2. Laboratory Technicians/Staff: the lab staff will use the system to:
- Manage lab equipment records
- View equipment availability
- Review and process loan requests
- Record equipment checkout
- Record equipment returns
- Update equipment condition and status
- Monitor overdue equipment

3. Laboratory Administrators: the administrators will use the system to:
- Manage users and user roles
- Manage equipment records
- Monitor loan and return activities
- View system reports
- Maintain the overall equipment inventory information

4. Faculty/Instructors: the faculty/instructors may use the system to:
- Monitor equipment usage where required
- View relevant loan information
- Support the management of equipment used for lab activities


## In-Scope Features

1. User Management
- User login and logout
- User authentication
- User roles and permissions
- Management of student and staff accounts
- Access to functions based on the user's role

2 Equipment Management
- Add lab equipment to the system
- Update equipment information
- Deactivate equipment records when equipment is no longer available
- Assign a unique identification number to equipment
- Store basic equipment information
- Record equipment condition and status

3 Equipment Search and Availability
- Search for lab equipment
- View equipment details
- Check equipment is available
- Display equipment status such as available, borrowed, overdue, damaged, or unavailable.

4 Loan Request Management
- Students can submit equipment loan requests
- Staff can view pending loan requests
- Staff can approve or reject loan requests
- The system records the borrower and relevant loan information
- Users can view the status of their loan requests

5 Equipment Checkout
- Record when equipment is issued to a borrower
- Record the borrower associated with the equipment
- Record the loan date
- Record the expected return date
- Update equipment availability after checkout

6 Equipment Return
- Record returned equipment
- Record the actual return date
- Update the equipment status after return
- Record the condition of equipment when it is returned
- Identify equipment that is overdue

7 Notifications
- Notify users when a loan request is approved or rejected
- Provide reminders related to expected return dates
- Notify users about overdue equipment

8 Reporting: The system will provide basic reports such as:
- Currently borrowed equipment
- Overdue equipment
- Equipment loan history
- Equipment return history
- Equipment usage information

## Out-of-Scope Features

Hardware-Based Tracking
- GPS tracking of equipment
- Development of specialized tracking hardware

Financial Functions
- Online payment processing
- Automatic collection of fines or replacement costs
- Integration with university financial systems

Equipment Purchasing
- Purchasing new lab equipment
- Supplier management
- Purchase-order management

External System Integration
- Integration with external lab inventory systems

Advanced Applications
- A separate native Android/iOS application
- AI-based predictive maintenance
- Automated physical inspection of equipment


## Major Requirements

1. The system shall allow authorized users to log in
2. The system shall provide different access permissions based on user roles
3. The system shall maintain records of lab equipment
4. The system shall allow users to search for equipment
5. The system shall display equipment availability and status
6. The system shall allow students to submit loan requests
7. The system shall allow authorized staff to approve or reject loan requests
8. The system shall record equipment checkout
9. The system shall record equipment returns
10. The system shall record the condition of returned equipment
11. The system shall identify overdue equipment
12. The system shall provide relevant notifications
13. The system shall maintain loan and return history
14. The system shall provide basic equipment and loan reports
15. The system shall restrict management functions to authorized users


## Major Deliverables

1. Working Laboratory Equipment Loan and Return System
- A functional system implementing the defined project scope.

2. User Management Module
- Authentication, user accounts, and role-based access.

3. Equipment Management Module
- Equipment records, status, condition, search, and availability.

4. Loan Management Module
- Loan requests, approval/rejection, and checkout records.

5. Return Management Module
- Return records, return dates, and equipment condition.

6. Notification Functionality
- Loan-status and overdue notifications.

7. Reporting Functionality
- Basic equipment and loan reports.

8. Database
- Storage for users, equipment, loan requests, loans, returns, and relevant system records.

9. System Documentation
- Documentation describing the system and its functionality.

10. Testing Documentation
- Test cases, testing results, and identified issues.

11. Source Code
- Complete project source code maintained in the team's GitHub repository.

12. Final Prototype/Demonstration
- A demonstrable version of the completed system.


## Scope Boundaries

The project focuses specifically on managing laboratory equipment loans and returns. The system covers the software processes involved in identifying equipment and checking availability and requesting equipment and approving requests and recording checkout and recording returns and monitoring equipment status, and maintaining loan records.

The project does not attempt to physically track equipment, purchase equipment, collect payments, or automatically inspect equipment.