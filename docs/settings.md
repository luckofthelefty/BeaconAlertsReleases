# Settings

---

## Appearance

The Appearance section lets you choose a color theme for the dashboard. Click any theme card to apply it. The change takes effect immediately.

---

## StreamElements TTS

Text-to-speech in Beacon Alerts is powered by StreamElements. To set it up, you need a free StreamElements account.

1. Go to [streamelements.com](https://streamelements.com) and log in.
2. Find your JWT token in your account settings.
3. Paste the full JWT into the token field in Settings and click Save.

Beacon extracts only the `authToken` claim from the JWT. The full token is not stored. Your credentials stay on your device.

Once configured, the section shows a confirmation with your StreamElements display name. TTS can then be enabled per alert in the alert editor.

---

## App settings

These options are only available in the desktop app.

**Open data folder** - opens the folder where Beacon Alerts stores its database and app data. Useful if you need to back up or move your data.

**Check for updates** - manually checks for a new version. The app also checks automatically on startup. If an update is available, it will download in the background and prompt you to restart when it is ready.

**Export all overlays** - downloads every overlay as a separate `.beacon` file. Each file is saved to your downloads folder. You can use these files to back up your work or move overlays to another machine.
