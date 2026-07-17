# Visual Editor

The visual editor is the main way to build alerts in a basic overlay (and the canvas for static and widget overlays). It has the layers panel on the left, the canvas in the center, the properties panel on the right, and the Alert Settings panel docked on the left edge.

---

## Top bar

- **Back button** - returns to the overlay page.
- **Alert name** - click to edit inline. An Unsaved indicator appears when there are changes.
- **Canvas size** - presets (1080p, 1440p, 4K, 720p, Vertical) or a custom width and height.
- **Zoom** - minus and plus buttons, click the percentage to type a value, **Fit** to fit the canvas to the window.
- **Show Others / Hide Others** - toggles faint outlines of the other alerts in this overlay, for aligning elements across alerts.
- **Streamer.bot status** - a dot showing the Streamer.bot connection (when configured).
- **Copy URL** and **Preview** - the overlay URL for OBS and a new-tab preview.
- **Variant Setup** - only when editing a variant; opens the condition builder.
- **Simulate** - fires a full simulated event (sub, raid, and so on) through the overlay, exercising event matching and queues.
- **Live checkbox** - when checked, Test also fires on every connected browser source (OBS included), not just the preview.
- **Test** - plays the alert with sample data. The arrow next to it opens Test with custom data, where you can edit the event payload first.
- **Save** - saves all changes. Ctrl+S also works.

Widget overlays replace Test with an **Advanced Widget Setup** button. See [Widgets](widgets.md).

---

## Layers panel

The layers panel lists every box on the canvas. Layers draw in order from bottom to top.

Available layer types:

- **Text** - a text box, with `{{variable}}` placeholders from event data.
- **Image** - a static image from a URL or the media library.
- **Video** - a video file, plays during the alert.
- **GIF** - an animated GIF.
- **Audio** - an audio file, plays during the alert.
- **Progress** - a progress bar bound to a goal or counter (widget overlays).

Each layer row has a visibility toggle, a lock toggle, and a delete button. Double-click to rename. Drag to reorder. Click a layer to select it and edit its settings in the properties panel.

---

## Canvas

- Click a box to select it, drag to move, use the handles to resize.
- Arrow keys nudge 1px; Shift + arrows nudge 10px.
- Ctrl-click to select multiple boxes and move them together.
- Right-click a box for Bring to Front, Send to Back, Duplicate, and Delete.
- Ctrl+Z to undo, Ctrl+Y or Ctrl+Shift+Z to redo. Rapid moves merge into a single undo step.

---

## Properties panel

The properties panel has four tabs: **Content**, **Layout**, **Animation**, and **Effects**. Sections vary by layer type.

### Layout

- Position (X, Y), size, and z-order.
- Transform: rotation.
- **Visibility Condition** - show this layer only when a condition matches the incoming event. For example, a crown image only when `tier == 3000`.

### Animation

- Entrance and exit animation presets with direction, duration, and delay.
- **Enable Keyframe Animator** switches the layer to a custom timeline instead (see below).

### Effects

- Opacity, blend mode, color adjustments (brightness, contrast, saturation, hue, grayscale, sepia, invert, blur), and a tint overlay.

### Text layers (Content tab)

- **Content** - the text, with `{{fieldName}}` placeholders like `{{user}}`. An **Insert a variable** button opens a searchable picker; a common-variables list shows fields for the alert's event type.
- **Variable Style** - different size and weight for the variable portions of the text.
- **Typography** - font family (Google Fonts supported), size, weight, style, letter spacing, line height.
- **Alignment** - horizontal, vertical, padding.
- **Color** - text color, background, opacity.
- **Text Shadow** - offset, blur, and color.
- **Text Outline** - a letter stroke with width and color, for readable text on any background.
- **Box Border** - width, style, radius, and color.
- **Text Animation** - typewriter, marquee, and other text reveals.

### Media layers

Image, GIF, video, and audio layers take a URL or a pick from the [media library](media-library.md). Audio layers also have a volume control.

---

## Keyframe animator

Enable the keyframe animator on a layer to animate position, size, rotation, and opacity along a custom timeline instead of entrance and exit presets.

The timeline panel appears at the bottom of the editor:

- Click the timeline to move the playhead and preview that moment; the canvas updates as you scrub.
- **Add Keyframe** captures the layer's current state at the playhead.
- Drag keyframes to retime them.
- Right-click a keyframe to pick its easing curve from grouped presets with curve previews.
- **Loop** repeats the keyframed animation, with an optional loop count.

A layer is animated by its keyframes once it has at least two.
