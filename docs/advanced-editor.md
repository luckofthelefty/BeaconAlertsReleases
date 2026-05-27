# Advanced Editor

The advanced editor is a full HTML/CSS/JS code sandbox. Use it for overlays that need custom code, like a Spotify Now Playing widget, a chat overlay, or anything the visual editor cannot handle.

---

## Layout

The editor has two main sections:

- **Left side** - the code editor with tabs across the top.
- **Right side** - a live preview of the overlay. Drag the divider between them to adjust the split.
- **Bottom** - a console panel for debugging. Drag the console divider to resize it.

---

## Code tabs

- **HTML** - the page markup.
- **CSS** - styles applied to the page.
- **JavaScript** - code that runs in the overlay.
- **Fields** - a JSON schema that defines configurable settings for the overlay.

The live preview updates a short time after you stop typing.

---

## The BEACON API

When your overlay loads in OBS, a `BEACON` global is injected automatically. Use it to listen for events.

```js
// Listen for a specific event
BEACON.on('Twitch.Follow', (data) => {
  console.log(data.user, 'followed');
});

// Listen for all events
BEACON.on('*', (type, data) => {
  console.log(type, data);
});

// Stop listening
BEACON.off();
```

`BEACON.config` contains metadata about the overlay:

```js
{
  overlayId: '...',
  name: 'My Overlay',
  token: '...',
  width: 1920,
  height: 1080
}
```

If you have defined fields (see below), their current values are available in `BEACON.fieldData`.

---

## Event data

Event data is normalized across all sources. Fields like `user`, `displayName`, `userName`, `userId`, and `tier` are available consistently regardless of whether the event came from Streamer.bot, BeaconCloud, or another source.

---

## Snippets

Click **Snippets** in the top bar to open a panel with ready-to-use code examples. Click any snippet to insert it at the current cursor position in the editor. Snippets cover common patterns like event listeners, show/hide helpers, CSS animations, and HTML structures.

---

## Event type

Set an event type in the top bar to bind the preview to a specific event. This controls which sample data is used when you click **Test** and which variable suggestions appear.

---

## Testing

Click **Test** to fire a test event to the preview. Check the **Live** box to also fire it on all connected browser sources (OBS, etc.).

---

## Fields

The Fields tab lets you define a JSON schema for settings that appear as form controls in the settings panel. This is useful if you want to make something configurable without editing code each time.

Example:

```json
{
  "textColor": {
    "label": "Text color",
    "type": "colorpicker",
    "default": "#ffffff"
  },
  "fontSize": {
    "label": "Font size",
    "type": "slider",
    "min": 12,
    "max": 72,
    "default": 32
  },
  "showBackground": {
    "label": "Show background",
    "type": "checkbox",
    "default": true
  }
}
```

Supported field types:

| Type | Description |
|------|-------------|
| `text` | Single-line text input |
| `textarea` | Multi-line text input |
| `number` | Number input (supports min, max, step) |
| `checkbox` | Boolean toggle |
| `colorpicker` | Color swatch and hex input |
| `slider` | Range slider |
| `dropdown` | Select from a list (add an `options` object) |
| `url` | URL input |
| `image-input` | Text field for an image path |
| `video-input` | Text field for a video path |
| `sound-input` | Text field for an audio path |
| `hidden-info` | Read-only display with a copy button |
| `button` | Opens a URL |

Fields can be grouped into collapsible sections using the `group` property.

In your HTML and CSS, use `{{fieldKey}}` to reference field values. These are replaced automatically when the preview renders.

---

## Console

The console panel at the bottom of the editor lets you debug your overlay code. It captures `console.log`, `console.error`, and other console output from the preview iframe. You can also type expressions into the console input and run them against the live preview context.

---

## Canvas size

Use the canvas size dropdown in the top bar to pick a preset or enter a custom width and height. Changes apply immediately.

---

## Saving

Click **Save** or press Ctrl+S. The preview refreshes after saving.
