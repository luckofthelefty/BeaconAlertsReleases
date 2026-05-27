# Visual Editor

The visual editor is the main way to build alerts in a basic overlay. It has three panels: layers on the left, the canvas in the center, and the properties panel on the right. The top bar holds the alert and canvas settings.

---

## Top bar

- **Back button** - returns to the overlay page.
- **Alert name** - click the name field to edit it inline.
- **Unsaved indicator** - a label appears when there are unsaved changes.
- **Canvas size** - click the current size to open a picker with preset sizes or a custom width and height input.
- **Zoom** - click the minus and plus buttons to zoom in or out. Click the percentage number directly to type a custom zoom level. Click **Fit** to fit the canvas to the available space.
- **Show Others / Hide Others** - toggles faint outlines of all other alerts in the same overlay on the canvas. Useful for aligning elements across alerts.
- **Streamer.bot status** - a dot that shows whether the app is connected to Streamer.bot.
- **Copy URL** - copies the overlay URL to the clipboard.
- **Preview** - opens the overlay in a new browser tab.
- **Variant Setup** - only visible when editing a variant. Opens the condition builder for this variant. See [Alerts and Variants](alerts-and-variants.md).
- **Live checkbox** - when checked, the Test button also fires the alert on every connected browser source (OBS, etc.), not just the preview pane.
- **Test** - plays the alert immediately using sample data so you can preview it in OBS.
- **Test dropdown** - click the small arrow next to the Test button to open a panel where you can provide custom event data before testing.
- **Save** - saves all changes. Ctrl+S also works.

---

## Layers panel

The layers panel on the left lists every box on the canvas for this alert. Layers are drawn in order from bottom to top.

### Adding layers

Click one of the add buttons at the top of the panel to add a new layer. Available types:

- **Text** - a text box. Supports variable placeholders from event data.
- **Image** - a static image from a URL or the media library.
- **Video** - a video file, plays during the alert.
- **GIF** - an animated GIF.
- **Audio** - an audio file, plays during the alert.
- **HTML** - raw HTML content for anything else.

### Layer controls

Each layer row has:

- A visibility toggle (eye icon) - hidden layers are not shown during playback.
- A lock toggle - locked layers cannot be selected or moved on the canvas.
- A delete button.

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

The properties panel on the right shows the settings for the selected layer. The sections available depend on the layer type.

### Position, size, and layer

- X and Y position.
- Width and height.
- Z-index (stacking order).

### Transform

- **Rotation** - rotates the layer in degrees.
- **Skew X and Skew Y** - shears the layer horizontally or vertically.

### Visibility condition

Set a condition that controls whether this layer is visible during playback. The layer will only show when the condition is met for the incoming event. For example, you can show a crown image only when `tier == 3000`.

### Animations

Each layer can have a show animation (plays when the alert starts) and a hide animation (plays before the alert ends).

For each animation you can set:

- Type (fade, slide, scale, etc.)
- Direction
- Duration in milliseconds
- Delay in milliseconds

### Keyframe animator

Enable the keyframe animator on a layer to animate its position, size, rotation, and opacity along a custom timeline instead of using the entry and exit animations.

When keyframe mode is enabled, the keyframe timeline panel appears at the bottom of the editor. Add keyframes at specific timestamps and set the values for that layer at each point. Beacon interpolates between them during playback.

### Opacity

Controls the overall transparency of the layer (0 to 100).

### Blend mode

Sets how the layer blends with layers behind it (Normal, Multiply, Screen, Overlay, etc.).

### Color adjustments

Fine-tune the visual appearance of the layer:

- Brightness, contrast, saturation, hue rotation.
- Grayscale, sepia, invert effects.
- Blur.

### Tint overlay

Apply a color tint on top of the layer with adjustable opacity.

### Text layers

- **Content** - the text to display. Use `{{fieldName}}` to insert event data, e.g. `{{user}}` for the viewer's name.
- **Variable Style** - apply different styles to specific variables within the text (color, weight, size).
- **Typography** - font family, font size, weight, line height.
- **Alignment** - horizontal and vertical text alignment within the box.
- **Color** - text color.
- **Text Shadow** - shadow offset, blur, and color.
- **Text Animation** - animate text appearance (typewriter, word-by-word, etc.).
- **Box Border** - border width, style, radius, and color.

### Image, GIF, and video layers

- URL or pick from the media library.

### Audio layers

- URL or pick from the media library.
- Volume.

### HTML layers

- Raw HTML content field.

---

## Keyframe timeline

When a layer has keyframe mode enabled, the keyframe timeline panel appears at the bottom of the editor. The timeline shows the duration of the alert and any keyframes set on the selected layer.

- Click the timeline to move the scrubber and preview the animation at that point in time.
- Click **Add Keyframe** to capture the current layer state as a keyframe at the current time.
- Drag keyframes to adjust their timing.
- The canvas updates in real time as you scrub to show the interpolated position.
