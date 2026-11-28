# LRUN — Community Walk/Run Tracker

## Pitch

LRUN is a small browser app for recording a community member's walk or run. It uses the phone's location to draw a route and show distance and time, then saves the activity on the same device without an account.

## Problem and users

**Draft problem:** In a local community, people who walk or run for exercise may have no simple, consistent way to remember their route, distance, and duration. Paper notes are easy to forget, while a basic activity log should not require an account.

**Users:** Community members who walk or run and have a GPS-enabled phone with a modern browser.

Validate this draft with someone in your actual barangay, school, or organization and replace “a local community” with that community before submitting.

## FR-01

A community member can record a walk or run with GPS, view its route, distance, and duration, and save the activity on the device so it is still available after a page refresh.

### Acceptance criteria

1. With location permission and a usable GPS fix, starting an activity shows the route, distance, and elapsed time.
2. GPS fixes with accuracy worse than 50 meters do not add route points or distance and show a weak-signal message.
3. Pausing stops tracking and the timer; resuming continues the same activity.
4. Finishing saves the activity and route locally; the saved activity remains available after refreshing the page.
5. If location permission is denied or location is unavailable, the app explains the problem and does not invent a route.

## Architecture and limits

The app is a single `index.html` page using HTML, CSS, and vanilla JavaScript. The browser Geolocation API supplies location fixes; Leaflet and OpenStreetMap display the map; `localStorage` stores completed activity summaries and route coordinates. There is no server, login, database, or cloud sync. Location and saved activities remain on the device, while the map requires internet access.
