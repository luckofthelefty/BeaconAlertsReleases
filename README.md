# Beacon Alerts

A desktop app for building and running stream overlay alerts. It runs entirely on your machine with a local server and embedded database.

Connect to [Streamer.bot](https://streamer.bot) for a local event source, or use [BeaconCloud](https://cloud.beaconalerts.app) to receive Twitch, Ko-fi, Streamlabs, and StreamElements events through the cloud with no local setup required.

---

## How it works

1. Launch the app. The local server and database start automatically.
2. Connect an event source: Streamer.bot over a local WebSocket, or BeaconCloud with a connection token.
3. Create an overlay using the drag-and-drop editor, the HTML/CSS/JS code sandbox, or a widget template.
4. Add alerts to the overlay and pick which events trigger each one.
5. Copy the overlay URL and paste it into OBS as a Browser Source.
6. When an event comes in, the matching alert plays.

---

## Features

Overlays
- Drag-and-drop visual editor with layers, animations, and a properties panel
- Full HTML/CSS/JS code sandbox with live preview and configurable fields
- Widget overlays that stay visible and update in response to events
- Export overlays as .beacon files, with an option to bundle media files
- Import .beacon files by drag and drop or from the Import button

Alerts
- Multiple alerts per overlay, each bound to one or more event types
- Weighted chance per alert when multiple alerts match the same event
- Variants let you play different animations based on conditions
- Condition builder with simple AND rules or advanced AND/OR groups
- Duplicate variants from the overlay page
- Choose priority mode (first matching variant wins) or random mode
- Per-alert duration, queue behavior, and optional text-to-speech
- Keyframe animator for per-layer timeline animation
- Show and hide animations per layer with type, direction, duration, and delay

Queues
- Blocking queues play one alert at a time in order
- Non-blocking queues fire alerts immediately without waiting
- Pause, skip, clear, and mute controls in the dashboard

Activity feed
- Live feed of events from Streamer.bot and BeaconCloud
- Filter by service and event type
- Expand any event to see the full data payload
- Replay past events from the feed
- Customize badge labels, display templates, and colors per event type

Connections
- Streamer.bot: connect via local WebSocket
- BeaconCloud: receive Twitch, Ko-fi, Streamlabs, and StreamElements events through the cloud

Media library
- Manage images, video, audio, and GIFs locally
- Tracks which alerts are using a file before you delete it

Other
- Text-to-speech via ElevenLabs or Amazon Polly
- Embedded database, no separate install needed
- Auto-updates with automatic database backups before each update

---

## Requirements

- Windows 10 or later (64-bit)
- OBS Studio or any software that supports browser sources
- One of the following for live events:
  - [Streamer.bot](https://streamer.bot) running on the same PC as OBS, or
  - A [BeaconCloud](https://cloud.beaconalerts.app) subscription

---

## Install

Download the latest installer from the [Releases](https://github.com/luckofthelefty/BeaconAlertsReleases/releases) page and run it. The app will update itself automatically when new versions come out.

---

## Documentation

- [Getting Started](docs/getting-started.md)
- [Overlays](docs/overlays.md)
- [Alerts and Variants](docs/alerts-and-variants.md)
- [Visual Editor](docs/visual-editor.md)
- [Advanced Editor](docs/advanced-editor.md)
- [Activity Feed](docs/activity-feed.md)
- [Queues](docs/queues.md)
- [Media Library](docs/media-library.md)
- [Settings](docs/settings.md)

For BeaconCloud setup and subscription info, see [docs.beaconalerts.app](https://docs.beaconalerts.app).

---

## What's New

### v0.6.x

- BeaconCloud integration: receive Twitch, Ko-fi, Streamlabs, and StreamElements events through the cloud without a local Streamer.bot install.
- Activity feed: right-click any service tab to filter which event types appear. Info icon in the feed header explains the controls.
- Activity feed: StreamElements and Streamlabs events now display with formatted badges, meta lines, and tier info matching the Twitch event style.
- Activity feed: SE subscriber events with 2 or more cumulative months are classified as ReSub automatically.

### v0.5.13

- File inputs now show readable media filenames instead of raw file IDs across visual and advanced editors.
- TTS now strips leading Twitch cheer tokens before speech (for example, "Cheer200 ...").
- Replayed activity events run full variant resolution before playback, matching live event behavior.

### v0.5.12

- Fixed replayed activity events so they now run full variant resolution before playback.

### v0.5.10

- Fixed variant priority ordering. Variants created before this update all shared the same sort order. Existing variants are automatically fixed on first launch.

### v0.5.9

- Fixed: when multiple overlay instances were open (OBS browser source plus the preview pane), they could each independently pick a different alert for the same event. Alert selection is now deterministic across all instances.

### v0.5.8

- Added weighted chance per alert. When multiple alerts are set to the same event type, assign a percentage to each one and the app picks one based on those weights.
- Fixed audio layers not playing in overlays.
- Fixed image and audio layer settings mixing together when switching a layer between types.

---

## License

MIT
