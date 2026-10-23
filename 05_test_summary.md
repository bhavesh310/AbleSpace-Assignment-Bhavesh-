# Section 6 — Test Summary

## Objective

Evaluate key AbleSpace staging workflows for functional correctness, validation, persistence, sorting, navigation, and responsive usability.

## Coverage

Testing covered student creation, search, edit and persistence; Calendar navigation and views; Data search/filter and data logging validation; Accommodations empty-state and dependent-field behavior; Service Time filtering and sorting; and responsive layout inspection in Google Chrome at mobile and tablet viewport sizes.

## Key findings

1. **Student creation:** Repeated clicks on Create were reported to create duplicate student records. This is the highest-priority functional finding because duplicate records can confuse users and lead to inconsistent data. Include a screenshot and exact reproduction details.
2. **Service Time sorting:** The tester observed Demo Student4 before Demo Student3 after selecting A–Z for Student Name following filtering. This finding requires a screenshot-backed retest with multiple records visible before being classified as a confirmed defect.
3. **Responsive layout:** In Chrome mobile and tablet emulation, the tester reported overlap involving navigation, content/tables, form controls, dropdowns, and text. Attach screenshots and record the viewport dimensions.
4. **Accommodations:** “No data found” and “Create Accommodation” appeared when no accommodation was available. The Option field became enabled after an accommodation was selected. This behavior was not classified as a confirmed defect.

## Positive results observed

- A fictional student was created, appeared in the list, and persisted after refresh.
- Searching for the created student worked.
- Editing a fictional student saved successfully and persisted after refresh.
- Calendar navigation, Month/Week/Day views, event details, refresh, and student filtering were reported to work.
- Data search/filter checks were reported to work.
- Data logging displayed required-field validation and succeeded after the required information was entered.
- The Accommodations Option field became enabled after selecting an accommodation.

## Limitations

- Exact mobile/tablet viewport dimensions and Chrome version were not recorded.
- Screenshots must be added to support the bug reports and responsive observations.
- Long-text and special-character boundary cases, back-navigation behavior, and exhaustive module coverage were not confirmed as tested.
- The Service Time sorting observation needs confirmation.
- The Accommodations layout concern needs clearer reproduction evidence.

## Overall assessment

Core student, Calendar, and Data workflows showed successful behavior in the checks reported. The main functional concern is duplicate student creation after repeated Create clicks. The Service Time sorting result and responsive layout overlap require evidence-backed follow-up. This report intentionally separates confirmed observations from findings that still need reproduction. The assignment should be submitted with the listed screenshots and completed environment details.
