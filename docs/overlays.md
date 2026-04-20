# Overlays

An overlay is a browser page that runs inside OBS as a Browser Source. Each overlay has its own URL, its own set of alerts, and its own canvas size.

---

## Creating an overlay

Go to **Overlays** in the sidebar and click **+ New Overlay**.

Pick a type:

- **Basic** - opens the drag-and-drop visual editor. Good for alert animations with images, text, video, and audio.
- **Advanced** - opens the HTML/CSS/JS code sandbox. Use this for anything that needs custom code, like a Spotify widget or a chat overlay.

After picking a type, give the overlay a name and click **Create**.

---

## Overlay types

### Basic

Basic overlays use the visual alert editor. You add alerts to the overlay, each alert has layers (text, image, video, etc.), and each layer has animation settings. The canvas is a fixed size that maps directly to your OBS browser source size.

See [Visual Editor](visual-editor.md) for details.

### Advanced

Advanced overlays give you a full code editor with HTML, CSS, and JavaScript tabs. A live preview updates as you type. You can define configurable fields that appear as form controls in the settings panel.

The `BEACON` JavaScript API is injected automatically. Use it to listen for Streamer.bot events:

```js
BEACON.on('Twitch.Follow', (data) => {
  // data contains the event payload from Streamer.bot
});

// Listen for all events
BEACON.on('*', (type, data) => {});
```

See [Advanced Editor](advanced-editor.md) for details.

---

## Managing overlays

Each overlay card shows the name, canvas size, overlay type, and the overlay URL.

From the card you can:

- **Enable or disable** the overlay with the toggle. Disabled overlays still load but will not receive or play alerts.
- **Rename** with the pencil icon.
- **Assign a queue** using the queue dropdown. This controls how alerts from this overlay are queued up. See [Queues](queues.md).
- **Copy the URL** to use in OBS.
- **Export** the overlay as a `.beacon` file.
- **Delete** the overlay (requires two clicks to confirm).

---

## Exporting and importing

Overlays can be exported as `.beacon` files and imported on another machine or shared with others.

To export, click the download icon on the overlay card. The file is saved to your downloads folder.

To import, click **Import** at the top of the Overlays page and select a `.beacon` file. A confirmation screen shows the overlay name, type, and alert count before anything is created. For advanced overlays, a warning is shown since the file contains JavaScript that will run in your browser.

Imported alerts start disabled by default. Media files are not included in exports, so any images or videos referenced by the alert will need to be re-added after importing.

---

## Canvas size

The canvas size determines the dimensions of the overlay page. Set it to match your OBS browser source size so alerts appear in the right positions.

Common sizes:
- 1920 x 1080 (standard 1080p)
- 2560 x 1440 (1440p)
- 1280 x 720 (720p)
- 1080 x 1920 (vertical / phone layout)

The canvas size can be changed from inside the alert editor or the advanced editor top bar.
