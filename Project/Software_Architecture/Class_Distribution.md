Component Distribution Table

ID   Component Name                      Responsibilities                        Included Classes
CO1  User and Access Management          Accounts, authentication and roles      User, Student, LabStaff, Admin
CO2  Equipment and Catalog Management    Equipment details, search and status    Equipment, EquipmentCatalog
CO3  Loan and Request Management         Requests, approvals and active loans    LoanRequest, Loan
CO4  Return Processing                   Equipment returns and late checks       ReturnTransaction
CO5  Reporting and Notifications         Usage reports and loan notifications    Report, Notification


Class Assignment Details

CO1
User
Student
LabStaff
Admin

These classes belong together because Student, LabStaff, and Admin are specialized types of User. The component owns account and role information. Actions involving other parts of the system will be coordinated through interfaces.

CO2
Equipment
EquipmentCatalog

These classes belong together because Equipment stores item details and status, while EquipmentCatalog provides search and listing functions for those items.

CO3
LoanRequest
Loan

These classes belong together because LoanRequest represents a request awaiting a decision, while Loan represents the actual checkout record after an approved request becomes a loan. The classes remain separate because a request does not always result in a loan.

CO4
ReturnTransaction

This class is responsible for recording a return and checking whether it was late. It interacts with Loan and Equipment through their components, rather than taking ownership of those classes.

CO5
Report
Notification

These classes provide supporting services to the rest of the system. Report generates usage and loan history information. Notification prepares and sends messages for loan events and reminders.


Distribution Check

Number of components
5

Number of distinct assigned classes
11

Classes assigned to more than one primary component
None

Classes left unassigned
None

LoanRecord is not counted as a separate class because the Lab 5 inventory states that it was merged into Loan. This distribution follows the eleven classes shown in the consolidated Lab 5 UML Class Diagram.
