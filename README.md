# ⚡ Manhunt Live

A mobile-first, real-time GPS Manhunt game built with Vanilla JavaScript, Leaflet.js, and Firebase Realtime Database. 

Play outdoor manhunt in parks, campuses, or neighborhoods with live geofencing, proximity vibration alerts, physical QR code tagging, and a tactical split-screen map.

## ✨ What's New in the Latest Update
* **QR Code Physical Tagging:** Hiders can pull up a dynamic QR ID on their screen. Catchers use the built-in camera scanner to physically "tag" them out.
* **Instant GPS Fallback:** If a player loses high-accuracy satellite lock (e.g., walking indoors), the engine instantly falls back to standard precision to prevent freezing.
* **Auto-Generated Tactical Codes:** Hosts are automatically assigned a secure, random 4-character room code to share.
* **Developer Re-entry Fix:** Smooth session recovery for the Master Admin without triggering repetitive PIN prompts on page refresh.

## 🎮 Core Features
* **Strict Split-Screen Mobile UI:** The top half is dedicated to the tactical Leaflet map; the bottom half houses role actions, alert banners, and dual-channel comms.
* **16-Class Character Roster:** Pick your operative avatar (🥷 Ninja, 🦊 Fox, 🐺 Wolf, 👻 Ghost, 🦁 Lion, 🤖 Droid, 🦅 Falcon, ⚡ Volt, and more).
* **Catcher Threat Aura:** Catchers are marked with an animated crimson red pulse layer on the map for high visibility.
* **Screen Wake Lock:** Uses the Screen Wake Lock API to prevent mobile displays from going to sleep, ensuring uninterrupted GPS streaming.
* **Custom Geofencing:** Hosts can set fixed-radius sectors or tap points on the map to draw custom boundary polygons. Hiders stepping outside have their live location exposed.
* **Radar Scan (Force Ping):** Tactical button to reveal all player locations instantly (configurable for Catchers, All, or Disabled).
* **Proximity Haptics & Audio:** Phones physically vibrate and play a heartbeat audio cue if an opponent closes within a 50-meter radius.
* **Dual-Channel Live Chat:** Global frequency for all operatives, alongside a private, encrypted Hider-only channel.
* **Head-Start Stealth Phase:** Catchers are blinded on the map for the first few minutes while Hiders disperse.
* **Automatic Database Cleanup:** Room and GPS telemetry records are automatically purged from Firebase once the match concludes.
* **Master Admin Override:** Dedicated developer controls hardcoded for quick lobby management and zero-cooldown radar sweeps.

## 🕹️ How to Play

### 1. Creating a Match (Commander)
1. Open the game link on mobile (or desktop for setup).
2. Tap **Create Tactical Room**.
3. Enter your Name, choose your Avatar, and note the auto-generated Room Code.
4. Configure match parameters:
   - **Match Duration:** Total game length in minutes.
   - **GPS Ping Interval:** Live continuous tracking, or interval-based (30s to 5m) to save battery.
   - **Head-Start Timer:** Time Hiders remain invisible to Catchers.
   - **Boundary:** Choose a circle radius or draw a custom polygon on the map.
5. Tap **Initialize Lobby** and share the Room Code with friends.

### 2. Joining a Match (Operative)
1. Open the game link on your phone.
2. Tap **Join Active Room**.
3. Enter your Name, the Room Code, and pick an Avatar.
4. Tap **Deploy Into Lobby** to join the host.

### 3. Gameplay Mechanics
* **Hiders:** Stay inside the defined boundary. If you leave the zone, your location turns amber and alerts Catchers. When a Catcher finds you, tap **Show ID Tag** so they can scan it, or press **Surrender** to mark yourself caught.
* **Catchers:** Track down Hiders before the clock expires. Use the **Sonar Sweep** to reveal real-time positions. Tap **Scan Target** to open your camera and scan a Hider's screen to officially capture them.
* **Extraction Zone:** In the final 3 minutes, a green extraction zone may spawn. Hiders must reach it and hold it for 30 seconds to win early!

## 🛠️ Tech Stack
* **Frontend:** Vanilla HTML5, CSS3, JavaScript (ES6 Modules)
* **Maps:** Leaflet.js with customized OpenStreetMap dark tiles
* **Backend:** Firebase Realtime Database
* **Device APIs:** Geolocation API, DeviceOrientation (Compass), Screen Wake Lock API, Web Audio API, Vibration API, HTML5-QRCode

## 🚀 Setup & Installation (For Developers)
Because this is entirely client-side, setup is incredibly simple:
1. Fork or clone this repository.
2. Create a free project on [Firebase](https://firebase.google.com/).
3. Enable **Realtime Database** and set the security rules to allow read/write for your testing (or set up anonymous auth).
4. Paste your Firebase configuration object into the designated `firebaseConfig` block inside the `index.html` file.
5. Host the `index.html` file on any static hosting service (GitHub Pages, Vercel, Netlify). *Note: HTTPS is strictly required for mobile browsers to allow GPS and Camera access.*

## ⚠️ Player Safety Guidelines
* Stay mindful of real-world surroundings at all times.
* Do not cross active vehicle roads, railways, or enter private/restricted properties.
* Avoid sprinting in poorly lit areas or rough terrain during nighttime matches.
* **Look up from your screen while moving!**
