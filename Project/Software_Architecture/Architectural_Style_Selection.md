Selected Architectural Style is 
component based architecture

Main Characteristics
Component Based Architecture divides a software system into separate components that each handle a specific set of responsibilities. Components communicate through clearly defined interfaces instead of depending directly on the internal details of other components.

In our project, the main responsibilities include managing users and their roles, maintaining equipment records, handling loan requests and loans, processing returns, and generating reports and notifications. These responsibilities can be organized into five components with clear interfaces between them.

Why This Style Is Appropriate
The Laboratory Equipment Loan and Return System has several related functions, but each function also has its own responsibilities. For example, searching for equipment is different from approving a loan request or recording a return. Dividing these functions into components makes the system easier for the team to design, implement, and test.

The architecture also fits our Lab 5 class diagram because related classes can be grouped together without changing their original responsibilities. Each of the eleven classes in the consolidated diagram can be assigned to one main component.

How It Supports Our Design Goals

Security and Authorization
User management and role checks can be handled by a dedicated component. Other components can use its interfaces to check whether a user is allowed to perform an action. This supports DG-01 by keeping authentication and authorization responsibilities organized.

Data Integrity and Reliability
Loan requests, active loans, equipment availability, and returns must stay consistent. Clearly defined interfaces can control how components update this information and help prevent incomplete or invalid transactions. This supports DG-02.

Maintainability and Modularity
Each component can be developed, tested, and updated separately as long as its interfaces remain consistent. A change to the reporting or notification functions, for example, should not require major changes to equipment management, this supports DG-03.

Main Advantages
The system is easier to understand because each component has a clear purpose.
Members can work on different components with less interference.
Individual components can be tested and maintained more easily.
Interfaces make it easier to reuse or replace parts of the system in the future.

Potential Limitations
We must carefully define and maintain the interfaces between components.
Some actions, such as returning equipment, involve multiple components and require coordination to keep records consistent.
If the responsibilities are not clearly separated, components may become too dependent on each other.
