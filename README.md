# LRUN

LRUN is a one-page, mobile-friendly community walking and running tracker. Its core feature is recording an outing with GPS, showing the route and activity stats, then saving the activity in the browser.

The application is entirely client-side: it has no backend, account system, database, build process, or automatic cloud synchronization. Completed activities are stored in the browser's local storage on the current device.

## Community Problem and FR-01

**Draft problem statement:** In a local community, people who walk or run for exercise can struggle to keep a consistent record of their route, distance, and time because notes are easy to forget and they may not want to create an account for a basic activity log. A simple web page that records an outing with the phone's GPS and saves it on the device would help.

**FR-01:** A community member can record a walk or run with GPS, view its route, distance, and duration, and save the activity on the device so it is still available after a page refresh.

The community wording is a draft. Replace it with your actual barangay, school, or organization and validate the need with a community member or classmate before submitting.

### Acceptance criteria

1. With location permission and a usable GPS fix, starting an activity shows the route, distance, and elapsed time.
2. GPS fixes with accuracy worse than 50 meters do not add a route point or distance and show a weak-signal message.
3. Pausing stops tracking and the timer; resuming continues the same activity.
4. Finishing an activity saves its summary and route locally, and the saved activity remains available after refreshing the page.
5. Denied or unavailable location access shows an explanatory message instead of recording a fabricated route.

See [PROJECT_BRIEF.md](PROJECT_BRIEF.md) for the pitch, users, and architecture, and [TEST_PLAN.md](TEST_PLAN.md) for a manual test table.

## Main Feature

LRUN supports the FR-01 workflow: start, pause, resume, and finish one walk or run; view its GPS route and stats; and keep completed activities in local storage. Map, direction, and activity-summary controls support that workflow.

## Key Features

- Run and walk activity modes
- Live GPS location and interactive route map
- Distance, elapsed time, pace, and GPS accuracy indicators
- Device direction support using GPS movement or compass data
- Start, pause, resume, and finish controls
- Confirmation and custom naming prompts for saved activities
- Saved activity history with rename and view actions
- Route summary cards displayed in-browser and downloadable as PNG images
- Responsive intro and activity screens for mobile, tablet, and desktop devices
- Browser-local data storage with no account or server required

## Technologies Used

- HTML5
- CSS3
- Vanilla JavaScript
- Web Geolocation API
- Device Orientation API
- HTML Canvas API
- Browser Local Storage
- [Leaflet](https://leafletjs.com/) 1.9.4
- [OpenStreetMap](https://www.openstreetmap.org/) map tiles

No JavaScript package manager or build tool is currently required.

## Project Structure

```text
LRUN/
├── index.html       # Application markup, styles, and tracking logic
├── lrun-logo.png    # LRUN logo displayed by the intro screen
├── README.md        # Project documentation
├── PROJECT_BRIEF.md # One-page project brief
├── PROMPT_LOG.md    # AI-use log
├── TEST_PLAN.md     # Manual acceptance test table
└── .gitignore       # Files and folders excluded from Git
```

The `lrun-logo.png` file must remain in the project root beside `index.html` because the page uses a relative image path.

## Prerequisites

- A modern browser with location support
- An internet connection for Leaflet assets and OpenStreetMap map tiles
- A local web server for development and testing

Browser location access is most reliable over HTTPS or localhost. Opening `index.html` directly with a `file://` URL may prevent GPS access or restrict browser storage.

## Installation

1. Clone the repository:

   ```powershell
   git clone https://github.com/lloydtagob16-cmd/Lrun.git
   cd Lrun
   ```

2. Keep `index.html` and `lrun-logo.png` together in the project root.

No dependency installation or build step is required.

## Run Locally

### Using Python

If Python is installed, run:

```powershell
python -m http.server 8000
```

Open `http://localhost:8000` in a browser.

### Using VS Code

1. Open the project folder in VS Code.
2. Install the Live Server extension, if it is not already available.
3. Select **Go Live** or open `index.html` with Live Server.
4. Allow location access when prompted.

## How to Use

1. Open LRUN and allow location access.
2. Select **Run** or **Walk**.
3. Select **Start activity** and keep the device with you while moving.
4. Use **Pause** and **Resume** when needed.
5. Select **Finish** and confirm that the activity should be saved.
6. Enter a name for the activity or use the generated default name.
7. Open **Saved activities** to view, rename, or download a summary image.

GPS readings vary by device and environment. LRUN ignores location fixes with accuracy worse than 50 meters and filters very small movements and likely large jumps before calculating route distance.

## Saved Data and Privacy

Completed activities, including route coordinates and summary details, are stored in the browser's local storage. Data is device- and browser-specific and is not uploaded to an LRUN server or synchronized between devices.

The application requests map tiles from OpenStreetMap and loads Leaflet from unpkg. The app itself does not send saved activity data to those services.

Clearing browser site data will remove saved activities. The app may not retain data when private browsing or strict browser storage settings are used.

## Deployment

The project can be hosted as a static site, including with GitHub Pages.

1. Push `index.html`, `lrun-logo.png`, `README.md`, and `.gitignore` to the repository.
2. On GitHub, open **Settings** > **Pages**.
3. Under **Build and deployment**, select **Deploy from a branch**.
4. Choose the desired branch and the repository root folder.
5. Save the settings and wait for the deployment to finish.
6. Open the HTTPS URL shown in the Pages settings.

HTTPS is recommended for GPS permissions on phones. GPS tracking also requires an internet connection for the map library and map tiles.

## Customization

- Edit the `<style>` section in `index.html` to change colors, spacing, or responsive layout.
- Edit the page markup to change labels and controls.
- Edit the JavaScript in `index.html` to adjust tracking, filtering, storage, or summary behavior.
- Replace `lrun-logo.png` with another logo using the same file name, or update its relative image path.

## Limitations

- Activity data is available only in the browser on which it was saved.
- There is no account, backend, cloud backup, or cross-device synchronization.
- Distance and route accuracy depend on the device GPS and its surroundings.
- Compass permission and orientation behavior vary by browser and operating system.
- Map tiles require internet access and are supplied by OpenStreetMap.
