# ⚡ Manhunt Live

A mobile-first, real-time GPS Manhunt game built with Vanilla JavaScript, Leaflet.js, and Firebase Realtime Database. 

Play outdoor manhunt in parks, campuses, or neighborhoods with live geofencing, proximity vibration alerts, and split-screen tactical maps.

---

## 🎮 Features

* **Strict 50/50 Mobile Interface:** Top 50% dedicated to tactical Leaflet mapping; bottom 50% houses role actions, alert banners, and communications.
* **Character Roster:** Select your avatar (🥷 Ninja, 🦊 Fox, 🐺 Wolf, 👻 Ghost, 🦁 Lion, 🤖 Robot, 🦅 Eagle, ⚡ Bolt).
* **Catcher Threat Aura:** Catchers are marked with an animated crimson red pulse layer on the map for high visibility.
* **Screen Wake Lock:** Uses the Screen Wake Lock API to prevent mobile displays from turning off, ensuring uninterrupted GPS streaming during matches.
* **Custom Geofencing:** Hosts can draw custom boundary polygons or set fixed radius circles. Hiders stepping outside have their live location exposed.
* **Radar Scan (Force Ping):** Tactical button to reveal all player locations instantly (configurable for Catchers, All, or Off).
* **Proximity Haptics:** Phones physically vibrate if an opponent closes in within 50 meters.
* **Dual-Channel Live Chat:** Global frequency for all players, alongside a private, secure hider-only channel.
* **Head-Start Stealth Phase:** Catchers are blinded for the first few minutes while Hiders disperse.
* **Automatic Database Cleanup:** Room and GPS location records are automatically deleted from Firebase once the game concludes.
* **Master Admin Override:** Dedicated developer controls hardcoded for **Vivek**.

---

## 🕹️ How to Play

### 1. Creating a Match (Host)
1. Open the game link on mobile or desktop.
2. Tap **Create Room**.
3. Enter your Name, choose your Character, and type a unique Room Code.
4. Configure match parameters:
   * **Game Duration:** Match length in minutes.
   * **GPS Ping Interval:** Live continuous tracking, or timed intervals (30s to 5m).
   * **Head-Start Timer:** Time Hiders remain invisible to Catchers.
   * **Boundary:** Choose circle radius or tap points on the setup map to trace a custom perimeter.
5. Tap **Launch Room** and share your Room Code with friends.

### 2. Joining a Match
1. Open the game link.
2. Tap **Join Room**.
3. Enter your Name, Room Code, select your Role (Hider / Catcher), and pick an Avatar.
4. Tap **Enter Match** to join the host's lobby.

### 3. Gameplay Mechanics
* **Hiders:** Stay inside the defined boundary. If you leave the zone, your location turns amber and alerts all catchers. If tagged, press **I'm Caught**.
* **Catchers:** Track down Hiders before time expires. Use **Radar Scan** to reveal real-time positions. Tap an enemy on the map to mark them caught.
* **Proximity Alert:** If an opponent enters a 50m radius, your device will vibrate in warning bursts.

---

## 🛠️ Tech Stack

* **Frontend:** Vanilla HTML5, CSS3, JavaScript (ES6 Modules)
* **Maps:** [Leaflet.js](https://leafletjs.com/) with OpenStreetMap tiles
* **Backend:** [Firebase Realtime Database](https://firebase.google.com/)

---

## ⚠️ Player Safety Guidelines

* Stay mindful of real-world surroundings at all times.
* Do not cross active vehicle roads, railways, or enter private properties.
* Avoid sprinting in poorly lit areas or rough terrains during nighttime matches.
