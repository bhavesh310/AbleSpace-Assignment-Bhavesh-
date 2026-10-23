# Section 3 — Detailed Manual Test Cases

## Test environment and conventions

- Application: AbleSpace staging environment
- Account: manually created test account
- Test data: fictional student data and existing demo records
- Statuses: Pass, Fail, or Needs confirmation, based on reported observations

### TC-01 — Create a student and verify persistence

**Priority:** High  
**Preconditions:** Logged in; Student/Caseload page accessible.  
**Test data:** Fictional first and last name; fill required fields only as needed.

**Steps**
1. Open Caseload/Students.
2. Select Add Student.
3. Enter a unique fictional first name and last name.
4. Complete any other required fields.
5. Select Create once.
6. Confirm the student appears in the list.
7. Refresh the page.
8. Search for the created student.

**Expected result**
- The form accepts valid required information.
- One student record is created.
- The record appears in the list and remains searchable after refresh.

**Actual result**
- Student creation, list display, search, and persistence after refresh were reported as successful.

**Status:** Pass

### TC-02 — Search for a student

**Priority:** High  
**Preconditions:** At least one known student record exists.  
**Test data:** A unique or known student name.

**Steps**
1. Open the Students list.
2. Enter the known student name in search.
3. Inspect the returned rows.
4. Replace the query with a name that does not exist.
5. Try a partial-name query.

**Expected result**
- Matching records are displayed for a valid query.
- A nonexistent query returns no matching records without showing unrelated students.
- Partial-name behavior is consistent with the search implementation.

**Actual result**
- Search for the created student and partial-name search were reported to work; the nonexistent-query check was also reported as working.

**Status:** Pass

### TC-03 — Edit a student and verify persistence

**Priority:** High  
**Preconditions:** A fictional test student exists.  
**Test data:** Change one non-sensitive field on the fictional record.

**Steps**
1. Find the fictional student.
2. Open the edit form.
3. Change one field.
4. Save the edit.
5. Reopen the student or inspect the list.
6. Refresh and verify the changed value.

**Expected result**
- The save operation completes successfully.
- The changed value remains after refresh.

**Actual result**
- The edit saved and the changed value persisted after refresh.

**Status:** Pass

### TC-04 — Prevent duplicate student creation from repeated Create clicks

**Priority:** High  
**Preconditions:** Student creation form is available.  
**Test data:** A unique fictional student name that has not already been used.

**Steps**
1. Open Add Student.
2. Enter valid required information for a unique fictional student.
3. Select Create repeatedly in quick succession, as occurred during the observed test.
4. Return to the student list.
5. Search for the submitted name and compare record IDs/count.

**Expected result**
- One submission creates one record.
- The Create action becomes disabled or subsequent clicks are safely ignored while the request is processing.
- The user receives one clear success result.

**Actual result**
- Repeated clicks were reported to create duplicate records.

**Status:** Fail — attach evidence. If the exact click timing and record count were not recorded, capture those details during a safe retest rather than inventing them.

### TC-05 — Calendar navigation and view changes

**Priority:** Medium  
**Preconditions:** Calendar page accessible.  
**Steps**
1. Open Calendar.
2. Navigate to another date or period.
3. Switch among Month, Week, and Day views.
4. Open an event detail.
5. Refresh the page.

**Expected result**
- Navigation and view controls respond.
- Events and empty states display without an application error.
- Event details open.
- Refresh does not break the calendar.

**Actual result**
- These checks were reported as working, including event details and refresh.

**Status:** Pass

### TC-06 — Validate required fields when logging data

**Priority:** High  
**Preconditions:** A student and an applicable goal are available.  
**Steps**
1. Open the Data workflow and start logging data.
2. Leave required note/data information incomplete.
3. Observe validation feedback.
4. Enter the student, goal, note, and data.
5. Submit once.
6. Confirm the log appears or the workflow reports success.

**Expected result**
- Missing required fields are identified clearly.
- The incomplete form cannot be submitted.
- With required fields completed, the data log is saved and visible.

**Actual result**
- A validation message indicated that note and data were required. The log succeeded after the student, goal, note, and data were provided.

**Status:** Pass for the observed validation and successful submission

### TC-07 — Verify Service Time A–Z sort after filtering

**Priority:** Medium  
**Preconditions:** Service Time contains at least two student records visible after filtering.  
**Steps**
1. Open Service Time.
2. Apply a search/filter that leaves multiple records visible.
3. Select A–Z for Student Name.
4. Compare the displayed names in order.
5. Clear the filter and repeat once.

**Expected result**
- Student names appear in ascending alphabetical order for the selected field.
- Filtering and sorting work together without reversing or scrambling the order.

**Actual result**
- “Demo Student4” was observed before “Demo Student3” after filtering and selecting A–Z.

**Status:** Needs confirmation — repeat with multiple visible records and attach a screenshot of the sort selection and resulting order. If reproduced, mark Fail.
