# LRUN

LRUN is a lightweight, mobile-friendly jogging and walking tracker. It is a static web app made with HTML, CSS, and JavaScript; there is no server or build step included.

## Recomended 

Use mobile phone

## Features

- Live map and GPS location
- Run and Walk activity modes
- Distance, elapsed time, pace, GPS accuracy, and direction
- Pause, resume, and finish controls
- Locally saved activity history with rename and date/time details
- Activity summary image with the route, available to view and download
- Intro screen and responsive phone, tablet, and desktop layouts

## Project files

- `index.html` — app layout, styles, and tracking logic
- `lrun-logo.png` — LRUN logo used by the intro screen

Keep the logo in the same folder as `index.html`; the page loads it using a relative path.

## Run it locally (optional)

GPS access generally requires a secure context. `localhost` is treated as secure by modern browsers, but opening `index.html` directly as a `file://` URL may prevent location access.

1. Open the project folder in VS Code.
2. Start a local web server, for example with the **Live Server** extension and its **Go Live** command.
3. Open the local site in your browser and allow location access.

Alternatively, if Python is installed, open a terminal in the project folder and run:

```powershell
python -m http.server 8000
```

Then open `http://localhost:8000`.

## Use the tracker

1. Open LRUN and allow location access when prompted. The map will try to show your current location.
2. Tap the activity selector to choose **Run** or **Walk**.
3. Tap **Start activity** and keep your phone with you while moving.
4. Use **Pause** and **Resume** as needed; tap **Finish** to save the activity.
5. In **Saved activities**, use **Rename** to change its name or **View** to open its summary image. Use **Save image** to download the summary.

GPS distance is approximate. LRUN ignores location fixes with accuracy worse than 50 m and filters very small movements and large jumps when calculating distance. Direction depends on the phone's compass or GPS movement data; compass permission may be requested on some phones.

## Save data and privacy

Completed activities, including route points, are saved in the current browser's local storage on that device. They are not synced to an account or backed up to a LRUN server. Clearing the browser's site data can delete them. The app itself does not upload saved activities, but it does request map tiles from OpenStreetMap and loads Leaflet from a CDN to display the map.

## Deploy and open with GitHub Pages

1. Push `index.html` and `lrun-logo.png` to the root of your GitHub repository. Keep both files together so the logo loads correctly.
2. In the repository on GitHub, open **Settings** > **Pages**.
3. Under **Build and deployment**, choose **Deploy from a branch**.
4. Choose the branch you use (usually `main`) and the `/(root)` folder, then select **Save**.
5. Wait for the Pages deployment to finish. Open the published URL shown in **Settings** > **Pages**; a project site usually looks like `https://<username>.github.io/<repository>/`.

Open that HTTPS URL on your phone and allow location access when prompted. GitHub Pages supplies HTTPS, which is required for phone GPS permissions. Keep an internet connection available for the map library and map tiles.

There is no backend, user account, cloud sync, or automatic Strava integration.

## Customize the app

- Edit the `<style>` section in `index.html` to change layout, colors, or responsive behavior.
- Edit the page markup to change labels and controls.
- Edit the JavaScript near the end of `index.html` to change tracking, distance, storage, or summary-card behavior.
- Replace `lrun-logo.png` with another image using the same filename, or update the relative image path in the page.
