# Advanced Editor

The advanced editor is a full HTML/CSS/JS code sandbox. Use it for overlays that need custom code, or start from one of the built-in advanced templates (Spotify Now Playing, Twitch Polls, Twitch Predictions, Weather, Closed Captions, Sound Alerts, Custom WebSocket Feed).

---

## Layout

- **Left** - the code editor with tabs across the top.
- **Right** - a live preview of the overlay. Drag the divider to adjust the split.
- **Bottom** - a console panel for debugging. Drag its divider to resize.

---

## Code tabs

- **HTML** - the page markup.
- **CSS** - styles applied to the page.
- **JavaScript** - code that runs in the overlay.
- **Fields** - a JSON schema that defines configurable settings for the overlay.

The live preview updates shortly after you stop typing. Save with the **Save** button or Ctrl+S.

---

## The BEACON API

When your overlay loads, a `BEACON` global is injected automatically. Use it to listen for events:

```js
// Listen for a specific event
BEACON.on('Twitch.Follow', (data) => {
  console.log(data.user, 'followed');
});

// Listen for all events
BEACON.on('*', (type, data) => {
  console.log(type, data);
});
```

Event data is normalized across sources, so fields like `user`, `displayName`, `userId`, and `tier` are consistent whether the event came from Twitch directly, Streamer.bot, or LuckyBot Cloud. Overlays also receive live stats variables and chat commands, which the built-in templates use.

---

## Snippets

Click **Snippets** in the top bar to open ready-to-use code examples. Click any snippet to insert it at the cursor. Snippets cover event listeners, show and hide helpers, CSS animations, and HTML structures.

---

## Testing

Set an event type in the top bar to bind the preview to sample data, then click **Test** to fire a test event at the preview. Check **Live** to also fire it on all connected browser sources.

---

## Fields

The Fields tab defines settings that appear as form controls on the overlay's settings panel, so things stay configurable without editing code. Use the **+ Add Field** button to build a field without writing JSON.

Supported field types:

| Type | Description |
|------|-------------|
| Text | Single-line text input |
| Textarea | Multi-line text input |
| Number | Number input (min, max, step) |
| Slider | Range slider |
| Checkbox | Boolean toggle |
| Color | Color swatch and hex input |
| Dropdown | Select from a list of options |
| Audio | Audio file path or media pick |
| File | File path or media pick |
| Hidden | Read-only display with a copy button |

Fields can be grouped into collapsible sections with the `group` property. In your HTML and CSS, `{{fieldKey}}` references a field's value and is replaced when the overlay renders.

---

## Template updates

Overlays created from a built-in template remember which one. When a LuckyBot update improves that template, an **Update template** button appears in the editor. Clicking it replaces the overlay's code with the latest version while keeping your field values. Manual code edits are overwritten, so skip the update if you have customized the code.

---

## Console

The console panel captures `console.log`, `console.error`, and other output from the preview. Type expressions into the console input to run them against the live preview. Check the console's **Live** box to also run typed snippets in every connected browser source, which is useful for debugging the overlay as it runs in OBS.

---

## Canvas size

Use the canvas size control in the top bar to pick a preset or enter custom dimensions. Changes apply immediately.
