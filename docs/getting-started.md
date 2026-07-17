# Getting Started

## What you need

- Windows 10 or later (64-bit)
- OBS Studio or any software that supports browser sources
- A Twitch account

That is everything. LuckyBot connects to Twitch directly with your login, so events, chat, and channel actions work with no other software. Streamer.bot and LuckyBot Cloud are optional add-ons covered in Step 5.

---

## Install

Download the latest installer from the [Releases](https://github.com/luckofthelefty/LuckyBotReleases/releases) page and run it. LuckyBot is added to your Start menu and desktop, and updates itself automatically when new versions come out.

---

## First launch

Open LuckyBot. A local server starts on port 58315 and an embedded database initializes automatically. There is nothing else to install or configure.

Click **Sign in with Twitch**. The app shows a code and a link. Open the link in your browser, enter the code, and approve the login. The dashboard opens on the Home page, which has a short walkthrough you can follow or dismiss.

---

## Step 1 - Create an overlay

Click **Overlays** in the sidebar, then **+ New Overlay**.

The template browser has five tabs:

- **Starter** - ready-made drop-ins. Stream Alerts gives you a full alert set (follow, sub, resub, gift sub, gift bomb, bits, raid) in one click.
- **Basic** - event-driven alerts built in the drag-and-drop visual editor.
- **Static** - always-on graphics.
- **Widget** - goals and live counters. Includes ready-made follower, sub, and bits goals that need no setup.
- **Advanced** - HTML/CSS/JS code sandbox, with templates like Spotify Now Playing, Twitch Polls, and Closed Captions.

Pick a template, give it a name, and click **Create**. The fastest path for a new setup is the Starter tab's Stream Alerts.

---

## Step 2 - Add the overlay to OBS

On the overlay card, click **Copy URL**. In OBS:

1. Add a new **Browser Source**.
2. Paste the copied URL into the URL field.
3. Set the width and height to match the canvas size shown on the overlay card (usually 1920 x 1080).

---

## Step 3 - Customize an alert

Open the overlay and click any alert to open the editor. From there:

1. Pick which events trigger it in the **Event** tab of the Alert Settings panel.
2. Add and style layers (text, image, video, GIF, audio) on the canvas.
3. Set show and hide animations, or use the keyframe animator for full timelines.
4. Set the hold duration in the **Duration** tab.
5. Click **Save** or press Ctrl+S.

See [Alerts and Variants](alerts-and-variants.md) and the [Visual Editor](visual-editor.md) for details.

---

## Step 4 - Test an alert

Click **Test** in the editor's top bar to play the alert with sample data. Check the **Live** box first if you also want the test to fire in OBS, not just the preview.

You can also replay any real past event from the [Activity Feed](activity-feed.md).

---

## Step 5 - Optional connections

LuckyBot works fully on its own. Two optional connections add more:

### Streamer.bot

Connecting a local [Streamer.bot](https://streamer.bot) instance adds YouTube events and anything else your Streamer.bot connects to. In Streamer.bot, enable the WebSocket server (Servers/Clients > WebSocket Server, default `127.0.0.1:8080`), then set the URL in **Settings > Connections > Streamer.bot** and click **Save & Reconnect**.

### LuckyBot Cloud

[LuckyBot Cloud](https://cloud.luckybot.app) relays events from services such as Ko-fi, Streamlabs, StreamElements, Fourthwall, and custom WebSocket feeds, and includes a mobile companion. Get a token at cloud.luckybot.app, paste it in **Settings > Connections > LuckyBot Cloud**, and click **Save & Connect**.

When more than one source delivers the same Twitch event, LuckyBot fires exactly one alert. Twitch's own feed wins, then Streamer.bot, then Cloud.

---

## Where to go from here

- [Overlays](overlays.md) - manage overlays, export and import
- [Alerts and Variants](alerts-and-variants.md) - conditions, variants, match modes
- [Visual Editor](visual-editor.md) - layers, animations, and the canvas
- [Widgets](widgets.md) - goals, counters, and live stats on screen
- [Chat](chat.md) - the built-in chat client and moderation tools
- [Chat Bot](chat-bot.md) - commands, counters, timers, and spam filters
- [Stream Tools](stream-tools.md) - polls, predictions, channel points, OBS control, captions
- [Activity Feed](activity-feed.md) - view and replay stream events
- [Queues](queues.md) - control how alerts are ordered and timed
- [Settings](settings.md) - connections, audio, appearance, and system options
