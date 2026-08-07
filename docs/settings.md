# Settings

The Settings page has four tabs: Connections, Audio, Appearance, and System.

---

## Connections

### Streamer.bot

Optional. Configure the WebSocket connection to a local Streamer.bot instance.

- **WebSocket URL** - the address LuckyBot connects to. The default is `ws://127.0.0.1:8080`.
- **Password** - only needed if your Streamer.bot WebSocket server has authentication enabled.
- **Enable debug events** - shows Streamer.bot debug events in the activity feed. Hidden by default because they are noisy.

Click **Save & Reconnect** after making changes.

### OBS Studio

Connect to OBS for the OBS control page (scenes, sources, audio mixer, stream and record controls).

1. In OBS, open **Tools > WebSocket Server Settings** and enable the server.
2. Enter the **Address** (default `localhost:4455`) and the server **Password**.
3. Click **Connect**.

The status dot shows Disconnected, Connecting, or Connected. Click **Disconnect** to drop the connection.

### LuckyBot Cloud

Optional. LuckyBot Cloud relays events from services such as Ko-fi, Streamlabs, StreamElements, Fourthwall, and custom WebSocket feeds, with no local software required.

Paste your connection token and click **Save & Connect**. Get a token at [cloud.luckybot.app](https://cloud.luckybot.app). Click **Validate** first to confirm the token and see which account it belongs to.

The status indicator shows the connection state. Click **Disconnect** to remove the saved token.

### Twitch Auth

LuckyBot uses your Twitch login for events, chat, and channel actions. Tokens refresh automatically every 15 minutes.

This section shows the current token status and expiry. Use **Refresh Auth Token** if you suspect the token is stale. If no refresh token is stored, log out and log back in.

### Spotify

Lets chat bot commands control Spotify (play, pause, skip) and lets viewers queue song requests. Playback control needs Spotify Premium, and Spotify must be playing on a device.

Uses your own free Spotify app: create one at developer.spotify.com/dashboard, add `beacon://spotify-callback` as a Redirect URI, and paste its Client ID and Secret here, then click **Connect Spotify**. If a music overlay already has Spotify credentials saved, **Copy from my music overlay** reuses them, and you still authorize once for playback control. This connection is separate from a music overlay's own Spotify connection (different permissions), though the same Spotify app works for both.

Use **Test** to confirm the connection is working, and **Disconnect** to remove it.

---

## Audio

Configure text-to-speech for your alerts.

### Provider

Choose between **ElevenLabs**, **Amazon Polly (AWS)**, and **TTS.Monster**.

- **ElevenLabs** - API key and Voice ID. A Browse voices link opens the ElevenLabs voice library.
- **Amazon Polly** - AWS Access Key ID, Secret Access Key, Region, and a voice picker (Brian, Amy, Emma, Matthew, Joanna, Salli, Joey, Ruth, Stephen).
- **TTS.Monster** - API key and Voice ID.

All keys are stored encrypted.

### Output Device

If you have more than one audio output device, a dropdown appears so you can choose which device TTS plays through. This only affects playback in the editor. OBS browser sources route audio through the OBS mixer regardless.

Click **Save** to apply changes, or **Test** to play a short sample using the current settings.

---

## Appearance

Click any theme card to change the dashboard color theme. The change applies immediately.

---

## System

### Startup

- **Run LuckyBot at Windows startup**
- **Open Activity Feed window at startup**
- **Ask for confirmation before closing LuckyBot**

### App

- **Open data folder** - opens the folder where LuckyBot stores its database and app files.
- **Check for updates** - manually checks for a new version. The app also checks on startup and updates in the background.
- **Export all overlays** - saves every overlay as a separate `.beacon` file.

### Diagnostics Logs

Export a ZIP of WebSocket and server logs for troubleshooting. Choose a time range (last 24 hours, 3 days, 7 days, or all available) and click **Export Logs ZIP**.

### Backups

LuckyBot takes a database snapshot automatically before each update, and can take them on a schedule.

- **Automatic scheduled backups** - toggle on and pick a frequency (Daily, Weekly, Monthly, or Custom), a time of day, and the day where it applies.
- **Skip while I'm live** - postpones a scheduled backup if you are streaming.
- **Keep the last N backups** - how many snapshots to retain (2 to 50).
- **Back up now** - takes a manual snapshot at any time.

Each backup shows the app version it was taken on and the timestamp. Click **Restore** to roll back to that snapshot. If the installer for that version is not in the backup folder, you can restore the database only.
