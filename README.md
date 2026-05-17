# Beacon Alerts

A desktop app for building and running stream overlay alerts. It runs entirely on your machine with a local server and embedded database. No accounts, no cloud services required.

Pair it with [Streamer.bot](https://streamer.bot) and alerts will play in OBS automatically whenever events happen on your stream.

---

## How it works

1. Launch the app. The local server and database start automatically.
2. Create an overlay using the drag-and-drop editor or the HTML/CSS/JS code sandbox.
3. Add alerts to the overlay and pick which Streamer.bot events trigger each one.
4. Copy the overlay URL and paste it into OBS as a Browser Source.
5. When an event comes in, the matching alert plays.

---

## Features

Overlays
- Drag-and-drop visual editor with layers, animations, and a properties panel
- Full HTML/CSS/JS code sandbox with live preview and configurable fields
- Export and import overlays as .beacon files

Alerts
- Multiple alerts per overlay, each tied to a Streamer.bot event type
- Variants let you play different animations based on conditions (e.g. T3 subs vs T1)
- Choose priority mode (first matching variant wins) or random mode
- Per-alert duration, queue behavior, and optional text-to-speech
- Show and hide animations per layer with type, direction, duration, and delay

Queues
- Blocking queues play one alert at a time in order
- Non-blocking queues fire alerts immediately without waiting
- Pause, skip, clear, and mute controls in the dashboard

Activity feed
- Live feed of every incoming Streamer.bot event
- Filter by service and event type, search by name
- Expand any event to see the full data payload
- Replay past events from the feed
- Customize badge labels, display templates, and colors per event type

Media library
- Manage images, video, audio, and GIFs locally
- No file uploads to external services
- Tracks which alerts are using a file before you delete it

Other
- Embedded database, no separate install needed
- Auto-updates

---

## Requirements

- Windows 10 or later (64-bit)
- [Streamer.bot](https://streamer.bot) running on the same PC as OBS

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

---

## What's New

### v0.5.10

- Fixed variant priority ordering. Variants created before this update all shared the same sort order, so priority mode (top-most match wins) could pick the wrong variant. Existing variants are automatically fixed on first launch.
- New variants now get the correct sort position when created, so priority order works immediately without needing to drag-reorder.

### v0.5.9

- Fixed: when multiple overlay instances were open (OBS browser source plus the preview pane), they could each independently pick a different alert for the same event, causing both to play. Alert selection is now deterministic across all instances so only one alert fires per event.

### v0.5.8

- Added weighted chance per alert. When multiple alerts are set to the same event type, you can assign a percentage to each one and the app will randomly pick one based on those weights. Leave all at 100 for equal odds. The chance input appears on each alert row in the dashboard.
- Fixed audio layers not playing in overlays.
- Fixed image and audio layer settings mixing together when switching a layer between types.

---

## License

MIT
