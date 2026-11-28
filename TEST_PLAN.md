# LRUN Manual Test Plan

Run these checks on a GPS-enabled device over HTTPS or localhost. Record actual results before submitting.

| # | Test | Expected result | Result |
|---|---|---|---|
| 1 | Allow location access, start an activity, and wait for an accurate GPS fix. | The map centers on the device, tracking is active, and valid movement updates route, distance, and elapsed time. | Not run |
| 2 | During an activity, use a location fix with accuracy worse than 50 meters. | A weak-signal message appears; that fix adds no route point or distance. | Not run |
| 3 | Pause an activity, wait, then resume it. | The timer and route stop while paused; resuming continues the same activity. | Not run |
| 4 | Deny location access when starting an activity. | An explanatory permission message appears and no route point is recorded. | Not run |
| 5 | Finish an activity and confirm saving. | The activity appears in Saved activities with its summary and route. | Not run |
| 6 | Refresh after saving an activity. | The saved activity remains available in the history. | Not run |
| 7 | Disable browser storage or provide invalid saved data, then reload. | The app reports that saved data could not be read or written rather than silently reporting success. | Not run |
