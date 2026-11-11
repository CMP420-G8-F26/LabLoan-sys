Description of the 3 UML UC Activity Diagrams
UC08, Submit Loan Request
Primary actor is Student

The student chooses the equipment and the requested loan dates, then submits the loan request. The system searches the equipment catalog for the selected equipment. If the equipment is found, the system creates a temporary loan request and checks that the requested dates are valid. If the dates are valid, the system checks whether the equipment is available during that date range.

If all checks succeed, the system saves the request with the status Pending and returns the request details and status. The student then sees the confirmation. If the equipment cannot be found, the dates are invalid, or the equipment is unavailable, the system displays the appropriate failure message and does not save the request.

This workflow uses decisions for equipment lookup, date validation, and equipment availability. The checks are performed in sequence, so no fork or join is needed.

UC11, Approve Loan Request
Primary actor are Lab Staff or Technician

The staff member opens the list of pending loan requests, selects a request, reviews its details, and chooses to approve it. The system checks whether the request is still Pending and whether the requested equipment is available. These two checks can be completed independently before the approval decision.

If the request is Pending and the equipment is available, the system approves the request, changes its status to Approved, and reserves the equipment by marking it Unavailable for other loans. If approval notifications are enabled, the system creates and sends a notification to the student. The staff member then sees the approval confirmation.

If the request is not Pending or the equipment is unavailable, the system denies the approval, leaves the records unchanged, and displays the reason to the staff member. Approval does not mean that equipment has been physically checked out; checkout is handled by a separate use case.

UC15, Record Equipment Return
Primary actor are Lab Staff or Technician

The staff member looks up the active loan for the returned equipment. If an active loan is found, the staff member enters the actual return date, inspects the equipment, and records its condition and any relevant notes. The system validates the return date and recorded condition. It also checks whether the return was late and whether the required notes are present for damaged equipment. These checks are combined before the return is accepted.

If the return information is valid, the system creates and processes a return transaction, completes the loan, and records its status as Returned. The system updates the equipment condition based on the inspection. Equipment returned in good condition becomes Available. Damaged equipment is recorded as Damaged and is not treated as available for borrowing. The system saves the return information and late status and shows a confirmation to the staff member.

If no active loan is found or the return details are invalid, the system displays an error and does not complete the return.
