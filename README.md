# LRUN

LRUN is a lightweight, mobile-friendly jogging and walking tracker that runs directly in the browser. It provides live GPS location, route visualization, elapsed time, distance, pace, and locally saved activity history.

The application is entirely client-side: it has no backend, account system, database, build process, or automatic cloud synchronization. Completed activities are stored in the browser's local storage on the current device.

## Main Purpose

LRUN helps users start, monitor, pause, resume, and finish walking or running activities. It calculates approximate movement distance, displays the route on an interactive map, and generates a downloadable PNG summary of each completed activity.

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
