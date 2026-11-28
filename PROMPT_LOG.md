# AI Prompt Log

This file records the AI prompts and requests used while developing **LRUN – Community Walk/Run Tracker**. Each prompt includes the AI-assisted work and the review or testing performed.

| # | Prompt / Request | AI-Assisted Work | Review or Test |
|---|---|---|---|
| 1 | "Find and fix an issue related to GPS." | Updated the GPS tracking flow so the Pause control becomes available after receiving a location fix. Improved the status text to reflect GPS signal quality. | Reviewed the code changes and checked that the whitespace check passed. |
| 2 | Adapt the existing GPS tracker to meet the Lab 1 community web app assignment requirements. | Helped define LRUN's community problem, FR-01 requirement, acceptance criteria, project brief, and manual test plan. Added an in-app community tracker description. | Reviewed the project documentation and tested the seven manual test cases listed in `TEST_PLAN.md`. All seven were reported as PASS. |
| 3 | "Add an Activity Type Filter to the existing Saved Activities section, with All Activities, Walking, and Running options. Use the existing savedActivities list and rendering logic. Do not modify LocalStorage records or break existing features." | Added filter controls to `index.html` so users can display all saved activities, walking activities only, or running activities only. | Browser testing verified that each filter displayed the expected activities, selecting All restored both types, and filtering did not change the stored LocalStorage value. Temporary test data was restored afterward. |

## Development Notes

- AI-generated code was reviewed before being accepted.
- Manual and browser testing were performed to check the application's functionality.
- The project uses HTML, CSS, JavaScript, browser LocalStorage, and the Geolocation API.
- No real personal information was used during testing.

**Project:** LRUN – Community Walk/Run Tracker  
**Community:** Ipil, Zamboanga Sibugay, Philippines
