# Visual Editor

The visual editor is the main way to build alerts in a basic overlay. It has three panels: layers on the left, the canvas in the center, and the properties panel on the right. The top bar holds the alert settings.

---

## Top bar

- **Back button** - returns to the overlay page
- **Alert name** - click to rename
- **Event type** - the Streamer.bot event that triggers this alert (only on parent alerts, not variants)
- **Queue behavior** - whether this alert joins the queue or plays immediately
- **Duration** - how long the alert plays in milliseconds
- **Canvas size** - resize the canvas
- **Zoom** - zoom the canvas in or out. The toolbar, labels, and resize handles stay the same visual size regardless of zoom level.
- **Streamer.bot status** - a dot that shows whether the app is connected to Streamer.bot
- **Test** - plays the alert immediately using sample data so you can preview it in OBS
- **Ghost outlines** - toggle showing faint outlines of other alerts on the same overlay. Useful for aligning things.
- **Save** - saves all changes. The button shows "Unsaved changes" when there is something to save. Ctrl+S also works.

---

## Layers panel

The layers panel on the left lists every box on the canvas for this alert. Layers are drawn in order from bottom to top.

### Adding layers

Click one of the add buttons at the top of the panel to add a new layer. Available types:

- **Text** - a text box. Supports variable placeholders from event data.
- **Image** - a static image from a URL or the media library
- **Video** - a video file, plays during the alert
- **GIF** - an animated GIF
- **Audio** - an audio file, plays during the alert
- **HTML** - raw HTML content for anything else

### Layer controls

Each layer row has:

- A visibility toggle (eye icon) - hidden layers are not shown during playback
- A lock toggle - locked layers cannot be selected or moved on the canvas
- A delete button

Click a layer to select it. The properties panel on the right will update to show that layer's settings.

Drag layers in the list to reorder them. The order determines which layers appear in front of others.

---

## Canvas

The canvas is the preview area in the center. It shows the alert at the set canvas size, scaled to fit your screen.

### Moving and resizing

Click a box to select it. Drag it to move. Use the handles on the edges and corners to resize.

Hold Shift and use the arrow keys to move in 10px steps. Arrow keys alone move 1px at a time.

### Multi-select

Hold Ctrl and click to select multiple boxes. You can move them together.

### Right-click menu

Right-click any box on the canvas for options:
- Bring to Front
- Send to Back
- Duplicate
- Delete

### Undo and redo

Ctrl+Z to undo, Ctrl+Y or Ctrl+Shift+Z to redo. The editor keeps 50 undo steps. Rapid moves and resizes are merged into a single undo entry.

---

## Properties panel

The properties panel on the right shows the settings for the selected layer.

### All layer types

- X and Y position
- Width and height
- Opacity
- Overflow (clip content or let it overflow the box)
- Visible and locked toggles

### Animations

Each layer can have a show animation (plays when the alert starts) and a hide animation (plays before the alert ends).

For each animation you can set:
- Type (fade, slide, scale, etc.)
- Direction
- Duration in milliseconds
- Delay in milliseconds

### Text layers

- Content - the text to display. Use `{{fieldName}}` to insert event data, e.g. `{{user}}` for the viewer's name.
- Font family
- Font size
- Color
- Weight
- Alignment
- Line height
- A variable picker that lists all available fields from the last live event

### Image, GIF, and video layers

- URL or pick from the media library

### Audio layers

- URL or pick from the media library
- Volume

### HTML layers

- Raw HTML content field
