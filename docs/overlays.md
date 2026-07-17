# Overlays

An overlay is a browser page that runs inside OBS as a Browser Source. Each overlay has its own URL, its own content, and its own canvas size.

---

## Creating an overlay

Go to **Overlays** in the sidebar and click **+ New Overlay**. The template browser opens with five tabs:

- **Starter** - ready-made drop-ins. Stream Alerts is a full alert set (follow, sub, resub, gift sub, gift bomb, bits, raid); Charity Goal tracks a live Twitch charity campaign.
- **Basic** - event-driven alerts built in the drag-and-drop visual editor.
- **Static** - an always-on canvas for persistent graphics.
- **Widget** - always-on goals and live counters: follower, sub, and bits goals plus a multi-goal stack, all working with no other software. See [Widgets](widgets.md).
- **Advanced** - the HTML/CSS/JS code sandbox, with templates like Spotify Now Playing, Twitch Polls, Twitch Predictions, Weather, Closed Captions, Sound Alerts, and a Custom WebSocket Feed.

Each tab also shows a **Shared Library** section with community templates you can import.

Pick a template, give the overlay a name, and click **Create**.

---

## Overlay types

### Basic

Basic overlays use the visual alert editor. You add alerts to the overlay, each alert has layers (text, image, video, GIF, audio), and each layer has animation settings. See [Visual Editor](visual-editor.md).

### Static

A static overlay is a single always-on canvas built in the same visual editor, without alert events. Use it for frames, badges, and other persistent graphics.

### Widget

Widgets stay on screen and update live: goal bars, counters, and any Stats page number. See [Widgets](widgets.md).

### Advanced

Advanced overlays give you a full code editor with HTML, CSS, JavaScript, and Fields tabs, plus a live preview. The `BEACON` JavaScript API is injected automatically:

```js
BEACON.on('Twitch.Follow', (data) => {
  // data contains the event payload
});
```

See [Advanced Editor](advanced-editor.md) for details.

---

## Managing overlays

Each overlay card shows the name, a type badge, the canvas size, and the overlay URL.

Double-click the overlay name to rename it inline. From the card you can:

- **Enable or disable** the overlay with the toggle. Disabled overlays will not receive or play alerts.
- **Assign a queue** using the queue dropdown (basic and advanced overlays only). See [Queues](queues.md).
- **Copy the URL** for OBS.
- **Preview** the overlay in a new browser tab.
- **Export** the overlay using the download icon.
- **Delete** the overlay with the trash icon.

---

## Exporting and importing

Overlays export as `.beacon` files you can move to another machine or share.

### Exporting

Click the download icon on the overlay card. The export dialog shows the overlay details and an **Include media files** option:

- Unchecked - a plain `.beacon` file with the overlay layout and alerts, without media. Media has to be re-added after importing elsewhere.
- Checked - a `.beacon` bundle that includes the media files used by the alerts. Larger, but self-contained.

### Importing

Click **Import** at the top of the Overlays page and pick a `.beacon` file, or drag and drop one anywhere on the page.

A confirmation screen shows the overlay name, type, and alert count before anything is created. Advanced overlays show a security warning, since the file contains JavaScript that will run in your browser source. Only import files from sources you trust.

Bundles upload their media automatically. Plain files that reference media open a dialog after import so you can assign replacements from your media library. All imported alerts start disabled.

---

## Canvas size

The canvas size determines the dimensions of the overlay page. Set it to match your OBS browser source size so everything lines up.

Common sizes:
- 1920 x 1080 (standard 1080p)
- 2560 x 1440 (1440p)
- 1280 x 720 (720p)
- 1080 x 1920 (vertical)

Canvas size can be changed from the editor top bar.

---

## Missing media check

Each time you open the Overlays page, LuckyBot checks your overlays for broken media references (files that were moved or deleted). If any are found, a dialog lets you reassign them from the media library.
