Component ID
CO1

Component Name
User and Access Management

Responsibilities
This component manages user accounts, login, logout, user roles, and access permissions. It keeps the information for students, laboratory staff, and administrators in one place. It supports checking whether a user is allowed to perform a protected action.

Supported Functionality
User authentication, account management, role assignment, access control, and identifying the user performing an action.

Included Classes
User
Student
LabStaff
Admin


Component ID
CO2

Component Name
Equipment and Catalog Management

Responsibilities
This component maintains equipment details, equipment conditions, equipment availability, and the searchable equipment catalog. It supplies accurate equipment information to the loan and return components.

Supported Functionality
Creating and updating equipment records, searching for equipment, viewing available items, and updating equipment condition or status when a loan or return is processed.

Included Classes
Equipment
EquipmentCatalog


Component ID
CO3

Component Name
Loan and Request Management

Responsibilities
This component manages requests to borrow equipment and the records of approved loans. It tracks the status of requests and loans, supports approval or rejection, and identifies overdue loans. It coordinates with equipment management when a checkout changes availability.

Supported Functionality
Submitting loan requests, checking request status, approving or rejecting requests, maintaining checkout records, and identifying overdue loans.

Included Classes
LoanRequest
Loan


Component ID
CO4

Component Name
Return Processing

Responsibilities
This component handles the return of borrowed equipment. It records the actual return date, checks whether the return was late, and records the condition of the equipment at return. It coordinates the final loan and equipment status changes with their owning components.

Supported Functionality
Recording returns, checking lateness, capturing returned equipment condition, and coordinating completion of a loan.

Included Classes
ReturnTransaction


Component ID
CO5

Component Name
Reporting and Notifications

Responsibilities
This component produces loan and equipment usage reports and prepares notifications related to loan decisions and overdue equipment. It obtains the necessary information from the other components without taking ownership of their records.

Supported Functionality
Generating usage and overdue reports, generating loan history reports, and preparing or sending loan notifications.

Included Classes
Report
Notification


Together these five components cover all eleven classes in the Lab 5 consolidated UML diagram. Each class has one primary component, while interactions between components will be represented using interfaces in the UML Component Diagram.
