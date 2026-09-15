# Software Process Model

## 1. Selected Software Process Model

For our project we selected the **Incremental Model**.

The Incremental Model develops the system in smaller parts called increments and each increment adds new functionality to the system and can be tested before moving to the next part.

We selected this model because our system has several different features that can be developed separately for example: we can first develop the user and equipment management features then add the loan and return features and finally add notifications and reports.

## 2. Why We Selected the Incremental Model

The Incremental Model is suitable for our project for several reasons.

1. It allows us to build a working version of the system early So we do not need to wait until every feature is completed before having something that works.

2. Our system can be divided into different parts. Equipment management, loan requests, returns and reports can be developed as separate increments.

3. Testing can be done after each increment. This makes it easier to find and fix problems before they affect the whole system.

4. Another reason is that feedback can be added during development. If laboratory staff or students suggest changes after seeing an early version, we can consider those changes in the next increment.

## 3. Planned Increments

### Increment 1 - User and Equipment Management

- User login
- User roles
- User information
- Adding equipment
- Updating equipment
- Viewing equipment
- Equipment status

### Increment 2 - Equipment Availability and Loan Requests

- Searching for equipment
- Checking equipment availability
- Submitting loan requests
- Viewing loan request status

### Increment 3 - Approval, Checkout and Return

- Approving or rejecting loan requests
- Recording equipment checkout
- Recording expected return dates
- Recording equipment returns
- Updating equipment status
- Recording equipment condition

### Increment 4 - Notifications and Overdue Tracking

- Overdue equipment tracking
- Return reminders
- Loan approval notifications
- Loan rejection notifications

### Increment 5 - Reports and Final Improvements

- Basic reports
- Loan history
- Return history
- Equipment usage information
- Final testing
- Bug fixing
- Final improvements

## 4. Overheads of the Incremental Model

Although the Incremental Model has benefits, it also has some overheads. One overhead is that the team needs to plan how the system will be divided into increments. If the increments are not planned properly, some features may depend on features that have not been developed yet.

Another overhead is repeated testing. Every time a new increment is added, we need to make sure that the new features work and that they did not break features from previous increments. There can also be additional integration work because the different increments need to work together as one system not as seperate systems.

### How We Will Manage These Overheads

- Plan the increments before starting development
- Define the main system structure early
- Use GitHub for version control
- Test each increment before moving to the next one
- Perform integration testing regularly
- Communicate between team members about changes to the system
- Keep the database structure organized

## 5. Drawbacks of the Incremental Model

One drawback is that changes made to an earlier increment may affect later increments. This can create additional work for the team.

Another drawback is that the system requires good planning between increments. If the team does not define the boundaries of each increment clearly, development can become confusing. There is also a possibility of spending more time on testing because previous functionality needs to be tested again when new features are added.

### How We Will Address These Drawbacks

We will try to reduce these problems by keeping the project scope clear and prioritizing the most important features first. The team will also use GitHub to keep track of changes and make it easier to work together. Each increment will be tested before moving forward, and we will perform regression testing after adding important new features.

If we have limited time, we will focus on the core functions of the system such as equipment management, loan requests and equipment returns before working on optional features.

## 6. Conclusion

To sum up we believe the Incremental Model is a good choice for the Laboratory Equipment Loan and Return System because the system can be divided into smaller functional parts. It allows us to develop and test the system step by step while also giving us the ability to improve the system during development.

The main overheads and drawbacks are additional planning, integration and repeated testing. We will manage these issues through clear planning, communication, GitHub version control and regular testing.
