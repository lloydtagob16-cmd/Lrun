# LRUN – Manual Test Plan

**Project:** LRUN – Community Walk/Run Tracker  
**Community:** Ipil, Zamboanga Sibugay, Philippines  
**Requirement:** FR-01  
**Testing Type:** Manual Functional Testing

## 1. Test Results

| ID | Test Case | Expected Result | Actual Result | Status |
|---|---|---|---|---|
| TC-01 | Start GPS tracking | GPS tracking starts and displays activity information | GPS tracking started successfully | PASS |
| TC-02 | Reject GPS accuracy worse than 50 meters | Weak GPS readings are rejected | Inaccurate GPS readings were rejected | PASS |
| TC-03 | Pause and resume activity | Activity pauses and resumes correctly | Pause and resume worked correctly | PASS |
| TC-04 | Deny GPS permission | Application displays an appropriate error message | GPS permission error message displayed | PASS |
| TC-05 | Finish and save activity | Activity summary is saved successfully | Activity was finished and saved successfully | PASS |
| TC-06 | Refresh and retain saved activities | Saved activities remain available after refreshing | Saved activities remained after refresh | PASS |
| TC-07 | Handle invalid or unavailable LocalStorage | Application handles storage errors appropriately | Storage error handling worked as expected | PASS |

## 2. Testing Summary

- Total test cases: 7
- Tests executed: 7
- Tests passed: 7
- Tests failed: 0
- Pass rate: 100%

## 3. Testing Environment

- Browser: Google Chrome
- Application: LRUN Community Walk/Run Tracker
- Storage: Browser LocalStorage
- Technologies: HTML, CSS, JavaScript
- Test data: Demonstration data only

## 4. Conclusion

All seven manual test cases for the LRUN Community Walk/Run Tracker passed during testing.

The application successfully demonstrated its main functionality, including GPS activity tracking, GPS accuracy validation, pause and resume controls, activity saving, and LocalStorage persistence.

The results indicate that the tested features meet their expected behavior for the FR-01 requirement.

All testing was performed using demonstration data without real personal information.
