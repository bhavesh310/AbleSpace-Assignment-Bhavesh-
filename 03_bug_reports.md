# Section 4 — Bug Reports

## BUG-01 — Repeated Create clicks create duplicate student records

**Module:** Caseload / Students  
**Severity:** Medium  
**Priority:** High  
**Status:** Observed

### Preconditions
The user is authenticated and can open the Add Student form.

### Steps to reproduce
1. Open Caseload/Students.
2. Select Add Student.
3. Enter valid required information for a unique fictional student.
4. Click Create repeatedly in quick succession, matching the observed interaction.
5. Return to the student list and search for the submitted name.
6. Compare the number of matching records and their IDs.

### Expected result
A single form submission creates exactly one student record. While the request is processing, repeated clicks should not submit duplicate create requests.

### Actual result
Repeated Create clicks were reported to create duplicate student records.

### Impact
Duplicate records can clutter the student list, create ambiguity for staff, and cause downstream work to be associated with the wrong record.


The screenshot should show the duplicate matching rows and, if available, their distinct record IDs. If no screenshot exists, perform one safe retest only if permitted and record the exact number of clicks and records. Do not create more duplicates unnecessarily.

### Suggested fix
Disable the Create button while the submission is in progress and make the server-side create operation resilient to duplicate submissions. Show one success message after the request completes.

---

## BUG-02 — Student Name A–Z sort appears incorrect after filtering

**Module:** Service Time  
**Severity:** Medium  
**Priority:** Medium  
**Status:** Needs confirmation.

### Preconditions
The filtered result contains at least two student records.

### Steps to reproduce
1. Open Service Time.
2. Apply a filter in the search section.
3. Select A–Z for Student Name.
4. Inspect the displayed order.
5. Clear the filter and repeat the sort.

### Expected result
Student names appear in ascending alphabetical order after filtering.

### Actual result
The tester reported that “Demo Student4” appeared before “Demo Student3” after filtering and selecting A–Z.

### Impact
Incorrect ordering can make records harder to locate and reduce confidence in the sorting controls.

Capture the selected filter, the A–Z setting, and at least two visible names in their displayed order.

### Classification note
Do not mark this as a confirmed defect until the order is reproduced with multiple visible records. If the names are not literal names in the application, document the exact displayed values.

---

## ACC-OBS-01 — Accommodations selection and empty state

**Module:** Accommodations  
**Severity/Priority:** Not assigned — insufficient evidence for a defect.

### Observed behavior
When no accommodation is available, the selection field displays “No data found” and “Create Accommodation.” The required Option field becomes enabled after an accommodation is selected.

### Assessment
The dependent-field behavior appears consistent with a field that requires a prior selection. The empty state may be intentional. Do not report the disabled Option field itself as a bug.

### Follow-up observation
A layout concern was described around the accommodation selection area, but the precise overlap and its effect on selecting options were not established clearly enough to write a reproducible defect.


