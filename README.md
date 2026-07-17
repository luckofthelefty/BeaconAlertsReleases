# LuckyBot

A desktop app for Twitch streamers. From a single window it runs alert overlays, a full multi-channel chat client, a native chat bot, moderation tools, channel points, polls and predictions, OBS control, closed captions, and a clip manager. It runs entirely on your machine with a local server and embedded database, and installs in under 100 MB.

LuckyBot connects to Twitch directly with your login. No Streamer.bot required, though connecting one adds more sources. [LuckyBot Cloud](https://cloud.luckybot.app) can relay Twitch, Ko-fi, Streamlabs, StreamElements, Fourthwall, and custom WebSocket feeds, and includes a mobile companion for watching chat and events from your phone.

---

## How it works

1. Launch the app. The local server and database start automatically.
2. Log in with Twitch. Events, chat, and channel actions work natively from there.
3. Create an overlay using the drag-and-drop editor, the HTML/CSS/JS code sandbox, a widget, or a ready-made starter.
4. Copy the overlay URL and paste it into OBS as a Browser Source.
5. When an event comes in, the matching alert plays.

Optional: connect Streamer.bot over a local WebSocket, or add a LuckyBot Cloud token in Settings. When multiple sources deliver the same event, LuckyBot fires exactly one alert, preferring Twitch's own feed first, then Streamer.bot, then Cloud.

---

## Features

Overlays
- Drag-and-drop visual editor with layers, animations, keyframe timelines, and a properties panel
- Full HTML/CSS/JS code sandbox with live preview, configurable fields, and one-click template updates
- Ready-made templates: stream alerts, goal widgets, Spotify now playing, Twitch polls and predictions, closed captions, weather, sound alerts, and more
- Widget overlays that stay on screen and update live: sub, bits, and follower goals, chatbot counters, and every Stats page variable
- Export overlays as .beacon files, with an option to bundle media; import by drag and drop
- Shared Library for publishing and importing community templates

Alerts
- Multiple alerts per overlay, each bound to one or more event types
- Weighted chance, variants with conditional logic, priority or random selection
- Per-alert duration, queue behavior, and optional text-to-speech
- Show and hide animations per layer, plus a keyframe animator for full timelines
- Blocking and non-blocking queues with pause, skip, clear, and mute controls

Chat
- Full chat client for your channel: badges, emotes, cheermotes, replies, deleted-message handling, and first-time-chatter highlights
- Moderate other channels in tabs, with mod actions, pins, polls, hype train and ad timers per channel
- Shared chat sessions show a participant banner and attribute messages to their source channel
- Pop out any chat to its own window, or add a styled chat overlay to OBS
- Message effects and gigantified emotes render like native Twitch, and cheers show inline with animated cheermotes

Chat bot
- Custom commands with variables, cooldowns, permission levels, and counters (deaths, wins, anything)
- Multi-action responses: conditions, fetches, variables, delays, and sound alerts from a single command
- Counters can be dropped onto an overlay in one click and update live as commands run
- Timed messages, quotes, spam filters, and banned words
- Runs from your own account or a separate bot account, server-side, even with the dashboard closed

Activity feed
- Live feed of events from every connected source, with per-service tabs and filters
- Expand any event to see the full payload; replay past events
- Customize badge labels, display templates, and colors per event type

Stream tools
- Home page with stream title, category, and tag editing
- Polls, predictions, and channel point reward management
- Moderation page: banned terms, blocked users, AutoMod settings
- Clips browser and raid finder
- OBS control: scenes, sources, and streaming status over obs-websocket
- Stats page with editable counts, goals, labels, and leaderboards
- Closed captions from a fully offline speech-to-text engine

Media library
- Manage images, video, audio, and GIFs locally
- Tracks which alerts use a file before you delete it

Other
- Text-to-speech via ElevenLabs or Amazon Polly
- Spotify now-playing overlay and playback controls
- Embedded database with scheduled backups, self-healing recovery, and a backup before every update
- In-app feedback that goes straight to the developer

---

## Requirements

- Windows 10 or later (64-bit)
- OBS Studio or any software that supports browser sources
- A Twitch account

Optional:
- [Streamer.bot](https://streamer.bot) for YouTube events and anything else your Streamer.bot instance connects to
- A [LuckyBot Cloud](https://cloud.luckybot.app) subscription for cloud-relayed events and the mobile companion

---

## Install

Download the latest installer from the [Releases](https://github.com/luckofthelefty/LuckyBotReleases/releases) page and run it. The app updates itself automatically when new versions come out, taking a database backup first.

---

## Documentation

- [Getting Started](docs/getting-started.md)
- [Overlays](docs/overlays.md)
- [Alerts and Variants](docs/alerts-and-variants.md)
- [Visual Editor](docs/visual-editor.md)
- [Advanced Editor](docs/advanced-editor.md)
- [Widgets](docs/widgets.md)
- [Chat](docs/chat.md)
- [Chat Bot](docs/chat-bot.md)
- [Stream Tools](docs/stream-tools.md)
- [Activity Feed](docs/activity-feed.md)
- [Queues](docs/queues.md)
- [Media Library](docs/media-library.md)
- [Settings](docs/settings.md)

---

## What's New

Recent highlights from the 0.6.2xx releases:

- Alert sources are prioritized Twitch EventSub first, then Streamer.bot, then Cloud, so alerts fire once and fast.
- Chat bot counters can power live overlay widgets, with a one-click Create Overlay button.
- Widget setup was reworked: plain-English goals, auto-named variables, and a tabbed variable picker. No setup needed to show any Stats page number.
- Cheers render as normal chat messages, keeping first-time-chatter labels and styling.
- Mod anniversaries, shared-chat attribution, and multi-month gift sub durations display correctly in chat.
- Page-by-page loading cut the app's memory use, especially with popout windows open.
- Sound alerts can play from chat commands through a dedicated overlay, with queued or overlapping playback.
- Fourthwall merch and gift events, plus hype train level-ups, reach advanced overlays.

The full changelog lives on the [Releases](https://github.com/luckofthelefty/LuckyBotReleases/releases) page.

---

## License

MIT
