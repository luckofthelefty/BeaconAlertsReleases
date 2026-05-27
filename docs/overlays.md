# Overlays

An overlay is a browser page that runs inside OBS as a Browser Source. Each overlay has its own URL, its own set of alerts, and its own canvas size.

---

## Creating an overlay

Go to **Overlays** in the sidebar and click **+ New Overlay**. This opens the template browser.

Pick a starting point from the template browser:

- **Basic** - opens the drag-and-drop visual editor. Good for alert animations with images, text, video, and audio.
- **Advanced** - opens the HTML/CSS/JS code sandbox. Use this for anything that needs custom code.
- **Widget** - a persistent canvas connected to your event source. Widgets stay visible between alerts and update in response to events.

After picking a type and an optional template, give the overlay a name and click **Create**.

---

## Overlay types

### Basic

Basic overlays use the visual alert editor. You add alerts to the overlay, each alert has layers (text, image, video, etc.), and each layer has animation settings. The canvas is a fixed size that maps directly to your OBS browser source size.

See [Visual Editor](visual-editor.md) for details.

### Advanced

Advanced overlays give you a full code editor with HTML, CSS, and JavaScript tabs. A live preview updates as you type. You can define configurable fields that appear as form controls in the settings panel.

The `BEACON` JavaScript API is injected automatically. Use it to listen for events:

```js
BEACON.on('Twitch.Follow', (data) => {
  // data contains the event payload
});

// Listen for all events
BEACON.on('*', (type, data) => {});
```

See [Advanced Editor](advanced-editor.md) for details.

### Widget

Widgets are persistent overlays that stay visible and react to events over time. Use them for things like a goal tracker, chat display, or now-playing bar.

---

## Managing overlays

Each overlay card shows the name, canvas size, overlay type, and the overlay URL.

Double-click the overlay name to rename it inline. Press Enter to confirm or Escape to cancel.

From the card you can:

- **Enable or disable** the overlay with the toggle. Disabled overlays still load but will not receive or play alerts.
- **Assign a queue** using the queue dropdown. This controls how alerts from this overlay are queued up. See [Queues](queues.md). The queue picker does not appear for widget overlays.
- **Copy the URL** to use in OBS.
- **Preview** the overlay in a new browser tab.
- **Export** the overlay using the download icon.
- **Delete** the overlay by clicking the trash icon and then confirming.

---

## Exporting and importing

Overlays can be exported as `.beacon` files and imported on another machine or shared with others.

### Exporting

Click the download icon on the overlay card to open the export dialog. You can choose to export as:

- **Plain file** - a JSON file containing the overlay layout and alerts, without media. Any images or videos will need to be re-added after importing on another machine.
- **Bundle** - a ZIP file that includes the overlay data and any media files used by the alerts. Bundles are larger but self-contained.

### Importing

Click **Import** at the top of the Overlays page and select a `.beacon` file. You can also drag and drop a `.beacon` file directly onto the Overlays page.

A confirmation screen shows the overlay name, type, and alert count before anything is created. For advanced overlays, a security warning is shown since the file contains JavaScript that will run in your browser. Only import files from sources you trust.

If you import a plain file (without a bundle) and the overlay references media files, a dialog will appear after import to let you assign those files from your media library.

All imported alerts start disabled by default.

---

## Canvas size

The canvas size determines the dimensions of the overlay page. Set it to match your OBS browser source size so alerts appear in the right positions.

Common sizes:
- 1920 x 1080 (standard 1080p)
- 2560 x 1440 (1440p)
- 1280 x 720 (720p)
- 1080 x 1920 (vertical / phone layout)

The canvas size can be changed from inside the alert editor or the advanced editor top bar.

---

## Missing media check

Each time you open the Overlays page, Beacon checks all your overlays for broken media references (files that have been moved or deleted). If any are found, a dialog lets you reassign them from the media library.
