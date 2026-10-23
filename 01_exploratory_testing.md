# Section 2 — Exploratory Testing

## Scope and approach

Exploratory testing was performed in the AbleSpace staging application using the manually created test account and fictional student data. The exploration focused on core student management, calendar, data logging, accommodations, service time, and responsive usability.

Existing demo records were treated as test data. No real users were contacted. Findings below reflect behavior reported during testing; items marked “Needs confirmation” should be reproduced and supported with screenshots before being treated as confirmed defects.

## Scenarios tested

| ID | Area | Scenario and check | Result |

| EXP-01 | Student management | Create a fictional student, confirm it appears in the student list, then refresh the page and check persistence. | Pass — the created student appeared in the list and remained after refresh. |

| EXP-02 | Student management | Search for the created student by name and inspect the returned records. | Pass — matching records appeared in search. Two records with the same name had different IDs; this alone was not treated as a defect. |

| EXP-03 | Student management | Edit the fictional student, save the change, refresh, and verify the saved value. | Pass — the edited value persisted after refresh. |

| EXP-04 | Student management | Click Create repeatedly and inspect whether more than one record is created. | Fail — repeated clicks produced duplicate student records. Attach evidence and include timing/number of clicks in the final report if known. |

| EXP-05 | Calendar | Open Calendar, navigate dates, switch Month/Week/Day views, open event details, and refresh. | Pass — the reported checks worked as expected. |

| EXP-06 | Calendar | Filter the calendar by student, clear the filter, and inspect session alignment, including events at the same time. | Pass — the selected student's sessions appeared at the expected times; simultaneous events appeared as separate strips. |

| EXP-07 | Data | Search for existing and nonexistent students, use partial-name search, apply/reset filters, and refresh. | Pass — the reported table, search, filter/reset, and refresh checks worked. |

| EXP-08 | Data logging | Attempt to log data without required information, then provide the student, goal, note, and data and submit. | Pass with validation observed — the form indicated that note/data were required; submission succeeded after the required information was entered. |

| EXP-09 | Accommodations | Inspect the empty state, select/create an accommodation for a fictional student, and check the dependent Option field. | Pass for dependency behavior — “No data found” and “Create Accommodation” appeared when no accommodation was available; the Option field became enabled after an accommodation was selected. A layout concern was also reported and needs screenshot-based confirmation. |

| EXP-10 | Service Time | Apply a filter, select Student Name A–Z, and inspect alphabetical ordering. | Potential defect — “Demo Student4” appeared before “Demo Student3.” Recheck with multiple visible records and capture the selected sort setting plus result order before final classification. |

## Additional responsive observation

In Google Chrome, at mobile and tablet viewport sizes, the user reported overlap among sidebar/navigation, tables or page content, buttons or form fields, dropdowns/popups, and text/headings.

## Exploratory limitations

- Very long text and special-character boundary cases were not confirmed as tested.
- Back-navigation behavior was not confirmed as tested.
- No claim is made that every module or every validation path was tested.
- Do not create additional duplicate records merely to reproduce EXP-04. Use existing evidence or a safe, single controlled retest only if permitted.
