# SaveTrack — Render-ready deployment

This package keeps the existing SaveTrack PWA and adds a tiny Node.js static-file server so it can deploy using Render's **Web Service** type.

## Render settings

Connect the GitHub repository containing these files at its root, then use:

- **Service type:** Web Service
- **Runtime:** Node
- **Root Directory:** leave blank
- **Build Command:** `npm install`
- **Start Command:** `npm start`

The project includes `package.json` and `server.js`. The server uses only built-in Node.js modules, so no extra packages are required. Render supplies the listening port through `PORT`.

## Important when updating GitHub

Extract this ZIP and upload/commit the *contents* of `SaveTrack_Render_Fixed` to the top level of the `saving-track` repository. Do not put the files inside an extra nested folder such as `SaveTrack_Mobile_PWA/` or `src/`.

Then in Render:
1. Open the existing `saving-track` Web Service.
2. Go to **Settings** and make sure **Root Directory** is blank.
3. Set Build Command to `npm install`.
4. Set Start Command to `npm start`.
5. Save changes and choose **Manual Deploy → Deploy latest commit**.

If you prefer not to replace the repository contents, you can instead set Root Directory to the folder that contains `package.json`.

## PWA installation

After deployment, open the HTTPS Render URL in Chrome (Android) or Safari (iPhone) and use the browser's install/add-to-home-screen option.

## Data note

The existing app stores data in the browser on each device. This deployment fix does not add cross-device cloud sync or a server database.


## Savings time prediction
The goal form now estimates how long a target may take based on the starting amount and a daily, weekly, or monthly recurring savings amount. It shows an approximate completion date and assumes consistent contributions with no withdrawals.

## Install on a phone
This is a mobile-friendly Progressive Web App (PWA). Deploy the project to a public HTTPS host (for example, Render using the included `render.yaml`) before installing it:
- **Android:** open the HTTPS site in Chrome, then use the browser menu → **Install app** or **Add to Home screen**.
- **iPhone:** open the HTTPS site in Safari → **Share** → **Add to Home Screen**.
The ZIP is the downloadable project package; a live HTTPS website must be deployed separately before phone installation. This package does not itself contain a signed native Android APK.


## Productivity upgrade (v1.1)
- Savings Coach view with recent deposit streaks and monthly deposit totals.
- Monthly savings challenge with progress toward a user-defined target.
- Emergency fund calculator based on essential monthly expenses, target coverage months, current amount set aside, and planned monthly contribution.
- Goal priority list highlights remaining amounts and suggested daily pace for deadlines.

These tools calculate estimates from manually recorded data on the current device. They do not connect to a bank, guarantee returns, or synchronize data across devices.
