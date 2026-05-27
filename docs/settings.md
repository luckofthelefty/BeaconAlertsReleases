# Settings

The Settings page has four tabs: Connections, Audio, Appearance, and System. The System tab is only available in the desktop app.

---

## Connections

### Streamer.bot

Configure the WebSocket connection to a local Streamer.bot instance.

- **WebSocket URL** - the address Beacon will connect to. The default is `ws://127.0.0.1:8080`. Change this if your Streamer.bot WebSocket server is on a different port or machine.
- **Enable debug events** - when checked, Streamer.bot debug events are shown in the activity feed. These are hidden by default because they are noisy.

Click **Save & Reconnect** after making changes.

### BeaconCloud

BeaconCloud is an optional cloud relay that sends Twitch, Ko-fi, Streamlabs, and StreamElements events to the app without requiring a local Streamer.bot install.

To connect, paste your connection token and click **Save & Connect**. Get a token at [cloud.beaconalerts.app](https://cloud.beaconalerts.app).

You can also click **Validate** first to confirm the token is valid and see which account it belongs to before saving.

The status indicator shows the current connection state:

- Green dot: connected
- Yellow dot: connecting or reconnecting
- Red dot: error (token rejected or subscription expired)

Click **Disconnect** to remove the saved token and close the connection.

See [docs.beaconalerts.app](https://docs.beaconalerts.app) for more on BeaconCloud.

### Twitch Auth

Beacon uses a Twitch OAuth token internally for features that need Twitch API access. The token refreshes automatically every 15 minutes.

This section shows the current token status and expiry. Use **Refresh Auth Token** if you suspect the token is stale or expired. If no refresh token is stored, log out and log back in to re-authenticate.

---

## Audio

Configure text-to-speech for your alerts.

### Provider

Choose between **ElevenLabs** and **Amazon Polly (AWS)**.

#### ElevenLabs

- **API Key** - paste your ElevenLabs API key. Once saved, the key is stored encrypted and only the placeholder text changes to confirm it is set.
- **Voice ID** - the ID of the ElevenLabs voice to use. Find voice IDs in the [ElevenLabs voice library](https://elevenlabs.io/voice-library).

#### Amazon Polly

- **AWS Access Key ID** and **AWS Secret Access Key** - your AWS credentials. Stored encrypted.
- **Region** - the AWS region to use for Polly requests.
- **Voice** - choose from a list of Polly voices. A full list is available in the [AWS documentation](https://docs.aws.amazon.com/polly/latest/dg/voicelist.html).

### Output Device

If you have more than one audio output device, a dropdown appears so you can choose which device TTS audio plays through. This only affects playback in the editor. OBS browser sources route audio through the OBS mixer regardless of this setting.

Click **Save** to apply changes, or **Test** to play a short sample using the current settings.

---

## Appearance

Click any theme card to change the dashboard color theme. The change applies immediately.

---

## System

This tab is only available in the desktop app.

### App

- **Open data folder** - opens the folder where Beacon stores its database and app files. Useful for backups or moving data to another machine.
- **Check for updates** - manually checks for a new version. The app also checks on startup. If an update is found, it downloads in the background and prompts you to restart when ready.
- **Export all overlays** - saves every overlay as a separate `.beacon` file to your downloads folder.

### Diagnostics Logs

Export a ZIP file containing WebSocket and server logs. Use this if you need to share logs for troubleshooting. Choose a time range (last 24 hours, 3 days, 7 days, or all available) and click **Export Logs ZIP**.

### Backups

Beacon takes a database snapshot automatically before each update. You can also create one manually at any time.

Each backup shows the app version it was taken on and the timestamp. Click **Restore** to roll back to that snapshot. The app will restart after a successful restore.

If the installer for that version is not in the backup folder, you will be prompted to place it there for a full rollback. You can also choose **Restore database only** to restore just the data without reinstalling that version.
