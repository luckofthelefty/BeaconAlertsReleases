# Getting Started

## What you need

- Windows 10 or later (64-bit)
- [Streamer.bot](https://streamer.bot) installed and running on the same PC as OBS
- OBS Studio or any software that supports browser sources

---

## Install

Download the latest installer from the [Releases](https://github.com/luckofthelefty/BeaconAlertsReleases/releases) page and run it. Beacon Alerts will be added to your Start menu and desktop.

---

## First launch

Open Beacon Alerts. The dashboard opens in an app window. A local server starts on port 4200 in the background and an embedded database initializes automatically. There is nothing else to install or configure.

---

## Step 1 - Create an overlay

Click **Overlays** in the sidebar, then **+ New Overlay**.

Pick a type:

- **Basic** - drag-and-drop visual editor, good for most alert setups
- **Advanced** - HTML/CSS/JS code sandbox, for custom overlays or anything that needs code

Give it a name and click **Create**.

---

## Step 2 - Add an alert

Inside the overlay, click **+ New** in the alerts panel on the right. Type a name like "Follower Alert" and press Enter.

This opens the alert editor. From here:

1. Set the **event type** in the top bar. This is the Streamer.bot event that triggers the alert, like `Twitch.Follow`.
2. Add layers to the canvas using the buttons in the layers panel on the left (text, image, video, audio, etc.).
3. Position and style each layer using the properties panel on the right.
4. Set animations on each layer in the Animation section of the properties panel.
5. Set the **Duration** in the top bar. This controls how long the alert plays, in milliseconds.
6. Click **Save** or press Ctrl+S.

---

## Step 3 - Add the overlay to OBS

Go back to the overlay page and click **Copy URL**. In OBS:

1. Add a new **Browser Source**.
2. Paste the copied URL into the URL field.
3. Set the width and height to match your canvas size (usually 1920 x 1080).

---

## Step 4 - Connect Streamer.bot

Beacon Alerts talks to Streamer.bot over a local WebSocket connection.

In Streamer.bot, go to **Servers/Clients > WebSocket Server** and make sure it is enabled and running on `127.0.0.1:8080`. That is the default, so it should already be set up.

The overlay connects automatically when it loads in OBS. You can confirm it is working by checking the Activity Feed in Beacon Alerts. Events should start appearing when Streamer.bot fires them.

---

## Step 5 - Test an alert

In the alert editor, click the **Test** button in the top bar. This plays the alert immediately using sample data so you can see it in OBS before going live.

---

## Where to go from here

- [Overlays](overlays.md) - manage multiple overlays, export and import
- [Alerts and Variants](alerts-and-variants.md) - conditions, variants, match modes
- [Visual Editor](visual-editor.md) - layers, animations, and the canvas
- [Queues](queues.md) - control how alerts are ordered and timed
- [Activity Feed](activity-feed.md) - view stream events
