Hassan Almarri Scenarios:
1. Student Requests Laboratory Equipment
Actor/Stakeholder: Student
Description:
1. A student checks the availability of a required laboratory equipment item.
2. The system displays the equipment as Available, Borrowed, Overdue, Damaged, or Unavailable.
3. If the item is available, the student submits a loan request.
4. The system processes and records the request.
5. The student views the request status as Pending, Approved, or Rejected.


2. Laboratory Staff Reviews Loan Requests
Actor/Stakeholder: Laboratory Staff / System
Description:
1. Laboratory staff open the list of pending equipment loan requests.
2. The system displays the pending requests for review.
3. Staff review the selected request.
4. After a decision is recorded, the system sends the student an appropriate approval or rejection notification.
5. The system keeps equipment availability and related loan information consistent with the current records.

Mohammad Nasser Ibrahim Scenarios:
Scenario 1: Equipment Search and Checkout
Actor: Student / Staff / Faculty, Laboratory Staff
Scenario: A user needs to borrow a laboratory equipment item.
1. The user searches for the required equipment using its identification number, description, or other relevant information.
2. The system displays matching equipment records, including the equipment ID, description, condition, and current status.
3. The user selects an available equipment item.
4. Laboratory Staff records the checkout information, including:
- Equipment ID
- Borrower
- Loan date
- Expected return date
5. The system checks that the entered information is valid.
6. The system records the loan and changes the equipment status from Available to Checked Out.
7. The system retains the loan and equipment-status information for future auditing.
8. Access to borrower and loan information is restricted to authorized users according to their roles.
9. If invalid information is entered or the equipment is unavailable, the system displays a clear error message.


Scenario 2: Equipment Return and Record Update
Actor: Laboratory Staff
Scenario: A borrower returns equipment that was previously checked out.
1. Laboratory Staff searches for the borrowed equipment using its equipment ID or relevant equipment information.
2. The system displays the equipment details, including its current status and loan information.
3. Staff verifies the equipment and records that it has been returned.
4. Staff enters the actual return date.
5. The system validates the return information.
6. The system updates the equipment status from Checked Out to Available.
7. The system retains the original loan information, expected return date, actual return date, and updated equipment status for auditing.
8. Authorized users can view the updated equipment condition and availability.
9. If the equipment cannot be found or invalid return information is entered, the system displays an appropriate error message.
10. The updated source code and related changes are maintained through the team's GitHub version-control repository.

Saud Alzaabi Scenarios:
Scenario 1: Viewing Loan and Return History
Actor: Student
Stakeholders: Student, Laboratory Staff, Administrator
Scenario Description:
A student logs into the system and selects the option to view loan and return history. The system verifies the student's account and displays the equipment previously borrowed, the loan dates, return dates, and current loan status. This allows the student to keep track of previous and current equipment loans.

Scenario 2: Generating Laboratory Reports
Actor: Laboratory Staff
Stakeholders: Laboratory Staff, Administrator, Faculty/Instructor
Scenario Description:
A laboratory staff member logs into the system and selects the report generation option. The staff member chooses the type of report, such as current loans, overdue equipment, loan history, return history, or equipment usage. The system collects the relevant information and generates the requested report for the authorized user to view.
